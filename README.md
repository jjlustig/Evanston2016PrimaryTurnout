# Evanston2016PrimaryTurnout
Data Available at https://data.cityofevanston.org/ 

Visualization Available at https://jjlustig.github.io/Evanston2016PrimaryTurnouts/

# Sample commands to parse through data #
```bash 

#Converts Shp files to GeoJson
ogr2ogr -f GeoJSON build/evanston.json build/Precincts/geo_export_6bb336c6-7ecd-45cf-8f19-69685f6b3170.shp -clipsrc -87.7324, 42.0191, -87.6650, 42.0718

#Converts Shp files to TopoJson
node_modules/topojson/bin/topojson -o build/topo-evanston.json --id-property='precinct,precinct' --external-properties='Presidential_Primary_Turnout_2016.csv' --properties="precinct=precinct,RegisteredVoters=+RegisteredVoters,BallotsCast=+BallotsCast" --projection='d3.geo.mercator().scale(400000).center([-87.6866, 42.0566])' build/evanston.json 


```
