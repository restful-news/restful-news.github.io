---
layout: default
title: Initial Front-end Build
date: 2018-04-20 11:45:31 +1000
---

[RN Analytics](https://github.com/restfulnews/app.restfulnews.com) is a single page application (SPA) which uses the [VueJS](https://vuejs.org/) framework, that makes use of the RESTful News API. During this initial phase, our team committed to building a generic web application, that'll showcase our API's key features (eg. company news searching). The three key features that have been implemented in the initial release are the following below.
1. Authentication: ability to login and sign up directly within the website.
2. Searching for news articles: ability to add & remove topics and company names via a simple UI and search for articles within certian time period.
3. Analytical View: compile a small analytical view from the search results.

Initially our team started of using React (another component-based JS library), however after running into several development issues, we decided to try out VueJS.

Vue's core library is focused on the view layer only, and is easy to pick up and integrate with other JS libraries. We are using several other JS libraries to compliment vue, including: axios (for http request handling), fecha (for date formating) and several others. You can take a look at our [package.json](https://github.com/restfulnews/app.restfulnews.com/blob/master/package.json) file to see what other modules we're using. 

This web application is independant from the API. It has it own repo, runs in its own isolated environment and manages and handles errors independantly of the API. 

## Libraries and Modules
RN Analytics' front end stack is made up of the web technologies.
* Vue: progressive javascript framework used to manage view rendering. 
* Vuex: state management library allowing us to commit actions to a central store, mutating the central application state.
* VueMaterial: Material design framework for VueJS.
* Bulma: CSS framework we used to manage layout related DOMs.
* Webpack: module bundling, which was included in the vue-cli for easy of use

## Directory structure
The project's directory structure looks like this:
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

- `components`: consists of dumb components. These components will have no knowledge of the application state, and will only get access to props (properties).
- `containers`: these are smart components that will have full access to the application's state. Pages are a likely candidate for these containers.
- `store`: contains vuex modules relevant to our application's store. In theory, each API route we have will have it's respective store on the front end.

## Data Flow
The data architecture diagram below highlights the different layers within the front end application and how data flows through each layer. 
![Data Architectecture Diagram](/assets/images/dad.jpg)
The state of the application is manipulated via actions and mutations. When a user triggers an action (ie. Sending a search request), a mutation is invoked. In vuex, we call this a `commit`. After this mutation is invoked, the invokee of the action calls a getter to obtain the next state.

## So what's next?
This build only provides a generic interface for our API (ie. provides basic functionality to highlight core aspects of our API). We plan on using this project as the foundation to our next prototype which will offer features more specific to our mission. Our mission and features will be the basis of our next post... So stay tuned!