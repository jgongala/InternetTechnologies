## VUE.JS Deployment on AWS

![Slide1](https://github.com/jgongala/InternetTechnologies/assets/65823190/b436ad15-ed84-4168-8c76-cd349f4ddc0c)

Team Members:

Julia Gongala | B00402569

Mustafa Jadoun | B00858426

Sheen Shelton | B00384867

Sunxing Yu | B01656116

![Slide2](https://github.com/jgongala/InternetTechnologies/assets/65823190/e0dd0c5d-72c9-408b-bf43-04a66f56a8cf)

## Introduction

Deploying Vue.js on AWS involves a series of essential steps to ensure a smooth and reliable operation. In this presentation, we will focus on the key components of deploying a Vue.js application on Amazon Web Services.

Starting from setting up an “*Amazon EC2 instance*” to configuring “*Nginx*” as a reverse proxy, we will cover everything you need to know to make your *Vue.js* application publicly accessible and ensure high availability and optimal performance.

So first, Let's dive into the world of Vue.js

![Slide3](https://github.com/jgongala/InternetTechnologies/assets/65823190/ba6441a5-aa72-42e7-b80c-37b292654f77)

## Popularity

Vue.js, often referred to as Vue, is an open-source “JavaScript” framework which is launched in 2014 by “*Evan You*”.

- Vue.js has gained remarkable popularity in web development that notable for its simplicity and flexibility.
- Rapidly becoming one of the most sought-after front-end frameworks.
- Strong ecosystem of libraries and tools.
- Growing community of developers which has garnered a significant following in recent years.

By examining the GitHub community for development and the Stack Overflow community for problem-solving and learning, we can make an informed assessment of Vue.js's popularity and support, as depicted in the image below.

### Popularity & Support image

![Slide4](https://github.com/jgongala/InternetTechnologies/assets/65823190/26a13159-09f2-44f7-9ce2-6f414394a8a6)

source: [monterai](https://www.monterail.com/blog/vue-vs-react)[ ](https://www.monterail.com/blog/vue-vs-react)website

![Slide5](https://github.com/jgongala/InternetTechnologies/assets/65823190/36ed0eac-7710-4b69-b08b-6b582081d8b8)

## Purpose

- Make web application development more manageable and efficient.
- Provides a progressive framework.
- Incremental Adoption which can be incrementally adopted into projects of all sizes.
- Versatility: Suitable for both simple Single-Page Applications (SPAs) and complex enterprise-level systems.
- Empowerment: Empowers developers to craft user interfaces with ease.

![Slide6](https://github.com/jgongala/InternetTechnologies/assets/65823190/2008a7e4-6752-4dcb-8aab-6e97c43911d8)

## Who Uses It

- Diverse Adoption: It is trusted by a diverse range of organizations and developers worldwide like these companies like Alibaba, Xiaomi, and Adobe, among others, have adopted Vue.js for their web projects.
- Accessible to All: Its approachable learning curve accommodates developers of all skill levels, from startups to established tech giants.
- In Summary: Vue.js is known for its simplicity, flexibility, and broad user base, empowering efficient development of dynamic and interactive web applications.
- All that make Vue.js A Trusted Framework Worldwide
- Here are some examples of companies that use Vue.js in their projects

![Slide7](https://github.com/jgongala/InternetTechnologies/assets/65823190/959c86e7-ee41-46e3-b8ba-25b064f33e47)

source: [monterai](https://www.monterail.com/blog/vue-vs-react)[ ](https://www.monterail.com/blog/vue-vs-react)website

![Slide8](https://github.com/jgongala/InternetTechnologies/assets/65823190/33004234-7a4c-4088-ac51-f2962f5b6d55)

## Simple Examples - Data Binding

**Demonstrating Vue.js Data Binding**

Text in the <p> element is bound to the ‘message’ property

- When you type in the input field
- The text in the <p> element updates in real-time, as depicted in the images below:
```
<!DOCTYPE html>
<html>
<head>
    <title>Vue.js Data Binding</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2.6.14/dist/vue.js"></script>
</head>
<body>
    <div id="app">
        <p>{{ message }}</p>
        <input v-model="message">
    </div>
    
    <script>
        new Vue({
            el: '#app',
            data: {
                message: 'Hello, Vue.js'
            }
        });
    </script>
</body>
</html>
```
![Slide9](https://github.com/jgongala/InternetTechnologies/assets/65823190/4432e630-6e4e-4a50-a6cc-3aa0d0e0aad3)

## Code Explanation
**HTML:**

- `<!DOCTYPE html>`: Defines the document type.
- `<html>`: Begins the HTML document.
- `<head>`: Contains meta-information and linked scripts/stylesheets.
- `<title>`: Specifies the page title.
- `<script>`: Links to the Vue.js library using a CDN (Content Delivery Network).
- `<body>`: Contains the main content.

**Vue.js Setup:**

- `<div id="app">`: Serves as the Vue container.
- `<p>{{ message }}</p>`: Demonstrates data binding.
- `<input v-model="message">`: Illustrates two-way binding.

**JavaScript Vue.js Initialization**

- new Vue({}) It creates a new Vue instance.
- el: '#app' : specifies that the Vue instance will control the element with the id "app."
- data: { message: 'Hello, Vue.js!’ } defines initial data for data binding.


![Slide10](https://github.com/jgongala/InternetTechnologies/assets/65823190/f333a957-7767-45b6-a7c7-15049589d59e)

## Simple Examples - Event Handling

**Showcase Vue.js Event handling**
- Clicking on the "Click me" button to triggers the “sayHello” method
- updates the greeting property to display a message
As depicted in the code below:
```
<!DOCTYPE html>
<html>

<head>
  <title>Vue.js Event Handling Example</title>
  <script src="https://cdn.jsdelivr.net/npm/vue@2.6.14/dist/vue.js"></script>
</head>

<body>
  <div id="app">
    <button v-on:click="sayHello">Say Hello</button>
    <p>{{ greeting }}</p>
  </div>

  <script>
    new Vue({
      el: '#app',
      data: {
        greeting: ''
      },
      methods: {
        sayHello: function () {
          this.greeting = 'Hello from Vue.js!';
        },
      },
    });
  </script>
</body>
</html>
```

![Slide11](https://github.com/jgongala/InternetTechnologies/assets/65823190/efe0bfb3-4085-4e08-b22d-8b9d2c207bbe)

## Code Explanation

**HTML:**

- `<!DOCTYPE html>`: Defines the document type.  
- `<html>`: Begins the HTML document. 
- `<head>`: Contains meta-information and linked scripts/stylesheets.
- `<title>`: Specifies the page title.
- `<script>`: Links to the Vue.js library using a CDN (Content Delivery Network).
- `<body>`: Contains the main content.

**Vue.js Setup:**
- `<div id="app">`: Serves as the Vue container.
- `<p>{{ greeting }}</p>`: Demonstrates data binding.
- `<button v-on:click="sayHello">`: Specifies that the `sayHello` method should be called when the button is clicked.

**JavaScript initializes Vue:**

- `new Vue({})`: Creates a new Vue instance.
- `el: '#app'`: Specifies that the Vue instance will control the element with the ID "app."
- `data: { greeting: '' }`: The data option defines the initial data for the Vue instance, setting the `greeting` property to an empty string.
- `methods: { sayHello: function() { ... } }`: Defines custom methods that can be called from the Vue instance. In this case, it sets the `greeting` property to 'Hello, Vue.js!' when the button is clicked.

![Slide12](https://github.com/jgongala/InternetTechnologies/assets/65823190/2b89a93a-de8c-45f2-a56c-203cab9a5419)

## Interactions with other technologies

Vue.js is designed to be highly compatible and easily integrated with other technologies commonly used in web development.

**HTML Integration:**
**Templates:**
- Vue.js employs HTML-based templates for UI design.
- Ease of use: templates resemble standard HTML.
- Dynamic & responsive UIs through data and directive binding.

**Custom HTML Attributes:**

- Vue.js enhances HTML with custom attributes called directives.
- Directives like v-bind and v-on add specific behaviors to elements.

**Component-Based Structure:**

- Vue.js advocates component-based architecture.
- Components encapsulate HTML, CSS, and JavaScript.
- Organizes and modularizes code for complex UIs.

![Slide13](https://github.com/jgongala/InternetTechnologies/assets/65823190/be4b457d-b9be-454f-be17-ff91d783e362)

## CSS and JavaScript Integration
**CSS**
**Scoped CSS:**

- Vue.js allows component-specific styles, preventing conflicts.
- Clean Structure: Ensures encapsulated and conflict-free styling.

**CSS Preprocessors:**

- Vue.js supports integration with CSS preprocessors for enhanced styling.

**JavaScript Libraries:**
**Vue Router:**

- Popular for routing in SPAs (single-page applications)
- Offers client-side routing with Vue.js
- Enables navigation between views, ensuring smooth user experience

**Vuex:**

- State management for large applications.
- Centralizes and manages application state and integrates seamlessly with Vue components.

# Third-Party Libraries:
**Compatibility & Integration:**

- Vue.js works well with various JavaScript libraries and plugins, simplifying the integration of third-party tools.

**RESTful APIs and Backend Technologies:**

- Though Vue.js is front-end-centric, it efficiently interacts with RESTful APIs and backend technologies for data handling.

![Slide14](https://github.com/jgongala/InternetTechnologies/assets/65823190/415c2c9f-3760-4c47-b6a5-1415704caa84)

## Vue.js in a System
Vue.js plays a crucial role in the front-end of a web application and seamlessly integrates into larger systems. Let's explore how Vue.js fits into the architecture of a web application:

**Front-End Framework:**

- Vue.js is integral to the front-end, seamlessly fitting into larger systems and focusing on the UI layer of web applications.

**Component-Based Architecture:**

- Vue.js supports a modular, component-based structure, streamlining development with reusable elements.

**Interactivity and Responsiveness:**

- Vue.js enables the creation of highly interactive and responsive applicationsvia two-way data binding, improving real-time user experience.

![Slide15](https://github.com/jgongala/InternetTechnologies/assets/65823190/0ee9e217-4985-4ee4-a068-6faa06f1798d)

## Summary

Vue.js is a robust front-end framework for building engaging and dynamic user interfaces.

It offers seamless integration with various backend technologies and a wide range of tools, suitable for applications of all sizes.

Vue.js ensures a responsive, interactive, and easily maintainable user experience.

![Slide16](https://github.com/jgongala/InternetTechnologies/assets/65823190/aa649e2c-f7f7-47c8-9e96-2d6ad76b2437)

## USE CASE SCENARIOS

*Chat Applications*

WhatsApp Web

- WhatsApp Web, the web version of the popular messaging app, utilizes Vue.js to provide a smooth and responsive chat experience. Vue.js enables real-time updates of messages and chat conversations, making it easy for users to stay connected.

Facebook Messenger

- Facebook Messenger's web version employs Vue.js to deliver real-time messaging capabilities. Vue's reactivity ensures that messages are instantly displayed, and new messages are received without the need for manual refreshes.

Slack

- Slack, a widely used team collaboration platform, incorporates Vue.js for its chat functionality. Vue.js helps create dynamic channels and threads while maintaining an organized and responsive chat experience.

- Vue.js enables the development of real-time chat applications that are interactive, responsive, and user-friendly. Vue's reactivity and component-based structure are instrumental in creating dynamic chat interfaces, allowing users to communicate seamlessly across different devices and browsers.




### SvelteKit

![Slide13](images/Slide13.png)
The website lists some of the features provided by SvelteKit.  This includes routing (without needing a separate router) and server side rendering.  Svelte will need to run on a suitable server.  For development the Vite development server is appropriate.

The structure of the project directory includes a `src` folder with the app.html and a routes folder with at least on `+pages.svelte` file.

![Slide14](images/Slide14.png)
The html file contains a `<div>` which displays %sveltekit.body% this is the location where the svelteKit output will be rendered.

There is no link required, the file which provides the output is the first `+page.svelte` in the routes folder.

![Slide15](images/Slide15.png)
A second display page can be added within a nested folder within routes.  The name of the folder, 'about' will provide the adress for navigation.  So this is unlike a web page navigation there is not an http://filename call.

The routing syntax is simple and straightforward.

![Slide16](images/Slide16.png)
It would not be efficient to include the same navigation code on every page which needed it so the code can be incorporated into a layout.

The `<slot/>` is the location on the layout where the content from the individual pages will be rendered.

![Slide17](images/Slide17.png)
Hopefully that is enough to be able to read through a demo file running in a docker development container.

## Demo App

![Slide18](images/Slide18.png)
Start Docker desktop.

Create and empty folder and then using CTRL + P ask the remote container plugin to open it in a container.  Follow the prompts to select a node plus typescript container and allow time for this to download content.

When the container is ready check the version of node.

Now create a svelte app using the latest svelte version.

Follow the choice which creates the demo app.

![Slide19](images/Slide19.png)
Make choices to use Typescript syntax and to add the prettier code formatter.

![Slide20](images/Slide20.png)
With no further options selected the project comes to completion.

There are a range of plug-ins for svelte which can be reviewed on github, however these are not required for the simple demonstration.

![Slide21](images/Slide21.png)
The package json file reflects the available vite scripts and the dependancies.

![Slide22](images/Slide22.png)
Change directory to the application folder and install the dependancies.

After a wait the project is ready to run on the vite server with npm run dev.

![Slide23](images/Slide23.png)
The demo includes a navigation menu, a welcome image, some text and a counter.  These elements will be brought in from smaller files.

![Slide24](images/Slide24.png)
The Sverdle demo game mimics the operation of the popular wordle site which gives the option to guess a five letter word.  Correctly guessed letters have a border added and correctly placed letters are highlighted.

Incorrectly guesse letters are grayed out on the alphabet display.

![Slide25](images/Slide25.png)
An example game is played out here from the first guess of 'bread' to the final correct word 'icily'.  Because the source words are provided from the server there is nothing in the browser which could allow the player to cheat.

![Slide26](images/Slide26.png)
Looking over the demo code the html has a place for sveltekit head and sveltekit body.  There is nothing of the displayed content here.

![Slide27](images/Slide27.png)
The layout provides the common content for all pages which includes text imnported from Header.svelte.

The `<slot/>` in the main section is where individual page details will render.

![Slide28](images/Slide28.png)
The home page is the first `+page.svelte` in the routes folder.

This includes the header information with the title 'home'.

The counter is read from the counter file.  There is no need for an import statement, just use the `<Counter />` element reference.

![Slide29](images/Slide29.png)
The navigation bar is in the Header file which is called into the top of the layout for all pages in the app.

![Slide30](images/Slide30.png)
As with React, the application can be built on Vite and previewed to check that it is working.  The use of a different port indicates that this is a build preview.

![Slide31](images/Slide31.png)
Unlike react, the output is not an html/javascript file which can run from the live server.  

To deploy the user must first install an adapter and then edit the svelte.config.js file to mathch the deployment target, such as a node server in this example.


![Slide32](images/Slide32.png)
A number of deployment targets exist and this does include a static HTML page where this is right for the application.

![Slide33](images/Slide33.png)
Looking at use cases on the svelte website it is evident that well functioned applications can be produced.

![Slide34](images/Slide34.png)
Here data visualisation is shown on a svelte page.

The companies are real and significant, but tend not to be the larger companies which are still using the commercially supported frameworks such as react.

![Slide35](images/Slide35.png)
If you are willing to work with a system which is not as popular as the main players there is a benefit in code of server side rendering and a syntax which becomes comfortable to work with.

