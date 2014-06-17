# Regions

Regions can be used to group your campuses. This is especially helpful for multi-site churches and should be used to model your church's structure.

Regions are an optional feature.

# Available API's

## Get regions

* `GET /regions.json` will return a list of all regions
* Data includes list of all campus ids within each region

```json
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

```json
{
  "id": 3,
  "name": "Region 2",
  "created_at": "2012-01-25T00:13:54Z",
  "updated_at": "2012-01-25T00:13:54Z",
  "campus_ids": [1, 2, 3]
}
```

## Create region

* `POST /regions.json` will create a new region

```json
{
  "name": "East",
}
```

This will return ```201 Created``` along with the current JSON representation of the region if the creation was a success.

## Edit region

* `PUT /regions/1.json` will update the specified region

```json
{
  "name": "West"
}
```

This will return ```200 OK``` if the update was a success, along with the current JSON representation of the region in the response body.

## Delete region

* `DELETE /regions/1.json` will delete the specified region and return ```204 No Content``` if that was successful.
