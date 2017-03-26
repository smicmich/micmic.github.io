---
layout: post
comments: true
title: Marcadores personalizados en Leaflet
---

En la entrada [anterior](https://smicmich.github.io/mapa-sencillo-leaflet/), revisamos cómo iniciar un mapa básico con Leaflet y agregar marcadores simples. Sin embargo,los marcadores que Leaflet tiene por defecto podrían no ser los adecuados si queremos hacer un mapa en el que queramos representar información diferente con cada marcador. Así que esta vez explicaré un poco cómo poner marcadores personalizados.

```html
<html>
<head>
  <title>Map-A!</title>
  <link rel="stylesheet" href="http://cdn.leafletjs.com/leaflet-0.7.3/leaflet.css"/>
  <script src="http://cdn.leafletjs.com/leaflet-0.7.3/leaflet.js"></script>
  <script src="https://code.jquery.com/jquery-2.1.1.min.js"></script>
  <style>
    #map{ height: 100% }
  </style>
</head>
<body>
 
  <div id="map"></div>
 
  <script>

var map = L.map('map').setView([19.434674586884228, -99.13136601448059], 14);
 
  L.tileLayer('http://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',
    {
		attribution: '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a>'
    }).addTo(map);
    
    L.marker([19.434882,-99.142477]).addTo(map).bindPopup('Bellas Artes, Bellas Artes!');
 
  </script>
</body>
</html>
```
## Agregar las variables de los marcadores
 
Añadir una variable que contenga los íconos que se usarán. Yo la nombraré ```supermapaIcon```. La variable contendrá la ruta del archivo de donde se obtendrá nuestro marcador y el tamaño que éste tendrá en el mapa, todo esto dentro de ```L.icon```.

```html
<html>
<head>
  <title>Map-A!</title>
  <link rel="stylesheet" href="http://cdn.leafletjs.com/leaflet-0.7.3/leaflet.css"/>
  <script src="http://cdn.leafletjs.com/leaflet-0.7.3/leaflet.js"></script>
  <script src="https://code.jquery.com/jquery-2.1.1.min.js"></script>
  <style>
    #map{ height: 100% }
  </style>
</head>
<body>
 
  <div id="map"></div>
 
  <script>

var map = L.map('map').setView([19.434674586884228, -99.13136601448059], 14);
 
  L.tileLayer('http://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',
    {
		attribution: '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a>'
    }).addTo(map);
    
    var supermapaIcon = L.icon({
    iconUrl: 'icons/pokeball.png',
    iconSize: [90,90],
});
    
    L.marker([19.434882,-99.142477]).addTo(map).bindPopup('Bellas Artes, Bellas Artes!');
 
  </script>
</body>
</html>
```

Ahora, después de las coordenadas, agregaremos la variable correspondiente al ícono: ```icon: supermapaIcon```.

```html
<html>
<head>
  <title>Map-A!</title>
  <link rel="stylesheet" href="http://cdn.leafletjs.com/leaflet-0.7.3/leaflet.css"/>
  <script src="http://cdn.leafletjs.com/leaflet-0.7.3/leaflet.js"></script>
  <script src="https://code.jquery.com/jquery-2.1.1.min.js"></script>
  <style>
    #map{ height: 100% }
  </style>
</head>
<body>
 
  <div id="map"></div>
 
  <script>

var map = L.map('map').setView([19.434674586884228, -99.13136601448059], 14);
 
  L.tileLayer('http://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',
    {
		attribution: '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a>'
    }).addTo(map);
    
    var supermapaIcon = L.icon({
    iconUrl: 'icons/pokeball.png',
    iconSize: [90,90],
});
    
    L.marker([19.434882,-99.142477], {icon:supermapaIcon}).addTo(map).bindPopup('Bellas Artes, Bellas Artes!');
 
  </script>
</body>
</html>
```

