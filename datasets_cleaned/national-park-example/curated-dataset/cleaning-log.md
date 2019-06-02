# Cleaning Log

### BCGlacierNationalParkWildlifeMortality1959-2017.csv
#### https://open.canada.ca/data/en/dataset/522ee7d2-4cf3-4c84-a55b-b03491ad62b0


Removed obervations of 'Poached' or 'Destroyed'

Changed Date format to YYYY-MM-DD

Changed Park abbreviation 'GNP' to 'Glacier National Park'

Removed oberservations with no coordinates

Converted coordinates from UTM to Latitude and Longitude using ArcGIS

GBIF identifier added to each record

Rename column headers:


Park renamed to location
Latitude renamed to decimalLatitude
Longitude renamed to decimalLongitude
Mortality Date renamed to eventDate
Species renamed to vernacularName
GBIF renamed to taxonID
Total Animals renamed to individualCount
Adult Female renamed to femaleAdult
Sex renamed to sex
Age_Class renamed to lifeStage
Mortality Type renamed to mortalityType
Original formatted date renamed to dateOriginal
Easting renamed to easting
Northing renamed to northing
