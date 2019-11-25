********
Appendix
********

.. index::
    single: Change Log

.. _change_log:

Change Log
==========

3.1.1
    Fixes
        * Fix084 - No longer find first habitat type on change in IHS habitat.

3.1.0
    Additions
        * CR54 (Show/edit priority habitats) - New pop-out windows to more clearly display/edit priority and potential priority habitats.
        * CR52 (Multiple priority habitat classifications) - Major enhancement to enable multiple priority and potential priority habitat classifications to be supported.
        * CR56 (Translation to IHS non-habitat codes) - Major enhancement to validate that any mandatory or recommended multiplex codes relating to the current habitat type have been selected.

3.0.2
    Fixes
        * Fix081 - Enable a subset of features for each selected INCID to be exported.
        * Fix083 - Ensure predicted count of toids/fragment selected works with any filter query.
          
3.0.1
    Fixes
        * Fix082 - Check if any OSMM updates before enabling review and bulk update functionality.

3.0.0
    Additions
        * Fix068 - New command in the main interface to enable auto zoom when selecting features for an incid in GIS.
        * Fix069 - New command in the main interface to enable auto select of features in GIS when moving to a new incid.
        * Fix071 - A user option to set the minimum zoom scale for when zooming to selected features in GIS.
        * Fix072 - A simple query filter window to search for a single INCID.
        * Fix073 - New command in the main interface to reset the window dimensions to their default values (in case a user has resized the window manually).
        * Fix076 - A user option to hide the group headers in main interface to reduce window height on small monitors.

    Changes
        * CR49 (Process bulk OSMM Updates) - Major enhancement to display and process and proposed OSMM updates.
        * Fix070 - Improvements to 'zoom to selected features' functionality to only zoom if the selected features don't already appear within the current map window extent.
        * Fix074 - Save the option to keep the main tool interface on top of other windows (previously this would have to be set each time the tool was started).
        * Fix075 - Ensure than filtered records are always displayed in INCID order.
        * Fix078 - Major overhaul/improvements to the bulk update functionality including a new interface before applying update to confirm how to handle existing multiplex codes, sources and priority habitats.
        * Fix079 - Updated 'About' window layout including links to online user and technical guides.

    Fixes
        * KI116 (Cancelled attribute updates) - Fixes bug when cancelled updates to a subset of INCID features were still applied when moving to another INCID.
        * KI117 (Bulk update errors) - Not specifically fixed but unable to reproduce errors following major overhaul/improvements (see Fix078).
        * Fix077 - Correctly trap the error if the database requires a later version of the started application (previously this error went unreported before the application closed).
        * Fix080 - Fix bug where changes to text fields in user options were not being saved when <Enter> key was pressed to save changes.

2.4.3
    Fixes
        * Fix067 - Select features in the active HLU layer directly (rather than via a selection set) to avoid problems during export later. This relates to ArcGIS installations only and only affects queries performed using the HLU tool that select a large number of features.

2.4.2
    Changes
        * Fix064 - Perform exports outside of edit sessions (in ArcGIS) to improve performance and reduce the memory usage when changes are saved at the end of the edit session.
        * Fix065 - Prompt the user for the export GIS layer name before starting export (rather than only once the attributes have been saved to a temporary database).
        * Fix066 - Improve the performance when exporting the attributes to a temporary database.

    Fixes
        * Fix063 - Apply the user option database connection timeout value rather than the fixed value of 15 seconds.

2.4.1
    Changes
        * Fix061 - Enable the tool to work with all 32bit versions of MapInfo (including MapInfo 15.0).
        * Fix062 - Enable tool to run in a multi-user virtual environment without needing to close all running instances of MapInfo first.


2.4.0
    Additions
        * CR44 (Editable Legacy Habitat field) - Make the legacy habitat field editable in the user interface with a drop-down menu of available values from the new 'lut_legacy_habitat' table.
        * Fix056 - Add a new option 'Show NVC Codes' to enable related NVC Codes to be shown or hidden in the user interface 'Habitats' tab.
        * Fix058 - Display the current database connection details in 'About' dialog.

    Changes
        * Fix059 - Do not display the map window number after the current layer name if there is only one map window in the GIS application.
        * Fix060 - Disable the switch GIS layer button and menu item if there is only one valid layer in the current GIS document/workspace.

    Fixes
        * Fix057 - Adjust the user interface window height correctly when showing/hiding the optional areas (NVC Codes & Reason/Process fields).

2.3.3
    Fixes
        * Fix052 - Ensure 'Get Map Selection' works in MapInfo when the selection is based on joining two or more tables.
        * Fix053 - Check if all selected features have unique keys in the active HLU layer to avoid any potential data integrity problems caused by splitting/merging when a physical split has not been completed.
        * Fix054 - Improvement to error reporting during the export process.
        * Fix055 - Enable connection via OLEDB to Access 2007 (.accdb) databases using Microsoft Access Database Engine (ACE) driver.

2.3.2
    Fixes
        * CR43 (Sort multiple fields in exports) - Fix an error when exports fail if the selected format includes the **source\_id** field from the **incid_sources** table with a *field\_format* of 'Lookup' or Both'.

2.3.1
    Additions
        * CR43 (Sort multiple fields in exports) - Sort all records from incid-related 'child' tables so that multiple fields will always appear in the same order in exported layers.

    Changes
        * Fix051 - Improve performance when filtering large number of incids.

2.3.0
    Additions
        * CR14 (Exporting IHS codes or descriptions) - Enable users to specify if individual fields should be exported with descriptions instead of codes by specifying a **field\_format** value of 'Code' or 'Lookup' in the exports_fields table.
        * CR15 (Concatenate IHS codes and descriptions) - Enable users to specify if individual fields should be exported with **both** codes and descriptions concatenated together by specifying a **field\_format** value of 'Both' in the exports_fields table.
        * CR16 (Adding exported features) - Ask users if they want to add the new GIS layer to the active map once the export has completed.
        * CR17 (Exporting date fields) - Enable **incid\_source** dates to be converted into a specific text date format by specifying a **field\_format** value (e.g. 'dd/MM/yyyy') in the exports_fields table.
        * Fix034 - Enable auto-increment fields to be included in export layers by specifying a **field\_type** of 99 (AutoNumber) in the exports_fields table.
        * Fix037 - Move the geometry length and area fields to the **end** of the list of fields for all export layers.
        * Fix038 - Display the export progress in the ArcGIS status bar correctly during an export.
        * Fix040 - Enable MapInfo users to set a default export folder path in the user options.
        * Fix042 - Warn users when an export may take some time because it is very large (i.e. exceeds 5000 incids).
        * Fix043 - Enable new 'dummy' fields to be included in export formats by specifying **table\_name** and **column\_name** values of '<none>' in the exports_fields table.
        * Fix044 - Enable maximum text field lengths to be specified in export formats by specifying a **field\_length** value in the exports_fields table.
        * Fix045 - Interweave multiple record fields from the same database table together (e.g. s1name, s1class, s1type, s2name, s2class, s2type, s3name, s3class, s3type).
        * Fix048 - Enable fields to be converted to a different data type in an export by specifying a **field\_type** in the exports_fields table.
        * Fix049 - Enable the multi-record counter to be inserted 'within' the export format **field\_name** (e.g 'source1name' by specifying 'source<no>name').
        * Fix050 - Warn ArcGIS users if export format **field\_names** may be truncated or renamed when exporting to shapefiles (which only support 10 character names).

    Changes
        * CR13 (Export features performance) - Improvements to 'Export' performance for small numbers of incids/features by saving selected features to a temporary GIS layer before joining to the database attributes.

    Fixes
        * Fix033 - Ignore case during export when comparing field names in the feature layer and database attributes to avoid duplicate fields in the export layer.
        * Fix035 - When 'Selected Only' checked only export **selected** features in GIS not **all** features for selected the incids.
        * Fix036 - Clear all missing/empty fields when exporting features with ArcGIS to avoid values from preceding records from being exported.
        * Fix039 - Check export layers won't exceed the MapInfo maximum record length (4000 bytes) or maximum .tab file size (2 Gb).
        * Fix041 - Check the selected export format contains the incid column to avoid errors trying to join the attribute data to the GIS layer.
        * Fix046 - Don't repeat details from the same *incid\_source** record in multiple source export fields when there are less than 3 source records.
        * Fix047 - Break the process of exporting database attributes into chunks to avoid errors with excessive SQL query lengths.

2.2.0
    Additions
        * CR5 (Select by Attribute Interface) - Added a new 'Advanced Query Builder' interface which allows users to build, verify, save and load free-form SQL queries. Check 'User Advanced Query Builder' in the options settings to use the new interface.
        * Fix032 - Added a new button/menu 'Select all Filtered INCIDs on Map' to enable users to select **all** of the incids in the active filter on map, not just the current incid.

    Changes
        * CR12 (Select by attributes performance) - Improvement to 'Select by Attribute' performance (now known as 'Filter by Attributes'). Where possible execute more complex SQL queries (up to a GIS-specific maximum SQL string length) instead of using GIS table joins.

2.1.1
    Additions
    * KI15 (User Interface style) - Enable the user to select any of three user interface styles (Original, Dark Grey & Light Grey).
    * CR37 (Site reference& site name) - Add the site reference field to the user interface to enable the user to view/edit the value relating to the current INCID.
    * CR39 (Split and merge complete messages) - Enable users to specify in the options if a pop-up message should be displayed following any of the split or merge operations.

    Removals
        * CR27 (Select current INCID) - Remove the 'Select by INCID' menu item and toolbar button as it serves no known purpose.

    Changes
        * CR7 (Split/merge options) - Display all four split and merge options on the menu bar and button toolbar and enable only the available options for the current selection.
        * CR11 (History tab) - Change the field names on the history tab to make it clearer the history refers to previous or modified value, not the current values).
        * CR20 (Window size/design) - Adjust the layout of the window to reduce the minimum height so support smaller screen resolutions.
        * CR25 (Reason and process fields) - Do not display the reason and process fields sub-section of the user interface when the tool is in read-only mode.
        * CR28 (INCID display field) - Enable the user to select the text in the INCID field and copy the value to the clipboard.
        * CR38 (Logical merge prompt window) - Widen the default 'Select INCID to keep' window width so that more attributes initially appear.

    Fixes
        * Fix031 - Fix crash by checking if the value of any 'editable' combobox is NULL before finding the text in the drop-down list.
        * CR2 (Apply button) - Changes to the 'IHS Habitat' field now trigger the 'Apply' button to be enabled.  The automatic selection of a source 'Habitat Type' when a 'Habitat Class' with only one possible Habitat Type is selected, disabled by CR2 in release v1.0.9, has now been re-instated.

2.1.0
    Additions
        * CR42 (Database upgrade kit) - A new standalone program 'HluDbUpdater.exe' has been created which runs sql scripts to apply database structure and/or content changes to any target HLU Tool database.  See [HLU Database Updater](https://github.com/HabitatFramework/HLUTool-DatabaseUpdater/releases) for the latest version of the program.

    Removals
        * CR29 (Habitat classification and code conversion to IHS) - the NVC Codes field has been removed temporarily as there is currently no space to display it. It can be reinstated in a future release if required when space allows.

    Changes
        * CR30 (Database validation on start-up) - Update database validation to reflect updates to the database structure and also check that the tool is not already running on the same machine.
        * CR29 (Habitat classification and code conversion to IHS) - Replace the IHS Category and NVC Category drop-down lists with new Habitat Classification and Habitat Type drop-down lists to provide users with ability to translate different input sources to IHS.
        * CR32 (Local flags) - Enable users to flag habitat classifications and habitat types as 'local' to indicate if they should appear in the relevant drop-down lists in the user interface.

    Fixes
        * Fix025 - Add a default sort order when loading all lookup tables to act as a backup sort order if the sort_order columns are zero (or all the same values).
        * Fix026 - Hide the MapInfo pop-up progress bar when updating tables and merging features.
        * Fix027 - Force the Incid table to be refilled after any split/merge processing to ensure that any updates updates immediately following don't fail.
        * Fix028 - Only update DateTime fields to whole seconds (ignoring fractions of a second) to avoid rounding differences when comparing fields during updates.
        * Fix029 - Ignore case when comparing column names in MapInfo to ensure all features are re-selected following a physical split.
        * Fix030 - Include time with date when updating DateTime fields in databases via ODBC connection type.


.. raw:: latex

    \newpage

.. index::
	single: Dos and Don'ts

.. _dos_and_donts:

DOs and DON'Ts
==============

It is essential that the following guidelines are followed to ensure that the tool runs smoothly:

**DOs:**

	* :strong:`DO` close all instances of MapInfo before launching the tool as the tool may try and communicate with the wrong instance of MapInfo.
	* :strong:`DO` close all instances of ArcGIS before launching the tool. Unlike with MapInfo, the tool will automatically communicate with the correct instance of ArcGIS, however multiple instances will require more memory and may therefore affect tool performance.
	* :strong:`DO` use a file geodatabase or personal geodatabase to store spatial information (ArcGIS users only).

**DO NOTs:**

	* :strong:`DO NOT` remove the HLU layer from the map while the tool is running.
	* :strong:`DO NOT` close the associated GIS while the tool is running, otherwise the tool will display an error message.
	* :strong:`DO NOT` create or open another map document or workspace in the associated GIS window while the tool is running.
	* :strong:`DO NOT` use a shapefile as this affects performance (ArcGIS users only).


.. note::

	New in version 1.0.7:
	
	* It is now possible to use a HLU GIS layer containing only a subset of all the INCIDs in the HLU database.
	* It is also possible to switch between different HLU GIS layers present in the open document or workspace using the *Switch GIS layer* function.


.. raw:: latex

	\newpage

.. index::
	single: What Happened

.. _what_happened:

What Happened?
==============

* ArcGIS generates a 'hard error' when the HLU Tool is used.

	* Solution 1:	The HLU ArcMap extension has not been enabled. Close and relaunch the tool, then enable the extension in ArcMap before using the tool.
	* Solution 2: 	ArcGIS has been closed while the tool was running. Close and relaunch the tool.

* The HLU Tool stops responding to GIS requests.

	* Solution 1: The HLU GIS layer is no longer active in the map or MapInfo has been closed while the tool was running. Close and relaunch the tool.

* The HLU Tool communicates with the wrong instance of the GIS software.

	* Close all GIS instances except the one associated with the HLU Tool. To avoid this issue, ensure all instances of ArcGIS or MapInfo are closed before launching the tool and do not open any additional instances whilst the tool is running. 

* The Bulk Update tool errors and fails to create history if the bulk update is applied to database records which do not have corresponding polygons in the HLU layer. 

	* Ensure that the database and map layer are kept in sync so this situation does not occur.


.. raw:: latex

	\newpage

GNU Free Documentation License
==============================

Permission is granted to copy, distribute and/or modify this document under 
the terms of the GNU Free Documentation License, Version 1.3 or any later
version published by the Free Software Foundation; with no Invariant Sections,
no Front-Cover Texts and no Back-Cover Texts.  A copy of the license is
included in the Appendix section.

.. raw:: latex

    The full GNU Free Documentation License can be viewed at `www.gnu.org/licenses/fdl-1.3.en.html <https://www.gnu.org/licenses/fdl-1.3.en.html>`_

.. only:: html

                    GNU Free Documentation License
                     Version 1.3, 3 November 2008
    
    
     Copyright (C) 2000, 2001, 2002, 2007, 2008 Free Software Foundation, Inc.
         <http://fsf.org/>
     Everyone is permitted to copy and distribute verbatim copies
     of this license document, but changing it is not allowed.
    
    0. PREAMBLE
    
    The purpose of this License is to make a manual, textbook, or other
    functional and useful document "free" in the sense of freedom: to
    assure everyone the effective freedom to copy and redistribute it,
    with or without modifying it, either commercially or noncommercially.
    Secondarily, this License preserves for the author and publisher a way
    to get credit for their work, while not being considered responsible
    for modifications made by others.
    
    This License is a kind of "copyleft", which means that derivative
    works of the document must themselves be free in the same sense.  It
    complements the GNU General Public License, which is a copyleft
    license designed for free software.
    
    We have designed this License in order to use it for manuals for free
    software, because free software needs free documentation: a free
    program should come with manuals providing the same freedoms that the
    software does.  But this License is not limited to software manuals;
    it can be used for any textual work, regardless of subject matter or
    whether it is published as a printed book.  We recommend this License
    principally for works whose purpose is instruction or reference.
    
    
    1. APPLICABILITY AND DEFINITIONS
    
    This License applies to any manual or other work, in any medium, that
    contains a notice placed by the copyright holder saying it can be
    distributed under the terms of this License.  Such a notice grants a
    world-wide, royalty-free license, unlimited in duration, to use that
    work under the conditions stated herein.  The "Document", below,
    refers to any such manual or work.  Any member of the public is a
    licensee, and is addressed as "you".  You accept the license if you
    copy, modify or distribute the work in a way requiring permission
    under copyright law.
    
    A "Modified Version" of the Document means any work containing the
    Document or a portion of it, either copied verbatim, or with
    modifications and/or translated into another language.
    
    A "Secondary Section" is a named appendix or a front-matter section of
    the Document that deals exclusively with the relationship of the
    publishers or authors of the Document to the Document's overall
    subject (or to related matters) and contains nothing that could fall
    directly within that overall subject.  (Thus, if the Document is in
    part a textbook of mathematics, a Secondary Section may not explain
    any mathematics.)  The relationship could be a matter of historical
    connection with the subject or with related matters, or of legal,
    commercial, philosophical, ethical or political position regarding
    them.
    
    The "Invariant Sections" are certain Secondary Sections whose titles
    are designated, as being those of Invariant Sections, in the notice
    that says that the Document is released under this License.  If a
    section does not fit the above definition of Secondary then it is not
    allowed to be designated as Invariant.  The Document may contain zero
    Invariant Sections.  If the Document does not identify any Invariant
    Sections then there are none.
    
    The "Cover Texts" are certain short passages of text that are listed,
    as Front-Cover Texts or Back-Cover Texts, in the notice that says that
    the Document is released under this License.  A Front-Cover Text may
    be at most 5 words, and a Back-Cover Text may be at most 25 words.
    
    A "Transparent" copy of the Document means a machine-readable copy,
    represented in a format whose specification is available to the
    general public, that is suitable for revising the document
    straightforwardly with generic text editors or (for images composed of
    pixels) generic paint programs or (for drawings) some widely available
    drawing editor, and that is suitable for input to text formatters or
    for automatic translation to a variety of formats suitable for input
    to text formatters.  A copy made in an otherwise Transparent file
    format whose markup, or absence of markup, has been arranged to thwart
    or discourage subsequent modification by readers is not Transparent.
    An image format is not Transparent if used for any substantial amount
    of text.  A copy that is not "Transparent" is called "Opaque".
    
    Examples of suitable formats for Transparent copies include plain
    ASCII without markup, Texinfo input format, LaTeX input format, SGML
    or XML using a publicly available DTD, and standard-conforming simple
    HTML, PostScript or PDF designed for human modification.  Examples of
    transparent image formats include PNG, XCF and JPG.  Opaque formats
    include proprietary formats that can be read and edited only by
    proprietary word processors, SGML or XML for which the DTD and/or
    processing tools are not generally available, and the
    machine-generated HTML, PostScript or PDF produced by some word
    processors for output purposes only.
    
    The "Title Page" means, for a printed book, the title page itself,
    plus such following pages as are needed to hold, legibly, the material
    this License requires to appear in the title page.  For works in
    formats which do not have any title page as such, "Title Page" means
    the text near the most prominent appearance of the work's title,
    preceding the beginning of the body of the text.
    
    The "publisher" means any person or entity that distributes copies of
    the Document to the public.
    
    A section "Entitled XYZ" means a named subunit of the Document whose
    title either is precisely XYZ or contains XYZ in parentheses following
    text that translates XYZ in another language.  (Here XYZ stands for a
    specific section name mentioned below, such as "Acknowledgements",
    "Dedications", "Endorsements", or "History".)  To "Preserve the Title"
    of such a section when you modify the Document means that it remains a
    section "Entitled XYZ" according to this definition.
    
    The Document may include Warranty Disclaimers next to the notice which
    states that this License applies to the Document.  These Warranty
    Disclaimers are considered to be included by reference in this
    License, but only as regards disclaiming warranties: any other
    implication that these Warranty Disclaimers may have is void and has
    no effect on the meaning of this License.
    
    2. VERBATIM COPYING
    
    You may copy and distribute the Document in any medium, either
    commercially or noncommercially, provided that this License, the
    copyright notices, and the license notice saying this License applies
    to the Document are reproduced in all copies, and that you add no
    other conditions whatsoever to those of this License.  You may not use
    technical measures to obstruct or control the reading or further
    copying of the copies you make or distribute.  However, you may accept
    compensation in exchange for copies.  If you distribute a large enough
    number of copies you must also follow the conditions in section 3.
    
    You may also lend copies, under the same conditions stated above, and
    you may publicly display copies.
    
    
    3. COPYING IN QUANTITY
    
    If you publish printed copies (or copies in media that commonly have
    printed covers) of the Document, numbering more than 100, and the
    Document's license notice requires Cover Texts, you must enclose the
    copies in covers that carry, clearly and legibly, all these Cover
    Texts: Front-Cover Texts on the front cover, and Back-Cover Texts on
    the back cover.  Both covers must also clearly and legibly identify
    you as the publisher of these copies.  The front cover must present
    the full title with all words of the title equally prominent and
    visible.  You may add other material on the covers in addition.
    Copying with changes limited to the covers, as long as they preserve
    the title of the Document and satisfy these conditions, can be treated
    as verbatim copying in other respects.
    
    If the required texts for either cover are too voluminous to fit
    legibly, you should put the first ones listed (as many as fit
    reasonably) on the actual cover, and continue the rest onto adjacent
    pages.
    
    If you publish or distribute Opaque copies of the Document numbering
    more than 100, you must either include a machine-readable Transparent
    copy along with each Opaque copy, or state in or with each Opaque copy
    a computer-network location from which the general network-using
    public has access to download using public-standard network protocols
    a complete Transparent copy of the Document, free of added material.
    If you use the latter option, you must take reasonably prudent steps,
    when you begin distribution of Opaque copies in quantity, to ensure
    that this Transparent copy will remain thus accessible at the stated
    location until at least one year after the last time you distribute an
    Opaque copy (directly or through your agents or retailers) of that
    edition to the public.
    
    It is requested, but not required, that you contact the authors of the
    Document well before redistributing any large number of copies, to
    give them a chance to provide you with an updated version of the
    Document.
    
    
    4. MODIFICATIONS
    
    You may copy and distribute a Modified Version of the Document under
    the conditions of sections 2 and 3 above, provided that you release
    the Modified Version under precisely this License, with the Modified
    Version filling the role of the Document, thus licensing distribution
    and modification of the Modified Version to whoever possesses a copy
    of it.  In addition, you must do these things in the Modified Version:
    
    A. Use in the Title Page (and on the covers, if any) a title distinct
       from that of the Document, and from those of previous versions
       (which should, if there were any, be listed in the History section
       of the Document).  You may use the same title as a previous version
       if the original publisher of that version gives permission.
    B. List on the Title Page, as authors, one or more persons or entities
       responsible for authorship of the modifications in the Modified
       Version, together with at least five of the principal authors of the
       Document (all of its principal authors, if it has fewer than five),
       unless they release you from this requirement.
    C. State on the Title page the name of the publisher of the
       Modified Version, as the publisher.
    D. Preserve all the copyright notices of the Document.
    E. Add an appropriate copyright notice for your modifications
       adjacent to the other copyright notices.
    F. Include, immediately after the copyright notices, a license notice
       giving the public permission to use the Modified Version under the
       terms of this License, in the form shown in the Addendum below.
    G. Preserve in that license notice the full lists of Invariant Sections
       and required Cover Texts given in the Document's license notice.
    H. Include an unaltered copy of this License.
    I. Preserve the section Entitled "History", Preserve its Title, and add
       to it an item stating at least the title, year, new authors, and
       publisher of the Modified Version as given on the Title Page.  If
       there is no section Entitled "History" in the Document, create one
       stating the title, year, authors, and publisher of the Document as
       given on its Title Page, then add an item describing the Modified
       Version as stated in the previous sentence.
    J. Preserve the network location, if any, given in the Document for
       public access to a Transparent copy of the Document, and likewise
       the network locations given in the Document for previous versions
       it was based on.  These may be placed in the "History" section.
       You may omit a network location for a work that was published at
       least four years before the Document itself, or if the original
       publisher of the version it refers to gives permission.
    K. For any section Entitled "Acknowledgements" or "Dedications",
       Preserve the Title of the section, and preserve in the section all
       the substance and tone of each of the contributor acknowledgements
       and/or dedications given therein.
    L. Preserve all the Invariant Sections of the Document,
       unaltered in their text and in their titles.  Section numbers
       or the equivalent are not considered part of the section titles.
    M. Delete any section Entitled "Endorsements".  Such a section
       may not be included in the Modified Version.
    N. Do not retitle any existing section to be Entitled "Endorsements"
       or to conflict in title with any Invariant Section.
    O. Preserve any Warranty Disclaimers.
    
    If the Modified Version includes new front-matter sections or
    appendices that qualify as Secondary Sections and contain no material
    copied from the Document, you may at your option designate some or all
    of these sections as invariant.  To do this, add their titles to the
    list of Invariant Sections in the Modified Version's license notice.
    These titles must be distinct from any other section titles.
    
    You may add a section Entitled "Endorsements", provided it contains
    nothing but endorsements of your Modified Version by various
    parties--for example, statements of peer review or that the text has
    been approved by an organization as the authoritative definition of a
    standard.
    
    You may add a passage of up to five words as a Front-Cover Text, and a
    passage of up to 25 words as a Back-Cover Text, to the end of the list
    of Cover Texts in the Modified Version.  Only one passage of
    Front-Cover Text and one of Back-Cover Text may be added by (or
    through arrangements made by) any one entity.  If the Document already
    includes a cover text for the same cover, previously added by you or
    by arrangement made by the same entity you are acting on behalf of,
    you may not add another; but you may replace the old one, on explicit
    permission from the previous publisher that added the old one.
    
    The author(s) and publisher(s) of the Document do not by this License
    give permission to use their names for publicity for or to assert or
    imply endorsement of any Modified Version.
    
    
    5. COMBINING DOCUMENTS
    
    You may combine the Document with other documents released under this
    License, under the terms defined in section 4 above for modified
    versions, provided that you include in the combination all of the
    Invariant Sections of all of the original documents, unmodified, and
    list them all as Invariant Sections of your combined work in its
    license notice, and that you preserve all their Warranty Disclaimers.
    
    The combined work need only contain one copy of this License, and
    multiple identical Invariant Sections may be replaced with a single
    copy.  If there are multiple Invariant Sections with the same name but
    different contents, make the title of each such section unique by
    adding at the end of it, in parentheses, the name of the original
    author or publisher of that section if known, or else a unique number.
    Make the same adjustment to the section titles in the list of
    Invariant Sections in the license notice of the combined work.
    
    In the combination, you must combine any sections Entitled "History"
    in the various original documents, forming one section Entitled
    "History"; likewise combine any sections Entitled "Acknowledgements",
    and any sections Entitled "Dedications".  You must delete all sections
    Entitled "Endorsements".
    
    
    6. COLLECTIONS OF DOCUMENTS
    
    You may make a collection consisting of the Document and other
    documents released under this License, and replace the individual
    copies of this License in the various documents with a single copy
    that is included in the collection, provided that you follow the rules
    of this License for verbatim copying of each of the documents in all
    other respects.
    
    You may extract a single document from such a collection, and
    distribute it individually under this License, provided you insert a
    copy of this License into the extracted document, and follow this
    License in all other respects regarding verbatim copying of that
    document.
    
    
    7. AGGREGATION WITH INDEPENDENT WORKS
    
    A compilation of the Document or its derivatives with other separate
    and independent documents or works, in or on a volume of a storage or
    distribution medium, is called an "aggregate" if the copyright
    resulting from the compilation is not used to limit the legal rights
    of the compilation's users beyond what the individual works permit.
    When the Document is included in an aggregate, this License does not
    apply to the other works in the aggregate which are not themselves
    derivative works of the Document.
    
    If the Cover Text requirement of section 3 is applicable to these
    copies of the Document, then if the Document is less than one half of
    the entire aggregate, the Document's Cover Texts may be placed on
    covers that bracket the Document within the aggregate, or the
    electronic equivalent of covers if the Document is in electronic form.
    Otherwise they must appear on printed covers that bracket the whole
    aggregate.
    
    
    8. TRANSLATION
    
    Translation is considered a kind of modification, so you may
    distribute translations of the Document under the terms of section 4.
    Replacing Invariant Sections with translations requires special
    permission from their copyright holders, but you may include
    translations of some or all Invariant Sections in addition to the
    original versions of these Invariant Sections.  You may include a
    translation of this License, and all the license notices in the
    Document, and any Warranty Disclaimers, provided that you also include
    the original English version of this License and the original versions
    of those notices and disclaimers.  In case of a disagreement between
    the translation and the original version of this License or a notice
    or disclaimer, the original version will prevail.
    
    If a section in the Document is Entitled "Acknowledgements",
    "Dedications", or "History", the requirement (section 4) to Preserve
    its Title (section 1) will typically require changing the actual
    title.
    
    
    9. TERMINATION
    
    You may not copy, modify, sublicense, or distribute the Document
    except as expressly provided under this License.  Any attempt
    otherwise to copy, modify, sublicense, or distribute it is void, and
    will automatically terminate your rights under this License.
    
    However, if you cease all violation of this License, then your license
    from a particular copyright holder is reinstated (a) provisionally,
    unless and until the copyright holder explicitly and finally
    terminates your license, and (b) permanently, if the copyright holder
    fails to notify you of the violation by some reasonable means prior to
    60 days after the cessation.
    
    Moreover, your license from a particular copyright holder is
    reinstated permanently if the copyright holder notifies you of the
    violation by some reasonable means, this is the first time you have
    received notice of violation of this License (for any work) from that
    copyright holder, and you cure the violation prior to 30 days after
    your receipt of the notice.
    
    Termination of your rights under this section does not terminate the
    licenses of parties who have received copies or rights from you under
    this License.  If your rights have been terminated and not permanently
    reinstated, receipt of a copy of some or all of the same material does
    not give you any rights to use it.
    
    
    10. FUTURE REVISIONS OF THIS LICENSE
    
    The Free Software Foundation may publish new, revised versions of the
    GNU Free Documentation License from time to time.  Such new versions
    will be similar in spirit to the present version, but may differ in
    detail to address new problems or concerns.  See
    http://www.gnu.org/copyleft/.
    
    Each version of the License is given a distinguishing version number.
    If the Document specifies that a particular numbered version of this
    License "or any later version" applies to it, you have the option of
    following the terms and conditions either of that specified version or
    of any later version that has been published (not as a draft) by the
    Free Software Foundation.  If the Document does not specify a version
    number of this License, you may choose any version ever published (not
    as a draft) by the Free Software Foundation.  If the Document
    specifies that a proxy can decide which future versions of this
    License can be used, that proxy's public statement of acceptance of a
    version permanently authorizes you to choose that version for the
    Document.
    
    11. RELICENSING
    
    "Massive Multiauthor Collaboration Site" (or "MMC Site") means any
    World Wide Web server that publishes copyrightable works and also
    provides prominent facilities for anybody to edit those works.  A
    public wiki that anybody can edit is an example of such a server.  A
    "Massive Multiauthor Collaboration" (or "MMC") contained in the site
    means any set of copyrightable works thus published on the MMC site.
    
    "CC-BY-SA" means the Creative Commons Attribution-Share Alike 3.0 
    license published by Creative Commons Corporation, a not-for-profit 
    corporation with a principal place of business in San Francisco, 
    California, as well as future copyleft versions of that license 
    published by that same organization.
    
    "Incorporate" means to publish or republish a Document, in whole or in 
    part, as part of another Document.
    
    An MMC is "eligible for relicensing" if it is licensed under this 
    License, and if all works that were first published under this License 
    somewhere other than this MMC, and subsequently incorporated in whole or 
    in part into the MMC, (1) had no cover texts or invariant sections, and 
    (2) were thus incorporated prior to November 1, 2008.
    
    The operator of an MMC Site may republish an MMC contained in the site
    under CC-BY-SA on the same site at any time before August 1, 2009,
    provided the MMC is eligible for relicensing.
    
    
    ADDENDUM: How to use this License for your documents
    
    To use this License in a document you have written, include a copy of
    the License in the document and put the following copyright and
    license notices just after the title page:
    
        Copyright (c)  YEAR  YOUR NAME.
        Permission is granted to copy, distribute and/or modify this document
        under the terms of the GNU Free Documentation License, Version 1.3
        or any later version published by the Free Software Foundation;
        with no Invariant Sections, no Front-Cover Texts, and no Back-Cover Texts.
        A copy of the license is included in the section entitled "GNU
        Free Documentation License".
    
    If you have Invariant Sections, Front-Cover Texts and Back-Cover Texts,
    replace the "with...Texts." line with this:
    
        with the Invariant Sections being LIST THEIR TITLES, with the
        Front-Cover Texts being LIST, and with the Back-Cover Texts being LIST.
    
    If you have Invariant Sections without Cover Texts, or some other
    combination of the three, merge those two alternatives to suit the
    situation.
    
    If your document contains nontrivial examples of program code, we
    recommend releasing these examples in parallel under your choice of
    free software license, such as the GNU General Public License,
    to permit their use in free software.

