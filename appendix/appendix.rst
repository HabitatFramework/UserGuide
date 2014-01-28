********
Appendix
********

.. index::
	single: Optimising performance

.. _optimising_performance:

Optimising Performance
======================

Creation of ArcGIS Map Document or MapInfo Workspace
----------------------------------------------------

An ArcGIS Map Document (.mxd) or MapInfo Workspace (.wor) must be created for use with the HLU GIS Tool. This should be optimised to ensure maximum performance, which should include the following:

* Ensure that the .mxd or .wor file only contains one copy of the HLU layer
* Add zoom layering to datasets so that detailed datasets such as the HLU layer and aerial photography are not displayed at smaller scales. Our recommended maximum extents are:

	* ArcGIS – Do not display out beyond:

		* HLU Layer:		1:24,000
		* Aerial Photography:	1:10,000

	* MapInfo – Max Zoom:

		* HLU Layer:		7.5 km
		* Aerial Photography:	3 km

* Ensure that the .mxd or .wor is saved at a sensible view level such as 1:10,000 scale rather the full extent of the HLU dataset

Use of HLU GIS Tool with ArcGIS or MapInfo
------------------------------------------

It takes a significant length of time for ArcGIS or MapInfo to draw an entire HLU GIS layer, therefore care should be taken when using certain tools to avoid this issue.

* ‘Zoom to Selection’ is useful for identifying the habitat polygons on the map, however if zoom layering is not used it may take a significant length of time to display the result depending upon the number of polygons selected and their geographical distribution.
* ‘Select by Attributes’ performs complex queries and selects the results in the GIS window. If a large number of results are returned, it could take a long time to select the spatial polygons in the GIS.
* If the layer is taking a long time to draw, pause or cancel the drawing using:

	* ArcGIS - Click the Pause button in the bottom left corner of the map window
	* MapInfo – Press the Esc key on your keyboard

* For ArcGIS users, if an ArcMap error occurs when the tool is used, check that the HLU ArcMap Extension is enabled in Tools > Extensions – see section ref:`?`.
* For ArcGIS users, we strongly recommend that the HLU layer is stored as a file geodatabase or personal geodatabase. **The tool will be significantly slower if the HLU layer is stored as a shapefile due to the limitations of the file format.**

	**e.g. exporting 152 features takes 18 minutes from a shapefile but takes under 3 minutes from a file geodatabase.**

* For MapInfo users, ensure the Cosmetic layer is editable when digitising a polygon for a split operation. The polygon will be added to the layer much faster than if the HLU layer was used and also removes the possibility that the polygon is not deleted after the split.

Selection of Database Type
--------------------------

The HLU GIS Tool is supplied with both Microsoft Access 2000 and SQL Server 2008 databases.

Microsoft Access is a versatile desktop database application, but does not have the same performance as other database systems. Database management systems such as SQL Server are optimised to handle large data volumes and complex queries, and can be significantly faster.

We therefore recommend using the HLU GIS Tool with SQL Server or a similar database management system, as this will improve performance when filtering the database records and updating attribute data.

Local vs. Network Storage
-------------------------

It is important to remember that application performance will depend upon the data transfer speed. Data stored locally on a single computer will provide good performance, but will limit access to the data to a single user. Data stored on a network drive is accessible to all users, but performance will be limited by the speed that the data can be transferred across the network.

Data Management
---------------

Only one copy of the database and the GIS layer should be used to avoid data becoming corrupted. If multiple copies are used e.g. an ArcGIS layer and a MapInfo layer or an Access database and a SQL Server database, changes to one GIS layer or database will not be present on the other, causing a mismatch between the attribute and spatial data.

Habitat data must not be edited directly in either the database or the GIS layer. Any modifications made outside the HLU GIS Tool could cause data corruption particularly if unique identifiers are altered.

However, if additional entries are required in the lookup tables, these may be added to the database directly. It is essential that the structure of these tables is not altered and we recommend that any updates to the data in these tables are carried out solely by the database administrator.


.. index::
	single: Known issues

.. _known_issues:

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

