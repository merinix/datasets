# Berlin Buildings

This zipped [shapefile](https://github.com/wbkd/datasets/blob/master/berlin-building-floors/berlin-building-floors.zip?raw=true) inlcudes buildings with their floor number and type.

### Data Attributes:

* **gml_id** (String) - Unique identifier
* **floors** (Integer) - Number of floors
* **b_type** (String) - Type of building

We converted the original shapefile with the following command to cast the floor numbers to integers and get rid of attributes we don't need:

```
$ ogr2ogr -f "ESRI Shapefile"  -t_srs crs:84 -sql "SELECT gml_id, Bezeichnung AS b_type, CAST(GESCHOSS AS integer(2)) AS floors FROM geschosse" berlin-buildings.shp geschosse.shp
```


### Source and publisher

Senatsverwaltung für Stadtentwicklung und Umwelt Berlin<br />
Fehrbelliner Platz 1, 10707 Berlin <br />
Telefon: +49-30-90139-5257 <br />
Fax: +49-30-90139-5251 <br />
E-Mail:  fisbroker@senstadtum.berlin.de<br />

**Original data source:** <br />
http://fbinter.stadt-berlin.de/fb/wfs/geometry/senstadt/re_gebgeschoss