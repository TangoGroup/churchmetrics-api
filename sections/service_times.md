# Service Times

Maecenas sed diam eget risus varius blandit sit amet non magna. Cras justo odio, dapibus ac facilisis in, egestas eget quam. Duis mollis, est non commodo luctus, nisi erat porttitor ligula, eget lacinia odio sem nec elit. Maecenas faucibus mollis interdum.

# Available API's

## Get service times

* `GET /service_times.json` will return a list of all service times
* Data includes related campus and event (if applicable)
* This call is paginated
* Optional paramters: event_id

```
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
    "street1": "5821 NW Expressway",
    "street2": "",
    "street3": "",
    "city": "Warr Acres",
    "state": "OK",
    "postal_code": "73132",
    "country": "US",
    "phone": "405-748-5433",
    "color": "ff6600",
    "lat": 35.5489,
    "lng": -97.6172,
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
    "street1": "7800 S. Walker Ave",
    "street2": "",
    "street3": "",
    "city": "Oklahoma City",
    "state": "OK",
    "postal_code": "73139",
    "country": "US",
    "phone": "405-216-5433",
    "color": "cc0099",
    "lat": 35.3893,
    "lng": -97.5211,
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
    "street1": "560 Sand Creek Roads",
    "street2": "",
    "street3": "",
    "city": "Albany",
    "state": "NY",
    "postal_code": "12205",
    "country": "US",
    "phone": "(518) 456-0969",
    "color": "E7772D",
    "lat": 42.7244,
    "lng": -73.8223,
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

## Create service time

* `POST /service_times.json` will create a new service time

## Edit service time

* `PUT /service_times/1.json` will update the specified service time

## Delete service time

* `DELETE /service_times/1.json` will delete the specified service_time