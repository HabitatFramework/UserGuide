.. index::
	single: Key Concepts

********
Concepts
********

.. index::
	single: MasterMap Framework
	see: Topographical identifier; TOID
	see: Fragment; TOID_Fragment_ID

.. _data_structure:

Data Components
===============

Due to the number and complexity of data attributes and the need to minimise data duplication and reduce data volumes the spatial data and attribute data are separated into separate components. The HLU Tool provides an interface that links the spatial and attribute data and presents them to the user as a single entity.

Spatial Data
------------
The spatial data is stored in one or more GIS layers together with a minimal set of attributes that uniquely identifies and summarises each spatial feature. Separating the spatial data from the attribute data reduces the number of attributes required for the spatial layer which improves performance in the GIS application.

Attribute Data
--------------
The attribute data is stored in a relational database in a 'normalised' relational structure (i.e. groups of related attributes are divided into smaller, separate tables and relationships are defined between the tables). A normalised relational database enables the attributes to be retrieved and maintained in a very logical, and universal, way whilst simultaneously reducing the data storage requirements and improving the data structure and integrity.


.. _habitat_framework:

Habitat Framework
=================

Although most habitat surveys performed in the last 20 years are typically available as GIS layers, the spatial accuracy of the feature boundaries can be very variable. The quality will typically depend upon a range of factors, such as:

	* The quality of the original field survey maps and notes.
	* The scale and age of the base digital mapping.
	* The quality and age of any aerial photography layers.
	* The skill and patience of the GIS user digitising the data.

This variability can make it very difficult to combine habitat layers and to compare changes between surveys from different years. Moreover, unless the GIS user was very skilled or geospatial topology [2]_ was employed there will be overlaps and gaps between features which can bring problems when using the data in spatial or statistical queries.

.. [2] Geospatial topology is the arrangement for how point, line, and polygon features share geometry and is often used to define and enforce data integrity rules (e.g. no gaps should exist between polygons, there should be no overlapping features, etc).

One solution to these problems is to integrate all the habitat layers into a single framework based on Ordnance Survey's MasterMap dataset. MasterMap is the largest scale national mapping produced by the Ordnance Survey and provides highly detailed and seamless coverage.

All OS MasterMap features have a Topographic Identity or 'TOID' that uniquely identifies each object. OS MasterMap Topographic Area features also have a number of attributes (chiefly the Descriptive Group and Descriptive Term) that provide information about the real world object that the feature represents and these can provide basic habitat and land use information that can supplment any available habitat survey data.

Apart from the spatial representation of the features, the habitat framework only retains the TOID from OS MasterMap because all other attributes can be retrieved using this if necessary. Where OS MasterMap features need to be sub-divided into smaller units in order to represent habitat survey details that are not already shown these still retain the original TOID but are also assigned a fragment identifier so that each fragment can be uniquely identified.


.. _incid:

INCremental IDentifier (INCID)
==============================

Every feature in the GIS layer, and associated attributes in the relational database, is assigned to an INCID (\ **INC**\ remental **ID**\ entifier). An INCID can be thought of as a logical grouping of features that share a common set of attributes and are spatially related (i.e. neighbouring or proximate) [3]_. Each INCID can relate to one or more features. Grouping features with common attributes in this way reduces the number of database records required and allows the features and their attributes to all be maintained together.

In order to amend the attributes for one or more features in a larger group of features (i.e. in the same INCID as other features) without updating the remaining features, the features must first be split into their own logical grouping - i.e. they must be assigned to a new INCID (see :ref:`logical_split` for more details.)

Similarly, features from different INCIDs that are actually related and should share the same common set of attributes can be merged into the same INCID (see :ref:`logical_merge` for more details.)

.. [3] Features in the same INCID do not have to be adjacent but it is recommended that they are at least spatially associated with one-another (e.g. they are within the same site or either side of the same road/railway).


.. raw:: latex

	\newpage

.. index::
	single: Priority Habitats

.. _priority_habitats:

Priority Habitats
=================

Some IHS Habitat and some multiplex codes (Formation, Management and Complex codes) are equivalent to, or more distinct than, priority habitats [4]_. When any such codes are selected in the main window :ref:`habitats_tab` the tool automatically adds the associated priority habitats to the 'Priority Habitats' section of the :ref:`details_tab`.

However, if priority habitat associated codes are changed or removed in the :ref:`habitats_tab` the tool does **not** automatically remove existing priority habitats from the 'Priority Habitats' section of the :ref:`details_tab`. Instead they are moved to the 'Potential Priority Habitats' section and the :ref:`determination_quality` is set to 'Previously present, but may no longer exist'.

.. note::
	Existing priority habitats that have been automatically moved to the 'Potential Priority Habitats' section but are no longer required must be deleted by the user (see :ref:`details_tab`.)

.. [4] Priority habitats are habitats identified as requiring action in the UK Biodiversity Action Plan (UK BAP) and continue to be regarded as conservation priorities in the UK Post-2010 Biodiversity Framework.


.. index::
	single: Potential Priority Habitats

.. _potential_priority_habitats:

Potential Priority Habitats
---------------------------

If a habitat area is close to, but does not currently meet, the definition of a priority habitat (but may do so with appropriate management or following habitat restoration work) then the appropriate priority habitat can be added to the 'Potential Priority Habitats' section of the :ref:`details_tab` with the :ref:`determination_quality` set to 'Not present but close to definition'.

If a priority habitat was known to have been present but it may no longer exist then it can be added to the 'Potential Priority Habitats' section of the :ref:`details_tab` with the :ref:`determination_quality` set to 'Previously present, but may no longer exist'.


.. index::
	single: Determination Quality

.. _determination_quality:

Determination Quality
---------------------

Every priority habitat and potential priority habitat must be assigned a determination quality. This categorises the accuracy with which the priority habitat has been determined and can be very useful when there is not a direct translation between the IHS habitat or multiplex codes and the priority habitat, or when the original survey source(s) are not as spatially accurate as the OS MasterMap features in the framework and hence there is some uncertainty of the exact position of the priority habitat.

.. tabularcolumns:: |L|C|

.. table:: Determination Quality values and usage

	+----------------------------------------------------------+----------------------------+
	|                  Determination Quality                   |         Usage              |
	+==========================================================+============================+
	| Definitely is this habitat                               | Priority Habitat           |
	+----------------------------------------------------------+----------------------------+
	| Habitat is in polygon, but not accurately mappable       | Priority Habitat           |
	+----------------------------------------------------------+----------------------------+
	| Habitat probably in polygon, but not accurately mappable | Priority Habitat           |
	+----------------------------------------------------------+----------------------------+
	| Probably is, but some uncertainty                        | Priority Habitat           |
	+----------------------------------------------------------+----------------------------+
	| Not present but close to definition                      | Potential Priority Habitat |
	+----------------------------------------------------------+----------------------------+
	| Previously present, but may no longer exist              | Potential Priority Habitat |
	+----------------------------------------------------------+----------------------------+


.. index::
	single: Interpretation Quality

.. _interpretation_quality:

Interpretation Quality
----------------------

Every priority habitat and potential priority habitat must be assigned an interpretation quality. This is selected based on an assessment of the quality of the original habitat type and it's relationship between it and the priority habitat type and also the age of the original habitat source.

.. tabularcolumns:: |L|C|C|C|

.. table:: Interpretation Quality matrix for different survey types and ages

	+------------------------------------------+-----------------------------------------+
	|               Survey Type                | Age of Survey                           |
	|                                          +---------------+------------+------------+
	|                                          | < 5 years     | 5-10 years | > 10 years |
	+==========================================+===============+============+============+
	| NVC quadrat                              | High (1)      | Medium (2) | Medium (3) |
	+------------------------------------------+---------------+------------+------------+
	| NVC rapid                                | Medium (2)    | Medium (3) | Medium (4) |
	+------------------------------------------+---------------+------------+------------+
	| Phase 1 and target notes                 | Medium (3)    | Medium (4) | Low (5)    |
	+------------------------------------------+---------------+------------+------------+
	| Phase 1 map only                         | Low (5)       | Low (5)    | Low (6)    |
	+------------------------------------------+---------------+------------+------------+
	| ESA/ SSSI site description/ species list | Medium (3)    | Medium (3) | Medium (4) |
	+------------------------------------------+---------------+------------+------------+
	| Aerial Photo, Landcover                  | Low (5)       | Low (6)    | Low (7)    |
	+------------------------------------------+---------------+------------+------------+
	| Expert knowledge of site quality         | Medium (4)    | Medium (4) | Low (5)    |
	+------------------------------------------+---------------+------------+------------+


.. _split:

Splitting Features
==================

There are two ways to split features depending upon the filter active in the tool - **logical split** and **physical split**.


.. index::
	single: Split; Logical

.. _logical_split:

Logical Split
-------------

Logical split is used to create a new INCID in the database based upon a subset of features selected from a single INCID in the GIS layer. Logically splitting one or more features assigns them to a different INCID than the other features in the current INCID which then allows them to be updated independently of the remaining features in the original INCID. 

For example, a group of adjacent permanent pasture features, each represented by a separate OS MasterMap feature, may be 'logically' grouped by being assigned to the same INCID because they share a common set of IHS codes, sources and other attributes. However, it may be discovered that one or more of the features are actually being managed differently to the remaining features. By logically splitting those features from the original INCID to form a new INCID those features can then be assigned a different IHS management code.

.. note::

	* Only if one or more features from a single INCID are present in the current filter will the tool allow a logical split to be performed.
	* The selected features must all belong to the same INCID.

.. index::
	single: Split; Physical

.. _physical_split:

Physical Split
--------------

Physical split is use to create one or more new TOID fragments in the database based upon a single TOID that has already been split in the GIS layer. Physically splitting a feature into fragments allows the fragments to be updated independently of each other (once they have also been assigned to different INCIDs - see :ref:`logical_split`.)

For example, a woodland may appear in OS MasterMap as a single feature, but compartments within the woodland may be managed differently and/or may have different characteristics. By physically splitting the woodland feature along the compartment boundaries each compartment can then be assigned to it's own INCID (by performing a logical_split) so that they can be assigned different matrix, formation and management codes.

.. note::

	* Only if two or more fragments from the same TOID and with the same TOID_Fragment_Id are present in the current filter will the tool allow a physical split to be performed.
	* Only one feature should be split in a single operation. Splitting multiple features will cause database synchronisation issues. 
	* If several features have been split, select the fragments for one original feature and split using the tool. Repeat this operation for the remaining features.
	* Ensure that the physical split is completed in the database prior to commencing any other operations such as 'Select by attributes …' to avoid database synchronisation issues.

.. caution::
	If two or more fragments from the same TOID and with the same TOID_Fragment_Id are selected in the GIS and **Get Map Selection** is clicked then the tool will recognise that the fragments must have been split by the user in the GIS layer and will **automatically** perform a physical split before displaying the attributes.

.. _merge:

Merging Features
================

There are two ways to merge features depending upon the filter active in the tool - **logical merge** and **physical merge**.

.. index::
	single: Merge; Logical

.. _logical_merge:

Logical Merge
-------------

Logical merge combines all the features selected in the GIS into a single INCID chosen from from the selected features. This assigns the attributes from the chosen INCID to all the other selected features and logically groups the features into a single INCID so that they can be updated together in the future.

.. index::
	single: Merge; Physical

.. _physical_merge:

Physical Merge
--------------

Physical merge combines fragments of a single TOID into a single, larger, feature in the GIS layer. As the fragments must already belong to the same INCID there are no attribute updates but the boundaries between adjacent features will be removed.

.. note::
	Only fragments belonging to the same TOID can be merged in a single operation. If fragments for several TOIDs need to be merged, the operation must be repeated for each TOID.


.. index::
	single: Update; Attribute Update Concept

.. _attribute_update:

Attribute Updates
=================

Attribute updates are the main mechanism for updating existing INCID details. Typically attribute changes can only be applied to one INCID at a time and any changes made are applied to the current INCID and, if any attributes changed are also held in the GIS layer (e.g. IHS Category or IHS Summary) then the changes are also applied to any features for the current INCID selected in the active GIS layer (or to all features for the current INCID if no features are selected).


.. index::
	single: Update; Bulk Update
	see: Bulk Update; 

.. _bulk_update:

Bulk Updates
============

Attribute updates can also be applied in bulk to multiple INCID records at the same time. Any changes made will be applied to all INCIDs in the active filter and will also be reflected in the active GIS layer if any attributes changed are also held in the GIS layer (e.g. IHS Category or IHS Summary).

.. note::
	This function is only available to configured users who have been given bulk update permissions. For details on configuring users see 'Lookup Tables' in the HLU Tool Technical Guide at `readthedocs.org/projects/hlutool-technicalguide <https://readthedocs.org/projects/hlutool-technicalguide/>`_.


.. index::
	single: Update; OSMM Update Concept

.. _osmm_update:

OSMM Updates
============

If the habitat framework has been externally processed against a more recent OS MasterMap (OSMM) update there may be proposed OSMM updates to review and apply. Any proposed updates are INCID specific and will appear at the top of the main interface (if one of the options to display them is configured in the user options) for the current INCID. Proposed updates can be reviewed one INCID at a time where they can either be accepted (when they become pending updates) or rejected. Pending updates can then be applied in bulk in a method similar to the bulk update process.

.. note::
	This function is only available to configured users who have been given bulk update permissions. For details on configuring users see 'Lookup Tables' in the HLU Tool Technical Guide at `readthedocs.org/projects/hlutool-technicalguide <https://readthedocs.org/projects/hlutool-technicalguide/>`_.

