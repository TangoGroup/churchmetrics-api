# Users

Users on your account can be assigned to a role and campus. 

## Roles

### Admins

Admins have full access to all data and settings for the account. If the user is assigned the "admin" role, they will not be assigned to any campus.

### Staff

Staff users are assigned to a particular campus. They can input data for up to 6 days after the service time. They do not have access to Church settings.

### Volunteer

Volunteers are assigned to a particular campus. They can only input data for a service time on the day of the actual service time. They only have access to the "Input" page -- not Church settings, dashboards, charts, or anything else.


# Available API's

## Get users

* `GET /users.json` will return a list of all users
* Data includes related campus (unless they are an admin)

```json
[{
  "id": 16763,
  "email": "test.user@lifechurch.tv",
  "created_at": "2012-01-25T00:46:34Z",
  "updated_at": "2012-08-24T19:53:44Z",
  "name": "test.user",
  "timezone": "Central Time (US & Canada)",
  "role": "staff",
  "campus_id": 6
}, {
  "id": 18342,
  "email": "test.user2@lifechurch.tv",
  "created_at": "2012-02-15T02:36:16Z",
  "updated_at": "2012-10-23T15:11:22Z",
  "name": "test.user2",
  "timezone": "Central Time (US & Canada)",
  "role": "admin"
}]
```


## Get user

* `GET /users/1.json` will return the specified user
* Data includes related campus (unless they are an admin)

```json
{
  "id": 25693,
  "email": "test@user.com",
  "created_at": "2013-03-04T19:53:06Z",
  "updated_at": "2013-03-04T20:23:45Z",
  "name": "test.volunteer",
  "timezone": "Central Time (US & Canada)",
  "role": "volunteer",
  "campus_id": 2
}
```

## Create user

* `POST /users.json` will create a new user

```json
{
  "email": "joe@schmoe.com",
  "locale": "en",
  "role": {
    "volunteer"
  },
  "campus": {
    "id": 1
  }
}
```

This will return ```201 Created``` along with the current JSON representation of the user if the creation was a success.

## Edit user

* `PUT /users/1.json` will update the specified user

```json
{
  "campus": {
    "id": 2
  }
}
```

This will return ```200 OK``` if the update was a success, along with the current JSON representation of the user in the response body.

## Delete user

* `DELETE /users/1.json` will remove the specified user from your church and return ```204 No Content``` if that was successful. 
