## Follow along at: [https://bondah.github.io/qgis2018](https://bondah.github.io/qgis2018)

# Objective
In this tutorial we will learn:
* how to add data to QGIS
* how to edit and analyze data in QGIS
* how to visualize data in QGIS

We will touch on various improvements found in QGIS version 3.0-3.2.

# What data will we use?
We are using GIS data from (exercise data is in the data folder):
* LA County: [LA County Boundaries](https://data.lacounty.gov/GIS-Data/County-Boundaries/pihd-kqzs)
* OpenStreetMap:
* National Park Service: [National Park Units](https://public-nps.opendata.arcgis.com/datasets/national-park-service-park-unit-boundaries/geoservice)

# Scope
We aren't going to go in-depth, but we will cover basic usage while highlighting new features.

# Code snippets
Intersection of tracts and rivers:
```sql
SELECT rivers.gnis_name as rivers, count(*) as tracts
	FROM rivers, tracts
	WHERE ST_Intersects(rivers.geom, tracts.geom)
	GROUP BY rivers
  ORDER BY rivers;
```
