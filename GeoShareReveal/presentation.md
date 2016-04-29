<!-- .slide: class="title" -->

## GeoShare
Proyecto Final de Master de Esri 2016

[https://github.com/Jimeno0/PFM-GeoShare/](https://github.com/Jimeno0/PFM-GeoShare/)

---

<!-- .slide: class="section" -->

## Introducción a la App

[![Everything Is AWESOME](http://img.youtube.com/vi/Hzyg60Gfl-M/0.jpg)](https://www.youtube.com/watch?v=Hzyg60Gfl-M "Everything Is AWESOME")

---

<!-- .slide: class="section" -->

## Material empleado

* ArcMap 10.3
	* Desarrollo del proyecto y tratamiento de datos
* PyScripter
	* Geoprocesamientos
* SQL Server
	* Gestionar permisos en la BBDD Enterprise
* ArcGIS Server Manager
	* Publicación de servicios
* ArcGIS Online
	* Creación de los Web Maps
	*Publicación de servicios
* Web AppBuilder for developers & Sublime Text 3
	* Creación de la aplicación web

---

<!-- .slide: class="section" -->


##Datos de partida

* Open Street Map

	* http://download.geofabrik.de/europe/spain.html

	* Pluggin para ArcMap: https://www.arcgis.com/home/item.html?id=75716d933f1c40a784243198e0dc11a1

* MDT
	
	* http://centrodedescargas.cnig.es/CentroDescargas/buscadorCatalogo.do?codFamilia=02107

---

<!-- .slide: class="section" data-transition="fade"-->

##Tratamiento de datos previos a la realización del Network

* Población de la red
* Correcciones topológicas
* Cálculo de los desniveles por tramo
* Cálculo del tiempo por tramo en bici
* Creación de la feature class de los puntos de interés

--



---

<!-- .slide: class="section" -->


##Creacion del Network

---

##Geoprocesamientos

---

##Arquitectura y versionado

---

##Publicación de los servicios

---

##Desarrollo de la app

---

###Objetivos

* Aplicación sencilla
* Fácil de usar
* Diseño atractivo

---

###Integración de Bootstrap en Web AppBuilder


https://github.com/tomwayson/web-appbuilder-bootstrap

![Bootstrap GitHub repo](images/BootstrapGitHub.png)

--

####Archivos necesarios

* index.html
* init.js

![Bootstrap on init](images/BootstrapOnInit.png)

--

####Requires

![Bootstrap on require](images/BootstrapOnRequire.png)


---

###Simplificación de la app

>* A través del config.json
	* Eliminación de widgets que no utilizamos
	* Ubicación de los widgets y personalización
	![configJson widget objects](images/json.png)

--

![widgets colocados](images/widgetsColocados.png)


--

###Otras ediciones de la App

>Para hacer cualquier cambio de la aplicación podemos identificar el elemento a traves de la consola de google chrome y luego viendo donde se encuentra el elemento aplicarle los cambios que consideremos necesarios

![Identificando elementos con la consola](images/indentifiicandoConsolaGoogle.png)

---

###Widgets

####Objetivo apliciación social

* Dieño:
	* Sencillo
	* Intuitivo
	* Atractivo

---

###Widgets de geoprocesamiento

* Cálculo de rutas
* Busqeda de puntos de interés cercanos

--

#### Cálculo de rutas

![Widget rutas](images/rutasWidget.png)

--

###HTML

* Tabs:

```HTML
	<ul class="nav nav-tabs" role="tablist">
		<li class="nav-item active">
	 		<a class="nav-link" 
	 		data-dojo-attach-event="onclick:funcionParamBici" href="#bici" 
	    	role="tab" data-toggle="tab">
	    		<img class="hidden-xs" 
	    		src = "http://localhost/ICONOS/icon-60693.png" alt = "Bycicle icon">
	    	</a>
	    </li>
	    ....   
```
* Tab-panel:


```HTML
    <div class="tab-content">
      <div class="tab-pane active" id="bici" role="tabpanel">
      <br>
        <label>
          <input type="checkbox" data-dojo-attach-point="trafficRadio" unchecked>
            Evitar carreteras con tráfico
          </label>
      </div>
      ....
```

--

###HTML

####Botones:

* Inicio & final

```HTML
<div id=inicioDiv>
	<button type="button" class="btn btn-default" data-dojo-attach-event="onclick:funcionCapaInicio">
    	<span class="glyphicon glyphicon-pushpin" aria-hidden="true"></span>
    	Inicio
    </button>
    <button type="button" class="btn btn-link" data-dojo-attach-event="onclick:funcionBorrar">
    	Borrar
    </button>
</div>
  ....
```
* Calcular

```HTML
    <div id= calculoDiv>
          <button type="button" class="btn btn-primary" data-dojo-attach-event="onclick:funcionCalcular">
            Calcular
          </button>
    </div>
```

--

--

###JAVASCRIPT

Ciclo de vida del widget

```javascript

	postCreate: function() {
	},
	startup: function() {
	},
	onOpen: function() {
	},
	onClose: function() {
	}
```

--

###JAVASCRIPT

```javascript
   	startup: function() {
	      this.inherited(arguments);
	      this.graphicPuntos = new GraphicsLayer();
	      this.map.addLayer(this.graphicLineas);
	      this.pInicioSymbol = new PictureMarkerSymbol('http://esri.github.io/quickstart-map-js/images/blue-pin.png',20,35);
	      this.pInicioSymbol.yoffset = 17;

	      ...
    	},

```
























---



<!-- .slide: class="section" -->

## List
* List item
	* List sub-item

---

<!-- .slide: class="section" -->

## List
* List item
	* List sub-item

---

<!-- .slide: class="section" -->

## Code
```javascript
var pi = 3.14;
var text = 'Hello world';
```

---

<!-- .slide: class="questions centered" -->

## Questions?

Contact info

---


<!-- .slide: class="end" -->
