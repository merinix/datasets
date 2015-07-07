**Berlin buildings**

This shapefile inlcudes all buildings in Berlin.
Attributes:

* **gml_id** (String) - Unique identifier
* **floors** (Integer) - Number of floors
* **b_type** (String) - Type of building

We converted the original shapefile with the following command to cast the floor numbers to integers and get rid of attributes we don't need:

```
$ ogr2ogr -f "ESRI Shapefile"  -t_srs crs:84 -sql "SELECT gml_id, Bezeichnung AS b_type, CAST(GESCHOSS AS integer(2)) AS floors FROM geb" berlin-buildings.shp berlin-geschosse.shp    

```



**Source and publisher:**
Senatsverwaltung für Stadtentwicklung und Umwelt Berlin
Fehrbelliner Platz 1, 10707 Berlin 
Telefon: +49-30-90139-5257 
Fax: +49-30-90139-5251 
E-Mail:  fisbroker@senstadtum.berlin.de

**Original data source:** 
http://fbinter.stadt-berlin.de/fb/wfs/geometry/senstadt/re_gebgeschoss
