---
layout: default
title: team01-6b
description: "Adding the CRUD utilities"
layout: default
parent: team01
grand_parent: lab
---

# {{ page.title}} - {{page.description}}

In this step, we are adding a Javascript file that allows us to do CRUD operations (Create/Read/Update/Destroy) on a particular
kind of object (e.g. `hotels`) using the code in 
The model to follow here is [`frontend/src/main/utils/restaurantUtils.js`](https://github.com/ucsb-cs156-s23/STARTER-team01/blob/main/frontend/src/main/utils/restaurantUtils.js) as a model.

The data is stored in something called *Browser Local Storage*.  Each web browser provides the capability for a website to 
maintain a key/value store specific to that site.   Note that this storage is local to not only to your local computer, but
even to different web browsers on the same computer, and different "user profiles" within the same browser.  So this is a very 
limited way of storing data, and is *not* suitable for most applications.  We are using it in this course (temporarily) 
only because it allows us to proceed with testing/learning some frontend development skills, and delay (for the time being)
the complications of communicating with a backend that implements a proper database.

**Testing is crucial**.  Starting with this step, each time we add code, we will add tests for that code.    We didn't do that with the
fixtures file, but that's really a special case; as a general rule, when you add code, you are required to add tests for that code.
The GitHub Actions scripts will actually enforce that rule; you'll get a "red X" (e.g. ❌ ) if you try to add code that doesn't have 
test coverage.

So in addition to looking at [`frontend/src/main/utils/restaurantUtils.js`](https://github.com/ucsb-cs156-s23/STARTER-team01/blob/main/frontend/src/main/utils/restaurantUtils.js), we also need to understand the file [frontend/src/tests/utils/restaurantUtils.test.js](https://github.com/ucsb-cs156-s23/STARTER-team01/blob/main/frontend/src/tests/utils/restaurantUtils.test.js)


#### Understanding [`frontend/src/main/utils/restaurantUtilities.js`](https://github.com/ucsb-cs156-s23/STARTER-team01/blob/main/frontend/src/main/utils/restaurantUtilities.js)

First, let's take a look at the big picture of `restaurantUtilities.js`.  Here's the entire file with the contents
of each arrow function omitted.  

```js
// get restaurants from local storage
const get = () => {
   // details omitted
};

const getById = (id) => {
   // details omitted
}

// set restaurants in local storage
const set = (restaurantCollection) => {
     // details omitted
};

// add a restaurant to local storage
const add = (restaurant) => {
      // details omitted
};

// update a restaurant in local storage
const update = (restaurant) => {
   // details omitted
};

// delete a restaurant from local storage
const del = (id) => {
   // details omitted
};

const restaurantUtils = {
    get,
    getById,
    add,
    update,
    del
};

export { restaurantUtils };
```

In the listing above, the first thing to notice is that the file consists of:
* Six arrow functions (`get`, `getById`, `set`, `add`, `update`, `del`)
* Declaration of an object called `restaurantUtils` which consists of five of these functions
  - Note that `get,` inside a javascript object is a shorthand notation for `get: get,`
  - Accordingly, the keys are `get`, `getById`, `add`, `update`, and `del`, and the values are the function themselves
* The statement `export { restaurantUtils };` which allows us to do this in another file:
  ```js
  import { restaurantUtils } from 'main/utils/restaurantUtils';
  ```

Note also that we don't export the `set` function.  Think of this like a "private method" of the 
restaurantUtils, while the others are similar to "public" methods.


Now let's look at each of the functions individually.

#### Understanding `get` fron [`frontend/src/main/utils/restaurantUtilities.js`](https://github.com/ucsb-cs156-s23/STARTER-team01/blob/main/frontend/src/main/utils/restaurantUtilities.js)

The `get` function looks like this:

```js
const get = () => {
    const restaurantValue = localStorage.getItem("restaurants");
    if (restaurantValue === undefined) {
        const restaurantCollection = { nextId: 1, restaurants: [] }
        return set(restaurantCollection);
    }
    const restaurantCollection = JSON.parse(restaurantValue);
    if (restaurantCollection === null) {
        const restaurantCollection = { nextId: 1, restaurants: [] }
        return set(restaurantCollection);
    }
    return restaurantCollection;
};
```

The line `const restaurantValue = localStorage.getItem("restaurants");` gets the text of the value
associated with the key `restaurants` from the browser local storage.

If this value is `undefined`, we set an intial value of `{ nextId: 1, restaurants: [] }` and pass that to the `set` function
which will convert this to a string representation and put it in local storage under the key `restaurants`.  The
object stores the next id value that will be assigned to a restaurant object, and a list of restaurants, initally empty (`[]`).

The line `const restaurantCollection = JSON.parse(restaurantValue);` converts the 
text representation of an object (as a string) to the actual object representation.

* To convert a string to an object, we use: `object = JSON.parse(string)`
* To convert an object to a strring, we use: `string = JSON.stringify(object)` 

#### Understanding `getById` fron [`frontend/src/main/utils/restaurantUtilities.js`](https://github.com/ucsb-cs156-s23/STARTER-team01/blob/main/frontend/src/main/utils/restaurantUtilities.js)

The `getById` looks for a particular restaurant by it's id and returns that
object.  Here's the code:

```js
const getById = (id) => {
    if (id === undefined) {
        return { "error": "id is a required parameter" };
    }
    const restaurantCollection = get();
    const restaurants = restaurantCollection.restaurants;

    /* eslint-disable-next-line eqeqeq */ // we really do want == here, not ===
    const index = restaurants.findIndex((r) => r.id == id);
    if (index === -1) {
        return { "error": `restaurant with id ${id} not found` };
    }
    return { restaurant: restaurants[index] };
}
```

The code here is mostly straightforward; the part that may need some explanation is this:

```js
    /* eslint-disable-next-line eqeqeq */ // we really do want == here, not ===
    const index = restaurants.findIndex((r) => r.id == id);
```

Note that Javascript has two kinds of test for equality: `==` and `===`.  It is typically the case that we want `===` which is a strict test for equality, however in this case we want `==` which is a looser test for equality. That is likely because this allows the `id` value to be either
an integer or string representation of the `id` while still maintaining the desired behavior.

However, the `eslint` utility will recommend a change from `==` to `===`, which will introduce a bug.  To suppress that warning,
we use the special comment `/* eslint-disable-next-line eqeqeq */`.  This syntax is explained in detail in the [eslint documentation](https://eslint.org/docs/latest/use/configure/rules)

#### Understanding `set` fron [`frontend/src/main/utils/restaurantUtilities.js`](https://github.com/ucsb-cs156-s23/STARTER-team01/blob/main/frontend/src/main/utils/restaurantUtilities.js)

This function is used internally to update the restaurants in local storage.  It is responsible for converting from object representation
to string representation and storing under the key `restaurants`.

This function is straightforward, so we won't explain in detail.  We'll just point out that your version for `hotels` (for example), should
use the key `hotels` rather than `restaurants` as the first parameter to `setItem`.  It's important that this key be consistent throughout the
file.  (In fact, one way to improve on the current code might be to factor this out into its own `const` value, such as `const storageKey = "restaurants";` and then use that in both the `setItem` and `getItem` calls, as an application of the [Don't Repeat Yourself (DRY) principle](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself).

```js
// set restaurants in local storage
const set = (restaurantCollection) => {
    localStorage.setItem("restaurants", JSON.stringify(restaurantCollection));
    return restaurantCollection;
};
```

#### Understanding `add` fron [`frontend/src/main/utils/restaurantUtilities.js`](https://github.com/ucsb-cs156-s23/STARTER-team01/blob/main/frontend/src/main/utils/restaurantUtilities.js)

The `add` routine is used to add a restaurant to the collection.  The restaurant should have all of the fields of
a restaurant object except the `id` field; that value is added by the `add` routine.

```js
// add a restaurant to local storage
const add = (restaurant) => {
    const restaurantCollection = get();
    restaurant = { ...restaurant, id: restaurantCollection.nextId };
    restaurantCollection.nextId++;
    restaurantCollection.restaurants.push(restaurant);
    set(restaurantCollection);
    return restaurant;
};
```

The line `const restaurantCollection = get();` retrieves the entire collection (initializing it to an empty collection if it doesn't already exist).

The next line illustrates an important use of the Javascript spread operator, i.e. `...`.  What this line of code does is to assign a new value to the
variable `restaurant`, consisting of a Javascript object that has:
* all of the fields of the old value of restaurant `...restaurant`
* then, an additional field with the key `id` and the value `restaurantCollection.nextId`

The effect is to add the id to the object.  Note that if the object already had an `id` value, this will
override that older value since `id: restaurantCollection.nextId` comes after `...restaurant`.

```js
    restaurant = { ...restaurant, id: restaurantCollection.nextId };
```

We then increment the `nextId` with `restaurantCollection.nextId++;` and then we add the restaurant to the collection with:
```js
 restaurantCollection.restaurants.push(restaurant);
```

We then use `set(restaurantCollection);` to update the restaurant collection, and we return the updated object (which now has an id number).

#### Understanding `update` fron [`frontend/src/main/utils/restaurantUtilities.js`](https://github.com/ucsb-cs156-s23/STARTER-team01/blob/main/frontend/src/main/utils/restaurantUtilities.js)

The update function is used to support updating the value of an existing restaurant. The parameter is a restaurant object with 
an `id` number.  That `id` should already exist in the restaurant collection; otherwise an error is returned.

Here's the code:

```js
// update a restaurant in local storage
const update = (restaurant) => {
    const restaurantCollection = get();

    const restaurants = restaurantCollection.restaurants;

    /* eslint-disable-next-line eqeqeq */ // we really do want == here, not ===
    const index = restaurants.findIndex((r) => r.id == restaurant.id);
    if (index === -1) {
        return { "error": `restaurant with id ${restaurant.id} not found` };
    }
    restaurants[index] = restaurant;
    set(restaurantCollection);
    return { restaurantCollection: restaurantCollection };
};
```

As you can see the code is similar to code from `getById` and `add`, so we won't explain further.

#### Understanding `del` fron [`frontend/src/main/utils/restaurantUtilities.js`](https://github.com/ucsb-cs156-s23/STARTER-team01/blob/main/frontend/src/main/utils/restaurantUtilities.js)

The `del` function is named `del` to avoid any conflict with the word `delete`.   It is used to delete a restaurant from the collection.
The `id` parameter should be the id of a restaurant already in the collection; otherwise, an error is returned.

Here's the code: 

```js
// delete a restaurant from local storage
const del = (id) => {
    if (id === undefined) {
        return { "error": "id is a required parameter" };
    }
    const restaurantCollection = get();
    const restaurants = restaurantCollection.restaurants;

    /* eslint-disable-next-line eqeqeq */ // we really do want == here, not ===
    const index = restaurants.findIndex((r) => r.id == id);
    if (index === -1) {
        return { "error": `restaurant with id ${id} not found` };
    }
    restaurants.splice(index, 1);
    set(restaurantCollection);
    return { restaurantCollection: restaurantCollection };
};
```

If you've followed the explanations of `getById`, `add`, and `update`, the only new thing here is `restaurants.splice(index, 1);` which
will remove one item at index `index`; for more details, you can read the [documentation of splice at the MDN website](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice).  In general, the [MDN documentation for JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) is a useful resource.

#### Understanding the checks for coverage and mutation testing

When we add a new file to our app, we also need to add tests.  If we were to add, for example, `frontend/src/tests/utils/hotelUtils.js` without adding test coverage, we'd get a result like this when trying to do a pull request:

<img width="929" alt="GitHub Actions Checks" src="https://user-images.githubusercontent.com/1119017/233858463-7f53ab44-ae57-42b5-9696-d7dcf2a2ca8e.png">

We see here that the GitHub Actions script `32-frontend-coverage` has failed, indicating that there is frontend code that is not covered by tests.
In the image above, we also see the yellow circle indicating that the `34-frontend-mutation-testing` is still running; as we've discussed in lecture, coverage generally runs an order of magnitude faster than mutation testing.  Eventually that one will turn to a red X as well:

<img width="692" alt="image" src="https://user-images.githubusercontent.com/1119017/233858582-740068a3-cb7c-4b0a-83a8-15009e3255d4.png">

When we get this result, what do we need to do?  First, let's review how to run coverage locally.

#### Running test coverage locally

To run test coverage locally, you need to be in the `frontend` directory.  

First run `npm test` to make sure that the test suite is all passing; it doesn't make sense to compute test coverage if you have failing tests.

Then run:
```
npm run coverage
```

You'll get a report on the console like this one:

<img width="1056" alt="image" src="https://user-images.githubusercontent.com/1119017/233858700-2b429c0d-d651-40f1-acc2-6b51f5a41d37.png">

Note that files with uncovered lines are shown in red, and also are flagged in the column for `Uncovered Line #s` (for users that may have color perception issues.)  This is helpful, but we can get much more detail by opening the detailed report in a web browser.  The filename for that report is `coverage/lcov-report/index.html`; on MacOS, you can open the file with this command:

```
open coverage/lcov-report/index.html 
```

On other platforms, use the "open file" feature of your web browser, and navigate to and open the file.

When we do that, we see this:

<img width="940" alt="image" src="https://user-images.githubusercontent.com/1119017/233862804-d345152a-77b9-4b14-8bdd-d56d866430e0.png">

The yellow color, and the number less than 100% in all four columns (statements, branches, functions, lines) shows us that the utils directory is where the problem lies.  We can click on the utils directory in this report, and see more detail:

<img width="934" alt="image" src="https://user-images.githubusercontent.com/1119017/233862904-54544cdd-4ea1-41bd-8691-4502ad2c026c.png">

The red color, and the zeros for `hotelUtils.js` show that we need test coverage for that file.  To get this test coverage,
we can add a file `frontend/src/tests/utils/hotelsUtils.test.js` using [`frontend/src/tests/utils/restaurantUtils.test.js`](https://github.com/ucsb-cs156-s23/STARTER-team01/blob/main/frontend/src/main/utils/restaurantUtils.test.js) as a model.  So we'll look at that in a moment.  But first, let's also 
look at how to run mutation testing locally.

Later, as we have partial coverage for a file, you can click on the file and see which lines are, and are not covered by tests.  For example, here is what that report looks like with just a few of the tests included, but not all of them:

<img width="697" alt="image" src="https://user-images.githubusercontent.com/1119017/233866365-9942b1ff-cb16-4c3a-8229-35b16e10480d.png">

As you can see, we have full coverage of the `get` function (as shown by the green color, and the numbers such as `1x`, `2x`, etc. showing how many times a line has been exercised by tests. But other parts of the file do not have coverage, as shown by the red color, and the absence of anything next to those lines.

#### Running mutation coverage locally

To run mutation test coverage locally, you need to be in the `frontend` directory.  

First run `npm test` to make sure that the test suite is all passing; it doesn't make sense to compute mutation coverage if you have failing tests.

Then, run:

```
npx stryker run
```

It may take a while to run.  When I ran `npm run coverage`, it took only 5 seconds, but `npx stryker run` took 53 seconds.  As the projects get larger, this number will get larger too.

Eventualy, you'll see a report on your console like this one:

<img width="1176" alt="image" src="https://user-images.githubusercontent.com/1119017/233865677-90895eff-15ca-4d6a-bcde-dc3567c1f389.png">

The red and the number less than 100% in the score column shows us where we need to focus, in this case `hotelUtils.js`.  As with `npm run coverage`, there is also a detailed HTML report, which we can find in the file `reports/mutation/html/index.html` (this file name is echoed on the console):

```
13:51:33 (81953) INFO HtmlReporter Your report can be found at: file:///Users/pconrad/github/ucsb-cs156-s23/team01-s23-4pm-1/frontend/reports/mutation/html/index.html
13:51:33 (81953) INFO MutationTestExecutor Done in 53 seconds.
```

We can open this in a web browser, and we see something like this:

<img width="915" alt="strykerjs example output" src="https://user-images.githubusercontent.com/1119017/233865763-ebae4a88-a0f9-4e72-b70d-5f96a1ed28c9.png">

As with `npm run coverage`, we can click on a directory to see more detail; clicking on `utils` takes us here, where we see that the issue is in `hotelUtils.js`:

<img width="917" alt="strykerjs example output" src="https://user-images.githubusercontent.com/1119017/233865821-61f69df7-e60a-4858-9968-7201f680f9c2.png">

Clicking on that takes us to the source code for `hotelUtils.js` where we can see which lines are covered, and which are not.  Here's what that looks like when there is no coverage at all. 

<img width="650" alt="image" src="https://user-images.githubusercontent.com/1119017/233865867-f37a0e41-e945-4200-8ab6-19b9adbd0938.png">

Note that you can explore the report and find out exactly what mutations were done that survived by clicking on the red circles.  Each time, this shows the "before/after" comparison of the original code and the mutated code.  You can use that information to come up with a strategy to write a test that will fail on that specific mutation:

![stryker-mutations](https://user-images.githubusercontent.com/1119017/233865937-70c70745-f35f-44df-9107-5ce414781de9.gif)


#### Understanding the big picture of [`frontend/src/tests/utils/restaurantUtils.test.js`](https://github.com/ucsb-cs156-s23/STARTER-team01/blob/main/frontend/src/main/utils/restaurantUtils.test.js)

Let's start by looking at the big picture of this file.  Here's the entire file with some details omitted:

```js
import { restaurantFixtures } from "fixtures/restaurantFixtures";
import { restaurantUtils } from "main/utils/restaurantUtils";

describe("restaurantUtils tests", () => {
    // return a function that can be used as a mock implementation of getItem
    // the value passed in will be convertd to JSON and returned as the value
    // for the key "restaurants".  Any other key results in an error
    const createGetItemMock = (returnValue) => (key) => {
       // details omitted
    };

    describe("get", () => {
       // details omitted
    });

    describe("getById", () => {
      // details omitted
    });
    
    describe("add", () => {
      // details omitted
    });

    describe("update", () => {
      // details omitted
    });
});
```

Looking at this, we see that the file starts, as most of our Javascript source files do, with some imports.  In this case, we are importing the functions
that we want to test, and the `restaurantFixtures` that can serve as example objects to test with.

We then have a block with this structure:

```
describe("restaurantUtils tests", () => {
   // details omitted.
});
```

This is a single call to the `describe` function which takes two parameters:
* a string describing a group of tests (in this case, "restaurantUtils tests")
* a Javascript arrow function `()=>{}` that contains all of the tests.

The `describe` function is a feature of [`jest`](https://jestjs.io/) which is the Javascript testing framework we are using.  There is [documentation for the `describe` function](https://jestjs.io/docs/api#describename-fn) if you want to learn more, but the basic idea is that we can group tests within calls to `describe`.  

As this example shows, `describe` function calls can be nested; indeed the entire outer describe contains five inner `describe` blocks:

```
describe("restaurantUtils tests", () => {
  
  // function definition of createItemGetMock omitted for now
  
  describe("get", () => {
      // details omitted
  });
  
  describe("getById", () => {
      // details omitted
  });
  
  // etc...
  
});
```

Each of the inner `describe` blocks corresponds to one of the five functions that the `restaurantUtils` module makes available.


Next, we'll look at a few of the tests.  

#### Understanding the tests in [`frontend/src/tests/utils/restaurantUtils.test.js`](https://github.com/ucsb-cs156-s23/STARTER-team01/blob/main/frontend/src/main/utils/restaurantUtils.test.js)

Since there are thirteen tests in `restaurantUtils.test.js` we won't go over all of them in detail; we'll review just a few so that you get the basic idea, and leave it to you to discover how the others work.

Let's start with the first test for the `get` function.  This test follows a general pattern for tests which is **arrange, act, assert**.

```js
        test("When restaurants is undefined in local storage, should set to empty list", () => {

            // arrange
            ...
            
            // act
            ...
            
            // assert
            ...
        });
```

The **arrange** section sets up the conditions for the tests. One of the important ideas here is the idea of a **mock**.  When we are doing unit
testing, we are trying to test one unit of code at a time, and not test other units that we may be depending on.   

We also don't want our tests
to have any side-effects that could change the outcome of other tests, which means we want to avoid writing to the file system, sending
real messages over the network, or storing things in a database.

In this case, the correctness of our code depends 
on the `localStorage.getItem()` and `localStorage.setItem()` functions working properly.  And we want to avoid actually writing things into `localStorage`,
or depending on `localStorage` being in a certain state.

So we set up a **mock implementation** of `localStorage`.  That is done with this code.  Here `Storage.prototype` is the built in Javascript object
that implements the `localStoarage` function.  The function [jest.spyOn](https://jestjs.io/docs/jest-object#jestspyonobject-methodname) is used to
create a mock function that is called instead of the real `localStorage.getItem`.  We do the same for `localStorage.setItem`.

```js
        test("When restaurants is undefined in local storage, should set to empty list", () => {

            // arrange
            const getItemSpy = jest.spyOn(Storage.prototype, 'getItem');
            getItemSpy.mockImplementation(createGetItemMock(undefined));

            const setItemSpy = jest.spyOn(Storage.prototype, 'setItem');
            setItemSpy.mockImplementation((_key, _value) => null);
            ...
        });
```

We also supply a mock implementation for both functions. The Jest [`mockImplementation`](https://jestjs.io/docs/mock-function-api/#mockfnmockimplementationfn) function takes a Javascript function as its argument.  In the case of `getItem`, we use the function
defined at the top of the outer `describe` block to create that function.  Since this function is documented with comments, we won't
explain further, except to point out that this is a *function that returns a function*, which may be a new idea; you don't see this
much in C++ and Java programming, but it is a key feature of functional programming languages such as LISP, Scheme, Scala, and others.
Over time, Javascript has evolved to incorporate many of the ideas of functional programming. We'll see it often in React code.

```js
    // return a function that can be used as a mock implementation of getItem
    // the value passed in will be convertd to JSON and returned as the value
    // for the key "restaurants".  Any other key results in an error
    const createGetItemMock = (returnValue) => (key) => {
        if (key === "restaurants") {
            return JSON.stringify(returnValue);
        } else {
            throw new Error("Unexpected key: " + key);
        }
    };
```

The `// Act ` section of a test involves actually invoking the unit under test, which in this case is the `add` function of `restaurantUtils.js`:

```
            // act
            const result = restaurantUtils.get();
```

This is followed by the `// Assert` section of the test, in which we call assertions about what should be true if the code is correct.
* Here we first check that we expect the `result` variable returned by `restaurantUtils.get();` to equal a certain value.  
* We can also check that our `setItem` function was called with the expected parameter value

```js
            // assert
            const expected = { nextId: 1, restaurants: [] } ;
            expect(result).toEqual(expected);

            const expectedJSON = JSON.stringify(expected);
            expect(setItemSpy).toHaveBeenCalledWith("restaurants", expectedJSON);
```

The remaining twelve tests follow a similar pattern, so we won't describe them in detail. We'll just point one thing that's slightly different, namely that in addition to asserting whether a mock function has been called, we can also assert that it was *not* called:

```
            expect(setItemSpy).not.toHaveBeenCalled();
```

This is occasionally useful for making sure we cover both branches of an if/else, for example, or that a mutation to an if test is killed.

#### Writing your own version of [`frontend/src/tests/utils/restaurantUtils.test.js`](https://github.com/ucsb-cs156-s23/STARTER-team01/blob/main/frontend/src/main/utils/restaurantUtils.test.js)

It may be possible to get full test and mutation coverage by just copying this file over, doing a search and replace (e.g. changing all instances of `restaurant` to `hotel`).

However, I suggest that once you do this, you comment out all of the describe blocks except for the one for `describe("get", () => {`, and then uncomment the tests one at a time so that you can see the effect on test coverage and mutation coverage.

The process looks like this:

1. Put yourself at command line in the `frontend` directory.
1. Copy `src/tests/utils/restaurantUtils.test.js` to, for example `src/tests/utils/hotelUtils.test.js`
2. Do a global search replace `restaurant` to hotel`
3. Comment out all of the inner `describe blocks` except the one for `get`, and comment out all but the first test inside the `get` block.
4. Run the tests with `npm test`.  They should pass; if they don't, fix that first.
5. Run test coverage with `npm run coverage`. You should see coverage gaps; look at this both in the console window and in the html report.
6. Also run `npx stryker run`.  You should see coverage gaps; look at this both in the console window and in the html report.
7. Now uncomment the tests a bit at a time, and see the effect on the coverage gaps.  This will help you understand what each test is doing.
8. When you get to 100% test coverage with both `npm run coverage` and `npx stryker run` you'll be almost ready for a pull request.
9. Make sure you also run `npx eslint --fix .` and address any issues it flags before making your PR.

