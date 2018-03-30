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
git clone git@github.com:restfulnews/api.git
cd api
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
