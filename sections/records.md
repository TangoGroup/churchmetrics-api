# Records

Maecenas sed diam eget risus varius blandit sit amet non magna. Cras justo odio, dapibus ac facilisis in, egestas eget quam. Duis mollis, est non commodo luctus, nisi erat porttitor ligula, eget lacinia odio sem nec elit. Maecenas faucibus mollis interdum.

# API's under development

## Get records

* `GET /records.json` will return a list of all records
* This call is paginated
* Optional paramaters: start_date, end_date, category_id, event_id, week_reference


## Get record

* `GET /records/1.json` will return the specified record


## Create record

* `POST /records.json` will create a new record

## Edit record

* `PUT /records/1.json` will update the specified record

## Delete record

* `DELETE /records/1.json` will delete the specified record