---
layout: default
---

<center><span class="site-title">Everything you need for intelligent news apps.</span></center><br>

RESTful News integrates natural language processing technologies with an open indexer, allowing developers to collate different news sources effectively. Developers can use their own API keys for different news platforms if they wish to exceed our 250 reqs/day limit.

RESTful News follows the [OpenAPI specifications](https://swagger.io/docs/specification/about/).

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


# API Usage

You can use our public api (`api.restfulnews.com`) right from your website / SPA (single page application) via CORS.

## Authentication
[HTTP BASIC Authentication](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication#Basic_authentication_scheme) returning a JWT token.
### Creating a user
```bash
curl -X POST http://api.restfulnews.com/users \
    -i -d "email=test@example.com&password=123456"
```
### Obtain an access token
```bash
curl -X POST http://api.restfulnews.com/auth \
    -i -u test@example.com:123456 -d "access_token=MASTER_KEY_HERE"
```

