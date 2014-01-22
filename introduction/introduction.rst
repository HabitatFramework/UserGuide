============
Introduction
============

In August 2009 Hampshire Biodiversity Information Centre (HBIC) awarded exeGesIS SDM the contract to develop a new toolkit which would manage their Habitat and Land Use spatial data. The new toolkit would be used by HBIC and Local Record Centres in the South-East of England, and therefore needed to be compatible with both ArcGIS and MapInfo.

The Habitat and Land Use (HLU) data consisted of a set of habitat polygons. Each habitat polygon had approximately 80 attributes. The decision was taken by Local Records Centres to split these habitat polygons into Ordnance Survey (OS) Mastermap derived polygons.

Whilst there are benefits to splitting the habitat polygons by OS Mastermap, such as ensuring polygon boundaries are accurate, the splitting process significantly increases the volume of data. On average, there are 33.5 Mastermap-derived polygons for each habitat polygon in the HLU data.

For example, :ref:`Table 1: Effect of OS Mastermap Split (Single Dataset)` indicates the effect on a 500 polygon dataset if the data was held in a single GIS layer.

.. table:: Table 1: Effect of OS Mastermap Split (Single Dataset)

	+------------+----------+--------------------+
	|            | Original | Split by Mastermap |
	+============+==========+====================+
	| Polygons   | 500      | 16,750             |
	+------------+----------+--------------------+
	| Attributes | 40000    | 1,340,000          |
	+------------+----------+--------------------+
	| Total      | 40,500   | 1,356,750          |
	+------------+----------+--------------------+

Due to the complexity of the attribute data required by the Local Records Centres and to minimise data duplication, the habitat attribute and spatial data were split into a relational database with an associated GIS layer. Splitting the attribute and spatial data, reduces the number of attributes required for the spatial layer to 6.

This offers a significant reduction in total attributes as shown in :ref:`Table 2: Effect of OS Mastermap Split (Attribute and Spatial Datasets)`. Nevertheless, there is still a significant increase in data volume versus the original HLU dataset.

.. table:: Table 2: Effect of OS Mastermap Split (Attribute and Spatial Datasets)

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


.. table:: Test
	|   | Original | Final |
	| < | >>>>>>>> | ##### |
	+---+----------+-------+
	| a |        1 |   100 |
	| b |        2 |   200 |
	|   |          |       |


