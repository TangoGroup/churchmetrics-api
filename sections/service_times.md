# Service Times

Service Times are the way you tell ChurchMetrics the times you'd like to work with when entering your weekly information.

They are broken down into two groups: Regular service times and Event service times. Event service times are tied to the Events that you have added into your account.

## Service Times for Events

When creating service times for Events, the service time must have:

1. `event_id`
2. `start_date`
3. `end_date`

For instance, if you need to setup services for Easter, you would first create the Event to obtain its `event_id`. Then you would create 

If you would like records for this service time to be included in regular reports, the `replaces` field must be `true`. This feature allows you to designate primary service times and secondary times. For instance, your Easter service times would probably be included in regular reports since they would overlap with regular weekend service times. A Saturday morning prayer breakfast time may not be included in regular reports since it would be an event that does not replace a regular weekend service time.

If a service time is associated with an Event, the API will return that Event data.


# Available API's

## Get service times

* `GET /service_times.json` will return a list of all service times
* Data includes related campus and event (if applicable)
* This call is paginated
* Optional paramters: event_id

```json
[{
  "id": 43475,
  "day_of_week": 0,
  "time_of_day": "2000-01-01T16:00:00Z",
  "timezone": "Central Time (US & Canada)",
  "relation_to_sunday": "Current",
  "created_at": "2012-09-27T14:48:35Z",
  "updated_at": "2012-09-27T14:48:35Z",
  "date_start": "2012-10-14",
  "date_end": "2012-10-15",
  "replaces": false,
  "campus": {
    "id": 3,
    "slug": "NOC",
    "description": "Northwest Oklahoma City",
    "region_id": 3,
    "timezone": "Central Time (US & Canada)",
    "active": true,
    "created_at": "2012-01-25T00:14:02Z",
    "updated_at": "2013-03-03T21:12:24Z"
  },
  "event": {
    "id": 4020,
    "name": "Lifestock",
    "created_at": "2012-04-09T17:42:06Z",
    "updated_at": "2012-04-09T17:42:06Z"
  }
}, {
  "id": 22755,
  "day_of_week": 0,
  "time_of_day": "2000-01-01T18:00:00Z",
  "timezone": "Central Time (US & Canada)",
  "relation_to_sunday": "Current",
  "created_at": "2012-02-06T16:24:56Z",
  "updated_at": "2012-02-06T16:24:56Z",
  "date_start": null,
  "date_end": null,
  "replaces": null,
  "campus": {
    "id": 11,
    "slug": "SOC",
    "description": "South Oklahoma City",
    "region_id": 3,
    "timezone": "Central Time (US & Canada)",
    "active": true,
    "created_at": "2012-01-25T00:14:02Z",
    "updated_at": "2013-03-04T02:19:53Z"
  }
}]
```


## Get service time

* `GET /service_times/1.json` will return the specified service time
* Data includes related campus and event (if applicable)

```
{
  "id": 37421,
  "day_of_week": 5,
  "time_of_day": "2000-01-01T20:00:00Z",
  "timezone": "Eastern Time (US & Canada)",
  "relation_to_sunday": "Before",
  "created_at": "2012-03-22T16:17:27Z",
  "updated_at": "2012-04-02T14:41:26Z",
  "date_start": "2012-04-02",
  "date_end": "2012-04-10",
  "replaces": true,
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

## Create service time

* `POST /service_times.json` will create a new record

```json
{
  "campus_id": 1,
  "day_of_week": 0,
  "time_of_day": "2000-01-01T16:00:00Z",
  "timezone": "Central Time (US & Canada)",
  "relation_to_sunday": "Current",
  "date_start": "2012-10-14",
  "date_end": "2012-10-15",
  "replaces": false,
  "event_id": 1
}
```

This will return ```201 Created``` along with the current JSON representation of the service time if the creation was a success.

## Edit service time

* `PUT /service_times/1.json` will update the specified service time

```json
{
  "date_end": "2014-10-15",
  "replaces": true,
}
```

This will return ```200 OK``` if the update was a success, along with the current JSON representation of the service time in the response body.

## Delete service_time

* `DELETE /service_times/1.json` will delete the specified service time and return ```204 No Content``` if that was successful. 
* Removing a service_time does not remove related records because all service time information is stored with the record.
