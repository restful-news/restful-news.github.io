---
layout: default
---

<center><span class="site-title">Everything you need for intelligent news apps.</span></center><br>

<div class="services-block">
    <div class="member trading">
        <span>Quantitative Trading</span>
    </div>
    <div class="member portfolio">
        <span>Portfolio Management</span>
    </div>
    <div class="member reading">
        <span>News Reading Apps</span>
    </div>
</div>

RESTful News integrates natural language processing technologies with an open indexer, allowing developers to collate different news sources effectively. Developers can use their own API keys for different news platforms if they wish to exceed our 250 reqs/day limit.

RESTful News follows the [OpenAPI specifications](https://swagger.io/docs/specification/about/).

# API Usage

You can use our public api (`api.restfulnews.com`) right from your website / SPA (single page application) via CORS.

## Authentication
[HTTP BASIC Authentication](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication#Basic_authentication_scheme) returning a JWT token.
### Creating a user
```bash
curl --request POST --url http://api.restfulnews.com/users \
--header 'content-type: application/json' \
--data '{ "email": "<email>", "password": "<password>", \
"name": "<name>", "picture": "<picture link>"}'
```
### Authenticate a user
```bash
curl http://api.restfulnews.com/auth -XPOST \
-H 'Content-Type:application/json' \
-d '{"email":"<email>","password":"<password>"}'
```
### Searching news
```bash
curl --request GET \
--url http://api.restfulnews.com/search?topics=<topics>&start_date=<iso_time>&end_date=<iso_time> \
--header 'authorization: Bearer <bearer token>' \
--header 'content-type: application/json' \
```
