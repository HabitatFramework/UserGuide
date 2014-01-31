.. index::
	single: Key concepts

********
Concepts
********

.. index::
	single: OS Mastermap
	single: toid
	see: Topographical identifier; toid
	single: toid_fragment_id
	see: fragment; toid_fragment_id

OS MasterMap Framework
======================

TOID
TOID_Fragment_Id


.. raw:: latex

	\newpage

.. index::
	single: incid
	see: Incremental Identifier; incid

Incremental Identifier
======================

INCID


.. raw:: latex

	\newpage

GIS layer and Database Separation
=================================




.. raw:: latex

	\newpage

Splits and Merges
=================

.. index::
	single: split

Split Features
--------------

Split features will performs two types of split depending upon the filter active in the tool. If one or more features from a single INCID are present in the current filter then the tool will perform a logical split. If two or more fragments from the same TOID and with the same TOID_Fragment_Id are present in the current filter then the tool will perform a physical split.

.. Note:: If two or more fragments from the same TOID and with the same TOID_Fragment_Id are selected in the GIS and 'Get Map Selection' is clicked then the tool will recognise that the fragments must have been split by the user in the GIS layer and will automatically perform a physical split before displaying the attributes.

.. index::
	single: logical split

Logical Split
^^^^^^^^^^^^^

Logical split is used to create a new INCID in the database based upon the subset of features selected from a single INCID in the GIS layer. The habitat details for the new INCID can then be updated independently of the other features in the original INCID.

To perform a logical split:

* Click ‘Switch to GIS Window’ and select the required features in the GIS layer.
* Return to the HLU main window and click ‘Get Map Selection’.
* Select one of the options in the ‘Process’ list.
* Click on ‘Split Features’. The new INCID will be created and set as the current record.

.. Note:: The selected features must all belong to the same INCID.

.. index::
	single: physical split

Physical Split
^^^^^^^^^^^^^^

Physical split creates one or more new TOID fragments in the database based upon a single TOID which has been split in the GIS layer.

ArcGIS
""""""

To perform a physical split:

* On the ‘Editor’ toolbar, click on ‘Editor’ and select ‘Start Editing’.
* Select the feature to be split.
* On the ‘Editor’ toolbar, select the ‘Cut Polygons Tool’ (for polygon features) or `Split Tool` (for lines) button as shown in the figure :ref:`figArcEMB`.

.. _figArcEMB:

.. figure:: ../images/figures/ArcGISEditMenuBar.png
	:align: center

	Edit Settings for Physical Split (ArcGIS)

* Using the Sketch tool on ‘Editor’ toolbar, draw a polyline.
* On the ‘Editor’ toolbar, click on ‘Editor’ and select ‘Save Edits’.
* The feature will be split but still selected as shown in the figure :ref:`figArcSFD`. Return to the HLU GIS Tool and click ‘Get Map Selection’.

.. _figArcSFD:

.. figure:: ../images/figures/ArcGISSplitFeaturesDiagram.png
	:align: center

	Split Features (ArcGIS)

* Select one of the options in the ‘Process’ list.
* Click on ‘Split Features’. The record will be updated and details added to the History tab for the INCID.

MapInfo
"""""""

To perform a physical split:

* Set the Cosmetic layer as ‘Editable’ and draw the feature to split by.

.. Tip:: The Cosmetic layer should be used due to the time required for MapInfo to add a new feature to the full HLU layer.

* Set the HLU layer as ‘Editable’.
* Select the feature to be split and go to Objects > Set Target.
* Select the polygon in the Cosmetic layer and go to Objects > Split.
* In the Data Disaggregation box, ensure that ‘Method’ for all fields is set to ‘Value’ as shown in the figure :ref:`figMIDD`, then click OK.

.. _figMIDD:

.. figure:: ../images/figures/MapInfoDataDisaggregationDialog.png
	:align: center

	Data Disaggregation Dialog (MapInfo)

* The feature will be split but still selected as shown in :ref:`figMISF`. Return to the HLU GIS Tool and click ‘Get Map Selection’.

.. _figMISF:

.. figure:: ../images/figures/MapInfoSplitFeaturesDiagram.png
	:align: center

	Split Features (MapInfo)

* Select one of the options in the ‘Process’ list.
* Click on ‘Split Features’. The record will be updated and details added to the History tab for the INCID. The Cosmetic layer will be cleared.

.. note::

	* Only one feature should be split in a single operation. Splitting multiple features will cause database synchronisation issues. 
	* If several features have been split, select the fragments for one original feature and split using the tool. Repeat this operation for the remaining features.
	* Ensure that the physical split is completed in the database prior to commencing any other operations such as ‘Select by attributes…’ to avoid database synchronisation issues.


.. index::
	single: merge

Merge Features
--------------

Merge features will performs two types of merge depending upon the filter active in the tool. If two or more features from multiple INCIDs are present in the current filter then the tool will perform a logical merge. If two or more fragments from the same TOID and with different TOID_Fragment_Ids are present in the current filter then the tool will perform a physical merge.

.. index::
	single: Logical merge

Logical Merge
^^^^^^^^^^^^^

Logical merge combines all the features selected in the GIS into a single INCID chosen from from the selected features. This assigns the attributes from the chosen INCID to all the other selected features and logically groups the features into a single INCID so that they can be updated together in the future.

To perform a logical merge:

* Click ‘Switch to GIS Window’ and select the features to be merged and a feature from the INCID they are to be merged with in the GIS layer.
* Return to the HLU main window and click ‘Get Map Selection’.
* Select one of the options in the ‘Process’ list.
* Click on ‘Merge Features’. A list of INCIDs will be displayed as shown in the figure :ref:`figLMD`.

.. _figLMD:

.. figure:: ../images/figures/LogicalMergeDialog.png
	:align: center

	Select INCID to Keep Dialog

* Click on the grey box to the left of the row to select an INCID. The associated feature will blink in the GIS window. Click ‘OK’.
* The selected features will be assigned to the selected INCID and details added to the History tab.
* If the merged features are fragments of the same TOID the user will be given the option to then perform a physical merge.

.. index::
	single: Physical merge

Physical Merge
^^^^^^^^^^^^^^

Physical merge combines fragments of a single TOID into a single, larger, feature in the GIS layer. As the fragments must already belong to the same INCID there are no attribute updates but the boundaries between adjacent features will be removed.

To perform a physical merge:

* Select two or more fragments from one TOID in the GIS layer as shown in the figure :Ref:`figPMD` (left).
* Return to the HLU main window and click ‘Get Map Selection’.
* Select one of the options in the ‘Process’ list.
* Click on ‘Merge Features’. The features will be combined in the GIS layer as shown in figure :Ref:`figPMD` (right).

.. _figPMD:

.. figure:: ../images/figures/PhysicalMergeDiagram.png
	:align: center

	Physical Merge – Before (left) and After (right)


.. Note:: Only fragments belonging to the same TOID can be merged in a single operation. If fragments for several TOIDs need to be merged, the operation must be repeated for each TOID.