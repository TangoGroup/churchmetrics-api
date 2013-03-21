# Categories

Categories are used to group the important data your church is tracking.

All accounts have Categories that we include by default. In addition to these default Categories you may add as many as you like.

# Available API's

## Get categories

* `GET /categories.json` will return a list of all categories

```
[{
  "id": 6,
  "name": "Attendance",
  "format": "number",
  "created_at": "2012-01-25T00:48:01Z",
  "updated_at": "2012-01-25T00:48:01Z"
}, {
  "id": 9,
  "name": "Contributions",
  "format": "currency",
  "created_at": "2012-01-25T00:48:03Z",
  "updated_at": "2012-01-25T00:48:03Z"
}]
```


## Get category

* `GET /categories/1.json` will return the specified category

```
{
  "id": 6,
  "name": "Attendance",
  "format": "number",
  "created_at": "2012-01-25T00:48:01Z",
  "updated_at": "2012-01-25T00:48:01Z"
}
```

# API's under development

## Create category

* `POST /categories.json` will create a new category

## Edit category

* `PUT /categories/1.json` will update the specified category

## Delete category

* `DELETE /categories/1.json` will delete the specified category