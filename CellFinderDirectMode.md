CellFinder's Direct Query Mode was added to solve some "problems" with Google's network location services. It mostly failed at solving these problems.

## The network location service ##

When CellFinder was first developed, the location returned by the network location service (also known as the coarse location provider) was almost always the exact location of the cell tower I was connected to. I could zoom in on the satellite view and see the tower at those coordinates. That's what motivated me to develop CellFinder.

The network location service works by having your phone send the CID and LAC of the tower your phone is connected to to a server at Google. It also sends information on neighboring cells and cells your phone were recently connected to. It can also send data on WiFi AP's your phone sees. Google uses all of this data to determine an approximate location for you.

Google has now been enhancing the network location service to be more accurate - it takes more data into account to give you a more accurate location for you based on the current cell, neighboring cells, signal strength, etc. This means that CellFinder no longer reports the cell tower location in some areas - maybe even most areas. Google can return a bunch of different locations for you when your phone is connected to the same tower - because the location isn't just based on that tower.

## Direct query mode ##

Direct Query mode solves a couple of the issues with the built-in API for accessing the network location service:

  1. WiFi networks aren't taken into account
  1. Neighboring cells aren't taken into account

Direct query mode sends Google's location server a single CID and LAC to determine the tower location.

Even this doesn't solve the problem - the location still isn't the exact location of the tower. The location is actually the centroid for the tower's coverage area. Sometimes the centroid is the same location of the tower, but in many cases it is not because the centroid is affected by the landscape and various issues with the antennas themselves.

When direct query mode is enabled, the location legend will say **centroid** instead of **network** when CellFinder knows that the location is the centroid. It's also possible to display **tower** if Google's data indicates that the location is a tower. I haven't seen it say that so I don't know if the location servers ever return with tower locations.