# File format #

If data saving is enabled in CellFinder, location data is stored on the SD card in the file `cellfinder.csv` in the root directory.

This CSV (comma separated value) file is formatted as such:

`Date, Network Operator, MCC, MNC, Cell LAC, Cell CID, Signal Strength, Location Provider, Latitude, Longitude, Altitude, Accuracy`

Data is appended to the file each time the location changes (either the GPS location or cell location).

If you have your phone plugged into a computer and the SD card is mounted, the file can't be written to, so make sure you disconnect the phone from a PC before trying to use this feature.

# Column descriptions #

Here's a brief description of each column:

  * **Date** - the date/time UTC in ISO 8601
  * **Network Operator** - the mobile carrier the phone is using
  * **MCC** - Mobile Country Code
  * **MNC** - Mobile Network Code
  * **Cell LAC** - Location Area Code
  * **Cell CID** - Cell ID
  * **Signal Strength** - signal strength in dBM
  * **Location Provider** - one of these:
    * gps - from the GPS (fine) location provider
    * network - from the Network (coarse) location provider
    * centroid - a centroid location from Google's location service
    * tower - a tower location from Google's location service
  * **Latitude** - latitude in degrees
  * **Longitude** - longitude in degrees
  * **Altitude** - altitude in meters (if available with the listed provider)
  * **Accuracy** - accuracy in meters (if available with the listed provider)

# Sample data #

Here's a sample of the data logged:

```
2009-04-05T21:30:15Z,T-Mobile,310,260,2499,7285489,-101,gps,34.050193,-84.354851,318,4
2009-04-05T21:30:17Z,T-Mobile,310,260,2499,7285489,-101,gps,34.050177,-84.354401,318,4
2009-04-05T21:30:18Z,T-Mobile,310,260,2499,7277387,-109,centroid,34.033258,-84.366072,0,2091
2009-04-05T21:30:20Z,T-Mobile,310,260,2499,7277387,-109,gps,34.050171,-84.353966,318,4
2009-04-05T21:30:20Z,T-Mobile,310,260,2499,7277387,-109,network,34.033258,-84.366072,0,2091
2009-04-05T21:30:21Z,T-Mobile,310,260,2499,7277387,-109,gps,34.050166,-84.353537,318,4
2009-04-05T21:30:24Z,T-Mobile,310,260,2499,7277387,-109,gps,34.050161,-84.353097,318,4
2009-04-05T21:30:25Z,T-Mobile,310,260,2499,7277387,-109,gps,34.050161,-84.352684,318,4
2009-04-05T21:30:27Z,T-Mobile,310,260,2499,7285489,-109,centroid,34.064429,-84.349477,0,1669
2009-04-05T21:30:27Z,T-Mobile,310,260,2499,7285489,-101,gps,34.050134,-84.352303,318,4
2009-04-05T21:30:28Z,T-Mobile,310,260,2499,7285489,-101,network,34.048844,-84.357774,0,3770
2009-04-05T21:30:29Z,T-Mobile,310,260,2499,7285489,-101,gps,34.050048,-84.351954,319,4
```