# Events

Events are anything that you would like to track that is not tied specifically to a weekend. These could be used for special events or services (like Easter and Christmas), weekday services, conferences, Bible studies, and more.

Once you're finished adding your event, you can then create service times for this event.

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