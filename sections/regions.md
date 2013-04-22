# Regions

Regions can be used to group your campuses. This is especially helpful for multi-site churches and should be used to model your church's structure.

Regions are an optional feature.

# Available API's

## Get regions

* `GET /regions.json` will return a list of all regions
* Data includes list of all campuses within each region

```
[{
  "id": 2,
  "name": "Region 1",
  "created_at": "2012-01-25T00:13:54Z",
  "updated_at": "2012-01-25T00:13:54Z",
  "campuses": [{
    "id": 15,
    "slug": "STO",
    "description": "South Tulsa",
    "region_id": 2,
    "timezone": "Central Time (US & Canada)",
    "active": true,
    "created_at": "2012-01-25T00:14:02Z",
    "updated_at": "2013-03-04T02:38:00Z"
   }
   …
  }, {
  "id": 3,
  "name": "Region 2",
  "created_at": "2012-01-25T00:13:54Z",
  "updated_at": "2012-01-25T00:13:54Z",
  "campuses": [{
    "id": 6,
    "slug": "CEN",
    "description": "Central",
    "region_id": 3,
    "timezone": "Central Time (US & Canada)",
    "active": true,
    "created_at": "2012-01-25T00:14:02Z",
    "updated_at": "2012-01-25T00:14:02Z"
  }
  … 
}]
```


## Get region

* `GET /regions/1.json` will return the specified region
* Data includes list of all campuses within the region

```
{
  "id": 3,
  "name": "Region 2",
  "created_at": "2012-01-25T00:13:54Z",
  "updated_at": "2012-01-25T00:13:54Z",
  "campuses": [{
    "id": 6,
    "slug": "CEN",
    "description": "Central",
    "region_id": 3,
    "timezone": "Central Time (US & Canada)",
    "active": true,
    "created_at": "2012-01-25T00:14:02Z",
    "updated_at": "2012-01-25T00:14:02Z"
  }
  … 
}
```

# API's under development

## Create region

* `POST /regions.json` will create a new region

## Edit region

* `PUT /regions/1.json` will update the specified region

## Delete region

* `DELETE /regions/1.json` will delete the specified region
