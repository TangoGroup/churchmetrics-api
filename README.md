# Church Metrics API

This is a REST-style API that uses JSON for serialization.

## Making a request

All URLs start with `https://churchmetrics.com/api/v1/`. **SSL only**. The path is prefixed with "api" and the API version. If we change the API in backward-incompatible ways, we'll bump the version marker and maintain stable support for the old URLs.

To make a request for all the users on your account, you'd append the projects index path to the base url to form something like `https://churchmetrics.com/api/v1/users.json`. In curl, that looks like:

```
curl -H "X-Auth-User: jdoe@church.com" -H "X-Auth-Key: a86850deb2742ec3cb41518e26aa2d89" https://churchmetrics.com/api/v1/users.json
```

To create something, it's the same deal except you also have to include the `Content-Type` header and the JSON data:

```
curl -H 'Content-Type: application/json' \
  -H "X-Auth-User: jdoe@church.com" \
  -H "X-Auth-Key: a86850deb2742ec3cb41518e26aa2d89" \
  -d '{ "value": "36" }' \
  https://churchmetrics.com/api/v1/records.json
```

That's all!

## Authentication

All requests are made by passing two header values: `X-Auth-User` and `X-Auth-Key`. The first is your email address, and the second is your personal API key. This key can be found on your personal profile page. This is secure since all requests use SSL.

**NOTE: Only "admin" accounts have API keys and can access the API.**


## No XML, just JSON

We only support JSON for serialization of data. Our format is to have no root element and we use snake\_case to describe attribute keys. This means that you have to send `Content-Type: application/json; charset=utf-8` when you're POSTing or PUTing data into ChurchMetrics. **All API URLs end in .json to indicate that they accept and return JSON.**

You'll receive a `415 Unsupported Media Type` response code if you attempt to use a different URL suffix or leave out the `Content-Type` header.

## Handling Errors

If ChurchMetrics is having trouble, you might see a 5xx error. `500` means that the app is entirely down, but you might also see `502 Bad Gateway`, `503 Service Unavailable`, or `504 Gateway Timeout`. It's your responsibility in all of these cases to retry your request later. 

## Parameters

Many API methods take optional parameters. For GET requests, any parameters not specified as a segment in the path can be passed as an HTTP query string parameter:

    $ curl -i "https://churchmetrics.com/api/v1/records.json?campus_id=2"
    
For POST requests, parameters not included in the URL should be encoded as JSON with a Content-Type of ‘application/json’.

## Pagination

Requests that return multiple items will be paginated to 30 items by default. You can specify further pages with the `?page` parameter. For some resources, you can also set a custom page size up to 100 with the `?per_page` parameter. 

    $ curl https://churchmetrics.com/api/v1/records.json?page=2&per_page=100
    

The pagination info is included in the [Link header](http://tools.ietf.org/html/rfc5988). It is important to follow these Link header values instead of constructing your own URLs. In some instances, pagination is based on SHA1 and not on page number.

	Link: <https://churchmetrics.com/api/v1/records.json?page=3&per_page=100>; rel="next",<https://churchmetrics.com/api/v1/records.json?page=50&per_page=100>; rel="last"
    
The possible `rel` values are:

`next`

Shows the URL of the immediate next page of results.

`last`

Shows the URL of the last page of results.

`first`

Shows the URL of the first page of results.

`prev`

Shows the URL of the immediate previous page of results.

## Rate Limiting

We limit requests to 5,000 per hour. You can check the returned HTTP headers of any API request to see your current status:

If you reach your limit, the server will return an error of ```403 Forbidden (Rate Limit Exceeded)```.

## Help us make it better

Please tell us how we can make the API better. If you have a specific feature request or if you found a bug, please use GitHub issues. Fork these docs and send a pull request with improvements.

To talk with us about the API, please contact us via our [help page](https://digeratiteam.zendesk.com/anonymous_requests/new).
