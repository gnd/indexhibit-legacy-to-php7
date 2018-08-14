# indexhibit-legacy-to-php7

This is a GNU diff patch file to help switch Indexhibit legacy sites (pre Indexhibit 2.x) to be compatible with PHP7.x. 
Most of the important changes were done to object / class initiation, and of course to mysql_* functions. 
Some changes are done so as to suppress unwanted warnings.

# Warning
This patch is to be used only when the Indexhibit site in question cannot be upgraded to Indexhibit 2.x. The patch only solves basic compatibility with PHP7.x and does not include newer Indexhibit functionality (included in Indexhibit 2.x versions). Also your Indexhibit legacy site might contain a lot of security holes that were fixed in Indexhibit 2.x versions, but not in Indexhibit legacy. Use at your own risk. It is always better to try to upgrade your site first, before using this patch.

# Usage
Enter the root directory containing Indexhibit files and directories. It should look like this: 
```
$ ls
files  htaccess  index.php  ndxz-studio
```
Backup the original files and directories:
```
mkdir backup; cp -pr index.php backup/; cp -pr ndxz-studio backup/
```
Download the patch:
```
wget https://raw.githubusercontent.com/gnd/indexhibit-legacy-to-php7/master/indexhibit_legacy_to_php7.diff
```
Apply the patch like this:
```
patch -p1 < indexhibit_legacy_to_php7.diff
```
Output should look like this:
```
$ patch -p1 < ../indexhibit_legacy_to_php7.diff 
patching file index.php
patching file ndxz-studio/common.php
patching file ndxz-studio/db/db.mysql.php
patching file ndxz-studio/defaults.php
patching file ndxz-studio/helper/editortools.php
patching file ndxz-studio/helper/html.php
patching file ndxz-studio/helper/time.php
patching file ndxz-studio/index.php
patching file ndxz-studio/lib/access.php
patching file ndxz-studio/lib/core.php
patching file ndxz-studio/lib/error.php
patching file ndxz-studio/lib/organize.php
patching file ndxz-studio/lib/processor.php
patching file ndxz-studio/lib/router.php
patching file ndxz-studio/lib/statistics.php
patching file ndxz-studio/lib/template.php
patching file ndxz-studio/module/exhibits/files.php
patching file ndxz-studio/module/exhibits/index.php
patching file ndxz-studio/module/stats/index.php
patching file ndxz-studio/module/system/files.php
patching file ndxz-studio/module/system/index.php
patching file ndxz-studio/site/plugin/exhibit.backgrounded.php
patching file ndxz-studio/site/plugin/exhibit.deux_column.php
patching file ndxz-studio/site/plugin/exhibit.grow_no_title.php
patching file ndxz-studio/site/plugin/exhibit.grow.php
patching file ndxz-studio/site/plugin/exhibit.no_thumbs_no_captions.php
patching file ndxz-studio/site/plugin/exhibit.no_thumbs_w_captions.php
patching file ndxz-studio/site/plugin/exhibit.over_and_over.php
patching file ndxz-studio/site/plugin/exhibit.slideshow.php
patching file ndxz-studio/site/plugin/exhibit.thickbox.php
patching file ndxz-studio/site/plugin/index.php
```
Your site should be now compatible with PHP 7.x. If anything should go wrong you can always revert your changes by using your backup. If everything is ok dont forget to remove the backup directory and its contents.
