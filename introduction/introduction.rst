============
Introduction
============

In August 2009 Hampshire Biodiversity Information Centre (HBIC) awarded exeGesIS SDM the contract to develop a new toolkit which would manage their Habitat and Land Use spatial data. The new toolkit would be used by HBIC and Local Record Centres in the South-East of England, and therefore needed to be compatible with both ArcGIS and MapInfo.

The Habitat and Land Use (HLU) data consisted of a set of habitat polygons. Each habitat polygon had approximately 80 attributes. The decision was taken by Local Records Centres to split these habitat polygons into Ordnance Survey (OS) Mastermap derived polygons.

Whilst there are benefits to splitting the habitat polygons by OS Mastermap, such as ensuring polygon boundaries are accurate, the splitting process significantly increases the volume of data. On average, there are 33.5 Mastermap-derived polygons for each habitat polygon in the HLU data.

For example, :ref:`Table1` indicates the effect on a 500 polygon dataset if the data was held in a single GIS layer.

.. table:: Table1
	Effect of OS Mastermap Split (Single Dataset)

	+-----------------+-------------+--------------------+
	|                 | Original    | Split by Mastermap |
	| <<<<<<<<<<<<<<< | >>>>>>>>>>> | >>>>>>>>>>>>>>>>>> |
	+=================+=============+====================+
	| Polygons        |         500 | 16,750             |
	+-----------------+-------------+--------------------+
	| Attributes      |      40,000 | 1,340,000          |
	+-----------------+-------------+--------------------+
	| Total           |      40,500 | 1,356,750          |
	+-----------------+-------------+--------------------+

Due to the complexity of the attribute data required by the Local Records Centres and to minimise data duplication, the habitat attribute and spatial data were split into a relational database with an associated GIS layer. Splitting the attribute and spatial data, reduces the number of attributes required for the spatial layer to 6.

This offers a significant reduction in total attributes as shown in :ref:`Table2`. Nevertheless, there is still a significant increase in data volume versus the original HLU dataset.



.. table:: Table2
	Effect of OS Mastermap Split (Attribute and Spatial Datasets)

	+--------------------+------------+---------------------------------------------+
	|                    | Original   | Attribute database and associated GIS Layer |
	+====================+============+=============================================+
	| HLU Records        |        500 |                                         500 |
	+--------------------+------------+---------------------------------------------+
	| HLU Attributes     |     40,000 |                                      40,000 |
	+--------------------+------------+---------------------------------------------+
	| Spatial Polygons   |            |                                      16,750 |
	+--------------------+------------+---------------------------------------------+
	| Spatial Attributes |	          |                                     100,500 |
	+--------------------+------------+---------------------------------------------+
	| Total              |     40,500 |                                     157,750 |
	+--------------------+------------+---------------------------------------------+

The HLU GIS Tool provides a user interface for maintaining the habitat and spatial data, including changes to attributes and changes to the spatial data. It also provides an audit trail to indicate when it was last edited, why and by whom.

The toolkit provides an interface that links the spatial and attribute data in multiple software environments. It can link ArcGIS and MapInfo with databases held in Access or SQL Server In principle, the toolkit could link to other database systems such as PostgreSQL and Oracle but these have not been tested and are not supported.

The performance of the tool is limited by the capabilities of third party software, particularly GIS software, which were not designed to handle large datasets split across multiple platforms.

In addition, one of the key requirements for this tool was the ability to use multiple GIS and database environments. Significant improvements in performance could have been achieved if the tool had been designed to work with a single environment e.g. ArcGIS and SQL Server but multiple environment functionality was a key requirement.

The HLU GIS Tool has been optimised as far as possible and there are no further technological enhancements that can be made to significantly improve performance. It is important therefore to ensure performance is optimised wherever possible through user operation. The following section suggests some simple approaches to improving performance.

The code for the HLU GIS Tool is ‘open source’.

Optimising Performance
----------------------
Creation of ArcGIS Map Document (.mxd) or MapInfo Workspace (.wor)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
An ArcGIS Map Document (.mxd) or MapInfo Workspace (.wor) must be created for use with the HLU GIS Tool. This should be optimised to ensure maximum performance, which should include the following:

