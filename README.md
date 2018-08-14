# indexhibit-legacy-to-php7

This is a GNU diff patch file to help switch Indexhibit legacy sites (pre Indexhibit 2.x) to be compatible with PHP7.x. 
Most of the important changes were done to object / class initiation, and of course to mysql_* functions. 
Some changes are done so as to suppress unwanted warnings.

# Usage
Enter the root directory containg Indexhibit files and directories. It should look like this: 
```
$ ls
files  htaccess  index.php  ndxz-studio
```
Download the patch. Apply the patch like this:
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
