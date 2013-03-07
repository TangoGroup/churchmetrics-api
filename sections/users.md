# Users

Maecenas sed diam eget risus varius blandit sit amet non magna. Cras justo odio, dapibus ac facilisis in, egestas eget quam. Duis mollis, est non commodo luctus, nisi erat porttitor ligula, eget lacinia odio sem nec elit. Maecenas faucibus mollis interdum.

# Available API's

## Get users

* `GET /users.json` will return a list of all users
* Data includes related campus (unless they are an admin)

```
[{
  "id": 16763,
  "email": "test.user@lifechurch.tv",
  "sign_in_count": 1,
  "current_sign_in_at": "2012-08-24T19:53:44Z",
  "last_sign_in_at": "2012-08-24T19:53:44Z",
  "created_at": "2012-01-25T00:46:34Z",
  "updated_at": "2012-08-24T19:53:44Z",
  "username": "test.user",
  "timezone": "Central Time (US & Canada)",
  "role": "staff",
  "campus": {
    "id": 6,
    "slug": "EDM",
    "description": "Central",
    "street1": "4600 E. 2nd St",
    "street2": "",
    "street3": "",
    "city": "Edmond",
    "state": "OK",
    "postal_code": "73034",
    "country": "US",
    "phone": "(405) 680-5433",
    "color": "00cc00",
    "lat": 35.6533,
    "lng": -97.4216,
    "region_id": 3,
    "timezone": "Central Time (US & Canada)",
    "active": true,
    "created_at": "2012-01-25T00:14:02Z",
    "updated_at": "2012-01-25T00:14:02Z"
  }
}, {
  "id": 18342,
  "email": "test.user2@lifechurch.tv",
  "sign_in_count": 2,
  "current_sign_in_at": "2012-10-23T15:11:22Z",
  "last_sign_in_at": "2012-02-15T16:57:43Z",
  "created_at": "2012-02-15T02:36:16Z",
  "updated_at": "2012-10-23T15:11:22Z",
  "username": "test.user2",
  "timezone": "Central Time (US & Canada)",
  "role": "admin"
}]
```


## Get user

* `GET /users/1.json` will return the specified user
* Data includes related campus (unless they are an admin)

```
{
  "id": 25693,
  "email": "test@user.com",
  "sign_in_count": 5,
  "current_sign_in_at": "2013-03-04T20:23:45Z",
  "last_sign_in_at": "2013-03-04T20:23:05Z",
  "created_at": "2013-03-04T19:53:06Z",
  "updated_at": "2013-03-04T20:23:45Z",
  "username": "test.volunteer",
  "timezone": "Central Time (US & Canada)",
  "role": "volunteer",
  "campus": {
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
}
```

# API's under development

## Create user

* `POST /users.json` will create a new user

## Edit user

* `PUT /users/1.json` will update the specified user

## Delete user

* `DELETE /users/1.json` will delete the specified user