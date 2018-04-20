---
layout: default
title: Initial Front-end Build
date: 2018-04-20 11:45:31 +1000
---

[RN Analytics](https://github.com/restfulnews/app.restfulnews.com) is a single page application (SPA) which uses the [VueJS](https://vuejs.org/) framework. During this initial phase our team committed to build a generic web application that'll showcase our API's key features (ie. company news searching). The three key features that have been implemented in our release include:
1. Authentication: ability to login and sign up using our /auth and /user API routes.
2. Searching for news articles: ability to add & remove topics and company names via a simple UI for a given time range. 
3. Analytical View: provide a small analytical view based on the search results.

Initially our team started of using React (another component-based JS library), however after running into several development issues, we decided to try out VueJS.

Vue's core library is focused on the view layer only, and is easy to pick up and integrate with other JS libraries. We are using several other JS libraries to compliment vue, including: axios (for http request handling), fecha (for date formating) and several others. You can take a look at our [package.json](https://github.com/restfulnews/app.restfulnews.com/blob/master/package.json) file to see what other modules we're using. 

## Libraries and Modules
RN Analytics' front end stack is made up of the web technologies.
* Vue: progressive javascript framework used to manage view rendering. 
* Vuex: state management library allowing us to commit actions to a central store, mutating the central application state.
* VueMaterial: Material design framework for VueJS.
* Bulma: CSS framework we used to manage layout related DOMs.
* Webpack: module bundling, which was included in the vue-cli for easy of use

## Directory structure
Our project structure looks like this:
```
app.restfulnews.com
├── App.vue
├── assets
│   ├── images
│   │   └── ...
│   └── sass
│       └── ...
├── components
│   ├── Empty404.vue
│   ├── GraphCard.vue
│   ├── NewsCard.vue
│   └── Timeline.vue
├── containers
│   ├── 404.vue
│   ├── Account.vue
│   ├── Auth.vue
│   ├── Bookmarks.vue
│   ├── Explore.vue
│   └── Home.vue
├── main.js
├── router
│   └── index.js
├── store
│   ├── app.js
│   ├── auth.js
│   ├── index.js
│   ├── search.js
│   └── user.js
└── utils
    ├── cookie.js
    └── http.js
```
The main folders we'll be focusing on are `components`, `containers`, `store`. 

- `components`: consists of dumb components. These components will have no knowledge of the application state, and will only get passed props (properties).
- `containers`: these are smart components that will have full access to the application

## Data Flow