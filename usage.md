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
--data '{ "email": "<email>", "password": "<password>" }'
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
--url 'http://api.restfulnews.com/search?topics=australia&companyids=woolworths&start_date=2011-02-22T23:39:03.000Z&end_date=2018-02-22T23:39:03.000Z' \
--header 'authorization: Bearer <bearer token>' \
--header 'content-type: application/json' \
```
