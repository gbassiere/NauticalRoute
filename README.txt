Description
===========

NauticalRoute is an OpenLayers control designed to trace nautical routes.

A *route* is understood as a point serie composed of:

- *departure*,
- *arrival*,
- intermediate *waypoints*.

Each route segment links two adjacent points and is known as a *leg*.

The NauticalRoute control will compute course, loxodromic distance and orthodromic distance for each leg.

Background
==========

This tool is initially developed for the needs of the OpenSeaMap project but tries to remain as generic as possible.

The project is a complete rewrite of the following prototypes:

- http://openstreetmap.tobwen.de/projects/oseam.html
- http://gis.ibbeck.de/ginfo/apps/OLExamples/OL28/navigation_OSeaM.asp

Usage
=====

Store the following elements in a web-accessible directory:

- ``NauticalRoute.css``
- ``NauticalRoute.js``
- ``export.php``
- ``img/``

In your Web page, load the CSS file and the JavaScript file. Then create the control with the following code:

 new OpenLayers.Control.NauticalRoute({exportUrl: 'export.php'});

You may need to adapt the export URL depending on your configuration.

For a more completed example, please check ``test.html``.

TODO list
=========

The following tasks need action:

- implement a pause/resume button in the popup to switch between route edition and navigation (with or without creation of a new route)
- live coordinate: display course and distance to the waypoint being drawn
- highlight waypoints on the drawn route (duplicate point features? needs a custom handler?)
- export as GPX
- test IE, Safari, Opera, Chrome
- store user settings in a cookie (language as well?)
- add support for any projection/displayProjection (simply transform to WGS84 before computing)
- show great circle routes
