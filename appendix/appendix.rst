********
Appendix
********

Known Issues and Bugs
=====================

* ArcGIS generates a ‘hard error’ when the HLU GIS Tool is used.

	* Solution 1:	The HLU ArcMap extension has not been enabled. Close and relaunch the tool, then enable the extension in ArcMap before using the toolkit.
	* Solution 2: 	ArcGIS has been closed while the tool was running. Close and relaunch the tool.

* The HLU GIS Tool stops responding to GIS requests.

	* Solution 1: The HLU GIS layer is no longer active in the map or MapInfo has been closed while the tool was running. Close and relaunch the tool.

* The HLU GIS Tool communicates with the wrong instance of the GIS software.

	* Close all GIS instances except the one associated with the HLU GIS tool. To avoid this issue, ensure all instances of ArcGIS or MapInfo are closed before launching the tool and do not open any additional instances whilst the tool is running. 

* The Bulk Update tool errors and fails to create history if the bulk update is applied to database records which do not have corresponding polygons in the HLU layer. 

	* Ensure that the database and map layer are kept in sync so this situation does not occur.
