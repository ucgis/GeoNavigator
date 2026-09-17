---
title: "Let's check that the data coverage is what you need?"
sub-title: "Does it cover the area, scale, time frame, or is it not detailed enough?"
parent: "ingest-data"
parent_url: /resources/ingest-data/
permalink: /data-coverage/
next-steps:
  - label: "I'm just mapping locations." 
    type: resource
    ref: finalize-map 
  - label: "I'd like to map something about the data." 
    type: resource
    ref: qual-quant 
  - label: "The data isn’t matching what I need." 
    type: resource
    ref: finding-gis-data 
  - label: "I need to do some data cleanup first." 
    type: resource
    ref: cleaning-messy-data 

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

Before going any further with mapping the data, make sure it completely covers the area you expected it to and only the area you need. If it doesn’t, there may be an issue with the way the data loaded into the GIS, or it may be that the data you acquired has gaps, covers a smaller extent than what you expected, or you just want a subset of the larger geographic area (e.g. a county when you have the full state).

**Is your data in the right part of the world?**   
  1. Check and reformat your x,y data if needed.   
  2. For geocoded addresses, you may need to do some additional data cleanup  
       
**Does it include the geographic areas you expect your data to cover?**  
  1. Different data providers may have different definitions for the geographic extent of natural features (e.g. the Sonoran Desert) or populated regions (e.g. the greater Los Angeles area). You may have to return to searching for data.  
  2. In some datasets, sensitive regions such as military installations may be excluded, creating holes in the area covered.

**Does your data include more than you need (e.g. you are only looking at a county, but your data covers the state, or you just need elementary schools, but your dataset includes middle and high schools too)?**   
  1. If you only need a smaller portion of your dataset, you can **filter** your data. Filtering is the process of isolating specific geographic features or attributes from a larger dataset based on defined criteria. It allows you to reduce clutter, run targeted spatial analyses, or prepare data for visual presentation.   
  2. GIS data can be filtered using three main approaches based on attributes, spatial relationships, or time.  
     **Attribute Filters:** Isolates data based on the tabular information linked to geographic features (e.g., selecting all roads where SPEED\_LIMIT \> 55).  
     **Spatial Filters:** Isolates data based on geometric relationships between two layers (e.g., finding all residential parcels that *intersect* a 100-year flood zone).  
     **Temporal Filters:** Isolates data based on a time component (e.g., viewing traffic accidents that occurred *after* 5:00 PM or *between* specific dates). 

**Is any of the data missing?** (Geographic coverage, Is the data outdated? Do you need something more recent?, etc.)  
  * Determine which data is missing and conduct a search for new/additional data.  
       
**Is there an issue with the data upload?** (Are there missing rows, ex. The table has 200 rows but you only have 50.)  
  * Check your original dataset and reupload to see if that resolves the issue.  
       
**Is your data too generalized?**   
  * You may need to find a more specific dataset if the data is too general for your area.

This is not an exhaustive list of questions, rather a guide to help you while you search for the data that is best for your project.
