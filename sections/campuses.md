# Campuses

ChurchMetrics allows you to enter as many campuses as you like. If you wish, you may also assign your campuses to different regions or groups.

You must have at least one campus in your account to use ChurchMetrics.

# Available API's

## Get campuses

* `GET /campuses.json` will return a list of all campuses

```
[{
  "id": 2,
  "slug": "ALB",
  "description": "Albany",
  "region_id": 2,
  "timezone": "Eastern Time (US & Canada)",
  "active": true,
  "created_at": "2012-01-25T00:14:02Z",
  "updated_at": "2013-03-04T22:09:56Z"
}, {
  "id": 6,
  "slug": "EDM",
  "description": "Edmond",
  "region_id": 3,
  "timezone": "Central Time (US & Canada)",
  "active": true,
  "created_at": "2012-01-25T00:14:02Z",
  "updated_at": "2012-01-25T00:14:02Z"
}]
```


## Get campus

* `GET /campuses/1.json` will return the specified campus

```
{
  "id": 2,
  "slug": "ALB",
  "description": "Albany",
  "region_id": 2,
  "timezone": "Eastern Time (US & Canada)",
  "active": true,
  "created_at": "2012-01-25T00:14:02Z",
  "updated_at": "2013-03-04T22:09:56Z"
}
```

# API's under development

## Create campus

* `POST /campuses.json` will create a new campus

## Edit campus

* `PUT /campuses/1.json` will update the specified campus

## Delete campus

* `DELETE /campuses/1.json` will delete the specified campus
