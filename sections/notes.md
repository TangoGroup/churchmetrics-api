# Notes

Notes are optional free text comments. One note is stored per campus and
service time. On that level you can have a record for each category, but
just one note. No individual notes per category.

# Available API's

- [Get notes](#get-notes)
- [Get note](#get-note)
- [Create note](#create-note)
- [Edit note](#edit-note)
- [Delete note](#delete-note)

## Get notes

* `GET /notes.json` returns a list of all notes
* This call is [paginated](../README.md#pagination)
* Data includes related campus, and event (if applicable) TODO this is pending for fix to https://github.com/lifechurch/churchmetrics/issues/845
* Optional query parameters: `start_time`, `end_time`, `start_week`, `end_week`, `event_id` (TODO issue #845), `campus_id`, `week_reference`
* Example response:
```json
[{
  "id": 1146320,
  "created_at": "2012-03-28T16:30:01Z",
  "updated_at": "2012-03-28T16:30:01Z",
  "week_reference": 2203,
  "service_date_time": "2012-03-27T17:00:00Z",
  "service_timezone": "Central Time (US & Canada)",
  "text": "This week many visitors from other campuses",
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
  "text": "Special outreach before service",
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

## Get note

* `GET /notes/1.json` returns the specified note
* Data includes related campus, and event (if applicable)
* Example response:
```json
{
  "id": 1146321,
  "created_at": "2012-03-28T16:30:01Z",
  "updated_at": "2012-03-28T16:30:01Z",
  "week_reference": 2203,
  "service_date_time": "2012-03-27T17:00:00Z",
  "service_timezone": "Central Time (US & Canada)",
  "text": "Special outreach before service",
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
}
```

## Create note

* `POST /notes.json` creates a new note
* See the permitted fields for note payload in the [Editable fields](#editable-fields) section
* Example payload:
```json
{
  "campus_id": 1,
  "service_time_id": 1,
  "service_date_time": "2012-03-27T17:00:00Z",
  "text": "Counted by Jason",
  "event_id": 1  
}
```
* This returns `201 Created` along with the current JSON representation of the note if creation succeeded
* `week_reference` is determined using the submitted `service_time_id` and `service_date_time`

## Edit note

* `PUT /notes/1.json` updates the specified note
* See the permitted fields for note payload in the [Editable fields](#editable-fields) section
* Example payload:
```json
{
  "text": "Records have been double-checked",
}
```
* This returns `204 No Content` if the update succeeded.

## Delete note

* `DELETE /notes/1.json` deletes the specified note and returns `204 No Content` if deletion succeeded

## Editable fields

The editable fields are:
- `campus_id`
- `event_id`
- `service_date_time`
- `service_time_id`
- `text`

These can be set in `POST` and `PUT` requests
- Any other fields are managed by ChurchMetrics, and are ignored even if included in request payload
