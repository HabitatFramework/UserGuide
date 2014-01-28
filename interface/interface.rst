.. index::
	single: Windows

**************
User Interface
**************

.. _dos_and_donts:

DOs and DON’Ts
================

It is essential that the following guidelines are followed to ensure that the tool runs smoothly:

DOs --

* :strong:`DO` close all instances of MapInfo before launching the tool as the tool may try and communicate with the wrong instance of MapInfo.
* :strong:`DO` close all instances of ArcGIS before launching the tool. Unlike with MapInfo, the tool will automatically communicate with the correct instance of ArcGIS, however multiple instances will require more memory and may therefore affect tool performance.
* For ArcGIS users, :strong:`DO` use a file geodatabase or personal geodatabase to store spatial information. :strong:`DO NOT` use a shapefile as this affects performance.

DO NOTs --

* :strong:`DO NOT` remove the HLU layer from the map while the tool is running.
* :strong:`DO NOT` close the associated GIS while the tool is running, otherwise the tool will display an error message.
* :strong:`DO NOT` create or open another map document or workspace in the associated GIS window while the tool is running.


.. note::

	New in version 1.0.5:
	
	* It is now possible to use a HLU GIS layer containing only a subset of all the incids in the HLU database.
	* It is also possible to switch between different HLU GIS layers present in the open document or workspace using the *Switch GIS layer* function.


.. raw:: latex

	\newpage

.. index::
	single: Windows; Main window

.. _main_window:

HLU Tool Window
===============

Once the HLU GIS Tool has been configured, the tool will start the associated GIS, then the main window will appear as shown in the figure :ref:`figUIMW`.

.. _figUIMW:

.. figure:: ../images/figures/UserInterfaceMainWindow.png
	:align: center
	:height: 350px
	:width: 567px

	HLU GIS Tool window


Records can be viewed or updated through the main window of the HLU GIS Tool. The following sections summarise the details available for each record. 

Required fields are highlighted in red on each tab. The ‘Apply’ button will be active when the required fields have been completed on all tabs.

INCID Box
---------

The ‘INCID’ box displays summary information for each INCID in the database, including area, perimeter, date created and date last modified as shown in the figure :ref:`figUIIS`.

.. Note:: If the user is not configured, the ‘By’ fields will display their Windows login. For details on configuring users, see section 3.1.

.. _figUIIS:

.. figure:: ../images/figures/UserInterfaceIncidSection.png
	:align: center

	INCID Section

* ‘Reason’ and ‘Process’ are required fields for all updates and are used on the History tab to indicate why the record was last updated. These fields are sticky i.e. the selected reason and process will be used for all updates in the current session unless they are altered manually.

IHS Tab
-------

The IHS tab displays the IHS details for the current database record as shown in the figure :Ref:`figUIIT`.

.. _figUIIT:

.. figure:: ../images/figures/UserInterfaceIHSTab.png
	:align: center
	:scale: 25

	IHS Tab

* ‘Category’ and ‘NVC’ drop-down lists are used to filter the ‘Habitat’ drop-down list to relevant IHS codes. The entries in these fields are not saved to the database.
* The drop-down lists in the IHS Matrix, IHS Formation, IHS Management and IHS Complex boxes allow you to define the habitat according to the SERC IHS guidelines.
* ‘IHS Summary’ is automatically generated based upon the options selected from the preceding drop-down lists.
* ‘Legacy Habitat’ is the pre-IHS habitat code.

Details Tab
-----------

Click on ‘Details’ to display the Details tab as shown in the figure :ref:`figUIDT`.

.. _figUIDT:

.. figure:: ../images/figures/UserInterfaceDetailsTab.png
	:align: center
	:scale: 50

	Details Tab

* ‘BAP Habitats’ is automatically updated based upon the habitat code selected on the ‘IHS’ tab. For new BAPhabitats, ‘Determination Quality’ and ‘Interpretation Quality’ must be entered.
* ‘Potential BAP Habitats’ allows you to define other BAP habitats which may also be present within the BAP habitat. An INCID may have a potential BAP habitat even if no BAP habitats are present.
* ‘General Comments’ is a text field which allows you to enter any additional comments up to 254 characters.
* ‘Maps’ contains two drop-down lists:
* ‘Boundary Map’ defines the source data used to identify the boundary.
* ‘Digitisation Map’ defines the map data used to digitise the boundary.
* ‘BiositeName’ is a text field which allows you to enter the name of the biosite.

Sources Tab
-----------

Click on ‘Sources’ to display the Sources tab as shown in the figure :ref:`figUIST`. Up to three sources can be defined for each INCID.

.. _figUIST:

.. figure:: ../images/figures/UserInterfaceSourcesTab.png
	:align: center

	Sources Tab

* ‘Name’ contains a list of data sources. For details on adding new sources, see section 3.1.
* ‘Vague Date’ allows you to enter the date of the dataset. This can be either a precise date e.g. 01/04/2010 or a vague date e.g. Spring 2010-Summer 2010, 1980-2010 or ‘Unknown’. For details on defining vague dates, see section 2.8.1.3.
* ‘Habitat Class’ defines the habitat classification used for this data source. If no habitat classification is used, select ‘Not Applicable’.
* ‘Habitat Type’ defines the type of habitat. This list is filtered based upon the habitat class.
* ‘Boundary Imp.’ sets the importance of the source data in determining the habitat boundary.
* ‘Habitat Imp.’ sets the importance of the source data in determining the habitat type.


.. Note::

	* If the default date for the selected data source has been configured, the ‘Vague Date’ field will be updated to the default date. If the default date has not been defined, then the ‘Vague Date’ field must be updated manually.
	* For boundary importance and habitat importance, there must only be one source set as ‘Primary’ or ‘Secondary’ for each field.

History Tab
-----------

The History tab displays a list of modifications made to the current INCID and the associated TOIDs. Each entry details what modification was made, when and by whom as shown in Figure 20. Entries are shown in descending date order. The number of entries can be configured in the Options, see section 2.8.1.

.. _figUIHT:

.. figure:: ../images/figures/UserInterfaceHistoryTab.png
	:align: center

	History Tab


.. raw:: latex

	\newpage

.. index::
	single: Windows; Options window

.. _options_window:

Options Window
==============

Allows users to alter the HLU configuration. There are three categories of options as shown in the figure :ref:`figOD`.

.. _figOD:

.. figure:: ../images/figures/OptionsDialog.png
	:align: center

	HLU Options Dialog

Database Options
----------------

* ‘Timeout’ sets the amount of time the tool will wait for the database to respond. The default value is 15. This value should be increased if an error occurs such as ‘The connection to the database timed out’.
* ‘Page Size’ sets how many records are retrieved from the database and stored in memory. The default value is 100. Increasing this value can improve performance when browsing records, however this will increase the amount of RAM required by the application and significant increases in the page size value could cause the tool to stop responding.
* ‘Display History Rows’ sets the number of entries displayed in the ‘History’ tab of the main window. For detail on the ‘History’ tab - see section 2.9.5.
* ‘Delete Empty Bulk Update Rows’ removes the details of child records if they are these fields are not completed in the bulk update form if this box is checked. By default this box is unchecked. 

	This affects the following sections of the main window:

	* IHS Matrix
	* IHS Formation
	* IHS Management
	* IHS Complex
	* BAP Habitat
	* Potential BAP Habitats
	* Sources

.. Warning::

	If the 'Delete Empty Bulk Update Rows' option is checked and a bulk update record has only 1 source record completed then, for each of the selected records, source 1 will be updated and if the selected record has data entered in sources 2 and 3, it will be deleted.

GIS Options
-----------

* ‘History Columns’ allows you to select which additional columns from the GIS layer are displayed in the History tab for each update. If the box is unchecked, the field will not be displayed.
* ‘Preferred GIS’ allows you to select whether the tool should use ArcGIS or MapInfo if both applications are installed on your computer. 

.. Note:: The tool must be closed and restarted for this change to take effect.

* ‘Map Document/Workspace’ sets the default map document or workspace opened by the HLU GIS Tool. As this field cannot be edited directly, you must click on the “…” button and browse to the new map document or workspace. 

.. Note:: If the preferred GIS is altered, this field must also be updated.

* ‘Warn before GIS selection’ allows you to enable or disable the warning message indicating the number of polygons which will be selected by the current query as shown in the figure :ref:`figGSWD`.

.. _figGSWD:

.. figure:: ../images/figures/GISSelectionWarningDialog.png
	:align: center

	GIS Selection Warning Box

Vague Date Season Names
-----------------------

These fields allow you to define how vague dates, such as 'Spring 2010-Autumn 2010' or '1989-2010', are entered so that they can be converted to dates in the HLU database.

 
The default value for the ‘Vague Date Delimiter’ is a hyphen ( - ). This can be altered to any character, however it must not be the same delimiter used by your computer to enter precise dates, such as 01/04/2010. The default delimiter used by Windows for English-format dates is a forward slash ( / ).


.. raw:: latex

	\newpage

.. index::
	single: Windows; Export window

.. _export_window:

Export Window
=============

Allows you to export data from the HLU database to a GIS layer using a pre-defined export format (see the figure :ref:`figED`.

For details on defining export formats, see section 3.3.

.. _figED:

.. figure:: ../images/figures/ExportDialog.png
	:align: center

	Export dialog

Select one of the export formats from the drop-down list.

If the database records have been filtered, the 'Selected only' checkbox is automatically ticked as shown in Figure 2 and only the records related to the selected INCIDs will be exported. Untick this box to export all records. For details on how to filter records, see section 2.6.

The 'Export Descriptions' checkbox replaces habitat codes with textual descriptions. This feature is only available for ArcGIS users due to record length restrictions in MapInfo.

