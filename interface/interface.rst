**************
User Interface
**************

DOs and DON’Ts
================

It is essential that the following guidelines are followed to ensure that the tool runs smoothly.

* :emphasis:`DO` close all instances of ArcGIS or MapInfo before the tool launching the tool. The tool will automatically communicate with the correct instance; however multiple instances will require more memory and will therefore affect tool performance.
* :emphasis:`DO NOT` remove the HLU layer from the map while the tool is running.
* For ArcGIS users, :emphasis:`DO NOT` create or open another map document in the associated GIS window while the tool is running.
* :emphasis:`DO NOT` close the associated GIS while the tool is running, otherwise the tool will display an error message.
* :emphasis:`DO` ensure that the HLU GIS layer contains polygons for all INCIDs in the HLU database.
* For ArcGIS users, :emphasis:`DO` use a file geodatabase or personal geodatabase to store spatial information. :emphasis:`DO NOT` use a shapefile as this affects performance.

HLU GIS Tool Window
===================

Once the HLU GIS Tool has been configured, the tool will start the associated GIS, then the main window will appear as shown below.

.. figure:: ../images/figures/UserInterfaceMainWindow.png
	:align: center
	:height: 400px
	:width: 250px

	HLU GIS Tool window

The following sections provide some guidelines for use and summarise the menu functionality. All menu functions are also available on the toolbar and the relevant icon is shown next to each heading.

File Menu
=========

.. |export| image:: ../images/icons/FileExport.png

|export| Export
---------------

Allows you to export data from the HLU database to a GIS layer using a pre-defined export format. For details on defining export formats, see section 3.3.

.. figure:: ../images/figures/ExportDialog.png
	:align: center

	Export dialog

Select one of the export formats from the drop-down list.

If the database records have been filtered, the ``Selected only`` checkbox is automatically ticked as shown in Figure 2 and only the records related to the selected INCIDs will be exported. Untick this box to export all records. For details on how to filter records, see section 2.6.

The ``Export Descriptions`` checkbox replaces habitat codes with textual descriptions. This feature is only available for ArcGIS users due to record length restrictions in MapInfo.

