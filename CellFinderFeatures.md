# Existing Features #

These are the features that are currently in CellFinder on the Android Market. The current version is 1.3.

## 1.3 ##

Version 1.3 was released on Apr 4, 2009 with a bunch of updates:

  * Allow panning with zoom buttons enabled (thanks Jesse Lockwood!)
  * Allow starting without GPS enabled
  * Show Cell ID in two formats - long and short
  * Option to show coordinates in MGRS (Military Grid Reference System) format (courtesy of IBM - http://www.ibm.com/developerworks/java/library/j-coordconvert/)
  * Experimental data saving feature - log all location data to a file on the SD card. See CellFinderDataLogging
  * Experimental Direct Mode option - see CellFinderDirectMode

## 1.2 ##

Version 1.2 was released a few hours after 1.1 because of a major crashing bug. CellFinder would crash if started with the GPS disabled.

## 1.1 ##

Version 1.1 was released on Dec 21, 2008 with these new features:

  * Signal strength in dBm
  * Show location with only one location source - so if no GPS signal is available, CellFinder will still show cell tower location
  * Show coordinates in other formats - DD.ddddd, DD MM.mmm, and DD MM SS.ss
  * Setting to enable a compass overlay on the map. Orienting the map based on the compass was requested, but this is much easier and hopefully just as useful.
  * About box shows application version in title

## 1.0 ##

Version 1.0 was the first version of CellFinder, released on Dec 10, 2008.

  * Auto Center Map - can center on midpoint, the GPS location, the network location, or can be disabled for panning around manually
  * Auto Zoom - will automatically try to fit both locations on the map at the same time
  * Distance units - configurable to be either miles, feet, or meters
  * Location refresh - configure the time between GPS updates to a value between 0 and 120 seconds
  * Satellite view - show satellite view from Google
  * Show cell data - show information about the connected cell tower (Operator name, MCC, MNC, Cell CID, Cell LAC, Signal strength in 'asu', cell tower coordinates, GPS coordinates

# Feature Requests #

  * Other cell base station information - BCCH, BSIC, NCC, and BCC - not really sure if this is possible with the Android platform
  * Show neighboring cells - I know that the hardware has this ability, but I don't know if it's possible to get at from a userland process. The Phone app holds the only handle to the RID service that can talk directly to the GSM chipset.
  * Storing data - this is a longer term project. It would be nice if CellFinder kept a database of all cell towers it has seen and had the ability to display them on a map
  * Ensure only cell tower location is retrieved - right now, it's possible for Google to send a location that is actually a WiFi AP. This needs fixed
  * Integration with http://www.deadcellzones.com
  * Integration with various Cell ID databases (http://www.opencellid.org/, http://www.celldb.org/)

# Possible Bugs #

  * CellFinder was observed showing a cell tower location on the other side of the world, needs looked into
  * Does not show correct cell ID in 3G mode? Should be 5 digits? This needs looked into. Apparently the lowest 16 bits of the cell ID is the cell ID that T-Mobile uses internally (can't confirm this yet).