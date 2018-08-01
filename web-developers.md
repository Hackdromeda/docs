# Web Developers

## Installing the Prerequisites

Before we start, please install the [prerequisites](https://internal.cloudcite.net/prerequisites/) and follow the instructions where applicable. After installing the prerequisites, [configure the project environment](https://internal.cloudcite.net/prerequisites/frontend-developers).

{% hint style="info" %}
If you experience any issues with installing prerequisite software or configuring the project environment, please message an admin on the [Discord channel](https://discordapp.com/invite/maCbhq7) or send a message on the Telegram group.
{% endhint %}

## Project Overview

CloudCite's web application is written in [HTML](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics), [CSS](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics), and [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript). Because we want to maintain consistency, we use TypeScript. Please read this [5 minute guide](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html) that explains how to use TypeScript. The JavaScript runtime that CloudCite runs on is [Node.js](https://nodejs.org/en/). Advanced web applications use JavaScript frameworks to maintain a well-defined project structure and increase productivity. CloudCite uses [Vue.js](https://vuejs.org/). It is **highly recommended** that you read the [Vue.js documentation](https://vuejs.org/v2/guide/) before contributing to CloudCite's development.

## Project Structure

This is a high level overview of CloudCite's project structure. Inside of the project folder, you will find these files and folders.

{% tabs %}
{% tab title="node\_modules" %}
The `node_modules` folder contains all of the dependencies of the project.
{% endtab %}

{% tab title="other\_websites" %}
The `other_websites` folder contains the maintenance and status page websites.
{% endtab %}

{% tab title="public" %}
The `public` folder contains the `static` folder, `index.html`, and `manifest.json`.

### static

The static folder contains static assets, such as [favicons](https://en.wikipedia.org/wiki/Favicon) and images. 

### index.html

The `index.html` file is the main HTML file. We will not be editing the `index.html` often.
{% endtab %}

{% tab title="src" %}
The `src` folder is very important. It contains the `assets` folder, `components` folder, `views` folder, `App.vue`, `main.ts`, `registerServiceWorker.ts`, `router.ts`, `shims-tsx.d.ts`, `shims-vue.d.ts`, and `store.ts`.

### assets

The `assets` folder is similar to the `static` folder. We will not be using the `assets` folder very often because there are differences in how the links are generated for static assets. 

### views

Views are [Vue components](https://vuejs.org/v2/guide/typescript.html#Class-Style-Vue-Components) that will be used as web pages. For example, `Home.vue`  is the homepage.

### components

While views and components are both Vue components, we use them for different things. Views are used as web pages. Components are used as reusable web components. We use components inside of views but we never use views inside of components. Views should not be reused. Components are designed to be reused. For example, the `Cite.vue` in the `components` folder is a reusable component that provides buttons we can click to cite different mediums, such as websites and digital images. We can use it like a regular HTML component. If we want to use the component in a view, we can simply include the &lt;Cite/&gt; closed HTML tag anywhere inside of the root element of a template. This would look something like this:

{% code-tabs %}
{% code-tabs-item title="Example Template" %}
```markup
<template> <!-- Template inside of a view -->
    <div> <!-- Every template must have a root element -->
        <Cite/> <!-- Cite component -->
    </div>
</template>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

### App.vue

`App.vue` is the main view that all of the views will be injected into. Inside of the template in `App.vue`, there is `<router-view/>`. The project uses internal routing, so a view will be injected into the `<router-view/>` when navigating between the web pages.

### router.ts

The `router.ts` file imports all of the views and then provides routes for them. 

{% code-tabs %}
{% code-tabs-item title="router.ts" %}
```javascript
import Vue from 'vue'
import Router from 'vue-router'
// Imports the Home view
import Home from './views/Home.vue'

Vue.use(Router)

export default new Router({ 
    mode: 'history', 
    routes: [ 
        { 
            // homepage uses the '/' path
            path: '/',
            // name of route 
            name: 'home',
            // component that will be used in the route
            component: Home 
        }
    ]
})
    
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}
{% endtabs %}

