# Geocoder

This is a Django app that lets you load Ordnance Survey data and use it to find places.

A list of `Places` from the Ordnance Survey is stored in a spatial database, and a url is provided to query them by name and return a JSON response containing matching places. Useful for autocompleting inputs that take town, city or road names.

In addition, the places are filtered by a series of bounding boxes, so that only places within the supplied boxes are returned.


## Prerequisites
* A [[GeoDjango][https://docs.djangoproject.com/en/dev/ref/contrib/gis/tutorial/#introduction] project (Note, this has only been tested with Django 1.4.5 and a PostGIS database)


## Installation
1. Add `geocoder` to your `INSTALLED_APPS` list in settings.py
2. Import the geocoder ajax url into your project's urls.py
3. Set `GEOCODER_BOUNDING_BOXES` to include one or more bounding boxes
3. Run `python manage.py syncdb`
4. Restart your web server, if necessary.


## Data

http://www.ordnancesurvey.co.uk/oswebsite/products/os-opendata.html

The Ordnance Survey make large data sets available under an open license. See the url above for more details. This app uses the OS Locator and 1:50k Gazetteer.


## Importing data

- Download the data from the Ordnance Survey website.
- Set the `GEOCODER_BOUNDING_BOXES` entry in your `settings.py`.
- Import the data using one of the import management commands, the path to the data file is the only argument.


## Licensing

Anywhere you make use of the data from the OS you should display the following text:

> Contains Ordnance Survey data © Crown copyright and database right 2013

See the [OS OpenData Licensing](http://www.ordnancesurvey.co.uk/oswebsite/opendata/licensing.html) page for more details.
