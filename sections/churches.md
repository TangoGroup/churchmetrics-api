# Churches

Basic information about your church

# Available API's


## Get church

* `GET /churches/me.json` will return your church

```json
{
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
