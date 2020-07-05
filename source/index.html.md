---
title: Slydo API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://slydo.co/'>Sign Up for a Developer Key</a>

includes:
  - transactions
  - request_payments  
  - webhooks
  - errors

search: false
---

# Introduction
✈️ *Slydo is a new kind of payment solution for Africa*

> **API endpoint**

```
https://developer.slydo.co
```

> Examples in this documentation are written using [httpie](https://github.com/jkbrzt/httpie) for clarity.

> To install `httpie` on macOS run `brew install httpie`


Welcome to the Slydo API! Our API is designed to be a predictable and intuitive interface for interacting with our 
platform, which offers both a REST API and webhooks.


<aside class="notice">
This page is a <b>work in progress</b> - if anything seems incomplete or unclear,
please feel free to
<a href='https://github.com/ubclaunchpad/inertia/issues/new/choose'>open a ticket</a>!
</aside>


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

<aside class="warning"><strong> Strong Customer Authentication</strong><br>Please store your API key securely and avoid displaying it publicly or sharing it.</aside>
