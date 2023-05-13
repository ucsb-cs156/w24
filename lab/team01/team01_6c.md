---
layout: default
title: team01-6c
description: "Adding the form"
layout: default
parent: team01
grand_parent: lab
---

# {{ page.title}} - {{page.description}}

In this step, you'll add:
* a file similar to [`RestaurantForm.js`](https://github.com/ucsb-cs156-m23/STARTER-team01/blob/main/frontend/src/main/components/Restaurants/RestaurantForm.js) that provides a form for users to enter data for a restaurant
* a file similar to [`RestaurantForm.stories.js`](https://github.com/ucsb-cs156-m23/STARTER-team01/blob/main/frontend/src/stories/components/Restaurants/RestaurantForm.stories.js) that allows developers to work with the component in isolation through [Storybook](https://storybook.js.org/)
* a file similar to [`RestaurantForm.test.js`](https://github.com/ucsb-cs156-m23/STARTER-team01/blob/main/frontend/src/tests/components/Restaurants/RestaurantForm.test.js) that provides test coverage for the form

#### Understanding [`frontend/src/main/components/Restaurants/RestaurantForm.js`](https://github.com/ucsb-cs156-m23/STARTER-team01/blob/main/frontend/src/main/components/Restaurants/RestaurantForm.js)

The file `RestaurantForm.js` provides a React component that allows the user to enter or edit details for a restaurant.

Here's an overview of the big picture structure of the file (with some details omitted):

```js
import React from 'react'
// more imports omitted

function RestaurantForm({ initialContents, submitAction, buttonLabel = "Create" }) {

    const navigate = useNavigate(); 
    // details of useForm call omitted
    const testIdPrefix = "RestaurantForm";

    return (
        <Form onSubmit={handleSubmit(submitAction)}>

            {initialContents && (
                <Form.Group className="mb-3" >
                    <Form.Label htmlFor="id">Id</Form.Label>
                    <!-- details of Form.Control omitted -->
                </Form.Group>
            )}

            <Form.Group className="mb-3" >
                <Form.Label htmlFor="name">Name</Form.Label>
                <!-- details of Form.Control and Form.Control.Feedback omitted -->
            </Form.Group>

            <Form.Group className="mb-3" >
                <Form.Label htmlFor="description">Description</Form.Label>
                <!-- details of Form.Control and Form.Control.Feedback omitted -->
            </Form.Group>

            <!-- details of two <Button /> elements omitted -->
        </Form>
    )
}

export default RestaurantForm;
```

Let's understand each of these parts a bit at a time.  

First the imports:

| Import | Purpose and Links to Documentation|
|--------|---------|
|`import React from 'react'` | Not strictly necessary anymore but this imports the React framework |
|`import { Button, Form } from 'react-bootstrap';` | This imports the components [`Button`](https://react-bootstrap.github.io/components/buttons/) and [`Form`](https://react-bootstrap.github.io/forms/overview/) from [`react-bootstrap`](https://react-bootstrap.github.io/) |
|`import { useForm } from 'react-hook-form'` | This imports the`useForm` hook from [`react-hook-form`](https://react-hook-form.com/) which is a library that provides validation for data entry form.  We'll explain the `useForm` hook more below. |
|`import { useNavigate } from 'react-router-dom';` | This imports the `useNavigate` hook from [`react-router-dom`](https://reactrouter.com/en/main); this gives us the ability to navigate to other pages (as explained in more detail below)|

Next, the first line of the function:

```
function RestaurantForm({ initialContents, submitAction, buttonLabel = "Create" }) {
```

Notice these things:
* The name of the function `RestaurantForm` is camel-cased, and starts with a capital letter; this is a standard naming convention for React components.
* The parameter to the function is a single object, which by React convention is called `props`, but in this cases we use Javascript argument destructuring to assign the individual components of the parameter to the variables `initialContents`, `submitAction` and `buttonLabel`.  The `buttonLabel` parameter has a default value of `"Create"`.   

Let's preview the purposes of these parameters:
* `initialContents` is passed in only when we are using the form to edit an existing object.  This block of code presents the form element for the `id`
   field only if `initialContents` is *truthy*, which in this context means not null and not undefined.  If initialConents is *falsy* then
   this element simply is not rendered in the output.   The value of `initialContents` is also used in the call to `use
   
   ```js
   {initialContents && (
                <Form.Group className="mb-3" >
                    <Form.Label htmlFor="id">Id</Form.Label>
                    <!-- Form.Control omitted for space -->
                </Form.Group>
           )}
   ``` 
   
   The value of `initialContents` is also used in `useForm` where we use either `initialContents` or an empty object `{}` as the 
   values that are displayed in the form when it is rendered on the page.

   ```js
   useForm(
        { defaultValues: initialContents || {}, }
    );
   ``` 
* `submitAction` is a function (typically in the form of an arrow function, i.e. `()=>{}`, that is invoked when the form is submitted
  (i.e. when the submit button is clicked.)   This action will be different for a `Create` page vs. an `Edit` page, so we pass it in 
  as a parameter.
* `buttonLabel` is the word that appears on the submit button.  The default is `Create`, but we can also pass in `Update` or anything
   else that we want to appear on the label for that button.
   
Let's next look at the lines of code that appear before the return:

```js
 const navigate = useNavigate();
    
    // Stryker disable all
    const {
        register,
        formState: { errors },
        handleSubmit,
    } = useForm(
        { defaultValues: initialContents || {}, }
    );
    // Stryker enable all
   
    const testIdPrefix = "RestaurantForm";
```

* `const navigate = useNavigate();` gives us an object `navigate` that can be used to navigate to another page.  The `Cancel` button
  uses `onClick={() => navigate(-1)}`, where the special value `-1` means "go back to the page you were on before", similar to a kind of
  "Back button".
* The next few lines are a call to the `useForm` hook (documented here: <https://react-hook-form.com/api/useform/>).   The object that follows `const` has three keys for the three values returned
  by `useForm`:
  - `register`: explained here: <https://react-hook-form.com/api/useform/register/>
  - `formState`: explained here: <https://react-hook-form.com/api/useform/formstate/>
  - `handleSubmit`: explained here: <https://react-hook-form.com/api/useform/handlesubmit/>
* Note that the call to `useForm` is surrounded by these comments, which disable mutation testing for the lines in between.  We do this because we do not yet have a good handle on how to properly set up tests to kill the various mutations that Stryker does on these lines of code.  If/when we do, we may remove these comments.
  ```
   // Stryker disable all
    /* call to useForm */
   // Stryker enable all
  ```
* Finally, the value of `const testIdPrefix = "RestaurantForm";` is used throughout the form as a prefix to the `data-testId` attribute of various
  HTML elements; for example: `data-testid={testIdPrefix + "-name"}` This helps ensure that the testId values in the file have a common prefix,
  and makes it easier to reuse this code.
  
Next, let's look at the `return` statement.   At a high level, this statement is simply this:

```js
 return (
        <Form onSubmit={handleSubmit(submitAction)}>
          <!-- stuff omitted --->
        </Form>
    )
}
```

This is typical of a React component in the functional style: the return statement should returns a single JSX expression consisting of a single element, i.e. single pair of open close tags such as `<Form></Form>` or a self-closing tag such as `<Form />`, possibly with some attributes, and some content.

In this case, what we are returning is a `<Form>` element.  

The parts inside the `<Form>` element comes from React Bootstrap (<https://react-bootstrap.github.io/forms/overview/>), which is where we can find the documentation for the parts such as `<Form.Group>`, `<Form.Label>` and `<Form.Control>`.   Rather than explaining each of these in detail, I'll refer you to the documentation.

In addition, we see inside the `<Form.Control>` elements expressions such as these:

For the id:
```js
  {...register("id")}
```

For the name:
```js
      {...register("name", {
          required: "Name is required.",
          maxLength : {
              value: 30,
              message: "Max length 30 characters"
          }
      })}
```

The `register` function comes from `react-hook-form`, and gives us a way to do validation of input.  It's various capabilities are documented here: <https://react-hook-form.com/api/useform/register/>.   If you need to change the validation for a particular field, that's where you can look to see
what is possible.  There are many ways to do validation, including regular expressions.

#### Creating a file similar to `restaurantForm.js`

For your `hotelForm` (for example), your job is to:
* Create a folder/directory `Hotels` with a capital `H` and plural under  `frontend/src/main/components/`, as a sibling of `Restaurants`
* Create a copy of `restaurantForm.js` called `hotelForm.js` inside that `Hotels` folder
* Search/replace (case-sensitive) `restaurant` with `hotel`, and `Restaurant` with `Hotel`
* Leave the parts pertaining to `id`
* Change `name` and `description` to whatever is appropriate for your item (you may keep `name` and `description` if they are appropriate)
* Add at least one more field, along with suitable validation

Now, we need to test whether this works, which we can do two different ways; first with Storybook, and then with jest/coverage/Stryker.

#### Understanding [`frontend/src/stories/components/Restaurants/RestaurantForm.stories.js`](https://github.com/ucsb-cs156-m23/STARTER-team01/blob/main/frontend/src/stories/components/Restaurants/RestaurantForm.stories.js)

To understand the next step, it helps to first review how to fire up the Storybook.

While in the `frontend` directory, type this at a shell prompt:

```
npm run storybook
```

This should launch a browser on port 6006 (i.e. <http://localhost:6006>) where you can see the Storybook.  You should 
see that there is already an entry for the `RestaurantForm` is what is produced by the file `RestaurantForm.stories.js`.  Your job in this step is ensure that a similar entry appears for the new `HotelForm`.

Let's review the contents of `RestaurantForm.stories.js`.  As you read, you may also find it helpful to review the [Storybook documentation on how to write stories](https://storybook.js.org/docs/react/writing-stories/introduction).

The file starts with these imports:
```js
import React from 'react';
import RestaurantForm from "main/components/Restaurants/RestaurantForm"
import { restaurantFixtures } from 'fixtures/restaurantFixtures';
...
```

* The first import simply imports the `React` framework (in more recent version of React, this is optional.)  
* The second import pulls in the form that is the basis of our story
* The third import pulls in the fixtures we defined; we'll use those for our story.

Next, we have an `export default` that exports a Javscript object with two keys, `title` and `component`.  The `title` is used to organize the storybook, while the `component` specifies the component that is the basis of the story.  You can read more about defining the `export default` object of of a story at the [Storybook documentation](https://storybook.js.org/docs/react/writing-stories/introduction).

```js
export default {
    title: 'components/Restaurants/RestaurantForm',
    component: RestaurantForm
};
```

This is followed by defining a value `Template` that renders
the component with the args passed in.  

```js
const Template = (args) => {
    return (
        <RestaurantForm {...args} />
    )
};
```

This is then followed by a sequence of different views
of the component, each with different values passed in for the
components arguments.  

* The first, `Default` shows what happens when the `submitText` is `Create`, and the `submitAction` is an arrow function that prints a message on the console that `Submit was clicked`.  (Note that to see the `console.log` messages, you need to use the `inspect` feature of your browser, and find the tab that shows the Console.)
* The second, `Show`, fills in the restaurant param with a single argument, and also passes nothing for the submitText, and an empty function for the submit actions. This is what the values looked like in the starter code, but this is arguably *incorrect*, or at least not ideal. Instead, 

```
export const Default = Template.bind({});

Default.args = {
    submitText: "Create",
    submitAction: () => { console.log("Submit was clicked"); }
};

export const Show = Template.bind({});

Show.args = {
    Restaurant: restaurantFixtures.oneRestaurant,
    submitText: "",
    submitAction: () => { }
};
```


#### Understanding [`/frontend/src/tests/components/Restaurants/RestaurantForm.test.js`](https://github.com/ucsb-cs156-m23/STARTER-team01/blob/main/frontend/src/tests/components/Restaurants/RestaurantForm.test.js)

Coming soon!

