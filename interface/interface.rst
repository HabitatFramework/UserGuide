.. index::
	single: Windows

*********
Interface
*********

.. index::
	single: Windows; Main window

.. _main_window:

HLU Tool Window
===============

Once the HLU GIS Tool has been configured, the tool will start the associated GIS, then the main window will appear as shown in the figure :ref:`figUIMW`.

.. _figUIMW:

.. figure:: ../images/figures/UserInterfaceMainWindow.png
	:align: center
	:scale: 70

	HLU GIS Tool - Main window


Records can be viewed or updated through the main window of the HLU GIS Tool. The following sections summarise the details available for each record. 

Required fields are highlighted in red on each tab. The ‘Apply’ button will be active when the required fields have been completed on all tabs.

INCID Section
-------------

The ‘INCID’ box displays summary information for each INCID in the database, including area, perimeter, date created and date last modified as shown in the figure :ref:`figUIIS`.

.. Note:: If the user is not configured, the ‘By’ fields will display their Windows login. For details on configuring users, see section 3.1.

.. _figUIIS:

.. figure:: ../images/figures/UserInterfaceIncidSection.png
	:align: center
	:scale: 85

	Main window - INCID Section

Reason/Process Section
----------------------

‘Reason’ and ‘Process’ (as shown in the figure :ref:`figUIRPS`) are required fields for all updates and are used on the History tab to indicate why the record was last updated. These fields are sticky i.e. the selected reason and process will be used for all updates in the current session unless they are altered manually.

.. _figUIRPS:

.. figure:: ../images/figures/UserInterfaceReasonProcessSection.png
	:align: center
	:scale: 85

	Main window - Reason/Process Section


IHS Tab
-------

The IHS tab displays the IHS details for the current database record as shown in the figure :Ref:`figUIIT`.

.. _figUIIT:

.. figure:: ../images/figures/UserInterfaceIHSTab.png
	:align: center
	:scale: 85

	Main window - IHS Tab

* ‘Category’ and ‘NVC’ drop-down lists are used to filter the ‘Habitat’ drop-down list to relevant IHS codes. The entries in these fields are not saved to the database.
* The drop-down lists in the IHS Matrix, IHS Formation, IHS Management and IHS Complex boxes allow users to define the habitat according to the SERC IHS guidelines.
* ‘IHS Summary’ is automatically generated based upon the options selected from the preceding drop-down lists.
* ‘Legacy Habitat’ is the pre-IHS habitat code.

Details Tab
-----------

Click on ‘Details’ to display the Details tab as shown in the figure :ref:`figUIDT`.

.. _figUIDT:

.. figure:: ../images/figures/UserInterfaceDetailsTab.png
	:align: center
	:scale: 85

	Main window - Details Tab

* ‘BAP Habitats’ is automatically updated based upon the habitat code selected on the ‘IHS’ tab. For new BAPhabitats, ‘Determination Quality’ and ‘Interpretation Quality’ must be entered.
* ‘Potential BAP Habitats’ allows users to define other BAP habitats which may also be present within the BAP habitat. An INCID may have a potential BAP habitat even if no BAP habitats are present.
* ‘General Comments’ is a text field which allows users to enter any additional comments up to 254 characters.
* ‘Maps’ contains two drop-down lists:
* ‘Boundary Map’ defines the source data used to identify the boundary.
* ‘Digitisation Map’ defines the map data used to digitise the boundary.
* ‘BiositeName’ is a text field which allows users to enter the name of the biosite.

Sources Tab
-----------

Click on ‘Sources’ to display the Sources tab as shown in the figure :ref:`figUIST`. Up to three sources can be defined for each INCID.

.. _figUIST:

.. figure:: ../images/figures/UserInterfaceSourcesTab.png
	:align: center
	:scale: 85

	Main window - Sources Tab

* ‘Name’ contains a list of data sources. For details on adding new sources, see section 3.1.
* ‘Vague Date’ allows users to enter the date of the dataset. This can be either a precise date e.g. 01/04/2010 or a vague date e.g. Spring 2010-Summer 2010, 1980-2010 or ‘Unknown’. For details on defining vague dates, see section 2.8.1.3.
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
	:scale: 85

	Main window - History Tab


.. index::
	single: Bulk updates

.. _bulk_update_window:

Bulk Updates
============

Allows users to update the attributes for multiple selected database records simultaneously.

.. Note:: This feature is only available to configured users who have been given bulk update permissions. For details on configuring users, see section 3.2.

To perform a bulk update:

* Filter the database records using ‘Select by attributes’ or select polygons in the GIS layer and click ‘Get Map Selection’. For details on filtering records, see section 2.6.

* Click ‘Bulk Update’ on the Edit menu or toolbar. The HLU GIS Tool enters bulk update mode and an empty form is displayed as shown in the figure :ref:`figUIBU`.

* The ‘Bulk Update’ box displays the number of INCIDs, TOIDs and fragments affected by the update and allows users to select whether to create a History record for this process.

* Enter the updated details in the IHS, Details, and Sources tabs, then click Apply. These fields will be updated for all the selected INCIDs.

.. _figUIBU:

.. figure:: ../images/figures/UserInterfaceBulkUpdate.png
	:align: center
	:scale: 70

	Main Window - Bulk Update Mode

.. Warning:: If ‘Delete Empty Bulk Update Rows’ is checked in the Options, child records will be deleted if these fields are not completed in the bulk update form. For details, see section 2.8.1.1.


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
	:scale: 90

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

* ‘History Columns’ allows users to select which additional columns from the GIS layer are displayed in the History tab for each update. If the box is unchecked, the field will not be displayed.
* ‘Preferred GIS’ allows users to select whether the tool should use ArcGIS or MapInfo if both applications are installed on their computer. 

.. Note:: The tool must be closed and restarted for this change to take effect.

* ‘Map Document/Workspace’ sets the default map document or workspace opened by the HLU GIS Tool. As this field cannot be edited directly, users must click on the “…” button and browse to the new map document or workspace. 

.. Note:: If the preferred GIS is altered, this field must also be updated.

* ‘Warn before GIS selection’ allows users to enable or disable the warning message indicating the number of polygons which will be selected by the current query as shown in the figure :ref:`figGSWD`.

.. _figGSWD:

.. figure:: ../images/figures/GISSelectionWarningDialog.png
	:align: center

	GIS Selection Warning Box

Vague Date Season Names
-----------------------

These fields allow users to define how vague dates, such as 'Spring 2010-Autumn 2010' or '1989-2010', are entered so that they can be converted to dates in the HLU database.

 
The default value for the ‘Vague Date Delimiter’ is a hyphen ( - ). This can be altered to any character, however it must not be the same delimiter used by the computer to enter precise dates, such as 01/04/2010. The default delimiter used by Windows for English-format dates is a forward slash ( / ).


.. raw:: latex

	\newpage

.. index::
	single: Windows; Export window

.. _export_window:

Export Window
=============

Allows users to export data from the HLU database to a GIS layer using a pre-defined export format (see the figure :ref:`figED`).

For details on defining export formats, see section 3.3.

.. _figED:

.. figure:: ../images/figures/ExportDialog.png
	:align: center

	Export dialog

* Select one of the export formats from the drop-down list.

* If the database records have been filtered, the 'Selected only' checkbox is automatically ticked as shown in Figure 2 and only the records related to the selected INCIDs will be exported. Untick this box to export all records. For details on how to filter records, see section 2.6.

* The 'Export Descriptions' checkbox replaces habitat codes with textual descriptions. This feature is only available for ArcGIS users due to record length restrictions in MapInfo.


.. raw:: latex

	\newpage

.. index::
	single: Windows; Query Builder window

.. _query_builder_window:

HLU Query Builder Window
========================

Allows users to filter the database records using the query builder shown in the figure :ref:`figQB`.

.. _figQB:

.. figure:: ../images/figures/QueryBuilder.png
	:align: center

	HLU Query Builder


* Boolean Operator allows users to perform logical selections using:

	* 'AND'
	* 'AND NOT'
	* 'OR'
	* 'OR NOT'.

.. Note:: The value of the ‘Boolean Operator’ field on the first row is not used.

* ‘(‘ and ‘)’ fields allow users to add additional brackets as shown in the example in the figure :ref:`figQB` to define how the query is executed.
* ‘Table’ and ‘Column’ define the table and field to be searched.
* ‘Operator’ provides a drop-down list of the available operators as shown in the figure :ref:`figSOL`.
* Value’ is the value to search for. Values can either be entered as text or selected from the drop-down list (where available).

.. _figSOL:

.. figure:: ../images/figures/SQLOperatorList.png
	:align: center

	List of Operators

Once users have entered the values for the current row, click on another row in the query builder to confirm the entry and enable the ‘OK’ button.

If a mistake has been made when entering the selection criteria, click on the grey box to the left of ‘Boolean Operator’ to select the row, then press the keyboard :kbd:`Delete` key to remove it.


.. Tip:: If features are likely to be selected from multiple INCIDs it will typically be much quicker to select features in the GIS (if the available attributes are sufficient for the selection) then use ‘Get Map Selection’.


.. raw:: latex

	\newpage

.. index::
	single: Windows; Switch GIS Layer window

.. _switch_layer_window:

Switch GIS Layer Window
=======================

Allows users to switch between GIS layers by selecting a different layer in the drop-down list (see the figure :ref:`figSGLD`). Only layers from the current workspace/document that are valid HLU layers (i.e. have the correct attribute names and formats) will appear in the drop-down list.

.. _figSGLD:

.. figure:: ../images/figures/SwitchGISLayerDialog.png
	:align: center

	Switch GIS Layer Dialog

