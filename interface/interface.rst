**************
User Interface
**************

DOs and DON’Ts
================

It is essential that the following guidelines are followed to ensure that the tool runs smoothly.

* :strong:`DO` close all instances of ArcGIS or MapInfo before the tool launching the tool. The tool will automatically communicate with the correct instance; however multiple instances will require more memory and will therefore affect tool performance.
* :strong:`DO NOT` remove the HLU layer from the map while the tool is running.
* For ArcGIS users, :strong:`DO NOT` create or open another map document in the associated GIS window while the tool is running.
* :strong:`DO NOT` close the associated GIS while the tool is running, otherwise the tool will display an error message.
* :strong:`DO` ensure that the HLU GIS layer contains polygons for all INCIDs in the HLU database.
* For ArcGIS users, :strong:`DO` use a file geodatabase or personal geodatabase to store spatial information. :strong:`DO NOT` use a shapefile as this affects performance.

HLU GIS Tool Window
===================

Once the HLU GIS Tool has been configured, the tool will start the associated GIS, then the main window will appear as shown in :num:`figure #figure1`.

.. _figure1:

.. figure:: ../images/figures/UserInterfaceMainWindow.png
	:align: center
	:height: 400px
	:width: 250px

	HLU GIS Tool window

The following sections provide some guidelines for use and summarise the menu functionality. All menu functions are also available on the toolbar and the relevant icon is shown next to each heading.

File Menu
=========

.. |export| image:: ../images/icons/FileExport.png
	:height: 16px
	:width: 16px

|export| Export
---------------

Allows you to export data from the HLU database to a GIS layer using a pre-defined export format. For details on defining export formats, see section 3.3.

.. figure:: ../images/figures/ExportDialog.png
	:align: center

	Export dialog

Select one of the export formats from the drop-down list.

If the database records have been filtered, the 'Selected only' checkbox is automatically ticked as shown in Figure 2 and only the records related to the selected INCIDs will be exported. Untick this box to export all records. For details on how to filter records, see section 2.6.

The 'Export Descriptions' checkbox replaces habitat codes with textual descriptions. This feature is only available for ArcGIS users due to record length restrictions in MapInfo.

.. |exit| image:: ../images/icons/FileExit.png
	:height: 16px
	:width: 16px

|exit| Exit
-----------

Exits the HLU GIS tool and allows you to decide whether or not to close the GIS window.

Edit Menu
=========

When the tool is launched, the database tool is read-only by default as indicated. To enable edit mode, the user details must be configured in the database (see section 3.2) and the spatial data must be editable in the GIS software.

.. |copy| image:: ../images/icons/EditCopy.png
	:height: 16px
	:width: 16px

|copy| Copy
-----------

Copies selected attributes so they can be applied to these fields in another record.

.. figure:: ../images/figures/CopyCheckboxes.png
	:align: center

	Checkboxes ticked to copy data

Tick the checkboxes next to the fields you wish to copy, as shown above, then click ‘Copy’.

.. |paste| image:: ../images/icons/EditPaste.png
	:height: 16px
	:width: 16px

|paste| Paste
-------------

Pastes the data copied by the ‘Copy’ tool into the same fields in another record.

For example, the fields copied in the figure above would be pasted into 'Source 3' on the new record.

.. Note:: It is not possible to copy data from one field in one record and paste it into a different field in another.

.. |bulkupdate| image:: ../images/icons/EditBulkUpdate.png
	:height: 16px
	:width: 16px

|bulkupdate| Bulk Update
------------------------

Allows you to update the attributes for all selected database records.

.. Note:: This feature is only available to configured users who have been given bulk update permissions. For details on configuring users, see section 3.2.

To perform a bulk update, filter the database records using ‘Select by attributes’ or select polygons in the GIS layer and click ‘Get Map Selection’. For details on filtering records, see section 2.6.

Click ‘Bulk Update’ on the Edit menu or toolbar. The HLU GIS Tool enters bulk update mode and an empty form is displayed as shown in the figure below.

The ‘Bulk Update’ box displays the number of INCIDs, TOIDs and fragments affected by the update and allows you to select whether to create a History record for this process.

Enter the updated details in the IHS, Details, and Sources tabs, then click Apply. These fields will be updated for all the selected INCIDs.

.. Note:: If ‘Delete Empty Bulk Update Rows’ is checked, child records will be deleted if these fields are not completed in the bulk update form. For details, see section 2.8.1.1.

.. figure:: ../images/figures/UserInterfaceBulkUpdate.png
	:align: center

	HLU Main Window in Bulk Update Mode

