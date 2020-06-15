<aside class="notice">
You must replace <code>$access_token</code> with your personal API key.
</aside>

# Webhooks

## Registering a Webhook

```shell
$ http POST "https://developer.slydo.co/api/v1/webhook/" \
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

This endpoint retrieves all webhooks.

### HTTP Request

`GET https://developer.slydo.co/api/v1/webhook/`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -------------
amount | true | If set to true, the result will also include cats.
currency | true | If set to true, the result will also include cats.
description | true | If set to true, the result will also include cats.
short description | true | If set to true, the result will also include cats.
note | true | If set to true, the result will also include cats.
category | true | If set to true, the result will also include cats.





<aside class="success">
Remember — a happy webhook is an authenticated webhook!
</aside>

## List webhook

```shell
curl "https://developer.slydo.co/api/v1/webhook/"
  -H "Authorization: $access_token"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all webhooks.

### HTTP Request

`GET https://developer.slydo.co/api/v1/webhook/`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include webhooks that have already been adopted.

<aside class="success">
Remember — a happy webhook is an authenticated webhook!
</aside>

## Retrieve transaction

```shell
curl "https://developer.slydo.co/api/v1/webhook//2"
  -H "Authorization: $access_token"
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

This endpoint retrieves a specific webhook.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET https://developer.slydo.co/api/v1/webhooks/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the webhook to retrieve

## Delete transaction

```shell
curl "https://developer.slydo.co/api/v1/webhook//2"
  -X DELETE
  -H "Authorization: $access_token"
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific webhook.

### HTTP Request

`DELETE https://developer.slydo.co/api/v1/webhook/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the webhook to delete
