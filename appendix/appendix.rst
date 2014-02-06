********
Appendix
********

.. index::
	single: Dos and Don'ts

.. _dos_and_donts:

DOs and DON'Ts
================

It is essential that the following guidelines are followed to ensure that the tool runs smoothly:

**DOs:**

	* :strong:`DO` close all instances of MapInfo before launching the tool as the tool may try and communicate with the wrong instance of MapInfo.
	* :strong:`DO` close all instances of ArcGIS before launching the tool. Unlike with MapInfo, the tool will automatically communicate with the correct instance of ArcGIS, however multiple instances will require more memory and may therefore affect tool performance.
	* :strong:`DO` use a file geodatabase or personal geodatabase to store spatial information (ArcGIS users only).

**DO NOTs:**

	* :strong:`DO NOT` remove the HLU layer from the map while the tool is running.
	* :strong:`DO NOT` close the associated GIS while the tool is running, otherwise the tool will display an error message.
	* :strong:`DO NOT` create or open another map document or workspace in the associated GIS window while the tool is running.
	* :strong:`DO NOT` use a shapefile as this affects performance (ArcGIS users only).


.. note::

	New in version 1.0.7:
	
	* It is now possible to use a HLU GIS layer containing only a subset of all the incids in the HLU database.
	* It is also possible to switch between different HLU GIS layers present in the open document or workspace using the *Switch GIS layer* function.


.. raw:: latex

	\newpage

.. index::
	single: What Happened

.. _what_happened:

What Happened?
==============

* ArcGIS generates a 'hard error' when the HLU GIS Tool is used.

	* Solution 1:	The HLU ArcMap extension has not been enabled. Close and relaunch the tool, then enable the extension in ArcMap before using the toolkit.
	* Solution 2: 	ArcGIS has been closed while the tool was running. Close and relaunch the tool.

* The HLU GIS Tool stops responding to GIS requests.

	* Solution 1: The HLU GIS layer is no longer active in the map or MapInfo has been closed while the tool was running. Close and relaunch the tool.

* The HLU GIS Tool communicates with the wrong instance of the GIS software.

	* Close all GIS instances except the one associated with the HLU GIS tool. To avoid this issue, ensure all instances of ArcGIS or MapInfo are closed before launching the tool and do not open any additional instances whilst the tool is running. 

* The Bulk Update tool errors and fails to create history if the bulk update is applied to database records which do not have corresponding polygons in the HLU layer. 

	* Ensure that the database and map layer are kept in sync so this situation does not occur.

