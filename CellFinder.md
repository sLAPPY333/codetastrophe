# About #

CellFinder is a tool for Android cell phones (currently only the T-Mobile G1) that will determine the location and direction of the cellular tower your phone is connected to.

It works by using both of the available location services - **coarse** (network-based) and **fine** (GPS-based). The coarse location is usually the location of the cell phone tower your phone is connected to, but it can also be a nearby WiFi hotspot. Because the GPS location is much more accurate and can determine your location within a matter of meters (or yards, for you yanks), it's possible to use the difference in locations to pinpoint the location and direction of the cell tower.

The cell tower location actually comes from Google - there is a web service that the location API in Android will query with the CID and LAC of the tower you're connected to and the service will respond with the latitude and longitude.

Google is constantly updating the location data returned for the network-based location service. **Since CellFinder was first written, Google no longer returns the location of the cell towers in my area! [Direct query mode](CellFinderDirectMode.md) was implemented to work around this, but even that won't return the correct tower locations.** So your mileage may very - some people report that CellFinder still works for them, others say it doesn't.

For a comprehensive list of features, feature requests, and bugs, see CellFinderFeatures.

# Known Issues #

  * **Accuracy** - Becuase the current code uses the Android location API's to get the cell tower location, it may not be accurate. The phone sends information about nearby cell towers and WiFi AP's to a location service on the web, and the response is usually the location of the cell tower you're connected to. Sometimes it is not, and this is happening with more frequency. It's possible that CellFinder won't show you tower locations at all.
  * **Waiting for signal (network)** - If you see **Waiting for signal...** for the network location (the one with the star), there is a workaround. Exit CellFinder, go into the Settings of the phone, go to Security & Location, then uncheck both **Use wireless networks** and **Enable GPS satellites**. Wait a few seconds, then re-check them. When you go back into CellFinder, it should get the CID and LAC of your tower and be able to get the location.
  * **Waiting for signal (GPS)** - If you see **Waiting for signal...** for the GPS location, the GPS can't see enough satellites to get a fix. The only way to get around this is to go somewhere with a clear view of the sky.

# Source #

The source code for CellFinder is at http://code.google.com/p/codetastrophe/source/browse/#svn/trunk/projects/cellfinder