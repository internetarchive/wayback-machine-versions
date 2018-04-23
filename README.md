# Wayback Machine Versions

## Development

To build, simply run the following commands:
* `npm install`
* `gulp build`

## Add Wayback Machine Versions To Your Webpages

Simply append the following lines to the `<head>` of your HTML source:

```html
<link rel="stylesheet" type="text/css" href="https://cdn.rawgit.com/internetarchive/wayback-machine-versions/0c2c778e/build/css/wayback-links.min.css" />
<script type="text/javascript" src="https://cdn.rawgit.com/internetarchive/wayback-machine-versions/0c2c778e/build/js/wayback-links.min.js"></script>
```

## Wayback Machine Versions Menu

After adding the Wayback Machine Versions javascript and css to your HTML file, a new down arrow icon will appear next to all the decorated links in the page. Clicking the down arrow in this link icon will pop up a menu with one or more of the following items, depending on the decoration attributes provided in each of the links.

* `Get near link date ...`: When clicking this menu item, the javascript library will use the datetime provided in the `data-versiondate` attribute along with the original url and redirect you to the closest archived playback page.

* `Get from ...`: Clicking this menu item will redirect you to the playback page url provided in the `data-versionurl` attribute. The value of `data-versionurl` can be single URL or comma separated URLs.
In the case of comma separated URLs, the items for the URLs will be listed in menu.

* `Get at current date`: Clicking this menu item will take you to the original url provided in the `data-originalurl` attribute.

* `Get near page creation date ...`: This menu item is similar to the `Get near link date ...`, except it uses the [Schema.org](http://schema.org) attribute `datePublished`, if provided in the linking HTML page. 

* `Get near page modified date ...`: This menu item is similar to the `Get near link date ...`, except it uses the [Schema.org](http://schema.org) attribute `dateModified`, if provided in the linking HTML page. 

## Exclude URLs from Wayback Machine Versions
You can exclude certain URLs in your webpage from showing the wayback machine versions drop down menu by adding following script before appending `wayback-machine-versions.min.js`

Add urls that should be excluded from wayback machine versions.
Accepts full urls or valid regular expression patterns of urls.

```
<script>
var WLuriPatternsToExclude = [
    "https?://archive.org*",
    "https?://blog.archive.org*"
];
</script>
```

## Example
* [test.html](https://github.com/internetarchive/wayback-machine-versions/blob/master/test/test.html)

This project is based on: http://robustlinks.mementoweb.org

