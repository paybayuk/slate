---
title: Slydo API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - customers
  - products
  - services
  - orders 
  - transactions
  - request_payments
  - webhooks
  - errors

search: false
---

# Introduction
> **API endpoint**

```
https://developer.slydo.co
```

> Examples in this documentation are written using [httpie](https://github.com/jkbrzt/httpie) for clarity.

> To install `httpie` on macOS run `brew install httpie`


Welcome to the Slydo API! Our API is designed to be a predictable and intuitive interface for interacting with our 
platform, which offers both a REST API and webhooks.


# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: $access_token"
```

> Make sure to replace `$access_token` with your API key.

Slydo uses API keys to allow access to the API. You can register a new Slydo API key at our [developer portal](https://developer.slydo.co/dashboard).

Slydo expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: $access_token`
