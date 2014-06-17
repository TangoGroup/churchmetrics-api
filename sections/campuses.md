# Campuses

ChurchMetrics allows you to enter as many campuses as you like. If you wish, you may also assign your campuses to different regions or groups.

You must have at least one campus in your account to use ChurchMetrics.

# Available API's

## Get campuses

* `GET /campuses.json` will return a list of all campuses

```json
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

```json
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

## Get weekly totals

* `GET /campuses/1/weekly_totals.json`
* Required parameters: ```category_id```
* Optional parameters: ```week_reference``` (defaults to current week)

```json
{
  "campus": {
    "id": 1,
    "slug": "OKC",
    "description": "Oklahoma City",
    "region_id": 1,
    "timezone": "Central Time (US & Canada)",
    "active": true,
    "created_at": "2012-01-25T00:14:02Z",
    "updated_at": "2013-05-06T00:14:48Z"
  },
  "category": {
    "id": 1,
    "name": "Attendance",
    "format": "number",
    "created_at": "2012-01-25T00:48:01Z",
    "updated_at": "2012-01-25T00:48:01Z"
  },
  "services_reporting": "7/7",
  "total": "1.7K",
  "percent_change": "2%"
}
```

## Create campus

* `POST /campuses.json` will create a new campus

```json
{
  "slug": "OKC",
  "description": "Oklahoma City",
  "timezone": "Central Time (US & Canada)",
  "active": true,
  "region_id": 1
}
```

This will return ```201 Created``` along with the current JSON representation of the campus if the creation was a success.

## Edit campus

* `PUT /campuses/1.json` will update the specified campus

```json
{
  "slug": "OKC",
  "description": "Oklahoma City"
}
```

This will return 200 OK if the update was a success, along with the current JSON representation of the campus.

## Delete campus

* `DELETE /campuses/1.json` will delete the specified campus and return ```204 No Content``` if successful.
