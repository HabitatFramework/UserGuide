************
Introduction
************

Background
==========

Since the introduction of the Integrated Habitat System (IHS) and the adoption of the habitat data standards introduced from the South-West pilot project there are now over 50 attributes for every recorded habitat feature (point, line or polygon). These attributes relate to each feature's IHS classification, source information, priority habitats, quality, modification history, etc. Furthermore, as valid values for many of these attributes are limited to specific options, and many are inter-related and dependent upon other values, maintaining habitat data has become complex and time-consuming. And if users only have native GIS application functionality to support them (i.e. a GIS layer with a standard attribute table) the likelihood of errors and inconsistencies being introduced is high.

The subsequent incorporation of the Ordnance Survey MasterMap boundaries and TOIDs into existing habitat datasets brought improved positional accuracy to the data, and in many cases also provided additional habitat and land-use source information. However, new datasets have significantly increased in volume with some county-wide datasets now containing over 2 million habitat features, with each feature having over 50 attributes. As a result the attributes and evidence-base required for habitat and land use information has grown so much in recent years that it is no longer practical to store or maintain the data in a standard GIS layer.

.. raw:: latex

	\newpage

Proposed solution
=================

In 2009 exeGesIS Ltd was engaged to develop a new GIS-based application to manage habitat and land use data based upon an OS MasterMap framework. It was funded by the Local Record Centres (LRCs) in the South East of England in partnership with Natural England.

One of the key requirements for the tool was the ability to use multiple GIS and database environments, so it was designed to be compatible with both ArcGIS and MapInfo and multiple databases including SQLServer or MS Access. In principle other database systems such as PostgreSQL and Oracle can be supported but these have not been tested.

The application needed to provide a user interface between the spatial data data held in GIS and the attribute data held in a relational database, maintaining changes to both the attributes and the spatial data. It also had to provide an audit trail to indicate when data was last edited, why and by whom.

.. raw:: latex

	\newpage

Data structure
==============

Spatial data
------------

The Habitat and Land Use (HLU) spatial data consists of one or more GIS layers containing features (points, lines or polygons). These features are combined with Ordnance Survey (OS) Mastermap features so that each HLU feature is aligned with the points, lines and boundaries of OS Mastermap. Features may not extend across or beyond OS Mastermap lines or boundaries but they can sub-divide features by splitting them into smaller fragments. A unique reference to the original OS Mastermap feature, known as a TOID (see :ref:`mastermap_framework`) is assigned to every HLU feature so that the original lines or boundaries of the OS Mastermap features can be re-established by merging features with the same TOID.

Whilst there are benefits to splitting the HLU features by OS Mastermap, such as ensuring polygon boundaries are accurate and do not overlap, the splitting process significantly increases the volume of data. For example, the table below indicates the effect of splitting on a 500 feature GIS layer.

.. tabularcolumns:: |L|R|R|

.. table:: Effect of OS Mastermap Split (Single Dataset)

	+------------+------------------------+------------------------------+
	|            | Original habitat layer | HLU layer split by Mastermap |
	+============+========================+==============================+
	| Features   | 500                    | 16,750                       |
	+------------+------------------------+------------------------------+
	| Attributes | 40,000                 | 1,340,000                    |
	+------------+------------------------+------------------------------+
	| Total      | 40,500                 | 1,356,750                    |
	+------------+------------------------+------------------------------+

So, in this example, there are 33.5 Mastermap-derived features in the new HLU dataset for each original habitat feature.

Attribute data
--------------

Due to the complexity of the attribute data required whilst simultaneously wishing to minimise data duplication and reduce dataset volume, the habitat attribute and spatial data were separated into a relational database with an associated GIS layer. Separating the attribute and spatial data reduced the number of attributes required for the spatial layer to only 6 (instead of the original 50+). This offers a significant reduction in the total number of attributes held in the GIS layer (as shown in the table below).

.. tabularcolumns:: |L|R|R|

.. table:: Effect of OS Mastermap Split (Attribute and Spatial Datasets)

	+-----------------------+------------------------+----------------------------+
	|                       | Original habitat layer | HLU attribute database and |
	|                       |                        | | associated GIS Layer     |
	+=======================+========================+============================+
	| HLU Records           | 500                    | 500                        |
	+-----------------------+------------------------+----------------------------+
	| HLU Attributes [1]_   | 25,000                 | 25,000                     |
	+-----------------------+------------------------+----------------------------+
	| Spatial Features [2]_ |                        | 16,750                     |
	+-----------------------+------------------------+----------------------------+
	| Spatial Attributes    |                        | 100,500                    |
	+-----------------------+------------------------+----------------------------+
	| Total                 | 25,500                 | 142,750                    |
	+-----------------------+------------------------+----------------------------+

The attribute data is stored in a ‘normalised’ relational structure which enables the attributes to be retrieved and maintained in a very logical way whilst simultaneously reducing the data storage requirements and improving the data structure and integrity.

.. [1] Assuming 50 attributes per feature.
.. [2] Assuming an average of 33.5 Mastermap-derived HLU features per original habitat feature.

.. raw:: latex

	\newpage

Benefits of the HLU Tool
========================

The tool provides a user-friendly and efficient interface enabling users to search, display and update the complex set of habitat and land use attributes held in the relational database whilst the spatial features are displayed in a GIS application. It provides a number of direct benefits and indirect benefits, including:

1. Ensuring that all attributes selected by users are valid and compatible (e.g. IHS complex codes are relevant for the selected habitat code).
2. Maintaining a brief but comprehensive history of all changes made to every habitat polygon.
3. Enabling management queries and statistics to be produced for a range of purposes using the relational database (e.g. the extent and reason for all priority habitat gains/losses in the last financial year).
4. Storing the data in a relational structure to reduce GIS data volumes and provide access efficiencies and flexibility.
5. Enabling data to be extracted in an number of formats, including the National Inventory dataset format, as broad habitat layers or as priority habitat layers.
6. Ensuring that all local datasets can be readily combined into regional or national datasets and direct comparisons can be made between local datasets.
7. Improved data retrieval/update response times which would otherwise be unacceptable directly in GIS given the volume and complexity of the underlying data.

