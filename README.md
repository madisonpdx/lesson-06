HTML DIV Tag
------------

A DIV tag represents a rectangular area in a web page. Add a DIV tag to the page, so we have somewhere to show our map. We are going to call this DIV 'map' by setting the ID attribute. We could name it anything, but map is a good description of what we are going to use this for.

```
<div id="map"></div>
```

JavaScript
----------

JavaScript is a programming language that is used to write code on a web page. There are two ways to add JavaScript to a web page. You can either link to a file that contains JavaScript, or write JavaScript directly in your web page. To create a map we are going to link to a JavaScript file that Google provides and we will write some code of our own to configure the map and add some markers.

```
<script type="text/javascript" src="https://maps.googleapis.com/maps/api/js?sensor=true"></script>
<script type="text/javascript"></script>
```

Functions
---------

Functions provide the ability to group lines of code together so that we can run specific code at specific times. Create a new function called 'initialize' inside the empty SCRIPT tag. 

```
function initialize() { }
```

Creating A Map
--------------

To draw a map, we need to code a little bit of configuration for the map, and then tell Google maps to draw a map in the DIV that we already added to the page. Use Google maps to find the latitude and longitude coordinates for Madison and use those to center the map. Play with the 'zoom' setting to make it easier to see things on the map.

```
var mapOptions = {
    center: new google.maps.LatLng(COORDINATES_HERE),
    zoom: 8,
    mapTypeId: google.maps.MapTypeId.ROADMAP
};

var map = new google.maps.Map(document.getElementById("map"), mapOptions);
```

Showing Map
-----------

We want to show the map once the web page is fully loaded. JavaScript provides a way to do this. Replace the BODY tag on the page with the one shown below. This will start our code running, which will cause the map to be displayed.

```
<body onload="initialize()">
```

Adding Markers
--------------

Use the below code to add a marker to the map. Add the coordinates for Madison to place the marker in the right place. Then see if you can add another marker for Subway.

```
var madison = new google.maps.Marker({
    position: new google.maps.LatLng(COORDINATES_HERE),
    map: map,
    title: 'Madison High School'
});
```

HTML Hash
---------

You can add a value to a page address using the # character. This value will be available in the page that you are linking to. So for example, instead of linking to map.html, you could link to map.html#subway. You can then access that value with JavaScript using the below code:

```
	window.location.hash
```

See if you can add code to the map page to show different markers depending on what value is passed to the page. You should Google search for 'JavaScript if else' to figure out what you need to do.