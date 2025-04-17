
**Minixed** is a minimal but nice-looking PHP directory indexer as a replacement for the Apache `mod_autoindex`.

How to use
----------

- Drop the [**`index.php`**] script in the same directory that contains files you want to index.

- Icons are hard coded into the source with Base-64.

- Style with CSS

To force the download of files, avoiding opening them in the browser, enable the Apache `headers` module and add the [**`.htaccess`**] file:

Configuration
-------------

There are PHP variables placed in the first lines of `index.php` you can configure.

- Enable navigation into subfolders:
	$browseDirectories = true; // Navigate into sub-folders

- Change the page title (and subtitle) providing strings that can contains some placeholders that will be *parsed* at runtime:
	$title = 'Index of {{path}}';
	$subtitle = '{{files}} objects in this folder, {{size}} total'; // Empty to disable

- Make breadcrumb links if titles contain `{{path}}`, useful when navigating into subfolders:
	$breadcrumbs = true; // Make links in {{path}}

- Tell the script how to build the files list:
	$showParent = false; // Display a (parent directory) link
	$showDirectories = true;
	$showDirectoriesFirst = true; // Lists directories first when sorting by name
	$showHiddenFiles = false; // Display files starting with "." too

- And how that list should look:
	$alignment = 'left'; // You can use 'left' or 'center'
	$showIcons = true;
	$dateFormat = 'dd/mm/yyyy HH:ii'; // Used in date() function
	$sizeDecimals = 1;
	
- Customize the content of the meta-tag "robots" if you want to give some search engine hints:
	$robots = 'noindex, nofollow'; // Avoid robots by default
