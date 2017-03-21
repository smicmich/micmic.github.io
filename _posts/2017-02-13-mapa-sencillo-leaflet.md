---
layout: post
comments: true
title: Cómo hacer un mapa sencillo en leaflet
---

## Antes que nada... ¿qué es Leaflet?

Leaflet es una librería de JavaScript para crear mapas interactivos ¿? Leaflet es la herramienta que hace que puedas agregar distintas funcionalidades a un mapa: marcadores, polígonos, capas, clusters para agrupar la información, geolocalización, etc.

¿Y qué es lo que hace todavía mejor a Leaflet? Que es fácil de usar aunque no tengas grandes conocimientos de programación. Se los digo yo que estudié gestión intercultural (jahaa) y logré hacer [este mapa](http://nemachtilo.mx/mapainteractivo.php) con un poquito de esfuerzo.

## Comencemos

Algunas de las cosas que necesitaremos:

- Conocer un poco de HTML, CSS Y JavaScript.
- Ganas de fallar varias veces hasta conseguir lo que quieres.

## Iniciar un archivo HTML 

Para comenzar a hacer un mapa, debemos crear un archivo HTML con ```title``` ```head```, ```body```, una sección para definir el estilo ```style``` y un bloque llamado ```map```.

```html
<html>
<head>	
	<title>
	</title>
	<style>
	</style>
</head>
	<body>
		<div id = 'map'>
		</div>
	</body> 
</html>
```

### Rellenar el documento

Una vez comenzado el archivo html, lo primero que debemos hacer es incorporar Leaflet al mapa en la cabeza del documento. Algo así:

```html
<html>
<head>
	  <title>Map-A!</title>
	  <link rel="stylesheet" href="http://cdn.leafletjs.com/leaflet-0.7.3/leaflet.css"/>
	  <script src="http://cdn.leafletjs.com/leaflet-0.7.3/leaflet.js"></script>
	  <style></style>

</head>
	<body>
 
  	<div id="map"></div>
 
	</body>
</html>
```
Si no quieren tomar leaflet de internet, bastará con que descarguen los archivos correspondientes [aquí](http://leafletjs.com/download.html) y especifiquen la ubicación de sus archivos.

### Tamaño y base (ponerlo guapo)

Esta parte servirá para indicar el tamaño que tendrá nuestro mapa y debe ir dentro de las etiquetas de estilo `<style>``</style>`. Además de eso, dentro de `body` y después de la sección `map` tendremos que agregar la base del mapa. La elección de la base tiene que ver con el tipo de información que se debe presentar.  Si la orografía e hidrografía del terreno no son de las cosas más importantes en nuestro mapa, podríamos escoger una base simple con pocos colores, pero si como parte de la información que queremos presentar, se deben considerar los asentamientos humanos y las zonas en las que todavía la mano del hombre no ha causado muchos daños, tal vez conviene utilizar un mapa satelital.

Un buen sitio para buscar mapas base es [este](https://leaflet-extras.github.io/leaflet-providers/preview/). Para agregar la base que se adapte mejor a nuestras necesidades, debemos crear añadir la etiqueta de ```script``` dentro de ```body``` y agregar la variable ```map```.

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
 
  </script>
</body>
</html>
```
<a href= "http://bl.ocks.org/micmicto/3d839eca390c719fd05cf66a3b65f7ef"></a>

Dentro de la variable ```map``` incluiremos las coordenadas del centro del mapa y el nivel de zoom al que se mostrará cuando se inicie. También añadiremos el link de la base que hayamos elegido y los créditos (No al plagio, dar crédito es importante).

### Insertar marcadores

Agregar marcadores es una buena manera de indicar la ubicación de diferentes lugares. Para ello solamente basta con agregar ```L.marker``` dentro del ```script```, agregar las coordenadas del lugar que queremos indicar y el texto que se mostrará cuando el usuario haga click sobre el marcador.

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
Pueden ver el mapa terminado <a href="http://bl.ocks.org/smicmich/0a48b64f6bbd0273f1184e19a2374116">aquí</a>.

Aunque por ahora parece un mapa simple, existen muchos [plugins](http://leafletjs.com/plugins.html) con los que se pueden añadir más funcionalidades.
