---
layout: default
title: API Usage
---

# API Usage

You can use our public api (`api.restfulnews.com`) right from your website / SPA (single page application) via CORS.
## Creating a user
```bash
curl --request POST --url http://api.restfulnews.com/users \
--header 'content-type: application/json' \
--data '{ "email": "<email>", "password": "<password>", \
"name": "<name>", "picture": "<picture link>"}'
```
## Authenticate a user
[HTTP BASIC Authentication](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication#Basic_authentication_scheme) returning a JWT token.
```bash
curl http://api.restfulnews.com/auth -XPOST \
-H 'Content-Type:application/json' \
-d '{"email":"<email>","password":"<password>"}'
```
## Searching news
```bash
curl --request GET \
--url http://api.restfulnews.com/search?topics=<topics>&start_date=<iso_time>&end_date=<iso_time> \
--header 'authorization: Bearer <bearer token>' \
--header 'content-type: application/json' \
```
