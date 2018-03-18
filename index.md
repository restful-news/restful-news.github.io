---
layout: default
---
# RESTful News API
RESTful News API enables developers to build appl.

RESTful News API conventions are based on [OpenAPI specifications](https://swagger.io/docs/specification/about/).


# Basic Usage 
## Authentication
[HTTP BASIC Authentication](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication#Basic_authentication_scheme) returning a JWT token.
### Creating a user
```bash
curl -X POST http://api.restfulnews.com/users -i -d "email=test@example.com&password=123456&access_token=MASTER_KEY_HERE"
```
```bash
curl -X POST http://api.restfulnews.com/auth -i -u test@example.com:123456 -d "access_token=MASTER_KEY_HERE"
```