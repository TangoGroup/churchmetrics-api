# Churches

Basic information about your church

# Available API's


## Get campus

* `GET /campuses/me.json` will return your church

```json
{
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
}
```

## Get weekly_totals

* `GET /churches/weekly_totals.json`
* Required parameters: ```category_id```
* Optional parameters: ```week_reference``` (defaults to current week)

```json
{
  "church": {
    "id": 1,
    "name": "Your Church",
    "currency": "usd",
    "street": "4600 E. 2nd Street",
    "city": "Edmond",
    "state": "OK",
    "postal_code": "73034",
    "country": "USA",
    "phone": "406-680-5433",
    "created_at": "2012-01-25T00:13:47Z",
    "updated_at": "2013-05-06T03:24:05Z"
  },
  "category": {
    "id": 1,
    "name": "Attendance",
    "format": "number",
    "created_at": "2012-01-25T00:48:01Z",
    "updated_at": "2012-01-25T00:48:01Z"
  },
  "services_reporting": "103/144",
  "this_week": {
    "reported": "1,758",
    "total": "2,141"
  },
  "last_week": {
    "reported": "1,608",
    "total": "1,975"
  },
  "last_year": {
    "reported": "1,911",
    "total": "2,216"
  }
}
```

# API's under development


## Edit church

* `PUT /churches/me.json` will update your church
