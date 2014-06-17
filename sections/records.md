# Records

Records are where your data is stored. One record is stored per category, per campus, per service time.

# Available API's

## Get records

* `GET /records.json` will return a list of all records
* This call is paginated
* Data includes related campus, category, and event (if applicable)
* Optional paramaters: ```start_time```, ```end_time```, ```start_week```, ```end_week```, ```category_id```, ```event_id```, ```campus_id```, ```week_reference```

```
[{
  "id": 1146320,
  "created_at": "2012-03-28T16:30:01Z",
  "updated_at": "2012-03-28T16:30:01Z",
  "week_reference": 2203,
  "service_date_time": "2012-03-27T17:00:00Z",
  "service_timezone": "Central Time (US & Canada)",
  "value": 50,
  "replaces": null,
  "category": {
    "id": 9,
    "name": "Attendance - Kids",
    "format": "number",
    "created_at": "2012-01-25T00:48:03Z",
    "updated_at": "2012-01-25T00:48:03Z"
  },
  "campus": {
    "id": 4,
    "slug": "INT",
    "description": "Internet",
    "region_id": null,
    "timezone": "Central Time (US & Canada)",
    "active": true,
    "created_at": "2012-01-25T00:14:02Z",
    "updated_at": "2013-03-04T03:13:22Z"
  },
  "event": null
}, {
  "id": 1146321,
  "created_at": "2012-03-28T16:30:01Z",
  "updated_at": "2012-03-28T16:30:01Z",
  "week_reference": 2203,
  "service_date_time": "2012-03-27T17:00:00Z",
  "service_timezone": "Central Time (US & Canada)",
  "value": 20,
  "replaces": null,
  "category": {
    "id": 10,
    "name": "Baptism - Adults",
    "format": "number",
    "created_at": "2012-01-25T00:48:46Z",
    "updated_at": "2012-01-25T00:48:46Z"
  },
  "campus": {
    "id": 4,
    "slug": "INT",
    "description": "Internet",
    "timezone": "Central Time (US & Canada)",
    "active": true,
    "created_at": "2012-01-25T00:14:02Z",
    "updated_at": "2013-03-04T03:13:22Z"
  },
  "event": {
    "id": 3834,
    "name": "Easter",
    "created_at": "2012-03-21T15:09:10Z",
    "updated_at": "2012-03-21T15:09:10Z"
  }
}]
```

## Get record

* `GET /records/1.json` will return the specified record
* Data includes related campus, category, and event (if applicable)

```
{
  "id": 1146564,
  "created_at": "2012-03-28T17:54:06Z",
  "updated_at": "2012-03-28T17:54:06Z",
  "week_reference": 2202,
  "service_date_time": "2012-03-17T00:00:00Z",
  "service_timezone": "Eastern Time (US & Canada)",
  "value": 22,
  "replaces": true,
  "category": {
    "id": 6,
    "name": "Attendance",
    "format": "number",
    "created_at": "2012-01-25T00:48:01Z",
    "updated_at": "2012-01-25T00:48:01Z"
  },
  "campus": {
    "id": 2,
    "slug": "ALB",
    "description": "Albany",
    "region_id": 2,
    "timezone": "Eastern Time (US & Canada)",
    "active": true,
    "created_at": "2012-01-25T00:14:02Z",
    "updated_at": "2013-03-04T22:09:56Z"
  },
  "event": {
    "id": 3834,
    "name": "Easter",
    "created_at": "2012-03-21T15:09:10Z",
    "updated_at": "2012-03-21T15:09:10Z"
  }
}
```

# API's under development

## Create record

* `POST /records.json` will create a new record

## Edit record

* `PUT /records/1.json` will update the specified record

## Delete record

* `DELETE /records/1.json` will delete the specified record
