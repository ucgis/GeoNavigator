---
title: "How to make an interactive map."
sub-title: "Transforming Your Map into an Interactive Experience."
parent: "finalize-map"
parent_url: /resources/finalize-map/
permalink: /resources/interactive-maps/
jobs_to_be_done:
  - "Identify key interactive map functions and their purposes."
  - "Select an appropriate platform for publishing an interactive map."
next-steps:
  - label: "I finished my map!"
    type: resource
    ref: celebration
---
<!--
<nav class="breadcrumbs">
  <a href="{{ '/' | relative_url }}">Home</a>

  {% if page.parent %}
    /
    <a href="{{ page.parent_url | relative_url }}">{{ page.parent }}</a>
  {% endif %}

  /
  <span>{{ page.title }}</span>
</nav>
-->
You’ve done all the work for creating a map \- congratulations\! Now it’s time to make the final version to share.

You are here because you want to make an interactive map rather than a static map (print, PDF, or other type of image). Interactive maps enable the user to engage with them in several ways, including:

* Turning map layers on or off in any combination  
* Panning and zooming   
* Clicking on a feature to learn more about it in a popup that appears

And it can get fancier than that\! You may have seen timelapse maps, 3D maps that you can tilt and spin, etc. But a good rule of thumb is to focus only on the types of interactions that will help the user understand the information presented in the map.

The best-known platform for creating interactive maps is ArcGIS Online. You can create an interactive web map directly in ArcGIS Online, or you can enable a map created in ArcGIS Pro to become an ArcGIS Online web map. Another Esri product, ArcGIS StoryMaps, allows you to share interactive maps along with text, video, and/or audio to provide context.

Similarly, QGIS has a plugin called [QGIS2Web](https://plugins.qgis.org/plugins/qgis2web/) that allows you to create a web map from your QGIS project.

Maps created in Google Earth for Web can be shared for others to explore just by copying the URL.

There are many considerations involved with making an interactive map. Below are just a few resources to help you.

## Resources:

* [ESRI: Create maps, scenes, and apps](https://doc.esri.com/en/arcgis-enterprise/latest/create/create-maps-and-apps.html?pivots=os-windows)  
* [Building Beautiful Interactive Mapping Applications with ArcGIS Basemap Services](https://www.youtube.com/watch?v=0gekWZy8k3w)  
* [QGIS](https://www.qgistutorials.com/en/docs/3/web_mapping_with_qgis2web.html)   
* [Google Earth: Create engaging map experience](https://mapsplatform.google.com/solutions/build-immersive-experiences/)
