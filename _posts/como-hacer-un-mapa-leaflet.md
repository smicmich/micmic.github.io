---
layout: post
comments: true
title: Cómo hacer un mapa sencillo en leaflet
---

## Antes que nada... ¿qué es Leaflet?

Leaflet es una librería de JavaScript para crear mapas interactivos ¿? Leaflet es la herramienta que hace que puedas agregarle distintas funcionalidades a un mapa como marcadores, polígonos, capas, clusters para agrupar la información, geolocalización, etc.

¿Y qué es lo que hace todavía mejor a Leaflet? Que es fácil de usar aunque no tengas grandes conocimientos de programación. Se los digo yo que estudié gestión intercultural (jahaa) y logré hacer [este mapa](http://nemachtilo.mx) con un poquito de esfuerzo.

**NOTA:** Si no quieren leer todo el post bastará con que copien, peguen y modifiquen la última caja de código del post ;)

## Comencemos

### Contenidos

- [Estructura de un mapa] (#estructura)
- [Código] (#iniciar-un-archivo-html)


Algunas de las cosas que necesitaremos:

- Conocer un poco de HTML, CSS Y JavaScript.
- Ganas de fallar varias veces hasta conseguir lo que quieres.

## Estructura

![Estructura de visualizacion de un mapa](/images/estructura-visualizacion.jpg)

![Estructura del código de un mapa](/images/estructura-codigo.jpg)

## Iniciar un archivo HTML 

Iniciar un archivo HTML con cabeza y cuerpo y un bloque llamado "map"

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

Esta parte servirá sobre todo para indicar el tamaño de nuestro mapa y debe ir dentro de las etiquetas de estilo `<style>``</style>`

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

### El cuerpo

Dentro de `body` y después de la sección `map` pondremos la información que queremos representar en el mapa ya sea en forma de marcadores, polígonos o líneas.
