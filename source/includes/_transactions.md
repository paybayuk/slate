# Transactions

Transactions are movements of funds into or out of an account.

Most properties on transactions are self-explanatory. We'll eventually get around to documenting them all, but in the 
meantime let's discuss the most interesting/confusing ones:

<aside class="warning"><strong>Security Warning</strong><br>
Please note that an insecurely stored API Key will result in abuse of the transaction endpoints.
</aside>


## Make Payment

```shell
$ http POST "https://developer.slydo.co/api/v1/transactions/create/" \
  -H "Authorization: Token $access_token" \
   # ... JSON Payment data ...
```

```json
{
    "amount": "1000",
    "currency": "NGN",
    "description": "Weekend shopping at my local shopping center",
    "short description": "Weekly shopping",
    "note": "Weekly Shopping",
    "category": "Shopping"
  }
```

> The above command returns JSON structured like this:

```json
{
    "id": "98564bac-5a94-4253-a442-1cf04beb13d3"
  }
```

This endpoint creates a single transaction(ie: send payment to another user).

### HTTP Request

`POST https://developer.slydo.co/api/v1/transactions/create/`

### Query Parameters

Parameter | Required | Type | Description
--------- | ------- | ------- | -------------
amount | true | int |If set to true, the result will also include cats.
currency | true | string | If set to true, the result will also include cats.
description | true | string | If set to true, the result will also include cats.
short description | true |string | If set to true, the result will also include cats.
note | true | string | If set to true, the result will also include cats.
category | true | string | If set to true, the result will also include cats.
to_customer | true | string | The username of the user to send the money to.


## List transactions

Returns a list of transactions.

```shell
GET "https://developer.slydo.co/api/v1/transactions/list/"
  -H "Authorization: $access_token"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": "98564bac-5a94-4253-a442-1cf04beb1300",
    "from_customer": "tobi.alade", 
    "to_customer": "agege.puffpuff", 
    "currency": "NGN", 
    "amount": 1000,
    "status": "Paid", 
    "category": "Food", 
    "slug": null, 
    "notes": "Hot Puff Puff",
    "short_description": "Hot and smoking Puff Puff",
    "description": "Hot and smoking Puff Puff, with sugar and vanilla.", 
    "settled_at": "2020-11-14T21:27:15.898206Z", 
    "created_at": "2020-11-16T12:18:42.589594Z", 
    "from_customer_avatar": "https://media.slydo.co/avatar/3ab17549781a43108d60ba56a4e5919b.jpg", 
    "to_customer_avatar": "https://media.slydo.co/avatar/2aa4fdf91ca147cb824f3280ab2fa3b9.jpg"
  },
  {
    "id": "98564bac-5a94-4253-a442-1cf04beb13d3",
    "from_customer": "tobi.alade", 
    "to_customer": "agege.puffpuff", 
    "currency": "NGN", 
    "amount": 500,
    "status": "Paid", 
    "category": "Food", 
    "slug": null, 
    "notes": "Hot Puff Puff",
    "short_description": "Hot and smoking Puff Puff",
    "description": "Hot and smoking Puff Puff, with sugar and vanilla.", 
    "settled_at": "2020-12-14T21:27:15.898206Z", 
    "created_at": "2020-12-16T12:18:42.589594Z", 
    "from_customer_avatar": "https://media.slydo.co/avatar/3ab17549781a43108d60ba56a4e5919b.jpg", 
    "to_customer_avatar": "https://media.slydo.co/avatar/2aa4fdf91ca147cb824f3280ab2fa3b9.jpg"
  }
]
```

### HTTP Request

`GET https://developer.slydo.co/api/v1/transactions/list/`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
all | true | If set to true, the result will include both sent and received transactions.
received | false | If set to true, the result will only include received transactions.
sent | true | If set to false, the result will only include sent transactions.


## Retrieve transaction

Returns an individual transaction, fetched by its id.

```shell
GET "https://developer.slydo.co/api/v1/transactions/<ID>/"
  -H "Authorization: $access_token"
```

> The above command returns JSON structured like this:

```json
{
  "id": "98564bac-5a94-4253-a442-1cf04beb13d3",
  "from_customer": "tobi.alade", 
  "to_customer": "agege.puffpuff", 
  "currency": "NGN", 
  "amount": 1000,
  "status": "Paid", 
  "category": "Food", 
  "slug": null, 
  "notes": "Hot Puff Puff",
  "short_description": "Hot and smoking Puff Puff",
  "description": "Hot and smoking Puff Puff, with sugar and vanilla.", 
  "settled_at": "2020-11-14T21:27:15.898206Z", 
  "created_at": "2020-11-16T12:18:42.589594Z", 
  "from_customer_avatar": "https://media.slydo.co/avatar/3ab17549781a43108d60ba56a4e5919b.jpg", 
  "to_customer_avatar": "https://media.slydo.co/avatar/2aa4fdf91ca147cb824f3280ab2fa3b9.jpg"
}
```

### HTTP Request

`GET https://developer.slydo.co/transactions/<ID>/`
