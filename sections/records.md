# Records

Records are where your data is stored. One record is stored per category, per campus, per service time.

# Available API's

- [Get records](#get-records)
- [Get record](#get-record)
- [Create record](#create-record)
- [Edit record](#edit-record)
- [Delete record](#delete-record)

## Get records

* `GET /records.json` returns a list of all records
* This call is [paginated](../README.md#pagination)
* Data includes related campus, category, and event (if applicable)
* Optional query parameters: `start_time`, `end_time`, `start_week`, `end_week`, `category_id`, `event_id`, `campus_id`, `week_reference`
* Example response:
```json
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

* `GET /records/1.json` returns the specified record
* Data includes related campus, category, and event (if applicable)
* Example response:
```json
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

## Create record

* `POST /records.json` creates a new record
* See the permitted fields for record payload in the [Editable fields](#editable-fields) section
* Example payload:
```json
{
  "category_id": 1,
  "campus_id": 1,
  "service_time_id": 1,
  "service_date_time": "2012-03-27T17:00:00Z",
  "service_timezone": "Central Time (US & Canada)",
  "value": 20,
  "replaces": true,
  "event_id": 1  
}
```
* This returns `201 Created` along with the current JSON representation of the record if creation succeeded
* `week_reference` is determined using the submitted `service_time_id` and `service_date_time`

## Edit record

* `PUT /records/1.json` updates the specified record
* See the permitted fields for record payload in the [Editable fields](#editable-fields) section
* Example payload:
```json
{
  "campus_id": 2,
  "value": 20,
}
```
* This returns `204 No Content` if the update succeeded.

## Delete record

* `DELETE /records/1.json` deletes the specified record and returns `204 No Content` if deletion succeeded

## Editable fields

The editable fields are:
- `campus_id`
- `category_id`
- `end_time`
- `end_week`
- `event_id`
- `replaces`
- `service_date_time`
- `service_time_id`
- `start_time`
- `start_week`
- `value`
- `week_reference`

These can be set in `POST` and `PUT` requests
- Any other fields are managed by ChurchMetrics, and are ignored even if included in request payload
