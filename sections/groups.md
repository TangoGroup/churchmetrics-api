# Groups

Groups are organizations in Church Metrics that can manage and report against other Church Metrics accounts that are a part of their Group (ex. church plants or denominations). For more info on groups, email info@churchmetrics.com

# Available API's

## Get records

* `GET /groups/records.json` will return a list of all records
* **By default, this will return records from all churches that belong to the group. You can optionally filter by ```church_id``` or ```tag_id```**
* This call is paginated
* Data includes related campus, category, and event (if applicable)
* Optional paramaters: ```church_id```,```tag_id```, ```start_time```, ```end_time```, ```start_week```, ```end_week```, ```category_id```, ```event_id```, ```campus_id```, ```week_reference```

```json
[
  {
    "id": 2,
    "week_reference": 2392,
    "service_date_time": "2015-11-13T18: 12: 21.000Z",
    "service_timezone": "Central Time (US & Canada)",
    "value": 981.0,
    "replaces": null,
    "created_at": "2015-11-13T19: 12: 22.000Z",
    "updated_at": "2015-11-13T19: 12: 22.000Z",
    "category": {
      "id": 1,
      "name": "Attendance",
      "format": "number",
      "kind": "Attendance",
      "created_at": "2015-11-13T19: 12: 22.000Z",
      "updated_at": "2015-11-13T19: 12: 22.000Z"
    },
    "campus": {
      "id": 7,
      "slug": "EDM",
      "description": "Edmond",
      "region_id": 1,
      "timezone": "Central Time (US & Canada)",
      "active": true,
      "created_at": "2015-11-13T19: 12: 22.000Z",
      "updated_at": "2015-11-13T19: 12: 22.000Z"
    },
    "event": null
  }
]
```

## Get churches

* `GET /groups/churches.json` will return a list of all churches in a group
* This call is paginated
* Optional paramaters: ```church_id```,```tag_id```

```json
[
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
]
```

## Get tags

* `GET /groups/tags.json` will return a list of all tags in a group
* This call is paginated
* data includes a list of church ids that have that tag
* Optional paramaters: ```church_id```,```tag_id```

```json
[
  {
    "id": 1,
    "name": "Tag 1",
    "created_at": "2015-11-13T19: 26: 16.000Z",
    "updated_at": "2015-11-13T19: 26: 16.000Z",
    "churches": [1,2,3]
  },
  {
    "id": 2,
    "name": "Tag 2",
    "created_at": "2015-11-13T19: 26: 16.000Z",
    "updated_at": "2015-11-13T19: 26: 16.000Z",
    "churches": [4,5,6]
  }
]
```
