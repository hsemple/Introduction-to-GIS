---
permalink: /openlayers/
title: "Introduction to Open Layers"
sidebar:
  nav: "docs"
---


OpenLayers is a JavaScript library that contain functions for creating interactive web maps.  Fortunately, the code samples can be understood with moderate effort.  Learn more about Open Layers by visiting their [homepage.)(https://openlayers.org/)



### Building a Simple Open Layers Web Mapping Application

1. First, take a look at this [site](https://medium.com/attentive-ai/working-with-openlayers-4-part-1-creating-the-first-application-9ab27bbd7a62) to see how a basic web mapping application is built using Open Layers.


2. Copy the code, save it as a html file, then run it on your local computer.  If any error arises, trouble shoot it.Once the code runs successfully, study the code and try to understand what each line does. Explanations are provided via links.

 
#### Code to Create a Simple Open Layers Map

    <!doctype html >
    <html lang = "en" >
    <head >
    <link rel = "stylesheet" href = "https://openlayers.org/en/v4.6.5/css/ol.css" type = "text/css" >
    <script src = "https://openlayers.org/en/v4.6.5/build/ol.js" >< /script> 
    </head>

    <style >
      .map {
        height: 600 px;
        width: 80 % ;
      } 
    </style> 

    <title > OpenLayers Example < /title>
    </head>


    <body >

    <h2 > My Map < /h2>

    <div id = "map" class = "map" >

    <script type = "text/javascript" >
        var map = new ol.Map({
            target: 'map',
            layers: [
                new ol.layer.Tile({
                    source: new ol.source.OSM()
                })
            ],
         view: new ol.View({
         center: ol.proj.fromLonLat([-66.879714, 10.474557]),
           zoom: 4
            })
        }); 

    </script>

    </div> 
    </body> 
    </html>



You can view the code explanation [here](https://openlayers.org/en/latest/doc/quickstart.html).  


<br>

### Extending the OpenLayers Application

In the previous unit, we created a simple web map that had only one layer, an Open Street Map base map. In this unit, we will add several of our own vector layers to the application. We will also add a couple of WMS layers from online sources.  Finally, we will add controls to the map to turn the layers on and off, and turn on the scale bar, and zoomslider.

 
The illustration below shows an OSM layer overlaid with a Michigan Geology layer. The code sample shows how it is accomplished.  Please make sure that you study the code in the Code Explanation below.



    <!doctype html>
    <html lang="en">
    <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1">
      <link rel="stylesheet" href="https://openlayers.org/en/v4.6.5/css/ol.css" type="text/css">
      <script src="https://openlayers.org/en/v4.6.5/build/ol.js"></script>
      <title>OpenLayers Web App</title>
      <style>
         html, body{
         margin: 0px;
         padding: 0px;
         border: 0px;
         }

         #map {
         height:85%;
         width: 63%;
         margin: auto;
         }

         #container {
         margin: auto;
         width: 90%;
         }
      </style>
    </head>
    <body>
      <div id=“container”>
         <div id="map">
            <center>
               <h1>  Interactive Web Map with Multiple Layers </h1>
            </center>
         </div>
         <script type="text/javascript">
            var osmlayer = new ol.layer.Tile({
            source: new ol.source.OSM()
            });
            
            
            // -- Load Michigan geology as a WMS layer --
            var arcGISTileLayer = new ol.layer.Tile({
              title: 'ArcGIS Tile',
              type: 'base',
              name: 'ArcGIS Map Tile',
              visible: false,
              source: new ol.source.TileArcGISRest({
                url: 'http://services.arcgisonline.com/ArcGIS/rest/services/World_Topo_Map/MapServer'})
              });
              arcGISTileLayer.setVisible(true);                  
            
            // -- Load US geology layer as a WMS layer --
            var geology = new ol.layer.Tile({
              source: new ol.source.TileWMS({
                url: 'https://mrdata.usgs.gov/services/kb?',
                params:{'LAYERS': 'Geology', 'TILED': true},
                })
               });
              geology.setVisible(false);	               
            
            var us_faults = new ol.layer.Tile({
              source: new ol.source.TileWMS({
                url: 'https://mrdata.usgs.gov/services/sgmc?',
                params:{'LAYERS': 'State_Geologic_Map_Compilation', 'TILED': true},
                })
               });
              us_faults.setVisible(true); 	
            
            // -- Load shapefiles into Openlayers as geojson.  
            var parcels = new ol.layer.Vector({
              source: new ol.source.Vector({
               format: new ol.format.GeoJSON(),
               url: 'bedrock_geology.geojson',
               defaultProjection :'EPSG:4326', projection: 'EPSG:3857'
               })
            });
            
            var map = new ol.Map({
               target: 'map',
               renderer: 'canvas',
               layers: [osmlayer, geology, parcels],
            
            view: new ol.View({
                center: ol.proj.fromLonLat([-85.257728,43.649808]),
                zoom: 6
               })
            });
            
            </script>
          </div>
       </body>
     </html>


#### Code Explanation
The most significant additions to this code relative to the previous one are the variables that contain map layers. The map layers are in GeoJson format. Both ArcMap and ArcGIS Pro have tools for exporting shapefiles to geojson format. GeoJSON is a popular format for handling geographic data on the web.  Many web mapping programs can parse it, including OpenLayers and Google Maps API.

For this application, I used QGIS to export the shapefiles to GeoJSON format.   Once the files are converted to geojson, you can upload them to the server. The layer is referenced in the code as shown below.  

        var roads = new ol.layer.Vector({
        source: new ol.source.Vector({ 
        format: new ol.format.GeoJSON(),  
	 url: 'roads.geojson',  	
        });	

Notice that the geojson is being declared as a Vector, and not as a Tile. The data source is vector. The URL is the URL of the geojson layer. In this case, because the geojson is in the same folder with the web page, we simply write the name of the file and along with its 

<br>


### Adding Open Layers Controls to the Map

The link below point to sample codes for adding open layers scale bar to your map. Study the sample, extract relevant sections of code, and add them to your code to build your application.

 * [Scale bar](https://labs.webgeodatavore.com/workshop-openlayers-3-foss4g-uk-2016/controls/scaleline.html)
 * [Adding a Zoom Slider](https://openlayers.org/en/latest/examples/zoomslider.html)

 
