
## Vue.JS Tutorial

## Contents
[Getting Started with your code - template file](#Getting Started with your code - template file)
[Vue.js Project Setup](#Vue.js Project Setup)
[Create Quiz App with us](#Create Quiz App with us)

### Getting Started with your code - template file

**Step 1: Include the Vue.js Library**

To create a Vue.js instance in an HTML file, you first need to include the Vue.js library in your HTML document. You can do this by adding the following code within the `<head>` section of your HTML file:

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Vue App</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2.6.14/dist/vue.js"></script>
</head>
<body>
    <!-- Your Vue app content goes here -->
</body>
</html>

```

**Step 2: Create Your Vue Instance**

Now, you can define your Vue instance within a `<script>` tag at the end of your HTML file, just before the closing `</body>` tag. Here's an example of creating a simple Vue instance!

```
<body>
    <div id="app">
        {{ message }}
    </div>

    <script>
        // Create a new Vue instance
        var app = new Vue({
            el: '#app', // Mount the instance to the element with the id "app"
            data: {
                message: 'Hello, Vue!'
            }
        });
    </script>
</body>
```

![step6](https://github.com/jgongala/InternetTechnologies/assets/65823190/9cf92618-474a-4695-880c-e2d0e5fc3ba1)


In this example, we create a Vue instance with the `new Vue()` constructor. We specify the `el` property to define the HTML element with the id "app" as the mounting point for our Vue instance. The `data` property contains the data that Vue.js will manage, in this case, a `message` property with the value "Hello, Vue!"

**Step 3: Interact with Vue Data**

You can now access the data defined in your Vue instance within your HTML by using double curly braces `{{ }}`. In this example, we're displaying the value of the `message` property within the `#app` element.

When you open your HTML file in a browser, you'll see "Hello, Vue!" displayed on the webpage. Vue.js is now managing the data binding for this element.

That's it! You've created a basic Vue instance in an HTML file. You can build upon this foundation to create more complex and interactive Vue.js applications.

## Basics Vue.js Components

**Directives**: 

*Interpolation*

![ezgif com-video-to-gif](https://github.com/jgongala/InternetTechnologies/assets/65823190/5c830cb5-c159-472e-a5e1-299b01025242)

Vue.js allows you to interpolate data into your template using double curly braces `{{ }}`. This is one of the most common ways to display dynamic data in your HTML.

```
<div id="app">
    {{ message }}
</div>
```

In this example,  `message` will be replaced with the value of the `message` property from your Vue instance. If `message` is "Hello, Vue!", the rendered HTML will be "Hello, Vue!".

Interpolation is a simple and effective way to display dynamic data in your Vue.js application.

*v-bind Directive*

To bind HTML attributes to data, you can use the `v-bind` directive. For example:

```
    <div id="app">
        <a v-bind:href="dynamicUrl">Visit Google</a>
    </div>
```

In this example, we have an HTML structure within a Vue.js application. Let's break it down:

- We define a container `<div>` with the `id` of "app." This `id` is important as it serves as the mounting point for our Vue.js instance.
- Inside the container, we have an anchor (`<a>`) element with the `v-bind:href` directive. This directive is used to bind the `href` attribute of the anchor element to a dynamic data property, `dynamicUrl`.

In the `<script>` section:

- We create a new Vue instance using `new Vue()`.
- We specify that this Vue instance should be mounted on the element with the `id` "app" using `el: '#app'`.

Inside the `data` section of the Vue instance:

- We define a property called `dynamicUrl` with the initial value of 'https://www.google.co.uk/'.
- This property will be used to control the URL in the link.

This setup allows the Vue instance to manage the `dynamicUrl` property, and any changes to it will automatically update the URL in the link.

```
    <script>
        new Vue({
            el: '#app',
            data: {
                dynamicUrl: 'https://www.google.co.uk/'
            }
        });
    </script>
```


As a result, when this HTML file is loaded in a browser:

- The link "Visit Google" will have the URL "https://www.google.co.uk/" by default. This is because the `dynamicUrl` property in the Vue instance is initially set to this URL.
- You can easily update the `dynamicUrl` property within your Vue instance to change the URL dynamically. Vue.js will ensure that the link's `href` attribute reflects the current value of `dynamicUrl`.

This example demonstrates the power of data binding in Vue.js for creating dynamic web applications. It allows you to effortlessly manage and update content on your webpage based on changes in your data properties, providing a foundation for building interactive and responsive web applications.

*v-on Directive*

![ezgif com-video-to-gif (1)](https://github.com/jgongala/InternetTechnologies/assets/65823190/32aeca0d-cc74-44ab-8f3b-9ba3efa8d78d)

The `v-on` directive in Vue.js is used to listen to events and execute methods when those events occur. It allows you to create interactive and responsive user interfaces by defining event listeners and specifying what should happen when those events are triggered. For example

```
<div id="app">
    <button v-on:click="doSomething">Click me</button>    
</div>
```

In this code snippet, we have a Vue.js application. Let's break it down:

- We start with a `<div>` element with the `id` of "app." This `id` serves as the mounting point for our Vue.js instance.
- Inside the container, there is a `<button>` element. This button is enhanced with the `v-on:click` directive. This directive is used to set up an event listener for a click event on the button.

```
<script>
    new Vue({
        el: '#app', 
        methods: {
            doSomething: function() {
                alert('Button clicked!'); 
            }
        }
    });
</script>
```

![step11](https://github.com/jgongala/InternetTechnologies/assets/65823190/be16af78-8718-4973-b444-e5ee3a815518)

In the script section, we are creating a Vue instance and defining its behavior. Let's break down the script:

- We create a new Vue instance using `new Vue()`.
- We specify the `el` property to define the HTML element with the `id` of "app" as the mounting point for our Vue instance. This means that the Vue instance will be associated with the element having the ID "app."
- Inside the Vue instance, we define a `methods` section. This section is where we specify the behavior of the application, particularly what should happen in response to user interactions.
- Within the `methods` section, we define a method named `doSomething`. This method is called when a certain event occurs. In this case, it's triggered by a click event on the button element within the "app" element.
- In the `doSomething` method, we define what should happen when the button is clicked. In this example, we use the `alert` function to show a pop-up alert with the message "Button clicked!".

**Methods and Event Handling**

```
<div id="app">
    <button v-on:click="doSomething">Click me</button>    
</div>

<script>
    var app = new Vue({
        el: '#app',
        data: {
            message: 'Hello, Vue!'
        },
        methods: {
            doSomething: function () {
                this.message = 'Button was clicked!';
            }
        }
    });
</script>
```

In the provided code example, we are working with Vue.js to demonstrate how to use methods and event handling. Let's break down the key components:

**HTML Structure:**

- We have an HTML structure enclosed in a div with the ID "app." This serves as the root element for our Vue instance.

**Button Element:**

- Inside the "app" div, there's a button element with the `v-on:click` directive. This directive is used to listen for a click event on the button element. When the button is clicked, it will trigger the specified method.

**Vue Instance:**

- We create a Vue instance called `app` and specify that it should be mounted on the element with the ID "app" using the `el` property.

**Data Property:**

- In the data section of the Vue instance, we define a property called `message` and initialize it with the value 'Hello, Vue!'. This property will be displayed in the HTML.

**Methods:**

- Inside the Vue instance, there's a methods section where we define a method called `doSomething`. This method will be called when the button is clicked.

**Event Handling:**

- The `doSomething` method is responsible for changing the `message` property. When the button is clicked, it updates the `message` property to 'Button was clicked!' using `this.message = 'Button was clicked!'`.

**v-on Directive:**

- The `v-on` directive is used for event handling. In this case, it's combined with `click`, so the `v-on:click` directive listens for a click event on the button.

When you click the button in the rendered Vue application, the `doSomething` method is executed, changing the `message` property's value. This change in data is automatically reflected in the HTML because Vue.js uses data binding to keep the view in sync with the data.

This is a fundamental example of how Vue.js allows you to define methods and handle events within your application, making it easy to create dynamic and interactive web applications.

**Directives and Conditionals**

*v-if, v-else-if, v-else*: You can use these directives for conditional rendering

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Vue App</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2.6.14/dist/vue.js"></script>
</head>
<body>
    <div id="app">
        <p v-if="isUserLoggedIn">Welcome, user!</p>
        <p v-if="isUserAdmin">You are an admin.</p>
        <p v-else-if="isUserModerator">You are a moderator.</p>
        <p v-else>Please log in.</p>
    </div>
    <script>
        var app = new Vue({
            el: '#app',
            data: {
                isUserLoggedIn: true,       // Example condition: user is logged in
                isUserAdmin: false,         // Example condition: user is not an admin
                isUserModerator: true,      // Example condition: user is a moderator
            }
        });
    </script>
</body>
</html>
```
![step13](https://github.com/jgongala/InternetTechnologies/assets/65823190/3f0cd938-329c-426e-bd19-ae8af65d1a36)

In this code example, we demonstrate how to implement conditional rendering in Vue.js using the `v-if`, `v-else-if`, and `v-else` directives. These directives allow you to display or hide content based on specific conditions.

HTML Structure:

- The HTML structure includes a div with the ID "app," which serves as the root element for our Vue instance.

Conditional Rendering Directives:

- We use Vue.js directives to conditionally render content based on the values of data properties.
- The first `<p>` element is enhanced with the `v-if` directive and checks the condition `isUserLoggedIn`. If `isUserLoggedIn` is `true`, it displays the "Welcome, user!" message.
- The second `<p>` element uses the `v-if` directive with the condition `isUserAdmin`. It checks if the user is an admin. If `isUserAdmin` is `true`, it displays the "You are an admin" message.
- The third `<p>` element employs the `v-else-if` directive with the condition `isUserModerator`. It checks if the user is a moderator. If `isUserModerator` is `true`, it displays the "You are a moderator" message.
- The final `<p>` element is associated with the `v-else` directive. It is displayed when none of the preceding conditions are met and shows the message "Please log in."
*Vue Instance:

- We create a Vue instance named `app` and specify that it should be mounted on the element with the ID "app."

Data Properties:

- In the data section of the Vue instance, we define three boolean properties: `isUserLoggedIn`, `isUserAdmin`, and `isUserModerator`. These properties represent example conditions. In a real application, these conditions could be dynamically set based on user roles or authentication status.

This example serves as a practical demonstration of Vue.js's capabilities in handling conditional rendering. By using `v-if`, `v-else-if`, and `v-else`, you can dynamically adjust the content displayed to users based on different conditions. This is a powerful feature for building interactive and personalized user interfaces.

*v-for*: Use this directive for rendering lists of data.

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Vue App</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2.6.14/dist/vue.js"></script>
</head>
<body>
    <div id="app">
        <ul>
            <li v-for="item in items">{{ item }}</li>
        </ul>

        <ul>
            <li v-for="(item, index) in items">{{ index + 1 }}. {{ item }}</li>
        </ul>

        <ul>
            <li v-for="(value, key) in user">{{ key }}: {{ value }}</li>
        </ul>

        <ul>
            <li v-for="n in 5">Item {{ n }}</li>
        </ul>
    </div>

    <script>
        var app = new Vue({
            el: '#app',
            data: {
                items: ['Item 1', 'Item 2', 'Item 3'],
                user: {
                    name: 'John Doe',
                    age: 30,
                    occupation: 'Developer'
                }
            }
        });
    </script>
</body>
</html>
```

![step15](https://github.com/jgongala/InternetTechnologies/assets/65823190/ceb26da0-fbc1-4ae6-9be8-6b04b34b41c9)

Rendering Lists in Vue.js:

In this code example, we showcase how to render lists and iterate over data structures using Vue.js directives. This is a fundamental concept for displaying dynamic content in Vue.js.

HTML Structure:

- The HTML structure consists of a div with the ID "app," serving as the root element for our Vue instance.

Rendering Lists:

We use various Vue.js directives to render lists in different ways.

1. *Rendering a Simple List:*

   - The first `<ul>` element contains a list of items rendered using the `v-for` directive. It iterates over the `items` array and displays each item as an `<li>` element.

2. *Rendering a List with Index:*

   - The second `<ul>` element uses the `v-for` directive to iterate over the `items` array, but it also provides an index using `(item, index)`. This allows us to display both the item and its index in the list.

3. *Rendering an Object:*

   - The third `<ul>` element utilizes `v-for` to iterate over the `user` object. It displays each key-value pair as an `<li>` element, showing the key and its associated value.

4. *Rendering a Fixed Number of Items:*

   - The fourth `<ul>` element demonstrates using `v-for` to loop through a range of numbers, in this case, from 1 to 5, and displays each item as "Item {{ n }}."

Vue Instance:

- We create a Vue instance named `app` and specify that it should be mounted on the element with the ID "app."

Data Properties:

- In the data section of the Vue instance, we define two data properties: `items` and `user`.
   - `items` is an array containing a list of items.
   - `user` is an object with key-value pairs representing user information.

This example serves as a practical guide to using Vue.js for rendering lists in different ways. It covers iterating over arrays, displaying indices, rendering objects, and generating a fixed number of items. Understanding these techniques is essential for building dynamic and data-driven user interfaces in Vue.js.

**Vue.js Components:**

Vue.js offers a powerful feature called components, which allow you to create reusable and modular building blocks for your application's user interface. Components can be thought of as self-contained units of functionality and appearance, making your code more organized and maintainable.

*Creating a Vue.js Component:*
Vue.js allows you to create reusable components. Here's a basic example of creating a component:

![step16](https://github.com/jgongala/InternetTechnologies/assets/65823190/5341ca96-af1b-4143-adf0-25ee9304957f)

![step17](https://github.com/jgongala/InternetTechnologies/assets/65823190/46164e47-8629-4f9c-8424-1901239dc891)

HTML Structure
Within the `<body>`, you'll find a `<div>` element with the id of "app." This element serves as the mounting point for our Vue instance, where we'll render our Vue component.

In this structure, the `<div>` with the id "app" is where our Vue.js application will be anchored. It's the designated location where the Vue component will be displayed and rendered on the web page. Any content or output generated by the Vue component will be inserted into this `<div>` element when the Vue application is in action.

Vue Instance
We create a new Vue instance using `new Vue({})`. This instance will control our application and is mounted on the element with the id "app" using el: '#app'.

Define a Vue Component

Within the Vue instance, we define a custom Vue component named "my-component" using the `components` option. The component definition includes:

- The `template` property, which contains the HTML structure of the component. It uses Vue.js's template syntax to display the `title` and `content` data properties.
- The `data` method, which returns an object containing data properties. In this case, we have `title` and `content` properties with initial values. 

Using the Vue Component

To use the "my-component" within your application, you can simply include `<my-component></my-component>` in your HTML. This is how you render and use the component.

Data Binding

The component's template section utilizes data binding to display the values of the title and content properties defined in the data section of the component. This enables dynamic content updates based on the component's data.

This example demonstrates a basic setup for creating and using a Vue.js component directly within an HTML file. You can expand on this foundation to build more complex Vue.js applications with reusable components.

### Vue.js Project Setup

Before you begin, make sure you have the following prerequisites installed on your computer:

- [Node.js](https://nodejs.org/) and [npm](https://www.npmjs.com/) (Node Package Manager).

**Step 1: Install Vue CLI (Command Line Interface)**

Vue CLI is a tool for scaffolding Vue.js projects. Install it globally on your system using npm:

![step1](https://github.com/jgongala/InternetTechnologies/assets/65823190/b0f7ff4d-c1ad-4866-90e6-fec97d8df58a)

**Step 2: Create a New Vue Project**

Once Vue CLI is installed, open your Visual Studio Code and open the directory directory where you want to create your project and run the following command:

![app1](https://github.com/jgongala/InternetTechnologies/assets/65823190/20dd59e3-9b36-49e6-8a57-3946f61bd987)

You're probably thinking what *vite* is? *Vite* is really powerful engine which will run our app.

Once installed and our project is created we will choose our framework which is vue.js

![app2](https://github.com/jgongala/InternetTechnologies/assets/65823190/71d32998-0049-4e7d-bfec-7529643a47db)

We will also select JavaScrip.

![app3](https://github.com/jgongala/InternetTechnologies/assets/65823190/3d19adfc-e1ee-45cf-afc6-377e5ce5bf04)

Now we will have to run npm install to install node packages.

![app4](https://github.com/jgongala/InternetTechnologies/assets/65823190/c119b19a-1bd4-416d-adfe-8ccc9d8a3515)
![app5](https://github.com/jgongala/InternetTechnologies/assets/65823190/8d268090-ec8f-4b91-9b52-fa3e97302ca7)

Now everything is successfully installed and we can go to our local host:

![app6](https://github.com/jgongala/InternetTechnologies/assets/65823190/de265434-6b0a-46cf-9b1e-a89b8bd79102)

And you should see below page:

![app7](https://github.com/jgongala/InternetTechnologies/assets/65823190/7ab8aed7-036b-45cc-9487-aee1ecc82549)

*Cool tip*

We recommend to install extension Vue Language Features (Volar)
![app8](https://github.com/jgongala/InternetTechnologies/assets/65823190/55dbe6d2-2511-4f72-aad5-2df5797fd3be)

**Step 3: Project Structure**

After creating the project, you'll see the following project structure:

- **node_modules:** This directory contains project dependencies. You don't need to modify anything in here; it's managed by npm.
- **public:** This directory is for static assets, and it typically contains the `index.html` file, which is the main HTML page for your Vue.js app.
- **src:** This directory is where your Vue.js application's source code is located. You'll be spending most of your time here, creating Vue components and writing application logic.
- **package.json:** This file contains project configuration, including the list of dependencies and various scripts for development, building, and testing.
- **README.md:** This is the project's documentation file, where you can provide information about your project, how to set it up, and how to use it.
- **.gitignore:** This file specifies which files and directories should be ignored by Git. It's used for version control and helps exclude files like build artifacts and dependencies.

This project structure provides a solid foundation for organizing your Vue.js application and its related files.

![app9](https://github.com/jgongala/InternetTechnologies/assets/65823190/db073a4b-541a-4bee-9884-8625b9a0cb37)

### Create Quiz App with us

**Remove not needed components**

![app10](https://github.com/jgongala/InternetTechnologies/assets/65823190/b625a3f0-6d29-44d5-9823-93eebb47a4ee)

If you are confused, and thinking why we are deleting this folder, it is a simple answer, we won't need it for this tutorial.

**App.vue file**

Make sure that your App.vue file looks like this:

![app11](https://github.com/jgongala/InternetTechnologies/assets/65823190/ededa4a6-3c85-4f18-aec6-5be998d2b189)

As we will start our project from scratch.

**Does it work?**

To check if our project is communicating with our local host, we will edit some styling and add temporary h1.
```
<template>
    <h1>Hello students! Hope you will enjoy our tutorial!</h1>
</template>
<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Montserrata', sans-serif;
  }

  body {
    background-color: #EDC7B7;
    color: #123c69;
  }
```

Once that done, go to your browser and refresh local host. Congrats if you see page below:

![app12](https://github.com/jgongala/InternetTechnologies/assets/65823190/ee0ba42a-9d25-4785-98c4-a02cf20965c1)

**Coding Questions for our Quiz** 

We will start our coding from creating question library. First thing that we are going to do is to import some packages.

```
import { ref, computed } from 'vue'
```

We're importing the ref and computed functions from the Vue.js library. These functions are used to create and manage reactive data in a Vue.js application.

Next we will have to define a questions variable as a *ref*. This means questions is a reactive reference to an array of objects.

```
const questions = ref([
    {
      question: 'What is Vue.js?',
      answer: 0,
      options: [
        'A front-end framework',
        'A library',
        'A back-end framework'
      ],
      selected: null
    },
    {
      question: 'How to use for loop in Vue.js?',
      answer: 2,
      options: [
        'vFor',
        '*v-for',
        'v-for'
      ],
      selected: null
    },
    {
      question: 'What keyword is used for generating a constant in Vue.js?',
      answer: 1,
      options: [
        'Define',
        'Const',
        'None of the above.'
      ],
      selected: null
    }
  ])
```

Next, let's break down the structure of the questions array of objects:
- Each object in the array represents a single question.
- Each question object has the following properties:
  
*question*: A string that represents the question itself.

*answer*: An index that specifies the correct answer in the options array.

*options*: An array of strings representing multiple choice options.

*selected*: Initially set to null, this property can be used to store the user's selected answer.

The code we've provided sets up the initial data structure for our quiz application. We can use Vue.js to create components and templates that interact with this data to build a complete interactive quiz.

**Variable**

As in every program we will have to define some variables: 

```
const quizCompleted = ref(false)
```

*quizCompleted* is a reactive reference created with ref. It is used to track whether the quiz has been completed or not. When quizCompleted is *false*, it means the quiz is not yet completed. This variable can be updated throughout our application to reflect the current state of the quiz. For example, when all questions have been answered, we will set quizCompleted to true to indicate that the quiz has been successfully completed.

```
const currentQuestion = ref(0)
```

*currentQuestion* is another reactive reference created with ref. It is used to keep track of the index of the current question that the user is working on. The 0 as its initial value indicates that the user is starting with the first question.
As the user progresses through the quiz by answering questions, we will increment the currentQuestion variable to move to the next question. For example, after the user answers the current question, we will update currentQuestion to move to the next question (e.g., increment it by 1).

These variables are essential for managing the state of a quiz application. We can use them to determine whether the quiz is ongoing or completed and to control the display of questions to the user by tracking the current question's index. They enable you to create a user-friendly and interactive quiz experience in your Vue.js application.

**Score**

```
  const score = computed(() => {
    let value = 0
    questions.value.map(q => {
      if (q.selected != null && q.answer == q.selected) {
        console.log('correct');
        value++
      }
    })
    return value
  })
```

*score* is a computed property created using Vue's computed function. Computed properties are used to derive a value based on other reactive properties. In this case, it calculates the user's score. Inside the computed function, a *value* variable is initialized to 0. This variable will be used to keep track of the user's score.

*questions.value.map(q => { ... })* is used to iterate through each *question* in the questions array that we created at the begining. It uses the *map* function to go through each question object.

Inside the loop, it checks if *q.selected* is not null (i.e., the user has made a selection) and if q.answer (the correct answer) matches q.selected (the user's selection). If both conditions are met, it means the user's selection is correct.

When a correct answer is found, the code increments the *value* variable by 1. This effectively counts the number of correct answers the user has given.

The code also logs 'correct' to the console when a correct answer is found. This can be useful for debugging or providing feedback.

After all questions have been checked, the computed property returns the final value of value, which represents the user's score in the quiz.

This computed property is a useful tool for calculating and displaying the user's score in your Vue.js quiz application. It checks the user's answers against the correct answers and keeps a running tally of correct responses, providing a score at the end of the quiz.

**Get/Next Question**

```
const getCurrentQuestion = computed(() => {
	let question = questions.value[currentQuestion.value]
	question.index = currentQuestion.value
	return question
})
```

*getCurrentQuestion* computed property in the context of a tutorial. This computed property is used to retrieve and provide the current question that the user should be presented with. It is designed to provide the current question that the user should answer in the quiz.

Inside the computed function, *questions.value[currentQuestion.value]* is used to access the current question. *questions.value* retrieves the array of questions, and *currentQuestion.value* provides the index of the current question, so this line effectively selects the current question object.

*question.index = currentQuestion.value* is used to add an index property to the question object. This index property stores the index of the current question. This can be useful for displaying the question number to the user.

The computed property returns the *question* object, which represents the current question that should be displayed to the user.

This computed property is valuable in a Vue.js quiz application as it simplifies the process of determining which question to display to the user based on the *currentQuestion variable*. It allows you to easily access the current question and its associated data for rendering in the user interface.

```
const nextQuestion = () => {
	if (currentQuestion.value < questions.value.length - 1) {
		currentQuestion.value++
		return
	}
	
	quizCompleted.value = true
}
```

*nextQuestion* function is designed to handle moving to the next question in your Vue.js quiz application. It checks whether there are more questions to navigate to and updates the state accordingly. *nextQuestion* is a function that doesn't take any arguments. It is intended to be called when the user wants to move on to the next question in the quiz.

*if (currentQuestion.value < questions.value.length - 1)* checks if there are more questions available to navigate to. It does this by comparing the index of the current question *(currentQuestion.value)* with the total number of questions *(questions.value.length)*. If there are more questions to go to, the code inside the if block is executed.

Inside the if block, *currentQuestion.value++* increments the *currentQuestion* index to move to the next question in the array.

If there are no more questions to navigate to (i.e., the user is at the last question), the code within the else block is executed.

In this case, *quizCompleted.value* is set to *true*, indicating that the quiz has been completed. This could be used to trigger some UI changes or actions to inform the user that they've finished the quiz.

This function is essential for controlling the flow of your quiz application, ensuring that the user can move through the questions and marking the quiz as completed when they've answered all the questions.

**Answer**

```
const SetAnswer = (e) => {
  questions.value[currentQuestion.value].selected = e.target.value;
  e.target.value = null;
}
```
The *SetAnswer* function appears to be responsible for recording the user's selected answer for the current question and then resetting the selection to null for the next question. *SetAnswer* is a function that takes an event (e) as its argument. This function is typically used as an event handler when a user selects an answer, such as when they click on a multiple-choice option.

*questions.value[currentQuestion.value]* is used to access the current question that the user is working on. *questions.value* represents the array of questions, and *currentQuestion.value* provides the index of the current question.

*questions.value[currentQuestion.value].selected = e.target.value* sets the selected property of the current question to the value of the selected answer. The *e.target.value* typically represents the value of the user's selection, which is recorded as their answer to the current question. This is how the user's answer is associated with the current question.

*e.target.value = null* is used to clear the selection after it has been recorded. This ensures that when the user proceeds to the next question, there are no pre-selected answers, and they have to make a new choice.

This function is an important part of your Vue.js quiz application because it manages the user's interactions with the questions. When a user selects an answer, it records their choice for the current question and then resets the selection for the next question, ensuring a clean state for each question.


**First Front End changes - Display question**

```
<template>
  <main class="app">

    <div class="h1">Quiz</div>

    <section class="quiz">
      <div class="quiz-info">

	<span class="question">{{ getCurrentQuestion.question }}</span>
	<span class="score">Score {{ score }}/{{ questions.length }}</span>
    </section>

  </main>
</template>
```

Now we are going to make first changes in our template. It displays the current question to the user within the "quiz" section of our application and currenct score out of all points available.

Just to reiterate, this template is responsible for rendering the main structure of our quiz application, including the quiz title ("Quiz") and the current question from the getCurrentQuestion computed property. 

Look how our app starts looking:

![app13](https://github.com/jgongala/InternetTechnologies/assets/65823190/08da5a9d-5782-40d9-960a-a56a0a24dacb)

Not bad isn't it? But we still need to work in template to add functionality to our app.

**Question options and navigation**

In this bunch of code that is a part of a Vue.js template for our quiz application we will add options for the current question and a button for navigating to the next question or finishing the quiz. 

*Option*

```
			<div class="options">
				<label 
					v-for="(option, index) in getCurrentQuestion.options" 
					:for="'option' + index" 
					:class="`option ${
						getCurrentQuestion.selected == index 
							? index == getCurrentQuestion.answer 
								? 'correct' 
								: 'wrong'
							: ''
					} ${
						getCurrentQuestion.selected != null &&
						index != getCurrentQuestion.selected
							? 'disabled'
							: ''
					}`">
					<inpu
						type="radio" 
						:id="'option' + index" 
						:name="getCurrentQuestion.index" 
						:value="index" 
						v-model="getCurrentQuestion.selected" 
						:disabled="getCurrentQuestion.selected"
						@change="SetAnswer" 
					/>
					<span>{{ option }}</span>
				</label>
			</div>

```

```<div class="options">```: This div element wraps the options for the current question. It appears to be a container for displaying the multiple-choice options to the user.

*v-for="(option, index) in getCurrentQuestion.options"*: This v-for directive loops through the options array of the current question using option as the value and index as the index. It allows you to render each option.

*:for="'option' + index"*: This :for binding is used to set the for attribute of the label element, associating it with the corresponding radio input element. This is a common practice in HTML for accessibility purposes.

*:class="..."*: This binding is used to dynamically set the class of the label element. The classes are determined based on several conditions:
- *option*: This class is always applied to each option.
- If *getCurrentQuestion.selected* is equal to index (the current option selected by the user), it checks if index is also equal to getCurrentQuestion.answer (the correct answer). If both conditions are met, it adds the class 'correct'; otherwise, it adds the class 'wrong'.
- If *getCurrentQuestion.selected* is not null and index is not equal to *getCurrentQuestion.selected*, it adds the class 'disabled'. This likely indicates that the user has made a selection, and other options should be disabled.

Inside the *label* element:

- *<input ...>*: This input element is of type "radio" and represents a single choice for the current question. It is associated with a specific option and can be selected by the user.
- *:id="'option' + index"*: This sets the id attribute of the radio input element, making it unique for each option.
- *:name="getCurrentQuestion.index"*: This sets the name attribute for the radio input, ensuring that only one option can be selected within the same question. The name is based on the current question's index.
- *:value="index"*: This sets the value for the radio input to index, which is a unique identifier for each option.
- *v-model="getCurrentQuestion.selected"*: This binds the selected value to the getCurrentQuestion.selected property. When the user selects an option, this value is updated.
- *:disabled="getCurrentQuestion.selected"*: If getCurrentQuestion.selected is not null, it means that the user has made a selection, and this option should be disabled.

```<span>{{ option }}</span>```: This span element displays the text of the current option.

```
			<button 
				@click="NextQuestion" 
				:disabled="!getCurrentQuestion.selected">
				{{ 
					getCurrentQuestion.index == questions.length - 1 
						? 'Finish' 
						: getCurrentQuestion.selected == null
							? 'Select an option'
							: 'Next question'
				}}
			</button>
```

```<button>```: This button element is used for navigating to the next question or finishing the quiz.

*@click="NextQuestion"*: This @click directive registers a click event handler, so when the button is clicked, the NextQuestion function is called to move to the next question.

*:disabled="!getCurrentQuestion.selected"*: The button is disabled if getCurrentQuestion.selected is null, indicating that the user hasn't made a selection. When the user selects an option, the button becomes enabled.

The content inside the button, enclosed within double curly braces {{ ... }}, is dynamically generated based on several conditions:

- *getCurrentQuestion.index == questions.length - 1*: If the current question is the last question (determined by comparing the current question's index with the total number of questions minus 1), the button text is 'Finish'.
- *getCurrentQuestion.selected == null*: If the user hasn't selected an option, the button text is 'Select an option'.
- If neither of the above conditions is met, the button text is 'Next question'.

This code represents the user interface for displaying questions and options and controlling the navigation in your Vue.js quiz application. It provides a dynamic and interactive quiz experience for users. And our application looks like this now:

![app14](https://github.com/jgongala/InternetTechnologies/assets/65823190/156f6c19-7721-49fa-845e-eda311402986)
![app15](https://github.com/jgongala/InternetTechnologies/assets/65823190/92907076-f75b-4fb0-889a-d18084971631)

And quick functionality presented below:

![gif1](https://github.com/jgongala/InternetTechnologies/assets/65823190/4063afc9-60f7-4313-b8bf-1620d864885e)

**Completed Quiz**

```
		<section v-else>
			<h2>You have finished the quiz!</h2>
			<p>Your score is {{ score }}/{{ questions.length }}</p>
		</section>
```

This section ia a part of your Vue.js template and is used to display the user's quiz results. 

```<section v-else>```: This section element is conditionally displayed using v-else. This means it will be shown when the preceding condition (likely related to whether the user has completed the quiz) is false. In other words, if the quiz is not completed, the section with the final quiz results will not be displayed.

```<h2>You have finished the quiz!</h2>```: This h2 element displays a message to the user when they have successfully completed the quiz. It informs the user that they have finished the quiz.

```<p>Your score is {{ score }}/{{ questions.length }}</p>```: This p element displays the user's quiz score. It uses the score computed property to dynamically show the user's score. The score is presented as ```"{{ score }}/{{ questions.length }}```, where score is the number of correct answers, and questions.length represents the total number of questions in the quiz. This format typically shows the user's correct answers out of the total possible score.

This section is an essential part of the user interface in your Vue.js quiz application as it provides feedback and displays the user's final score when they complete the quiz. It's a great way to give users a sense of achievement and to summarize their performance in the quiz.

** Final Touch - let's make it pretty*

Since our application is fully functional, it's time to make our application pretty.

```
<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Montserrata', sans-serif;
  }

  body {
    background-color: #EDC7B7;
    color: #123c69;
  }

  .app {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 2rem;
    height: 100vh;
  }

  h1 {
	font-size: 2rem;
	margin-bottom: 2rem;
}

.quiz {
	padding: 1rem;
	width: 100%;
	max-width: 640px;
}

.quiz-info {
	display: flex;
	justify-content: space-between;
	margin-bottom: 1rem;
}

.quiz-info .question {
	color: #123c69;
	font-size: 1.25rem;
}

.quiz-info.score {
	color:#123c69;
	font-size: 1.25rem;
}

.options {
	margin-bottom: 1rem;
}

.option {
	padding: 1rem;
	display: block;
	background-color: #EEE2DC;
	margin-bottom: 0.5rem;
	border-radius: 0.5rem;
	cursor: pointer;
}

.option:hover {
	background-color: #BAB2B5;
}

.option.correct {
	background-color: #2cce7d;
}

.option.wrong {
	background-color: #ff5a5f;
}

.option:last-of-type {
	margin-bottom: 0;
}

.option.disabled {
	opacity: 0.5;
}

.option input {
	display: none;
}

button {
	appearance: none;
	outline: none;
	border: none;
	cursor: pointer;
	padding: 0.5rem 1rem;
	background-color: #EEE2DC;
	color:  #123c69;
	font-weight: 700;
	text-transform: uppercase;
	font-size: 1.2rem;
	border-radius: 0.5rem;
}

button:disabled {
	opacity: 0.5;
}

h2 {
	font-size: 2rem;
	margin-bottom: 2rem;
	text-align: center;
}

p {
	color:  #123c69;
	font-size: 1.5rem;
	text-align: center;
}

</style>
```

You made it. You created your first vue.js application

![gif2](https://github.com/jgongala/InternetTechnologies/assets/65823190/7fcad215-c7c6-446d-967b-13c6c98e140f)




That's it! You've successfully set up a Vue.js project and are ready to start building your web application. For more details and advanced configuration options, you can refer to the official [Vue.js documentation](https://vuejs.org/) and [Vue CLI documentation](https://cli.vuejs.org/).



## [Presentation](index.md)

