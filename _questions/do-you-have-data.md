---
title: "Do you have the data you need?"
sub-title: "Here are some questions to think through about your data before you get started mapping."
permalink: /do-you-have-data/
next-steps:
  - label: "Yes, it's a GIS file or online mapping platform"
    type: question
    ref: choose-a-platform
  - label: "Yes, it's a spreadsheet"
    type: resource
    ref: what-is-geo-id
  - label: "Yes, it's a digitized image of a map"
    type: resource
    ref: work-with-images
  - label: "No, I don't have data that’s ready to be used"
    type: resource
    ref: finding-gis-data
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

To get started mapping, you’ll need data that’s tied to locations. Knowing what format your data is in will help you map it in the most efficient way. You may find that you have several different types of data. We recommend starting with one type and then revisiting this page to review your other types. 

Additional questions to think about before and during your mapping adventures:  
* Does your data cover your area of interest? 
* Does it represent what you need it to in the way you need it to? 
* Does it contain personally identifiable information (PII)? 
* Does it cover the time period you need it to?

<!-- Expand / Collapse Controls -->
<div style="margin: 1.5rem 0;">
  <button onclick="expandAll()">Expand all</button>
  <button onclick="collapseAll()">Collapse all</button>
</div>
<details class="collapsible">
<summary><strong>GIS Files + Online Platforms</strong></summary>
<p></p>Sometimes we find data that’s available in one of the many acceptable GIS file formats. Here are some common GIS file types:
  <ul>
  <li>Shapefile (zipped collection of subfiles): Contains point, lines, and areas</li>
  <li>GeoJSON (.geojson)</li>
  <li>KML/KMZ (.kml/.kmz)</li>
  <li>GeoTIFF (.tiff)</li>
  <li>Geodatabase (.gdb)</li> 
  <li>Geopackage (.gpkg)<</li>
  <li>ArcGIS Pro project package (.ppkx)v</li> 
  </ul>
<p>There may be other times where you don’t have a tangible file. Your data might already be in an online GIS platform.</p> 
</details>
<details class="collapsible">
<summary><strong>Spreadsheets</strong></summary>
<p>Many times you may have data that is in a spreadsheet format. If your data is in a spreadsheet, you must have at least one field that contains location based information. This may include, Latitude/Longitude, an address, or some other type of geographic identifier (such as census tracts, administrative boundaries, school districts, or other).
  <ul>
  <li>CSV</li>
  <li>XLSX</li>
  <li>TXT</li>
</ul>
</p>
</details>
<details class="collapsible">
<summary><strong>Image</strong></summary>
<p>If you have a scanned image of a map, you can utilize it in a GIS platform.</p> 
</details>
<details class="collapsible">
<summary><strong>Other</strong></summary>
<p>Depending on the size of your data and where it’s coming from, the data may be provided as a service that you can add directly to your map rather than downloading it. Reach out to your Librarian if you are interested in this.</p>
</details>

<script>
function expandAll() {
  document.querySelectorAll('details.collapsible')
    .forEach(d => d.open = true);
}

function collapseAll() {
  document.querySelectorAll('details.collapsible')
    .forEach(d => d.open = false);
}
</script>
