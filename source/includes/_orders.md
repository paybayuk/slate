<aside class="notice">
You must replace <code>$access_token</code> with your personal API key.
</aside>

# Orders

## List orders

```shell
curl "https://developer.slydo.co/api/v1/orders/"
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

This endpoint retrieves all Orders.

### HTTP Request

`GET https://developer.slydo.co/api/v1/orders/`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include Orders that have already been adopted.

<aside class="success">
Remember — a happy Orders is an authenticated Orders!
</aside>

## Retrieve orders

```shell
curl "https://developer.slydo.co/api/v1/orders/2"
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

This endpoint retrieves a specific Orders.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET https://developer.slydo.co/Orders/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Orders to retrieve

## Delete orders

```shell
curl "https://developer.slydo.co/api/v1/orders/2"
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

This endpoint deletes a specific Orders.

### HTTP Request

`DELETE https://developer.slydo.co/api/v1/orders/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Orders to delete
