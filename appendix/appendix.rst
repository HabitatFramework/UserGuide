********
Appendix
********

.. index::
    single: Appendix; Change Log
    single: Change Log

.. _change_log:

Change Log
==========

**4.0.2**
(31st July 2024)

    * :guilabel:`Improved` ???

**4.0.1**
(27th March 2024)

    * :guilabel:`New` Option to show or hide the source habitat group in the main window Habitat tab
    * :guilabel:`New` Option to show or hide the habitat secondaries summary in the main window Habitat tab
    * :guilabel:`New` Optional validation for the mandatory secondary habitats based on the source habitat type
    * :guilabel:`New` Optional validation of potential priority habitat determination quality
    * :guilabel:`Fixed` Disable OSMM update buttons when no update is pending
    * :guilabel:`Fixed` Clear the selected table and operator in the advanced filter when clearing
    * :guilabel:`Fixed` Adjust secondary table height automatically when window height is changed
    * :guilabel:`Fixed` Error during INCID update when incid_mm_polygon fields to be null
    * :guilabel:`Fixed` Display modified details in the history records correctly

**4.0.0**
(1st January 2024)

    * :guilabel:`New` Support UKHab rather than IHS as the central habitat classification
    * :guilabel:`Improved` 'None' priority habitat type replaced by determination and interpretation fields
    * :guilabel:`Improved` Reset the active incid filter when selected feature(s) are not found in GIS
    * :guilabel:`Improved` Load all lookup tables during initialisation to improved performance
    * :guilabel:`Improved` Various data integrity checks when selecting, splitting, merging or updating INCIDs
    * :guilabel:`New` Mandatory habitat secondaries field in the Habitats tab
    * :guilabel:`New` Optional habitat secondaries suggestions and tips in the Habitats tab
    * :guilabel:`New` Don't enable outstanding edits to be saved when moving away from the current INCID
    * :guilabel:`New` Display data version (e.g. 'Live' or 'Test') in the About window
    * :guilabel:`Removed` Standard, non-advanced, query builder

**3.1.4**
(22nd April 2022)

    * :guilabel:`Improved` Enable auto zoom when selecting features on map (*Fix097*)
    * :guilabel:`Improved` Enable get map selection when in OSMM update mode (*Fix101*)
    * :guilabel:`Improved` Enable OSMM updates to be manually accepted/rejected in normal mode (*Fix103*)
    * :guilabel:`Improved` Check if the user is sure before closing application (*Fix106*)
    * :guilabel:`Fixed` Bug when no features found in current layer when applying OSMM filter (*Fix098*)
    * :guilabel:`Fixed` Prevent OSMM updates being actioned too quickly (*Fix099*)
    * :guilabel:`Fixed` Clear invalid multiplex codes on change of habitat (*Fix100*)
    * :guilabel:`Fixed` Display correct number of selected features on export (*Fix102*)
    * :guilabel:`Fixed` Reset interface height and width correctly (*Fix104*)
    * :guilabel:`Fixed` Trap error when unable to register Access table during selection and export (*Fix105*)
    * :guilabel:`Fixed` Reset filter when no features selected in current layer on get map selection (*Fix107*)
    * :guilabel:`Fixed` Prevent existing multiplex codes from not being displayed (*Fix108*)

**3.1.3**
(12th June 2020)

    * :guilabel:`Fixed` Delete existing sources when bulk applying OSMM update (*Fix093*)
    * :guilabel:`Fixed` Insert new primary BAP habitats when bulk applying OSMM update (*Fix094*)
    * :guilabel:`Improved` Show OSMM XRef ID in user interface for pending OSMM updates (*Fix095*)
    * :guilabel:`Improved` Improve performance when applying/rejecting multiple OSMM updates (*Fix096*)

**3.1.2**
(17th April 2020)

    * :guilabel:`New` List all IHS habitat codes when habitat type is blank (*Fix090*)
    * :guilabel:`New` Enable advanced filter when reviewing OSMM updates (*Fix092*)
    * :guilabel:`Fixed` Enable bulk update options only if habitat has changed (*Fix087*)
    * :guilabel:`Fixed` Add warning to delete multiplex codes option in bulk update (*Fix088*)
    * :guilabel:`Fixed` Only enable split/merge functions after select from map (*Fix089*)
    * :guilabel:`Fixed` Apply bulk updates even when multiplex codes are not replaced (*Fix091*)

**3.1.1**
(25th November 2019)

    * :guilabel:`Fixed` Clear habitat type when IHS habitat changes (after change of incid) (*Fix084*)
    * :guilabel:`Fixed` Clear multiplex warnings when at least one recommended code is selected (*Fix085*)
    * :guilabel:`Fixed` Clear error messages if priority habitats have been fixed in pop-up window (*Fix086*)

**3.1.0**
(5th November 2019)

    * :guilabel:`New` New pop-out windows to display/edit priority and potential priority habitats (*CR54*)
    * :guilabel:`New` Enable multiple priority habitat classifications to be supported (*CR52*)
    * :guilabel:`New` Validate mandatory or recommended multiplex codes have been selected (*CR56*)

**3.0.2**
(14th October 2019)

    * :guilabel:`Fixed` Enable a subset of features for each selected INCID to be exported (*Fix081*)
    * :guilabel:`Fixed` Ensure predicted count of toids/fragment works with any filter query (*Fix083*)
          
**3.0.1**
(10th October 2019)

    * :guilabel:`Fixed` Check for OSMM updates before enabling OSMM review and bulk update (*Fix082*)

**3.0.0**
(1st August 2019)

    * :guilabel:`New` Enable auto zoom when selecting features for an incid in GIS (*Fix068*)
    * :guilabel:`New` Enable auto select of features in GIS when moving to a new incid (*Fix069*)
    * :guilabel:`New` Option to set minimum zoom scale when zooming to selected features in GIS (*Fix071*)
    * :guilabel:`New` Simple query filter window to search for a single INCID (*Fix072*)
    * :guilabel:`New` Enable window dimensions to be reset to their default values (*Fix073*)
    * :guilabel:`New` Option to hide the group headers in main interface to reduce window height (*Fix076*)
    * :guilabel:`Improved` Major enhancement to display and process and proposed OSMM updates (*CR49*)
    * :guilabel:`Improved` Improvements to 'zoom to selected features' functionality (*Fix070*)
    * :guilabel:`Improved` Save option to keep the main tool interface on top of other windows (*Fix074*)
    * :guilabel:`Improved` Ensure than filtered records are always displayed in INCID order (*Fix075*)
    * :guilabel:`Improved` Major overhaul of bulk update functionality with new confirm window (*Fix078*)
    * :guilabel:`Improved` Updated 'About' window with links to online user and technical guides (*Fix079*)
    * :guilabel:`Fixed` Bug when cancelled updates to a subset of INCID features were still applied (*KI116*)
    * :guilabel:`Fixed` Bulk update error where determination quality is blank (*KI117*)
    * :guilabel:`Fixed` Trap error when database requires a later version of the started application (*Fix077*)
    * :guilabel:`Fixed` Changes to text fields in options not being saved using <Enter> key (*Fix080*)

**2.4.3**
(27th February 2018)

    * :guilabel:`Fixed` Export problems (in ArcGIS) after selecting features in the active GIS layer (*Fix067*)

**2.4.2**
(22nd January 2018)

    * :guilabel:`Improved` Performance (in ArcGIS) by exporting outside of edit sessions (*Fix064*)
    * :guilabel:`Improved` Prompt user for export GIS layer name before starting export (*Fix065*)
    * :guilabel:`Improved` Performance when exporting attributes to a temporary database (*Fix066*)
    * :guilabel:`Fixed` Apply database connection time-out option instead of default 15 seconds (*Fix063*)

**2.4.1**
(6th June 2016)

    * :guilabel:`Improved` Enable use with all 32bit versions of MapInfo (*Fix061*)
    * :guilabel:`Improved` Enable use on multi-user virtual systems if MapInfo already running (*Fix062*)


**2.4.0**
(29th March 2015)

    * :guilabel:`New` Legacy habitat field editable with list from new 'lut_legacy_habitat' table (*CR44*)
    * :guilabel:`New` Option to show/hide related NVC Codes in the 'Habitats' tab (*Fix056*)
    * :guilabel:`New` Display the current database connection details in 'About' dialog (*Fix058*)
    * :guilabel:`Improved` Hide map window number from layer name when only one window (*Fix059*)
    * :guilabel:`Improved` Disable switch GIS layer button/menu when only one valid GIS layer (*Fix060*)
    * :guilabel:`Fixed` Adjust interface height correctly when showing/hiding optional areas (*Fix057*)

**2.3.3**
(23rd January 2015)

    * :guilabel:`Improved` Improvement to error reporting during the export process (*Fix054*)
    * :guilabel:`Improved` Enable connection via OLEDB to Access 2007 (.accdb) databases (*Fix055*)
    * :guilabel:`Fixed` 'Get Map Selection' bug (in MapInfo) if selection uses multiple tables (*Fix052*)
    * :guilabel:`Fixed` Check all selected features have unique keys before splitting/merging (*Fix053*)

**2.3.2**
(18th December 2014)

    * :guilabel:`Fixed` Bug exporting the **source\_id** field with a *field\_format* of 'Lookup' or 'Both' (*CR43*)

**2.3.1**
(14th December 2014)

    * :guilabel:`New` Sort records from 'child' tables so multiple fields are exported in same order (*CR43*)
    * :guilabel:`Improved` Performance when filtering large number of incids (*Fix051*)

**2.3.0**
(28th November 2014)

    * :guilabel:`New` Enable fields to be exported with codes or descriptions (*CR14*)
    * :guilabel:`New` Enable fields to be exported with **both** codes and descriptions (*CR15*)
    * :guilabel:`New` Prompt users to add the new GIS layer when an export has completed (*CR16*)
    * :guilabel:`New` Enable **incid\_source** dates to be exported in different date formats (*CR17*)
    * :guilabel:`New` Enable auto-increment fields to be included in export layers (*Fix034*)
    * :guilabel:`New` Move the geometry (length and area) fields to the **end** of all export layers (*Fix037*)
    * :guilabel:`New` Display the export progress (in ArcGIS) correctly during an export (*Fix038*)
    * :guilabel:`New` Enable users (in MapInfo) to set a default export folder path option (*Fix040*)
    * :guilabel:`New` Warn users an export may take some time (if it exceeds 5,000 incids) (*Fix042*)
    * :guilabel:`New` Enable new 'dummy' fields to be included within export formats (*Fix043*)
    * :guilabel:`New` Enable maximum text field lengths to be specified in export formats (*Fix044*)
    * :guilabel:`New` Interweave multiple record fields from the same 'child' table together (*Fix045*)
    * :guilabel:`New` Enable fields to be converted to a different data type during an export (*Fix048*)
    * :guilabel:`New` Enable the multiple record counter to be included in an export **field\_name** (*Fix049*)
    * :guilabel:`New` Warn users (in ArcGIS) of truncated **field\_names** exporting to shapefiles (*Fix050*)
    * :guilabel:`Improved` Performance when exporting small numbers of incids (*CR13*)
    * :guilabel:`Fixed` Bug during export when comparing GIS layer and database field names (*Fix033*)
    * :guilabel:`Fixed` Only export **selected** features in GIS when 'Selected Only' checked (*Fix035*)
    * :guilabel:`Fixed` Clear all missing/empty fields when exporting features (in ArcGIS) (*Fix036*)
    * :guilabel:`Fixed` Check exports (in MapInfo) won't exceed the max. record length/file size (*Fix039*)
    * :guilabel:`Fixed` Check the selected export format contains the incid column (*Fix041*)
    * :guilabel:`Fixed` Don't repeat details from the same *incid\_source** record (*Fix046*)
    * :guilabel:`Fixed` Avoid errors with excessive SQL query lengths (*Fix047*)

**2.2.0**
(31st October 2014)

    * :guilabel:`New` 'Advanced Query Builder' interface for filtering records (*CR5*)
    * :guilabel:`New` 'Select all Filtered INCIDs on Map' button/menu (*Fix032*)

    * :guilabel:`Improved` Performance of 'Select by Attribute' (now known as 'Filter by Attributes') (*CR12*)

**2.1.1**
(3rd October 2014)

    * :guilabel:`New` Enable selection of new user interface styles (Dark Grey & Light Grey) (*KI15*)
    * :guilabel:`New` Site reference field added to the interface (*CR37*)
    * :guilabel:`New` Optional pop-up message following any of the split or merge operations (*CR39*)
    * :guilabel:`Removed` 'Select by INCID' button and menu as it served no known purpose (*CR27*)
    * :guilabel:`Improved` Only enable buttons/menus for split and merge options when available (*CR7*)
    * :guilabel:`Improved` Clarify previous and modified field values on the history tab (*CR11*)
    * :guilabel:`Improved` Reduce interface minimum height to support smaller screen resolutions (*CR20*)
    * :guilabel:`Improved` Hide the reason and process fields when the tool is in read-only mode (*CR25*)
    * :guilabel:`Improved` Enable INCID field text to be copied to the clipboard (*CR28*)
    * :guilabel:`Improved` Widen the 'Select INCID to keep' window (*CR38*)
    * :guilabel:`Fixed` Bug in editable drop-down lists when NULL value is present (*Fix031*)
    * :guilabel:`Fixed` Changes to the 'IHS Habitat' field now enabled the 'Apply' button (*CR2*)

**2.1.0**
(15th August 2014)

    * :guilabel:`New` Standalone 'HluDbUpdater' application to apply database changes (*CR42*)
    * :guilabel:`Removed` NVC Codes field (temporarily) as there is currently no space in interface (*CR29*)
    * :guilabel:`Improved` Update database validation and check the tool is not already running (*CR30*)
    * :guilabel:`Improved` Replaced IHS/NVC Category fields with Habitat Class/Type fields (*CR29*)
    * :guilabel:`Improved` Only habitat classes/types flagged 'local' appear in the drop-down lists (*CR32*)
    * :guilabel:`Fixed` Apply default sort order to lookup tables when *sort\_order* same/blank (*Fix025*)
    * :guilabel:`Fixed` Hide progress bars (in MapInfo) when updating and merging features (*Fix026*)
    * :guilabel:`Fixed` Bug updating incid immediately after split/merge process (*Fix027*)
    * :guilabel:`Fixed` Bug comparing DateTime fields with fractions of seconds during updates (*Fix028*)
    * :guilabel:`Fixed` Error re-selecting features after physical split (in MapInfo) (*Fix029*)
    * :guilabel:`Fixed` Include time in DateTime fields when updating via ODBC connection type (*Fix030*)


.. raw:: latex

    \newpage

.. index::
    single: Appendix; Licence
    single: Licence

.. _licence:

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

