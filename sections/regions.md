# Regions

Regions can be used to group your campuses. This is especially helpful for multi-site churches and should be used to model your church's structure.

Regions are an optional feature.

# Available API's

## Get regions

* `GET /regions.json` will return a list of all regions
* Data includes list of all campus ids within each region

```
[{
  "id": 2,
  "name": "Region 1",
  "created_at": "2012-01-25T00:13:54Z",
  "updated_at": "2012-01-25T00:13:54Z",
  "campus_ids": [1, 2, 3]
  }, {
  "id": 3,
  "name": "Region 2",
  "created_at": "2012-01-25T00:13:54Z",
  "updated_at": "2012-01-25T00:13:54Z",
  "campus_ids": [4, 5, 6]
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
  "campus_ids": [1, 2, 3]
}
```

# API's under development

## Create region

* `POST /regions.json` will create a new region

## Edit region

* `PUT /regions/1.json` will update the specified region

## Delete region

* `DELETE /regions/1.json` will delete the specified region
