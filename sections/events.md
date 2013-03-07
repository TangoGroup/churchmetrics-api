# Events

Maecenas sed diam eget risus varius blandit sit amet non magna. Cras justo odio, dapibus ac facilisis in, egestas eget quam. Duis mollis, est non commodo luctus, nisi erat porttitor ligula, eget lacinia odio sem nec elit. Maecenas faucibus mollis interdum.

# Available API's

## Get events

* `GET /events.json` will return a list of all events

```
[{
  "id": 3834,
  "name": "Easter",
  "created_at": "2012-03-21T15:09:10Z",
  "updated_at": "2012-03-21T15:09:10Z"
}, {
  "id": 4020,
  "name": "Lifestock",
  "created_at": "2012-04-09T17:42:06Z",
  "updated_at": "2012-04-09T17:42:06Z"
}]
```


## Get event

* `GET /events/1.json` will return the specified event

```
{
  "id": 3834,
  "name": "Easter",
  "created_at": "2012-03-21T15:09:10Z",
  "updated_at": "2012-03-21T15:09:10Z"
}
```

# API's under development

## Create event

* `POST /events.json` will create a new event

## Edit event

* `PUT /events/1.json` will update the specified event

## Delete event

* `DELETE /events/1.json` will delete the specified event