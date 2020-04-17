**********
Change Log
**********

.. index::
    single: Change Log

.. _change_log:

Change Log
==========

**3.1.2**
(17th April 2020)

    * :guilabel:`New` List all IHS habitat codes when habitat type is blank (*Fix090*)
    * :guilabel:`New` Enable advanced filter when reviewing OSMM updates (*Fix092*)
    * :guilabel:`Fixed` Enable bulk update options only if habitat has changed (*Fix087*)
    * :guilabel:`Fixed` Add warning to delete multiplex codes option in bulk update (*Fix088*)
    * :guilabel:`Fixed` Only enable split/merge functions after select from map (*Fix089*)
    * :guilabel:`Fixed` Fix bug when applying bulk updates where multiplex codes are not replaced (*Fix091*)

**3.1.1**
(25th November 2019)

    * :guilabel:`Fixed` Clear habitat type when IHS habitat changes (after change of incid or paste) (*Fix084*)
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
    * :guilabel:`Fixed` Only export **selected** features in GIS When 'Selected Only' checked (*Fix035*)
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

