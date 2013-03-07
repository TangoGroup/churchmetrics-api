# Regions

Maecenas sed diam eget risus varius blandit sit amet non magna. Cras justo odio, dapibus ac facilisis in, egestas eget quam. Duis mollis, est non commodo luctus, nisi erat porttitor ligula, eget lacinia odio sem nec elit. Maecenas faucibus mollis interdum.

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
    "street1": "Bixby North Elementary",
    "street2": "7101 East 121st St S",
    "street3": "",
    "city": "Bixby",
    "state": "OK",
    "postal_code": "74008",
    "country": "US",
    "phone": "(918) 938-0900",
    "color": "ffe500",
    "lat": 35.9506,
    "lng": -95.8771,
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