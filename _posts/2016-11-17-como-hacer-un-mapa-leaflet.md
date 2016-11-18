---
layout: post
title: Cómo hacer un mapa en leaflet
---

## Antes que nada... ¿qué es Leaflet?

Leaflet es una librería de JavaScript para crear mapas interactivos ¿? Leaflet es la herramienta que hace que puedas agregarle distintas funcionalidades a un mapa como marcadores, polígonos, capas, clusters para agrupar la información, geolocalización, etc.

¿Y qué es lo que hace todavía mejor a Leaflet? Que es fácil de usar aunque no tengas grandes conocimientos de programación.

**NOTA:** Si no quieren leer todo el post bastará con que copien, peguen y modifiquen la última caja de código del post ;)

## Comencemos

Algunas de las cosas que necesitaremos:

- Conocer un poco de HTML, CSS Y JavaScript.
- Ganas de fallar varias veces hasta conseguir lo que quieres.

## Iniciar un archivo HTML con cabeza y cuerpo

```html
<!DOCTYPE html>
<html>
<head>
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
<!DOCTYPE html>
<html>
<head>
<script src="http://cdn.leafletjs.com/leaflet-0.7.7/leaflet.js"></script>
<link rel="stylesheet" href="http://cdn.leafletjs.com/leaflet-0.7.7/leaflet.css" />
	<style>
	</style>
</head>
	<body>
		<div id = 'map'>
		</div>
	</body>
</html>
```
Si no quieren tomar leaflet de internet, bastará con que descarguen los archivos correspondientes [aquí](http://leafletjs.com/download.html) y especifiquen la ubicación de sus archivos.

### Indicar el estilo del mapa (ponerlo guapo)

Esta parte servirá sobre todo para indicar el tamaño de nuestro mapa y debe ir dentro de las etiquetas de estilo.

```html
<!DOCTYPE html>
<html>
<head>
<script src="http://cdn.leafletjs.com/leaflet-0.7.7/leaflet.js"></script>
<link rel="stylesheet" href="http://cdn.leafletjs.com/leaflet-0.7.7/leaflet.css" />
	<style>
		 #map { 
		    width: 100%;
		    height: 580px;
		    box-shadow: 5px 5px 5px #888;
		 }
	</style>
</head>
	<body>
		<div id = 'map'>
		</div>
	</body>
</html>
```
