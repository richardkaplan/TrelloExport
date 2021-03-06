TrelloExport
============
TrelloExport is a Chrome extension to export data from Trello to Excel, Markdown, HTML and OPML.

You can now find it on [Chrome Web Store](https://chrome.google.com/webstore/detail/trelloexport/kmmnaeamjfdnbhljpedgfchjbkbomahp).


## Support
Please open issues on [Github](https://github.com/trapias/trelloExport/issues) or onto the dedicated [Trello board](https://trello.com/b/MBnwUMwM/trelloexport).


## Release history

### Version 1.9.41

Released 03/27/2018:

- persist TrelloExport options to localStorage: CSS, selected export mode, selected export type, name of 'Done' list (([issue #24](https://github.com/trapias/TrelloExport/issues/24)))
- fix due date locale
- expand flag to export archived cards to all kind of items, and filter consequently
- list boards from all available organizations with the "multiple boards" export type

    

### Version 1.9.40

A couple of fixes, released 11/12/2017:

- https://github.com/trapias/TrelloExport/issues/28 ok with Done prefix
- contains vs startsWith filters for the "done" function


### Version 1.9.39

Released 08/02/2017:

- fix custom fields loading ([issue #27](https://github.com/trapias/TrelloExport/issues/27))
- fix card info export to MD ([issue #25](https://github.com/trapias/TrelloExport/issues/25))


### Version 1.9.38

Released 05/12/2017:

- css cleanup
- re-enabled tooltips
- export custom fields (pluginData handled with the "Custom Fields" Power-Up) to Excel, (issue #22 https://github.com/trapias/TrelloExport/issues/22)


### Version 1.9.37

Released 05/07/2017:

Bugfix multiple css issues and a bad bug avoiding the "add member" function to work properly, all due to the introduction of bootstrap css and javascript to use the bootstrap-multiselect plugin; now removed bootstrap and manually handled multiselect missing functionalities. Temporary disabled tooltips, based on bootstrap.


### Version 1.9.36

Released 04/25/2017:

- filter by list name, card name or label name
- help tooltips


### Version 1.9.35:

Fixed a css conflict that caused Trello header bar to loose height.

### Version 1.9.34:

Released 04/24/2017:

- only show columns chooser for Excel exports
- can now set a custom css for HTML export
- can now check/uncheck all columns to export


### Version 1.9.33:

Released 04/24/2017:

- new data field dateLastActivity exported (issue #18 https://github.com/trapias/TrelloExport/issues/18)
- new data field numberOfComments exported (issue #19 https://github.com/trapias/TrelloExport/issues/19)
- new option to choose which columns to export to Excel (issue #17 https://github.com/trapias/TrelloExport/issues/17)


### Version 1.9.32:

Enhancements:

- hopefully fixed bug with member fullName reading
- new option to export labels and members to Excel rows, like already available for checklist items (issue #15 https://github.com/trapias/TrelloExport/issues/15)
- new option to show attached images inline for Markdown and HTML exports (issue #16 https://github.com/trapias/TrelloExport/issues/16)


### Version 1.9.31:

Bugfix release:

- fix due date format in Excel export (issue #12)
- fix missing export of archived cards (issue #13)

### Version 1.9.30:

New CSS and options to format HTML exported files.

- fix 1.9.29 beta (not published to Chrome Web Store)
- finalize new css for HTML exports


### Version 1.9.28:

- fix cards loading: something is broken with the paginated loading introduced with version 1.9.25; to be further investigated


### Version 1.9.27:

- fix ajax.fail functions
- fix loading boards when current board does not belong to any organization

### Version 1.9.26:

- export points estimate and consumed from Card titles based on Scrum for Trello
- improved regex for Trello Plus estimate/spent in card titles


Changes  merged from [pull request #11](https://github.com/trapias/TrelloExport/pull/11) by [Chris](https://github.com/collisdigital), thank you! 


### Version 1.9.25
New feature: paginate cards loading, so to be able to load all cards even when exceeding the Trello API limit of 1000 records per call.

Please consider this a beta: it's not yet available on the Chrome Web Store, so if you want to try it please install locally (see below).


### Version 1.9.24

New features:

- new checkboxes to enable/disable exporting of comments, checklist items and attachments
- new option to export checklist items to rows, for Excel only


### Version 1.9.23
Added new capability to **export to OPML**.

More in this [blog post](http://trapias.github.io/blog/trelloexport-1-9-23).

### Version 1.9.22
A couple of enhancements:

- fix improper .md encoding as per [issue #8](https://github.com/trapias/TrelloExport/issues/8)
- new option to decide whether to export archived items


### Version 1.9.21
Some small improvements, and a new function for **exporting to HTML**.

Details:

- some UI (CSS) improvements for the options dialog
- improved options dialog, resetting options when switching export type
- new columns for Excel export: 'Total Checklist items' and 'Completed Checklist items'
- better checklists formatting for Excel export
- export to HTML

#### HTML export mode
The produced file is based on the Markdown export: the same output is generated and then converted to HTML with [showdown](https://github.com/showdownjs/showdown). Suggestions and ideas about how to evolve this are welcome.


### Version 1.9.20:
Fixes due to Trello UI changes.

### Version 1.9.19
Partial refactoring: export flow has been rewritten to better handle data to enable different export modes. **It is now possible to export to Excel and Markdown**, and more export formats could now more easily be added.

- refactoring export flow
- updated jQuery Growl to version 1.3.1
- new Markdown export mode

More info in this [blog post](http://trapias.github.io/blog/trelloexport-1-9-19). 

### Version 1.9.18
Improving UI:

- improve UI: better feedback message timing, yet still blocking UI during export due to sync ajax requests
- removed data limit setting from options dialog - just use 1000, maximum allowed by Trello APIs
- fix filename (YYYYMMDDhhmmss)
- fix some UI issues


### Version 1.9.17
Finally fixed (really) exporting ALL comments per card. We're now loading comments per single card from Trello API, which is **much slower** but assures all comments are exported.

### Version 1.9.15
Finally fixing comments export: should have finally fixed exporting of comments and 'done time' calculations: thanks @fepsch for sharing a board and allowing to identify this annoying bug.

### Version 1.9.14
Some bugfix and some new features.

**Fixes**:

- fixed card completion calculation when exporting multiple boards (fix getMoveCardAction and getCreateCardAction)
- loading comments with a new function (getCommentCardActions), trying to fix issues with comments reported by some users; please give feedback

**New features**:

- formatting dates in user (browser) locale
- added support for multiple 'Done' list names
- added capability to optionally filter exported lists by name when exporting multiple boards

Both the 'Done list name' and 'Filter lists by name' input boxes accept a comma-separated list of partial list names, i.e. just specify multiple names in the textbox like 'Done,Completed' (without apices). Lists will then be (case insensitively) matched when their name starts with one of these values.

More info in this [blog post](http://trapias.github.io/blog/trelloexport-1-9-14/). 

### Version 1.9.13:
Some (interesting, hopefully!) improvements with this version:

- new 'DoneTime' column holding card completion time in days, hours, minutes and seconds, formatted as per [ISO8601](https://en.wikipedia.org/wiki/ISO_8601)
- name (prefix) of 'Done' lists is now configurable, default "Done"
- larger options dialog to better show options
- export multiple (selected) boards
- export multiple (selected) cards in a list (i.e. export single cards)

More info in this [blog post](http://trapias.github.io/blog/trelloexport-1-9-13/). Give feeback!


### Version 1.9.12:
Fixed a bug by which the previously used BoardID was kept when navigating to another board.


### Version 1.9.11:

- added a new Options dialog
- export full board or choosen list(s) only
- add who and when item was completed to checklist items as of [issue #5](https://github.com/trapias/trelloExport/issues/5)

More info in this [blog post](http://trapias.github.io/blog/trelloexport-1-9-11/).

Your feedback is welcome, just comment on the blog, on the dedicated [Trello board](https://trello.com/b/MBnwUMwM/trelloexport) or open new issues.


### Version 1.9.10:

- adapt inject script to modified Trello layout

### Version 1.9.9:

- MAXCHARSPERCELL limit to avoid import errors in Excel (see https://support.office.com/en-nz/article/Excel-specifications-and-limits-16c69c74-3d6a-4aaf-ba35-e6eb276e8eaa)
- removed commentLimit, all comments are loaded (but attention to MAXCHARSPERCELL limit above, since comments go to a single cell)
- growl notifications with jquery-growl http://ksylvest.github.io/jquery-growl/

### Version 1.9.8:
Use Trello API to get data, thanks https://github.com/mjearhart and https://github.com/llad:

- https://github.com/llad/export-for-trello/pull/20
- https://github.com/mjearhart/export-for-trello/commit/2a07561fdcdfd696dee0988cbe414cfd8374b572

### Version 1.9.7:
- fix issue #3 (copied comments missing in export)

### Version 1.9.6
- order checklist items by position (issue #4)
- minor code changes

### Version 1.9.5
- code lint
- ignore case in finding 'Done' lists (thanks [AlvonsiusAlbertNainupu](https://disqus.com/by/AlvonsiusAlbertNainupu/))

### Version 1.9.4
Fixed bug preventing export when there are no archived cards.

### Version 1.9.3
Whatsnew for version 1.9.3:

- restored archived cards sheet

### Version 1.9.2
Whatsnew for version 1.9.2:

- fixed blocking error when duedate specified - thanks @ggyaniv for help
- new button loading function: the "Export Excel" button should always appear now

### Version 1.9.1
Whatsnew for version 1.9.1:

- fixed button loading
- some code cleaning

### Version 1.9.0
Whatsnew for version 1.9.0

- switched to SheetJS library to export to excel, cfr [https://github.com/SheetJS/js-xlsx](https://github.com/SheetJS/js-xlsx "https://github.com/SheetJS/js-xlsx")
- unicode characters are now correctly exported to xlsx


### Version 1.8.9
Whatsnew for version 1.8.9:

- added column Card #
- added columns memberCreator, datetimeCreated, datetimeDone and memberDone pulling modifications from [https://github.com/bmccormack/export-for-trello/blob/5b2b8b102b98ed2c49241105cb9e00e44d4e1e86/trelloexport.js](https://github.com/bmccormack/export-for-trello/blob/5b2b8b102b98ed2c49241105cb9e00e44d4e1e86/trelloexport.js "https://github.com/bmccormack/export-for-trello/blob/5b2b8b102b98ed2c49241105cb9e00e44d4e1e86/trelloexport.js")
- added linq.min.js library to support linq queries for the above modifications


#### Notes
I modified the **escapeXML** function in **xlsx.js** to avoid errors with XML characters when loading the spreadsheet in Excel. I tested exporting quite big boards like Trello Development or Trello Resources and no more have issues with invalid characters.
I put a couple of sample export files in the xlsx subfolder.

**Columns**: the list of columns exported is now:

	columnHeadings = ['List', 'Card #', 'Title', 'Link', 'Description', 'Checklists', 'Comments', 'Attachments', 'Votes', 'Spent', 'Estimate', 'Created', 'CreatedBy', 'Due', 'Done', 'DoneBy', 'Members', 'Labels']

##### datetimeDone and memberDone
These fields are calculated intercepting when a card was moved to the Done list. While bmccormack's code only checks for this list, I check for cards being moved to any list whose name starts with "Done" (e.g. using lists named "Done Bugfix", "Done New Feature" and so will work).


#### Formatting
I tried formatting data in a readable format, suggest changes if you don't like how it is now.

**Comments** are formatted with [date - username] comment, e.g.:

	[2014-01-31 18:38:31 - kathyschultz1] the add-on for exporting to Excel is a good start, but I'm w/all who dream of a report that includes checklists and comments. Thanks Trello warriors!

I added **commentLimit** to limit the number of comments to extract: play with the value (default 100) as per your needs.
There are currently no limits in the number of checklists, checklist items or attachments.

**Attachments** are listed in a similar way, with [filename] (bytes) url, e.g.:

	[chrome.jpg] (62806) https://trello-attachments.s3.amazonaws.com/4d5ea62fd76aa1136000000c/520a29971618ecef3c002181/dc1d95c904a04a6a986b775e55f58bd9/chrome.jpg

**Excel formatting**: after opening the excel you will have to adjust columns widths and formatting. I normally align cells on top and wrap text to have a readable format - see the samples in xlsx.


## How to install
Get it on the [Chrome Web Store](https://chrome.google.com/webstore/detail/trelloexport/kmmnaeamjfdnbhljpedgfchjbkbomahp). 

If you want to install from source, just follow these steps:

1. Download the repository as a zip file
2. Extract zip
3. Go to Chrome Exensions: [chrome://chrome/extensions/](chrome://chrome/extensions/)
4. Click on Developer Mode checkbox
5. Click on Load unpacked extension...
6. Select the folder containing the source files
7. Reload Trello


## How to use
1. From a board, click to show the menu in right sidebar
2. Click on Share, print, and export...
3. Click on TrelloExport
4. Choose options for export
5. Click "Export", wait for the process to complete and you get your file downloaded.


## Credits
This is a fork of the original "Export for Trello" extension, available at [https://github.com/llad/export-for-trello](https://github.com/llad/export-for-trello).
