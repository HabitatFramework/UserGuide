.. index::
	single: glossary

********
Glossary
********

.. glossary::

	Incid
		An **Inc**\ remental **id**\ entifier used as a unique reference to a logical group of one or more features. See :Ref:`incid` for more details.

	TOID
		A unique *topographical identifier* applied to features in Ordnance Survey's MasterMap product. See :Ref:`mastermap` for more details.

	Fragment ID
		An incremental number used as a unique reference to individual features (fragments) of a single TOID. See :Ref:`mastermap` for more details.

	Logical Split
		Creates a single new INCID record in the database for the features selected from an existing INCID in the GIS layer. See :Ref:`logical_split` for more details.

	Physical Split
		Creates one or more new TOID fragments in the database based upon a single TOID which has been split in the GIS layer. See :Ref:`physical_split` for more details.

	Logical Merge
		Combines all the attributes for the features selected in the GIS into a single INCID record of one of the selected features. See :Ref:`logical_merge` for more details.

	Physical Merge
		Combines two or more fragments of a single TOID into a single, larger, feature in the GIS layer. See :Ref:`physical_merge` for more details.

	Split
		The tool can perform two types of split, Logical Split or Physical Split, depending upon the filter active in the tool. See :Ref:`split` for more details.

	Merge
		The tool can perform two types of merge, Logical Merge or Physical Merge, depending upon the filter active in the tool. See :Ref:`merge` for more details.

	Export
		Combines spatial data for the selected features from GIS with the associated attribute data from the database into a single new GIS layer based upon a pre-defined export format. See :Ref:`export_window` for more details.

	Apply
		Applies any changes made by the user to all the features for the INCID in the active feature in the main window. See :Ref:`main_window` for more details.

	Bulk Update
		Enables updates to the attributes for multiple selected Incids simultaneously. See :Ref:`bulk_update_window` for more details.

	IHS
		Integrated Habitat System - a hierarchical integration of existing habitat and land use classifications used in the UK. IHS was devised by Somerset Environmental Records Centre.

	Priority Habitat
		Habitats identified as requiring action in the UK Biodiversity Action Plan (UK BAP) and continue to be regarded as conservation priorities in the UHS Post-2010 Biodiversity Framework.

	Potential Priority Habitat
		Habitat areas that are close to, but do not currently meet, Priority Habitat definitions but may do with appropriate management or following habitat restoration work.

	Vague Date
		A specific date, range of dates or imprecise date that can be specified in a variety of formats (e.g. '23 Mar 1987', 'Mar 1987 - Jun 1987', 'Spring 1987').

	Habitat Class
		One of the habitat classification systems used in the UK to record or describe an area of habitat (e.g. 'Phase 1', 'NVC', 'BAP Priority').

	Habitat Type
		The code and/or descriptive term of a habitat classification system that best represents an area of habitat (e.g. 'B312', 'CG2', 'Lowland Calcareous Grassland').

	Source
		A dataset, document or reference used as the source of habitat or land use information.

	Boundary Importance
		The relative importance of each source when determining the boundary location of all the features in an Incid (e.g. of 'Primary' or 'Secondary' importance).

	Habitat Importance
		The relative importance of each source when determining the IHS habitat and associated IHS codes for all the features in an Incid (e.g. of 'Primary' or 'Secondary' importance).

	Determination Quality

	Interpretation Quality

	Interpretation Comment

	Process
		The activity being undertaken that has lead to applying this change to the spatial or attribute data of the current Incid. May relate to a specific project (e.g. 'Grassland Inventory Updates 2008'), an ongoing process (e.g. 'SINC habitat monitoring') or an adhoc update based on new information available (e.g. 'Aerial photo interpretation').

	Reason
		The underlying explanation for the change in habitat or land use. It may be as a result of known changes in the habitat (e.g. 'Habitat loss', 'Habitat degredation', 'Habitat creation' or 'Habitat enhancement') or it may be that new information indicates the existing data is wrong or that there has been a change but the underlying the cause is unknown (e.g. 'New survey information or re-interpretation').
