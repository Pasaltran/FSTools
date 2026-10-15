FiberSense Plugin Tools - version 1.0.0 (QGIS 4.0 or newer)
===========================================================

Install: QGIS > Plugins > Manage and Install Plugins > Settings > Add
  Name: FiberSense
  URL:  https://raw.githubusercontent.com/Pasaltran/FSTools/main/plugins.xml?nocache=1
Then search "FiberSense" under All and install "FiberSense Toolset".
QGIS 3 users are offered version 0.3.0.

Tools are under Plugins > FiberSense Tools and in the Processing Toolbox > FiberSense.


Heat Map Generation V3 (new in 1.0.0)
-------------------------------------
Colours a Utility layer (water, gas, ...) by its distance from a Duct / Fiber
layer, and the Duct by its distance from the Utility, in 1 m bands up to the
max offset (1-25 m). Sections beyond the max offset are drawn thin black.
Designed for national-scale networks: the utility is read once and pipes away
from the duct are not geometry-processed.
  Layers must use a projected CRS in metres (see Select Best CRS).
  Outputs: heat map layers, results table, optional GPKG/SHP (one per heat
  map), Excel results table, KMZ (requires the "KML Tools" plugin).
  "Include the whole Utility network" off = much smaller output around the duct.

Heat Map Generation (V2)
------------------------
Original heat map tool, kept unchanged for comparison with V3.

Circuit Efficiency V2
---------------------
Generates offsets for multiple circuits against a utility layer and reports
how efficiently the circuits cover it. "Detailed Efficiency" needs GRASS
(QGIS 4 on macOS does not bundle GRASS: install GRASS 8.4 into /Applications).

POI Lookup Assets
-----------------
Takes a LAT, LON point and generates a PDF map of features around the point.
  LAT, LON Coordinate: separated by a space or comma (required).
  Map Scale: 50-100 is a good start; larger numbers zoom out; minimum 10.
  Append LAT LON / Append Map Scale: add these to the output filename.
  Output PDF File: path and base file name for the PDF.

Select Best CRS
---------------
Selects the projected CRS with the least distortion for a given layer.

Circuit and Splice Builder
--------------------------
Builds and validates circuit routes and splice tables.

Thames tools
------------
Vector Subset Export by Polygon; Join DMA sections into DMA areas.
