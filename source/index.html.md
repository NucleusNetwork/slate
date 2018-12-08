---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the nCoreX API! You can use our API to access nCoreX API endpoints, which can get information on interacting with the Exchange API and calling smart contract functions

We have language bindings in Shell and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const NCoreClient = require('nCore-client');
const API_URL = 'http://nucleusd-backend-staging.us-east-1.elasticbeanstalk.com';
const thisClient = new NCoreClient(API_URL);
```

<aside class="notice">
You can also replace <code>API_URL</code> with local or testnet or livenet specific URLS.
</aside>

# Pairs

## Get All Pairs

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const nCoreClient = require('./index');

const thisClient = new nCoreClient('http://localhost:3001');

(async () => {
  // 1. Fetch all pairs
  console.log(await thisClient.getPairs());
})();
```

> The above command returns JSON structured like this:

```json
[
  {
    "name": "ETH/BTC",
    "id": "5bdd684dbf2da658d81c16d1"
  },
  {
    "name": "XDP/ETH",
    "id": "5bfc44d41307d7534c44ff8b"
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.
