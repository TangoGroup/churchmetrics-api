# Projections

Projections are datum entered by your organization and used for comparison purposes throughout Church Metrics. 
Each projection contains a ```value```, ```category_id```, and ```campus_id```.

# Available API's

## Get projections

* `GET /projections.json` will return a list of all projections
* This call is paginated
* Data includes related campus and category
* Optional paramaters: ```category_id```, ```campus_id```, ```start_week```, ```end_week```

```json
[{
  "id": 1,
  "value": 175.0,
  "week_reference": 1878,
  "campus": {
    "id": 1,
    "slug": "FTW",
    "description": "Fort Worth",
    "region_id": 1,
    "timezone": "Central Time (US & Canada)",
    "active": true,
    "created_at": "2012-01-25T00:14:02Z",
    "updated_at": "2013-09-01T20:03:56Z"
  },
  "category": {
    "id": 1,
    "name": "Attendance",
    "format": "number",
    "created_at": "2012-01-25T00:48:01Z",
    "updated_at": "2012-01-25T00:48:01Z"
  }
}, {
  "id": 2,
  "value": 262.0,
  "week_reference": 1878,
  "campus": {
    "id": 1,
    "slug": "FTW",
    "description": "Fort Worth",
    "region_id": 1,
    "timezone": "Central Time (US & Canada)",
    "active": true,
    "created_at": "2012-01-25T00:14:02Z",
    "updated_at": "2013-09-01T20:03:56Z"
  },
  "category": {
    "id": 2,
    "name": "Contributions",
    "format": "currency",
    "created_at": "2012-01-25T00:48:03Z",
    "updated_at": "2012-01-25T00:48:03Z"
  }
}]
```

## Get projection

* `GET /projection/1.json` will return the specified projection
* Data includes related campus and category

```json
{
  "id": 1,
  "value": 262.0,
  "week_reference": 1878,
  "campus": {
    "id": 1,
    "slug": "FTW",
    "description": "Fort Worth",
    "region_id": 1,
    "timezone": "Central Time (US & Canada)",
    "active": true,
    "created_at": "2012-01-25T00:14:02Z",
    "updated_at": "2013-09-01T20:03:56Z"
  },
  "category": {
    "id": 2,
    "name": "Contributions",
    "format": "currency",
    "created_at": "2012-01-25T00:48:03Z",
    "updated_at": "2012-01-25T00:48:03Z"
  }
}
```

## Create projection

* `POST /projections.json` will create a new projection

```json
{
  "campus_id": 1,
  "category_id": 1,
  "value": 100.0,
  "week_reference": 2000
}
```

This will return ```201 Created``` along with the current JSON representation of the projection if the creation was a success.

## Edit projection

* `PUT /projections/1.json` will update the specified projection

```json
{
  "campus_id": 1,
  "category_id": 1,
  "value": 100.0,
  "week_reference": 2000
}
```

This will return ```200 OK``` if the update was a success, along with the current JSON representation of the projection in the response body.

## Delete projection

* `DELETE /projections/1.json` will delete the specified projection and return ```204 No Content``` if successful. 
