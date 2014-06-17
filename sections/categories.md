# Categories

Categories are used to group the important data your church is tracking.

* All accounts have Categories that we include by default. 
* In addition to these default Categories you may add as many as you like.
* ```kind``` can be of these different values: "Attendance", "Contributions", "Salvations", or "Other"

# Available API's

## Get categories

* `GET /categories.json` will return a list of all categories

```json
[{
  "id": 6,
  "name": "Attendance",
  "format": "number",
  "kind": "Attendance",
  "created_at": "2012-01-25T00:48:01Z",
  "updated_at": "2012-01-25T00:48:01Z"
}, {
  "id": 9,
  "name": "Contributions",
  "format": "currency",
  "kind": "Attendance",
  "created_at": "2012-01-25T00:48:03Z",
  "updated_at": "2012-01-25T00:48:03Z"
}]
```


## Get category

* `GET /categories/1.json` will return the specified category

```json
{
  "id": 6,
  "name": "Attendance",
  "format": "number",
  "kind": "Attendance",
  "created_at": "2012-01-25T00:48:01Z",
  "updated_at": "2012-01-25T00:48:01Z"
}
```

## Create category

* `POST /categories.json` will create a new category

```json
{
  "name": "Attendance",
  "format": "number",
  "kind": "Attendance"
}
```

This will return ```201 Created``` along with the current JSON representation of the category if the creation was a success.


## Edit category

* `PUT /categories/1.json` will update the specified category

```json
{
  "name": "Attendance",
  "format": "number",
  "kind": "Attendance"
}
```

This will return ```200 OK``` if the update was a success, along with the current JSON representation of the category in the response body.

## Delete category

* `DELETE /categories/1.json` will delete the specified category and return ```204 No Content``` if successful.
* _WARNING_: Deleting categories will remove all related Records.
