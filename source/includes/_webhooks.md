<aside class="notice">
You must replace <code>$access_token</code> with your personal API key.
</aside>

# Webhooks

**Receive event notifications from Slydo with webhooks**

**__Listen for events on your Slydo account so that your integrations can automatically react.__**


Slydo uses webhooks to notify your application about events happening in your Slydo account. 
Webhooks are really useful for asynchronous events like when a payment was made into your account or 
when a customer rejects your payment request.


**Using webhooks with your Slydo integration in just two steps:**

1. Create a webhook endpoint on your server/service.
1. Register the endpoint with Slydo to go live.


<aside class="notice">
Not all Slydo integrations require webhooks. Keep reading to learn more about what webhooks 
are and when you should use them.
</aside>


**What are webhooks**

Webhooks are one of a few ways that web applications can send automated messages or information to one another. 
It allows you to send real-time data from one application to another whenever a given event occurs.

**When to use webhooks**

Webhooks can be used if you need to know when the state of an object in your Slydo account changes so 
that your integration can take necessary actions in your application.

The specific actions your webhook endpoint may take differs based upon the event. Some current event your 
integrations may listen to are:

* Payment Request Created
* Payment Request Rejected
* Payment Request Accepted
* Payment Received


Webhooks can also be used to provide state and API responses to services or systems that use Slydo data for 
things like replication, analytics, or alerting.


## Registering a Webhook

After building, testing, and deploying your webhook to production, set up the endpoint so that Slydo knows 
where to send events changes. It’s also helpful to go through the development checklist to ensure a smooth 
transition when taking your integration live.

**Add your webhook endpoint to your account**

Webhook endpoints are configured in the Dashboard’s Webhooks settings page or programmatically using webhook endpoints.

**Add endpoints in the Dashboard**

In the Dashboard’s Webhooks settings section, click Add endpoint to reveal a form to add a new endpoint for 
receiving events. You can enter any URL as the destination for events. 
You can choose to be notified of all event types, or only specific ones from the event list. 
You can find a full list of all event types in the API docs.

**Add endpoints with the API**

You can also programmatically create webhook endpoints. As with the form in the Dashboard, 
you can enter any URL as the destination for events and which event types to subscribe to. 


```shell script
http -f POST "https://api.slydo.co/v1/webhook/" \
  event=payment-received \
  url=https://example.com/webhook/process-payment-received
```


> The above command returns JSON structured like this:

```json
{
    "id": "payment-received",
    "event": "payment-received",
    "url": "https://example.com/webhook/process-payment-received"
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
