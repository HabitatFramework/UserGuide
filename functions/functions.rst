.. |selectonmap| image:: ../icons/SelectOnMap.png
	:height: 16px
	:width: 16px

.. |logicalsplit| image:: ../icons/LogicalSplit.png
	:height: 16px
	:width: 16px

.. |logicalmerge| image:: ../icons/LogicalMerge.png
	:height: 16px
	:width: 16px

.. |getmapselection| image:: ../icons/GetMapSelection.png
	:height: 16px
	:width: 16px

.. |physicalsplit| image:: ../icons/PhysicalSplit.png
	:height: 16px
	:width: 16px

.. |physicalmerge| image:: ../icons/PhysicalMerge.png
	:height: 16px
	:width: 16px

.. |apply| image:: ../icons/Apply.png
	:height: 23px
	:width: 58px


.. index::
	single: Functions

*********
Functions
*********

.. index::
	single: Updates; Attribute Update

.. _attribute_update:

Attribute Update
================

Attribute Updates are the main mechanism for updating existing INCID details.

To update the attributes of an INCID:

* Ensure that the active HLU GIS layer is editable (for ArcGIS users click :guilabel:`Editor` on the Editor toolbar, select :guilabel:`Start Editing` and choose the active HLU layer, for MapInfo users set the active HLU layer as 'Editable').
* Select the feature or features to be updated.
* Click |getmapselection| :guilabel:`Get Map Selection`.
* Make the required changes to the INCID attributes, ensuring that any fields highlighted as missing or in error are addressed.
* Click |apply| :guilabel:`Apply`. The INCID will be updated and details will be added to the History tab.


.. note::
	The :guilabel:`Apply` button will only be displayed if:
		* The user is listed in the lut_user table.
		* The active GIS layer is in edit mode.
		* The user has made one or more changes to the current INCID.
		* There are no fields in error.

.. caution::
	If changes are made to an INCID and applied when only a subset of the TOIDs or fragments for that INCID are selected in GIS the user may be notified (depending upon their user Options) as shown in the figure :ref:`figAUWD`. See :ref:`options_interface` for more details.

.. _figAUWD:

.. figure:: figures/AttributeUpdateWarningDialog.png
	:align: center

	Attribute Update Warning Dialog

.. _split:

Split Features
==============

Features can be split logically or physically depending upon the filter active in the tool. If one or more features from a single INCID are present in the current filter then the tool will allow a logical split to be performed. If two or more fragments from the same TOID and with the same TOID_Fragment_Id are present in the current filter then the tool will allow a physical split to be performed.

.. raw:: latex

	\newpage

.. index::
	single: Split; Logical

.. _logical_split:

Logical Split
-------------

Logical split is used to create a new INCID in the database based upon a subset of features selected from a single INCID in the GIS layer. Logically splitting one or more features assigns them to a different INCID than the other features in the current INCID which then allows them to be updated independently of the remaining features in the original INCID.

	.. note::
		All selected features must belong to the same INCID.

To perform a logical split:

* Select the subset of features to be split in the GIS layer as shown in the **right** part of the figure :ref:`figLSFD`.
* Return to the HLU Tool window and click |getmapselection| :guilabel:`Get Map Selection`.
* Click |logicalsplit| :guilabel:`Logical Split`. A new INCID will be created and displayed as the current record.


To display all the features in the INCID of a given feature:

* Select the feature of interest in the GIS layer.
* Return to the HLU main window and click |getmapselection| :guilabel:`Get Map Selection`.
* Click |selectonmap| :guilabel:`Select Current INCID on Map`. All the features associated with the current INCID will be displayed as shown in the **left** part of the figure :ref:`figLSFD`.

.. _figLSFD:

.. figure:: figures/LogicalSplitDiagram.png
	:align: center

	Logical Split – Before (left) and After (right)


.. raw:: latex

	\newpage

.. index::
	single: Split; Physical

.. _physical_split:

Physical Split
--------------

Physical split is use to create one or more new TOID fragments in the database based upon a single TOID that has already been split in the GIS layer. Physically splitting a feature into fragments allows the fragments to be updated independently of each other (once they have also been assigned to different INCIDs - see :ref:`logical_split`.)

.. note::

	* Only one feature should be split in a single operation. Splitting multiple features will cause database synchronisation issues. 
	* If several features have been split, select the fragments for one original feature and split using the tool. Repeat this operation for the remaining features.
	* Ensure that the physical split is completed in the database prior to commencing any other operations such as 'Select by attributes …' to avoid database synchronisation issues.

.. caution::
	If two or more fragments from the same TOID and with the same TOID_Fragment_Id are selected in the GIS and **Get Map Selection** is clicked then the tool will recognise that the fragments must have been split by the user in the GIS layer and will **automatically** perform a physical split before displaying the attributes.


ArcGIS
^^^^^^

To perform a physical split in ArGIS:

* On the 'Editor' toolbar (shown in the figure :ref:`figArcEMB`), click :guilabel:`Editor` and select :guilabel:`Start Editing`.

.. _figArcEMB:

.. figure:: figures/ArcGISEditMenuBar.png
	:align: center

	Edit Settings for Physical Split (ArcGIS)

* Select the feature to be split.
* On the 'Editor' toolbar, click :guilabel:`Cut Polygons Tool` draw a polyline through the feature to be split.

	.. tip::
		It is not necessary to **Save Edits** after splitting the feature in GIS because the changes will be saved automatically once the split has been completed with the tool.

* The feature will be split but still selected as shown in the figure :ref:`figArcSFD`. Return to the HLU Tool and click |getmapselection| :guilabel:`Get Map Selection`.

.. _figArcSFD:

.. figure:: figures/ArcGISSplitFeaturesDiagram.png
	:align: center

	Split Features (ArcGIS)

* Click |physicalsplit| :guilabel:`Physical Split`. The record will be updated and details added to the History tab for the INCID.


MapInfo
^^^^^^^

To perform a physical split in MapInfo:

* Set the Cosmetic layer as 'Editable' and draw the feature to split by.

.. tip::
	The Cosmetic layer should be used due to the time required for MapInfo to add a new feature to the full HLU layer.

* Set the HLU layer as 'Editable'.
* Select the feature to be split and go to Objects > Set Target.
* Select the polygon in the Cosmetic layer and go to Objects > Split.
* In the Data Disaggregation dialog ensure that 'Method' for all fields is set to 'Value' as shown in the figure :ref:`figMIDD`, then click :guilabel:`OK`.

.. _figMIDD:

.. figure:: figures/MapInfoDataDisaggregationDialog.png
	:align: center

	Data Disaggregation Dialog (MapInfo)

* The feature will be split but still selected as shown in the figure :ref:`figMISF`. Return to the HLU Tool and click |getmapselection| :guilabel:`Get Map Selection`.

.. _figMISF:

.. figure:: figures/MapInfoSplitFeaturesDiagram.png
	:align: center

	Split Features (MapInfo)

* Click |physicalsplit| :guilabel:`Physical Split`. The record will be updated and details added to the History tab for the INCID. The Cosmetic layer will be cleared.


.. raw:: latex

	\newpage

.. _merge:

Merge Features
==============

Merge features will performs two types of merge depending upon the filter active in the tool. If two or more features from multiple INCIDs are present in the current filter then the tool will allow a logical merge to be performed. If two or more fragments from the same TOID and with different TOID_Fragment_Ids are present in the current filter then the tool will allow a physical merge to be performed.

.. index::
	single: Merge; Logical

.. _logical_merge:

Logical Merge
-------------

Logical merge combines all the features selected in the GIS into a single INCID chosen from from the selected features. This assigns the attributes from the chosen INCID to all the other selected features and logically groups the features into a single INCID so that they can be updated together in the future.

To perform a logical merge:

* Select the features to be merged and a feature from the INCID they are to be merged with in the GIS layer.
* Return to the HLU main window and click |getmapselection| :guilabel:`Get Map Selection`.
* Select one of the options in the 'Process' list.
* Click |logicalmerge| :guilabel:`Logical Merge`. A list of INCIDs will be displayed as shown in the figure :ref:`figLMD`.

.. _figLMD:

.. figure:: figures/LogicalMergeDialog.png
	:align: center

	Select INCID to Keep Dialog

* Click on the grey box to the left of the row to select an INCID. The associated feature will blink in the GIS window. Click :guilabel:`OK`.
* The selected features will be assigned to the selected INCID and details added to the History tab.
* If the merged features are fragments of the same TOID the user will be given the option to then perform a physical merge.

.. raw:: latex

	\newpage

.. index::
	single: Merge; Physical

.. _physical_merge:

Physical Merge
--------------

Physical merge combines fragments of a single TOID into a single, larger, feature in the GIS layer. As the fragments must already belong to the same INCID there are no attribute updates but the boundaries between adjacent features will be removed.

To perform a physical merge:

* Select two or more fragments from one TOID in the GIS layer as shown in the **left** part of the figure :ref:`figPMD`.
* Return to the HLU main window and click |getmapselection| :guilabel:`Get Map Selection`.
* Select one of the options in the 'Process' list.
* Click |physicalmerge| :guilabel:`Physical Merge`. The features will be combined in the GIS layer as shown in the **right** part of the figure :ref:`figPMD`.

.. _figPMD:

.. figure:: figures/PhysicalMergeDiagram.png
	:align: center

	Physical Merge – Before (left) and After (right)


.. note::
	Only fragments belonging to the same TOID can be merged in a single operation. If fragments for several TOIDs need to be merged, the operation must be repeated for each TOID.






.. raw:: latex

	\newpage

.. index::
	single: Filter

.. _filter:

Filters
=======


.. index::
	single: Filter; by Attributes

.. _filter_by_attributes:

Filter by Attributes
--------------------




	The message will indicate the expected number of features that will be selected (as shown in the figure :ref:`figGSWD`).

	.. _figGSWD:

	.. figure:: figures/GISSelectionWarningDialog.png
		:align: center

		GIS Selection Warning Dialog


	In the event that the SQL query that would be required to select the features in GIS would be too long or complex the message will also warn the user that a temporary join (which may take some time) will need to be performed in GIS (as shown in the figure :ref:`figGSWD2`).

	.. _figGSWD2:

	.. figure:: figures/GISSelectionJoinWarningDialog.png
		:align: center

		GIS Selection with Join Warning Dialog




.. index::
	single: Filter; by INCID

.. _filter_by_incid:

Filter by Incid
---------------









.. raw:: latex

	\newpage

.. index::
	single: Update; Bulk Update

.. _bulk_update:

Bulk Update Mode
================

Bulk updates allow users to update the attributes for multiple INCID database records, and associated features in the active GIS layer, simultaneously.

.. note::

	* Bulk update mode can only be started once a filter is applied to the INCID records.
	* Bulk update mode is only available to configured users who have been given bulk update permissions. For details on configuring users see 'Lookup Tables' in the HLU Tool Technical Guide `readthedocs.org/projects/hlutool-technicalguide <https://readthedocs.org/projects/hlutool-technicalguide/>`_.

To bulk apply updates:

* Filter the database records using 'Select by attributes' or select polygons in the GIS layer and click :guilabel:`Get Map Selection`. For details on filtering records see :ref:`query_builder_window`.

* Click *:guilabel:`Edit... --> Bulk Apply Updates` to enter bulk update mode. An empty form is displayed as shown in the figure :ref:`figUIBU`.

.. _figUIBU:

.. figure:: figures/UserInterfaceBulkUpdate.png
	:align: center
	:scale: 70

	Main window - Bulk Update Mode


* The 'Bulk Update' section displays the number of INCIDs, TOIDs and fragments affected by the update and allows users to select whether to create a History record for this process.

* Enter the updated details in the Habitats, Details, and Sources tabs, then click :guilabel:`Apply`. These fields will be updated for all the selected INCIDs.

.. caution::
	If 'Delete Empty Bulk Update Rows' is checked in the Options, child records will be deleted if these fields are not completed in the bulk update form. See :ref:`options_database` for more details.







.. raw:: latex

	\newpage

.. index::
	single: Update; OSMM Update

.. _osmm_update:

OSMM Update
===========





.. raw:: latex

	\newpage

.. index::
	single: Export

.. _export_function:

Export
======

Export allows users to combine spatial geometries from a HLU GIS layer and attribute data from the HLU database into a combined GIS layer using a pre-defined export format.


