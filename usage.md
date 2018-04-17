---
layout: default
title: API Usage
---

# API Usage

You can use our public api (`api.restfulnews.com`) right from your website / SPA (single page application) via CORS.

## Curl Usage

### Creating a user
```bash
curl --request POST --url http://api.restfulnews.com/users \
--header 'content-type: application/json' \
--data '{ "email": "<email>", "password": "<password>" }'
```

### Authenticate a user
[HTTP BASIC Authentication](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication#Basic_authentication_scheme) returning a JWT token.
```bash
curl http://api.restfulnews.com/auth -XPOST \
-H 'Content-Type:application/json' \
-d '{"email":"<email>","password":"<password>"}'
```

### Searching news
```bash
curl --request GET \
--url 'http://api.restfulnews.com/search?topics=australia&companyids=woolworths&start_date=2011-02-22T23:39:03.000Z&end_date=2018-02-22T23:39:03.000Z' \
--header 'authorization: Bearer <bearer token>' \
--header 'content-type: application/json' \
```

## Python Usage

You can use our api through a dedicated python module.

### Instalation

To install the python module use:
```
pip install pythonRestfullNews
```

You are then free to use our python module as outlined below after importing the module

```python
import pythonRestfulNews as prn
```

### Creating a User

To create a user user the `create_user` function. Make sure that the password that you give satisfies the requirements of a safe password.
You will need to save the result of the token to use later in searching for news.

```python
resp = prn.create_user('email@gmail.com', 'password')
token = resp['token']
```

### Authenticating a User

If at any stage you are unable to find the token that you were provided when creating a user, do not make a new user. You can retrieve your exisitng token by using the auth function which is called `retrieve_token`. You can use it as follows:

```python
resp = prn.retrieve_token('email@gmail.com', 'password')
token = resp['token']
```

### Searching News

To search for news you need only provide your token as well as the fields below. Company ids can be either the full name or the company code, topics are for narrowing the serach and the dates provide a range for the search.

```python
topics = 'food'
companyids = 'woolworths'
start_date = '2018-03-01T00:00:00.000Z'
end_date = '2018-03-25T00:00:00.000Z'
        
news = prn.search_news(token, topics, companyids, start_date, end_date)
```
You can access any of the fields as defined in http://docs.restfulnews.com/#api-Search-SearchNews by using the news dictionary. For example if I wanted to find the  title of the news I would after running the above code do:

```python
title = news['title']

```

### More information on Python module
For more information on the python module please visit our github page for it: https://github.com/restfulnews/pythonRestfulNews
