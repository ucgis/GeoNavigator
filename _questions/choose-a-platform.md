---
title: "Let's choose a platform for your map!"
sub-title: "Explore your options for creating, analyzing, and sharing maps"
permalink: /choose-a-platform/
next-steps:
  - label: "I still need to find some data first."
    type: resource
    ref: finding-gis-data
  - label: "My data is clean"
    type: resource
    ref: ingest-data 
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

Choosing an appropriate GIS platform for your needs comes down to your goals, timeframe, and GIS expertise. Do you need to make simple web maps, do complex spatial analysis, or manage large sets of data?  

Not all GIS or mapping platforms are the same! While almost all of them can perform basic mapping tasks, some are complicated to learn because they can perform specialized or computational tasks in addition to the basics. Other platforms are focused on telling stories with maps. Some are web-based, others need to be installed on your device. While some platforms are well-known, more obscure ones may be exactly what you need.

## Considerations
Everyone’s needs for making a map can vary widely. Here is some guidance that can help frame your choice of an appropriate platform.

<!-- Expand / Collapse Controls -->
<div style="margin: 1.5rem 0;">
  <button onclick="expandAll()">Expand all</button>
  <button onclick="collapseAll()">Collapse all</button>
</div>

<details class="collapsible" markdown="1">
<summary markdown="span"><strong>What do you need to do?</strong></summary>  
  <ul>
    <li>If you just need to plot locations, create a heat map, or tell a visual story, you don't need something with heavy analytical software.</li>
    <li>If you plan to do data manipulation, raster/vector geoprocessing, 3D mapping, etc., then choose a product that provides more robust analytics.</li> 
  </ul>
</details>
<details class="collapsible" markdown="1">
<summary markdown="span"><strong>Do you have experience working with GIS software previously? Do you have a deadline?</strong></summary>
  <ul>
    <li>If you don't have much experience or are on a tight deadline, choose a simpler platform that might feature drag and drop functionality and requires little to no training to use. If you have the time and are already familiar with GIS tools, consider choosing a platform with more features for creating the map you envision.</li> 
  </ul>
</details>
<details class="collapsible" markdown="1">
<summary markdown="span"><strong>What is your computing platform (Windows / Mac)?</strong></summary>  
  <ul>
    <li>Esri’s ArcGIS Pro only runs well on Windows machines, although you might have the option of accessing it through a virtual machine. By contrast, QGIS will run equally well on multiple computing platforms.</li>  
  </ul>
</details>
<details class="collapsible" markdown="1">
<summary markdown="span"><strong>What type of files are you working with? (raster / vector) Are you creating data or using existing data?</strong></summary>   
  <ul>
    <li>GIS platforms vary in their ability to work with different data formats, including data you collected (drone, GPS, etc.) or data from external sources.</li>
    <li>If you want to analyze raster data, talk to your librarian about specialized tool options.</li>  
  </ul>
</details>
<details class="collapsible" markdown="1">
<summary markdown="span"><strong>Are you working alone or with a group?</strong></summary>   
  <ul>
    <li>Platforms such as ArcGIS Online allow for collaboration in groups, and for crowd-sourced updates to a map. Some desktop GIS provide the means for collaborative work. Usually, only one person can work on the map at a time.</li> 
  </ul>
</details>
<details class="collapsible" markdown="1">
<summary markdown="span"><strong>Do you have a preference between vendor based systems vs. open source platforms?</strong></summary>    
  <ul>
    <li>Vendor based (subscription required): users can access this software by individual subscription or through a campus subscription. Such platforms tend to come with support, extensive documentation, and possibly integration with other tools. Some vendor tools have freemium business models, where you can use a basic version for free but would have to pay for advanced capabilities.</li>
    <li>Open Source (no subscription required): free to use and community driven. Tends to have community support. A benefit of using open source software is that you will maintain access when you leave the university.</li>   
  </ul>
</details>
<details class="collapsible" markdown="1">
<summary markdown="span"><strong>Do you need to share your work through an interactive platform (maps, tables, narrative)?</strong></summary>   
  <ul>
    <li>Some platforms are designed for easily sharing maps and visualizations online.</li>   
  </ul>
</details>
<details class="collapsible" markdown="1">
<summary markdown="span"><strong>Are you sharing work and data with non GIS users?</strong></summary>   
  <ul>
    <li>Consider a platform that provides an easy-to-understand user interface.</li>  
  </ul>
</details>
<details class="collapsible" markdown="1">
<summary markdown="span"><strong>Do you need to keep a level of security around your data?</strong></summary>   
  <ul>
    <li>ArcGIS Online allows different levels of sharing. Choose a desktop platform if you need to restrict access to elements of your data.</li>
    <li>Check with your librarian to get more guidance if data security is a concern.</li>
  </ul>
</details>

## Don’t know where to begin in choosing a GIS platform? 
Take a look at the [GIS and Digital Mapping Tools matrix](https://docs.google.com/spreadsheets/d/e/2PACX-1vRO90zVdeOgK7gMNa1lLuP7RfZXsqB0SYuW5vgmRsOMpWjlg9ruUbjiSSIf8lqq5OiCp0f6tLDTHOEr/pubhtml) compiled by UC Riverside Library. The matrix evaluates the capabilities of several mapping platforms side by side all in one view, with additional tabs that only show tools related to making a map, analyzing spatial data, or creating a narrative with maps. The [associated library research guide](https://guides.lib.ucr.edu/c.php?g=171041&p=8392166) contains additional information about each tool.

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
