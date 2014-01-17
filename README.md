# Sublime Text Web Mapping Snippets

_Work in progress._

Type the snippet shortcode and then press <kbd>Tab</kbd> to complete the snippet. Each shortcut provides a basic HTML page skeleton for the latest version of popular JavaScript mapping APIs. 

The snippets are listed below in alphabetical order. The '$1' indicates the position of the caret/s. Any snippet that has a $1/$2/$3/etc. uses this technique. Pressing tab will cycle you through these positions.

Feel free to expand upon these snippets as you please.

---

__gmaps__
```html
<!DOCTYPE html>
<html>
  <head>
    <meta name="viewport" content="initial-scale=1.0, user-scalable=no" />
    <style type="text/css">
      html { height: 100% }
      body { height: 100%; margin: 0; padding: 0 }
      #map-canvas { height: 100% }
    </style>
    <script type="text/javascript"
      src="https://maps.googleapis.com/maps/api/js?key=$1&sensor=$2">
    </script>
  </head>
  <body>
    <div id="map-canvas"/>
    <script type="text/javascript">
      function initialize() {
        var map = new google.maps.Map(document.getElementById("map-canvas");
      }
      google.maps.event.addDomListener(window, 'load', initialize);
    </script>
  </body>
</html>
```

__leaflet__

```html
<!DOCTYPE html>
<html>
<head>
<meta charset=utf-8 />
<title>$1</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
  <script src="http://cdn.leafletjs.com/leaflet-0.7.1/leaflet.js"></script>
  <link rel="stylesheet" href="http://cdn.leafletjs.com/leaflet-0.7.1/leaflet.css" />
  <style type="text/css">
    body { margin:0; padding:0; }
    #map { position:absolute; top:0; bottom:0; width:100%; }
  </style>
</head>
<body>
  <div id="map"></div>
  <script>
    var map = L.map('map');
    L.tileLayer('http://{s}.tile.cloudmade.com/{key}/{styleId}/256/{z}/{x}/{y}.png', {
        key: $2,
        styleId: "997",
        attribution: 'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, <a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="http://cloudmade.com">CloudMade</a>'
    }).addTo(map);
    $3
  </script>
</body>
</html>
```

__mapbox__

```html
<!DOCTYPE html>
<html>
<head>
<meta charset=utf-8 />
<title>$1</title>
  <meta name='viewport' content='width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no' />
  <script src='//api.tiles.mapbox.com/mapbox.js/v1.5.2/mapbox.js'></script>
  <link href='//api.tiles.mapbox.com/mapbox.js/v1.5.2/mapbox.css' rel='stylesheet' />
  <style>
    body { margin:0; padding:0; }
    #map { position:absolute; top:0; bottom:0; width:100%; }
  </style>
</head>
<body>
  <div id="map"></div>
  <script type="text/javascript">
    var map = L.mapbox.map('map', 'examples.map-9ijuk24y');
    $2
  </script>
</body>
</html>
```