---
layout: default
title: Local Installation
---
# Local Installation

## Requirements
- MongoDB
- Node >7.4
- pm2 (production)


## Setting up & running locally
### 1. Clone the repo.
```bash
git clone git@github.com:restful-news/restful-news.git
cd restful-news
```
### 2. Install dependencies.
```bash
npm i
```
### 3. Initalise the environment.
```bash
cp .env.example .env
```
Replace the provided example keys with your own keys in `.env`.
### 4. Start the server.
```bash
npm start
```
Note: Make sure mongodb is running.

## Commands

```bash
npm test # test using Jest
npm run test:unit # run unit tests
npm run test:integration # run integration tests
npm run coverage # test and open the coverage report in the browser
npm run lint # lint using ESLint
npm run dev () # run the API in development mode
npm run prod # run the API in production mode
npm run docs # generate API docs
```

## Directory structure

### Overview

You can customize the `src` and `api` directories.

```
src/
├─ api/
│  ├─ user/
│  │  ├─ controller.js
│  │  ├─ index.js
│  │  ├─ index.test.js
│  │  ├─ model.js
│  │  └─ model.test.js
│  └─ index.js
├─ services/
│  ├─ express/
│  ├─ facebook/
│  ├─ mongoose/
│  ├─ passport/
│  ├─ sendgrid/
│  └─ your-service/
├─ app.js
├─ config.js
└─ index.js
```

### src/api/

Here is where the API endpoints are defined. Each API has its own folder.

#### src/api/some-endpoint/model.js

It defines the Mongoose schema and model for the API endpoint. Any changes to the data model should be done here.

#### src/api/some-endpoint/controller.js

This is the API controller file. It defines the main router middlewares which use the API model.

#### src/api/some-endpoint/index.js

This is the entry file of the API. It defines the routes using, along other middlewares (like session, validation etc.), the middlewares defined in the `some-endpoint.controller.js` file.

### services/

Here you can put `helpers`, `libraries` and other types of modules which you want to use in your APIs.

## Error handling

Errors are handled by the `services/error` middleware. You can pass errors within an async call by calling `next(error)` where error is an Object with a Prototype of error. The APIError constructor function has been provided for creating anticipated operational errors.

## Logging

Logging is achieved via Pino. In development mode we can pipe Node's stdout into Pino for pretty printing.

