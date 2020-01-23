# afu_nabodat_dataimport

```
docker run --rm --name edit-db -p 54321:5432 --hostname primary \
-e PG_DATABASE=edit -e PG_LOCALE=de_CH.UTF-8 -e PG_PRIMARY_PORT=5432 -e PG_MODE=primary \
-e PG_USER=admin -e PG_PASSWORD=admin \
-e PG_PRIMARY_USER=repl -e PG_PRIMARY_PASSWORD=repl \
-e PG_ROOT_PASSWORD=secret \
-e PG_WRITE_USER=gretl -e PG_WRITE_PASSWORD=gretl \
-e PG_READ_USER=ogc_server -e PG_READ_PASSWORD=ogc_server \
sogis/oereb-db:latest
```

```
java -jar /Users/stefan/apps/ili2pg-4.3.2/ili2pg-4.3.2.jar --dbhost localhost --dbport 54321 --dbdatabase edit --dbusr admin --dbpwd admin \
--dbschema afu_nabodat --models "NABODAT_ErgebnisseBodenbelastung_Punktdaten_LV95_V1_1;ErgebnisseBodenbelastung_Punktdaten_Codelisten_V1_1" \
--defaultSrsCode 2056 --strokeArcs --createGeomIdx --createFk --createFkIdx --createEnumTabs \
--beautifyEnumDispName --createMetaInfo --createUnique --createNumChecks --nameByTopic \
--createTidCol \
--modeldir "http://models.geo.admin.ch;." --schemaimport 


java -jar /Users/stefan/apps/ili2pg-4.3.2/ili2pg-4.3.2.jar --dbhost localhost --dbport 54321 --dbdatabase edit --dbusr admin --dbpwd admin \
--dbschema afu_nabodat --models ErgebnisseBodenbelastung_Punktdaten_Codelisten_V1_1 \
--importTid \
--modeldir "http://models.geo.admin.ch;." --import NABODAT_ErgebnisseBodenbelastung_Punktdaten_Codelisten_Analysedaten_V1_1.xml

java -jar /Users/stefan/apps/ili2pg-4.3.2/ili2pg-4.3.2.jar --dbhost localhost --dbport 54321 --dbdatabase edit --dbusr admin --dbpwd admin \
--dbschema afu_nabodat --models ErgebnisseBodenbelastung_Punktdaten_Codelisten_V1_1 \
--importTid \
--modeldir "http://models.geo.admin.ch;." --import NABODAT_ErgebnisseBodenbelastung_Punktdaten_Codelisten_Analyseparameter_V1_1.xml

java -jar /Users/stefan/apps/ili2pg-4.3.2/ili2pg-4.3.2.jar --dbhost localhost --dbport 54321 --dbdatabase edit --dbusr admin --dbpwd admin \
--dbschema afu_nabodat --models ErgebnisseBodenbelastung_Punktdaten_Codelisten_V1_1 \
--importTid \
--modeldir "http://models.geo.admin.ch;." --import NABODAT_ErgebnisseBodenbelastung_Punktdaten_Codelisten_Profildaten_V1_1.xml

java -jar /Users/stefan/apps/ili2pg-4.3.2/ili2pg-4.3.2.jar --dbhost localhost --dbport 54321 --dbdatabase edit --dbusr admin --dbpwd admin \
--dbschema afu_nabodat --models ErgebnisseBodenbelastung_Punktdaten_Codelisten_V1_1 \
--importTid \
--modeldir "http://models.geo.admin.ch;." --import NABODAT_ErgebnisseBodenbelastung_Punktdaten_Codelisten_Projektstandort_V1_1.xml

java -jar /Users/stefan/apps/ili2pg-4.3.2/ili2pg-4.3.2.jar --dbhost localhost --dbport 54321 --dbdatabase edit --dbusr admin --dbpwd admin \
--dbschema afu_nabodat --models NABODAT_ErgebnisseBodenbelastung_Punktdaten_LV95_V1_1 \
--importTid \
--disableValidation \
--modeldir "http://models.geo.admin.ch;." --import NABODAT_ErgebnisseBodenbelastung_Punktdaten_LV95_V1_1-20191212T172539.xtf
```