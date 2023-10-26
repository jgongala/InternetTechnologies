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

- Text in the <p> element is bound to the ‘message’ property
- When you type in the input field
- The text in the <p> element updates in real-time, as depicted in the code below:

  
  
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

![Slide14](https://github.com/jgongala/InternetTechnologies/assets/65823190/415c2c9f-3760-4c47-b6a5-1415704caa84)

# Third-Party Libraries:
**Compatibility & Integration:**

- Vue.js works well with various JavaScript libraries and plugins, simplifying the integration of third-party tools.

**RESTful APIs and Backend Technologies:**

- Though Vue.js is front-end-centric, it efficiently interacts with RESTful APIs and backend technologies for data handling.

![Slide15](https://github.com/jgongala/InternetTechnologies/assets/65823190/0ee9e217-4985-4ee4-a068-6faa06f1798d)

## Vue.js in a System
Vue.js plays a crucial role in the front-end of a web application and seamlessly integrates into larger systems. Let's explore how Vue.js fits into the architecture of a web application:

**Front-End Framework:**

- Vue.js is integral to the front-end, seamlessly fitting into larger systems and focusing on the UI layer of web applications.

**Component-Based Architecture:**

- Vue.js supports a modular, component-based structure, streamlining development with reusable elements.

**Interactivity and Responsiveness:**

- Vue.js enables the creation of highly interactive and responsive applicationsvia two-way data binding, improving real-time user experience.

![Slide16](https://github.com/jgongala/InternetTechnologies/assets/65823190/aa649e2c-f7f7-47c8-9e96-2d6ad76b2437)

## Summary

Vue.js is a robust front-end framework for building engaging and dynamic user interfaces.

It offers seamless integration with various backend technologies and a wide range of tools, suitable for applications of all sizes.

Vue.js ensures a responsive, interactive, and easily maintainable user experience.

![Slide17](https://github.com/jgongala/InternetTechnologies/assets/65823190/5f6f5523-2e63-4c3a-8e3b-076e7bd74022)

## USE CASE SCENARIOS

*Chat Applications*

WhatsApp Web

- WhatsApp Web, the web version of the popular messaging app, utilizes Vue.js to provide a smooth and responsive chat experience. Vue.js enables real-time updates of messages and chat conversations, making it easy for users to stay connected.

Facebook Messenger

- Facebook Messenger's web version employs Vue.js to deliver real-time messaging capabilities. Vue's reactivity ensures that messages are instantly displayed, and new messages are received without the need for manual refreshes.

Slack

- Slack, a widely used team collaboration platform, incorporates Vue.js for its chat functionality. Vue.js helps create dynamic channels and threads while maintaining an organized and responsive chat experience.

- Vue.js enables the development of real-time chat applications that are interactive, responsive, and user-friendly. Vue's reactivity and component-based structure are instrumental in creating dynamic chat interfaces, allowing users to communicate seamlessly across different devices and browsers.

![Slide18](https://github.com/jgongala/InternetTechnologies/assets/65823190/a323334d-2e46-4fd5-8755-a1eaff442089)

*Dynamic E-Commerce Product Catalog*

Vue Storefront

- Vue Storefront is an open-source, headless Progressive Web App (PWA) built with Vue.js specifically for e-commerce. It provides a highly customizable and fast shopping experience. Vue Storefront can seamlessly integrate with various e-commerce backends like Magento, WooCommerce, and more.

Typetura

- Typetura is a typography tool that uses Vue.js to allow designers and developers to create dynamic and responsive typography. Vue's reactivity and component-based structure help users visualize changes in typography instantly.

Vogue

- Even major fashion brands like Vogue use Vue.js for their online platforms. Vue.js enables Vogue to showcase dynamic content, articles, and images while maintaining a smooth and engaging user experience.

- Vue.js empowers developers to create interactive, responsive, and feature-rich web applications. It offers a seamless integration of front-end functionality with back-end systems, making it an ideal choice for building dynamic product catalogs in the e-commerce sector and beyond.

![Slide19](https://github.com/jgongala/InternetTechnologies/assets/65823190/283a8b81-4fc6-477a-a491-b4b40247be6b)

*Real-Time Dashboard for IoT Monitoring*

Weather Monitoring Dashboard

- Weather.com, a popular weather monitoring website, uses Vue.js for its interactive weather dashboard. Vue.js enables real-time updates of weather conditions, forecasts, and interactive maps, providing users with accurate and up-to-date information.

Energy Consumption Monitoring

- Smappee, an energy monitoring and management platform, utilizes Vue.js for its dashboard. Users can track real-time energy consumption, identify energy-saving opportunities, and control smart devices with ease.
- Vue.js empowers developers to build real-time IoT monitoring dashboards that are interactive, responsive, and capable of handling large volumes of data from diverse sensors and devices. Vue's reactivity and component-based architecture make it an ideal choice for creating user-friendly interfaces that enable efficient monitoring and control of IoT ecosystems.

![Slide20](https://github.com/jgongala/InternetTechnologies/assets/65823190/afdb9aed-248f-44d7-ad0b-65b701a6a15f)

*Financial Dashboard*

Yahoo Finance

- Yahoo Finance, a popular financial news and data platform, utilizes Vue.js extensively. Vue.js powers the dynamic stock charts, real-time market data updates, and interactive portfolio tracking features, providing users with an informative and engaging experience.

TradingView

- TradingView, a widely used platform for traders and investors, relies on Vue.js for its advanced charting capabilities. Vue.js enables the creation of responsive and customizable stock charts, technical analysis tools, and real-time trading features.

Financial News Aggregators

- Websites like CNBC employ Vue.js to deliver real-time financial news updates, market analysis, and video content. Vue.js enables the integration of live data feeds and interactive multimedia elements, enhancing the user's financial news experience.
- Vue.js empowers developers to create real-time financial dashboards that are not only visually appealing but also highly functional. Vue's reactivity and component-based structure make it well-suited for handling dynamic financial data, providing users with the latest market insights and financial information in a responsive and user-friendly manner.

*Real-Time Collaborative Task Management Tool*

ClickUp

- ClickUp, an all-in-one productivity platform, relies on Vue.js for its task management capabilities. Vue.js enables the creation of customizable task lists, real-time chat, and integrations with various productivity tools.

Trello

- Trello, a popular project management and collaboration platform, uses Vue.js extensively. Vue.js powers the dynamic task boards, real-time updates, and collaborative features, making it easy for teams to manage projects efficiently.
- Vue.js empowers developers to create real-time collaborative task management tools that enhance team productivity and project organization. Vue's reactivity and component-based architecture make it well-suited for building interactive and responsive interfaces that enable efficient task management and team collaboration.

![Slide22](https://github.com/jgongala/InternetTechnologies/assets/65823190/6251ac93-16d6-41f0-a69d-cac5092f1121)

Vue.js is essential to a contemporary e-learning platform since it offers a dynamic and interactive learning environment. Students get access to a wide variety of courses, each with interactive tests, video lectures, and discussion boards. Vue.js guarantees a fluid user experience that enables students to monitor their progress, turn in assignments, and participate in real-time discussions with peers and teachers. Due to its responsiveness and component-based design, this technology enables real-time content updates, device compatibility, and the creation of an engaging learning environment.

![Slide23](https://github.com/jgongala/InternetTechnologies/assets/65823190/710e106e-d30d-4311-b9e2-25525e4adc9c)

## Pros and Cons of using Vue.js

![Slide24](https://github.com/jgongala/InternetTechnologies/assets/65823190/a5a9a23d-10e5-4fce-ac19-5eeb008f8fe1)

**	Advantages of Vue.js: **

- Easy Learning: ideal for all developers.
- Reactivity: Automatic UI updates simplify state management.
- Component-Based Architecture: Promotes modularity and reusability.
- Vue Router: By making straightforward to create single-page applications.
- Vuex: For state management in large apps. 
- Performance: Due to the Vue.js features like virtual DOM and optimized rendering.
- Flexible Integration: Easily fits into existing projects.
- Active Community: Enthusiastic developer support through forums and social media.

![Slide25](https://github.com/jgongala/InternetTechnologies/assets/65823190/d0430e63-2f7d-4e2f-8b17-a344937bf537)

**	Disadvantages of Vue.js: **

- Smaller Ecosystem: Fewer third-party resources compared to larger frameworks like React or Angular 
- Large Apps: May not suit extremely complex and large projects; consider React or Angular. 
- Limited corporate Backing: Largely community-maintained, raising long-term support concerns. 
- Learning Advanced Features: Requires effort to master advanced features. 
- Documentation Variety: Multiple tools with separate documentation sources such as Vue Router, Vuex, and Vue CLI. 

So, the developers should consider its smaller ecosystem and potential limitations

![Slide26](https://github.com/jgongala/InternetTechnologies/assets/65823190/3cf3e049-0489-4fa2-bcc5-417d3bfd7172)

## Deploying on AWS

**Create**
1. Create AWS Account

2. Create EC2 Instance

3. Create Apache2 server

4. Upload Your Web App Files

![Slide27](https://github.com/jgongala/InternetTechnologies/assets/65823190/9505c9d2-6a2a-41ff-81b6-920d7427f268)

## 	Deploying on AWS - Create EC2 Instance 
**Create EC2 instance:** By following these steps:

1. Sign into your AWS account following this link: <https://aws.amazon.com/>

2. Click on EC2 dashboard.

3. Launch a new EC2 instance

4. Select an Amazon Machine Image (AMI) with a Linux distribution.

5. Configure instance details, including network settings and security groups.

6. Review and launch the instance.

7. Create or use an existing key pair for SSH access.

8. Launch the instance.

Now Connect to Your EC2 Instance

![Slide28](https://github.com/jgongala/InternetTechnologies/assets/65823190/8c2220d8-fe7f-4a0e-9c10-f987bf97be3a)

##	Deploying on AWS – Instal web server & upload files!

**Install web server:**

1. Update the package manager and install Apache.

2. Configure Apache to serve your web app

**Upload Your Web App Files:**

By connect your host to Visual Studio Code tool, and will allow you to modify your web app.

Now Test your Web App through a web browser to ensure it is functioning correctly.

![Slide29](https://github.com/jgongala/InternetTechnologies/assets/65823190/09393e78-66cb-4902-a8cb-95e1b4dc80b4)

## Reference Notes:

- Vue.js Official Documentation: <https://vuejs.org/>
- Vue.js GitHub Repository: <https://github.com/vuejs/vue>
- Vue Router Documentation: <https://router.vuejs.org/>
- Vuex Documentation: <https://vuex.vuejs.org/>
- Create EC2 instance: [https://docs.aws.amazon.com/efs/latest/ug/gs-step-one-create-](https://docs.aws.amazon.com/efs/latest/ug/gs-step-one-create-ec2-resources.html)[ec2-resources.html](https://docs.aws.amazon.com/efs/latest/ug/gs-step-one-create-ec2-resources.html)
- Getting started with Amazon: [https://docs.aws.amazon.com/efs/latest/ug/getting-](https://docs.aws.amazon.com/efs/latest/ug/getting-started.html) [started.html](https://docs.aws.amazon.com/efs/latest/ug/getting-started.html)

![Slide30](https://github.com/jgongala/InternetTechnologies/assets/65823190/6ae471ad-879e-4e7b-9f5d-130338a4f16e)

## Questions ..?




