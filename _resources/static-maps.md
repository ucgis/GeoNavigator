---
title: "How to print or take a screenshot of a map."
sub-title: "A static map is a fixed, non-interactive image of a geographic area"
parent: "finalize-map"
parent_url: /finalize-map/
permalink: /resources/static-maps/
jobs_to_be_done:
  - "Evaluate map scale, layout, readability, and accessibility before finalizing a map."
  - "Select suitable output settings, including map size and print resolution (DPI)."
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
You’ve done all the work for creating a map **congratulations!** 

Now it’s time to make the final version to share.

If your map is going to be a static rather than an interactive map, you have a few options for creating a map suitable for printing.

## Export

GIS platforms typically provide an option for exporting (some software may use the terms “share” or “print”) your map to file formats such as PDFs, JPGs, or others. 

Before exporting:

* Make sure your map is zoomed to the appropriate scale and centered so all of your data will be visible in the resulting file.  
* Check the appearance of your map, ensuring that symbols are easily distinguishable from each other and that labels are easily read. Also apply any tools for checking accessibility that may be available. Make any necessary adjustments.  
* Verify the size of your output map and how it will be printed. Is it a stand alone map? Is this a map to be included in a report or publication?   
  * DPI: In Esri software, standard printing resolutions range from 150 to 300 DPI (dots per inch). For professional cartography, 300 DPI is the gold standard. 

## Screenshot

Sometimes, just taking a screenshot of your map will suffice. The Snipping Tool in Microsoft Office, or keyboard shortcuts for a Mac (Shift \+ Command \+ 4), will enable you to capture a copy of what you see on your screen. Depending on the need, you could include the Contents pane in your screen capture to serve as a legend.

## Layout

Desktop GIS platforms such as ArcGIS Pro and QGIS have tools for you to create a map layout, where you can add features to the final map such as a title, legend, annotation, and a north arrow. 

It can be challenging to learn how to work with layout tools. If your map is simple enough and will have explanatory text associated with it, you may be able to avoid creating a layout. 

If you are working in ArcGIS Online and need some of the layout elements, you’ll have the opportunity to add layout elements whether you print or export the final map. Resources about layouts are provided below.

## Resources

* [ArcGIS Online: Print maps](https://doc.arcgis.com/en/arcgis-online/get-started/print-maps-mv.htm)  
* [ArcGIS Online: get started with apps](https://doc.arcgis.com/en/arcgis-online/get-started/arcgis-apps.htm)  
* [Layout in ArcGIS Pro](https://pro.arcgis.com/en/pro-app/3.4/get-started/add-maps-to-a-layout.htm)   
* [Layout in QGIS](https://docs.qgis.org/3.44/en/docs/training_manual/map_composer/map_composer.html)
