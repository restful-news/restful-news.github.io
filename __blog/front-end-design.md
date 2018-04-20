---
layout: default
title: Front End Design - RN Analytics
---

[RN Analytics](https://github.com/restfulnews/app.restfulnews.com) is a single page application (SPA) written in javascript, using the  [VueJS](https://vuejs.org/) framework. 

Initially our team started of using React (another component-based JS library), however after running into several development issues regarding application state management, we decided to try Vue. Vue's core library is focused on the view layer only, and is easy to pick up and integrate with other JS libraries. We are using several other JS libraries to compliment vue, including: axios (for http request handling), fecha (for date formating) etc... You can take a look at our [package.json](https://github.com/restfulnews/app.restfulnews.com/blob/master/package.json) file to see what other modules we're using. 

## Front End Stack
RN's front end stack consists of the following web technologies.
* Vue: main framework used to manage view rendering etc. 
* Vuex: state management library allowing us to use a central store.
* VueMaterial: Material design framework consisting of stylised material components that work well with vue
* Bulma: CSS framework we use to manange our grids etc
* Webpack: for module bundling, which was included in the vue-cli for easy of use

## Components


## Application State Management


## Accessing the API


## Conclusion