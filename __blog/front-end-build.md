---
layout: default
title: Initial Front-end Build
date: 2018-04-20 11:45:31 +1000
---

[RN Analytics](https://github.com/restfulnews/app.restfulnews.com) is a single page application (SPA) which uses the [VueJS](https://vuejs.org/) framework to utilise the RESTful News API. During this initial phase, our team committed to building a generic web application that will showcase our API's key features (E.g. company news searching). The three key features that have been implemented in the initial release are:
1. Authentication: ability to login and sign up from within the website.
2. Searching for news articles: ability to add & remove topics and company names via a simple UI and search for articles within a certain time period.
3. Analytical View: compile a small analytical view from the search results.

Initially our team made use of React (another component-based JS library), however after running into several development issues we decided to shift to VueJS.

Vue's core library is focused on the view layer only and is easy to integrate with other JS libraries. We are making use of several other JS libraries to compliment Vue, including axios (for http request handling), fecha (for date formating) and several others. You can take a look at our [package.json](https://github.com/restfulnews/app.restfulnews.com/blob/master/package.json) file to see what other modules are being utilised.

This web application is independent of the API. It has it own repository, runs in its own isolated environment and manages and handles errors independent of the API.

## Libraries and Modules
RN Analytics' front end stack is made up of the web technologies:
* Vue: Progressive javascript framework used to manage view rendering
* Vuex: State management library allowing actions to be committed to a central store, mutating the central application state
* VueMaterial: Material design framework for VueJS
* Bulma: CSS framework used to manage layout related DOMs
* Webpack: Module bundling, which was included in the vue-cli for easy of use

## Directory structure
The project's directory structure can be represented as:
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
The main folders we will be focusing on for development are `components`, `containers`, `store`.

- `components`: consists of dumb components. These components will have no knowledge of the application state, and will only have access to props (properties).
- `containers`: these are smart components that will have full access to the application's state. Pages are a likely candidate for these containers.
- `store`: contains vuex modules relevant to our application's store. In theory, each API route we have will have it's respective store on the front end.

## Data Flow
The data architecture diagram below highlights the different layers within the front end application and how data flows through each layer.
![Data Architectecture Diagram](/assets/images/dad.jpg)
The state of the application is manipulated via actions and mutations. When a user triggers an action (ie. Sending a search request), a mutation is invoked. In vuex, we call this a `commit`. After this mutation is invoked, the invokee of the action calls a `getter` to obtain the next state.

## So what's next?
This build only provides a generic interface for our API (ie. provides basic functionality to highlight core aspects of our API). We plan on using this project as the foundation of our next prototype which will offer features more specific to our mission. Our mission and features will be the basis of our next post... So stay tuned!
