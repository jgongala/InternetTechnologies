
## Vue.JS Tutorial

## Vue.js Project Setup

Before you begin, make sure you have the following prerequisites installed on your computer:

- [Node.js](https://nodejs.org/) and [npm](https://www.npmjs.com/) (Node Package Manager).

**Step 1: Install Vue CLI (Command Line Interface)**

Vue CLI is a tool for scaffolding Vue.js projects. Install it globally on your system using npm:

![step1](https://github.com/jgongala/InternetTechnologies/assets/65823190/b0f7ff4d-c1ad-4866-90e6-fec97d8df58a)

```
npm install -g @vue/cli
```


**Step 2: Create a New Vue Project**

Once Vue CLI is installed, navigate to the directory where you want to create your project and run the following command:

![step2](https://github.com/jgongala/InternetTechnologies/assets/65823190/b7c73b9f-c72b-4cbc-9190-20ee1250830d)


```
vue create weather-app
```

**Step 3: Project Structure**

After creating the project, you'll see the following project structure:

- **node_modules:** This directory contains project dependencies. You don't need to modify anything in here; it's managed by npm.
- **public:** This directory is for static assets, and it typically contains the `index.html` file, which is the main HTML page for your Vue.js app.
- **src:** This directory is where your Vue.js application's source code is located. You'll be spending most of your time here, creating Vue components and writing application logic.
- **package.json:** This file contains project configuration, including the list of dependencies and various scripts for development, building, and testing.
- **README.md:** This is the project's documentation file, where you can provide information about your project, how to set it up, and how to use it.
- **.gitignore:** This file specifies which files and directories should be ignored by Git. It's used for version control and helps exclude files like build artifacts and dependencies.

This project structure provides a solid foundation for organizing your Vue.js application and its related files.

**Step 4: Start the Development Server**

To view your Vue.js app, start the development server. Navigate to the project directory and run the following commands:

![step3](https://github.com/jgongala/InternetTechnologies/assets/65823190/1d9abfe1-aa84-4f1e-84db-0b0910ea11af)

```
cd weather-app
npm run serve
```

This command will start the development server, and you will see a [URL](http://localhost:8080) where you can access your app.

**Step 5: Edit Your Vue App**

Open the project in your code editor of choice. The main Vue component can be found in the `src` directory, typically in a file named `App.vue`. You can start editing this file and add your Vue components in the `components` directory.

- **App.vue:** This is the main Vue component that serves as the entry point for your application. You can customize the content and structure of your app in this file.
- **components:** This directory is where you can create and organize your Vue components. Vue components are reusable pieces of your application that encapsulate HTML, CSS, and JavaScript.

Feel free to make changes, create new components, and design your Vue.js app to meet your project requirements.

Once you've made your modifications, you can see the changes by reloading the development server.

**Step 6: Build for Production**

When you're ready to deploy your Vue app, you can create a production build by running the following command:

```bash
npm run build
```

This command will generate optimized, minified, and bundled files in the `dist` directory, which you can deploy to a web server.

That's it! You've successfully set up a Vue.js project and are ready to start building your web application. For more details and advanced configuration options, you can refer to the official [Vue.js documentation](https://vuejs.org/) and [Vue CLI documentation](https://cli.vuejs.org/).

## Getting Started with your code

**Include the Vue.js Library**

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

![step6](https://github.com/jgongala/InternetTechnologies/assets/65823190/9cf92618-474a-4695-880c-e2d0e5fc3ba1)


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

In this example, we create a Vue instance with the `new Vue()` constructor. We specify the `el` property to define the HTML element with the id "app" as the mounting point for our Vue instance. The `data` property contains the data that Vue.js will manage, in this case, a `message` property with the value "Hello, Vue!"

**Step 3: Interact with Vue Data**

You can now access the data defined in your Vue instance within your HTML by using double curly braces `{{ }}`. In this example, we're displaying the value of the `message` property within the `#app` element.

When you open your HTML file in a browser, you'll see "Hello, Vue!" displayed on the webpage. Vue.js is now managing the data binding for this element.

That's it! You've created a basic Vue instance in an HTML file. You can build upon this foundation to create more complex and interactive Vue.js applications.

## Basic Vue.js Directives: 

**Interpolation**

https://github.com/jgongala/InternetTechnologies/assets/65823190/346e3b97-bdc6-491f-af41-111f305b7cb8

Vue.js allows you to interpolate data into your template using double curly braces `{{ }}`. This is one of the most common ways to display dynamic data in your HTML.

```
<div id="app">
    {{ message }}
</div>
```

In this example,  `message` will be replaced with the value of the `message` property from your Vue instance. If `message` is "Hello, Vue!", the rendered HTML will be "Hello, Vue!".

Interpolation is a simple and effective way to display dynamic data in your Vue.js application.

*v-bind Directive*

https://github.com/jgongala/InternetTechnologies/assets/65823190/1e1f4e94-fe8a-4d88-830f-384fbe887ea4

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

**v-on Directive**

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

## Vue.js Methods and Event Handling

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

## Vue.js Directives and Conditionals

1.	v-if, v-else-if, v-else: You can use these directives for conditional rendering

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

**HTML Structure:**

- The HTML structure includes a div with the ID "app," which serves as the root element for our Vue instance.

**Conditional Rendering Directives:**

- We use Vue.js directives to conditionally render content based on the values of data properties.
- The first `<p>` element is enhanced with the `v-if` directive and checks the condition `isUserLoggedIn`. If `isUserLoggedIn` is `true`, it displays the "Welcome, user!" message.
- The second `<p>` element uses the `v-if` directive with the condition `isUserAdmin`. It checks if the user is an admin. If `isUserAdmin` is `true`, it displays the "You are an admin" message.
- The third `<p>` element employs the `v-else-if` directive with the condition `isUserModerator`. It checks if the user is a moderator. If `isUserModerator` is `true`, it displays the "You are a moderator" message.
- The final `<p>` element is associated with the `v-else` directive. It is displayed when none of the preceding conditions are met and shows the message "Please log in."

**Vue Instance:**

- We create a Vue instance named `app` and specify that it should be mounted on the element with the ID "app."

**Data Properties:**

- In the data section of the Vue instance, we define three boolean properties: `isUserLoggedIn`, `isUserAdmin`, and `isUserModerator`. These properties represent example conditions. In a real application, these conditions could be dynamically set based on user roles or authentication status.

This example serves as a practical demonstration of Vue.js's capabilities in handling conditional rendering. By using `v-if`, `v-else-if`, and `v-else`, you can dynamically adjust the content displayed to users based on different conditions. This is a powerful feature for building interactive and personalized user interfaces.

2. v-for: Use this directive for rendering lists of data.

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

**Rendering Lists in Vue.js:**

In this code example, we showcase how to render lists and iterate over data structures using Vue.js directives. This is a fundamental concept for displaying dynamic content in Vue.js.

**HTML Structure:**

- The HTML structure consists of a div with the ID "app," serving as the root element for our Vue instance.

**Rendering Lists:**

We use various Vue.js directives to render lists in different ways.

1. **Rendering a Simple List:**

   - The first `<ul>` element contains a list of items rendered using the `v-for` directive. It iterates over the `items` array and displays each item as an `<li>` element.

2. **Rendering a List with Index:**

   - The second `<ul>` element uses the `v-for` directive to iterate over the `items` array, but it also provides an index using `(item, index)`. This allows us to display both the item and its index in the list.

3. **Rendering an Object:**

   - The third `<ul>` element utilizes `v-for` to iterate over the `user` object. It displays each key-value pair as an `<li>` element, showing the key and its associated value.

4. **Rendering a Fixed Number of Items:**

   - The fourth `<ul>` element demonstrates using `v-for` to loop through a range of numbers, in this case, from 1 to 5, and displays each item as "Item {{ n }}."

**Vue Instance:**

- We create a Vue instance named `app` and specify that it should be mounted on the element with the ID "app."

**Data Properties:**

- In the data section of the Vue instance, we define two data properties: `items` and `user`.
   - `items` is an array containing a list of items.
   - `user` is an object with key-value pairs representing user information.

**Tutorial Purpose:**

This example serves as a practical guide to using Vue.js for rendering lists in different ways. It covers iterating over arrays, displaying indices, rendering objects, and generating a fixed number of items. Understanding these techniques is essential for building dynamic and data-driven user interfaces in Vue.js.

## Vue.js Components
Vue.js allows you to create reusable components. Here's a basic example of creating a component:

**Vue.js Components:**

Vue.js offers a powerful feature called components, which allow you to create reusable and modular building blocks for your application's user interface. Components can be thought of as self-contained units of functionality and appearance, making your code more organized and maintainable.

**Creating a Vue.js Component:**
Vue.js allows you to create reusable components. Here's a basic example of creating a component:

![step16](https://github.com/jgongala/InternetTechnologies/assets/65823190/5341ca96-af1b-4143-adf0-25ee9304957f)

![step17](https://github.com/jgongala/InternetTechnologies/assets/65823190/46164e47-8629-4f9c-8424-1901239dc891)

**HTML Structure**
Within the `<body>`, you'll find a `<div>` element with the id of "app." This element serves as the mounting point for our Vue instance, where we'll render our Vue component.

In this structure, the `<div>` with the id "app" is where our Vue.js application will be anchored. It's the designated location where the Vue component will be displayed and rendered on the web page. Any content or output generated by the Vue component will be inserted into this `<div>` element when the Vue application is in action.

**Vue Instance**
We create a new Vue instance using `new Vue({})`. This instance will control our application and is mounted on the element with the id "app" using el: '#app'.

**Define a Vue Component**

Within the Vue instance, we define a custom Vue component named "my-component" using the `components` option. The component definition includes:

- The `template` property, which contains the HTML structure of the component. It uses Vue.js's template syntax to display the `title` and `content` data properties.
- The `data` method, which returns an object containing data properties. In this case, we have `title` and `content` properties with initial values. 

**Using the Vue Component**

To use the "my-component" within your application, you can simply include `<my-component></my-component>` in your HTML. This is how you render and use the component.

**Data Binding**
The component's template section utilizes data binding to display the values of the title and content properties defined in the data section of the component. This enables dynamic content updates based on the component's data.

This example demonstrates a basic setup for creating and using a Vue.js component directly within an HTML file. You can expand on this foundation to build more complex Vue.js applications with reusable components.

## [Presentation](index.md)

