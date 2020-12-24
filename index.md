---
layout: default
altair-loader:
  altair-cityasthma: "final/1cityasthma.json"
hv-loader:
  hv-chart-1: ["charts/measlesHvplot.html", "500"] # second argument is the desired height
folium-loader:
  folium-chart-1: ["charts/foliumChart.html", "400"] # second argument is the desired height
  folium-chart-2: ["charts/percent_no_internet.html", "400"] # second argument is the desired height
---

# Understanding the relationship between nature, health, and wealth

Through altair plots, maps, and holoviz maps, I wanted to visualze whether there was an overlap between health, wealth, and nature.

I used data from [The CDC](https://chronicdata.cdc.gov/500-Cities-Places/500-Cities-Census-Tract-level-Data-GIS-Friendly-Fo/k86t-wghb).

# Part 1 - Understanding Health



## Altair Example

I wanted to start by understanding the relationship between access to healthcare and health issues. I started by looking at the relationship between access to healthcare and asthma. Below is a chart that shows this relationship.

<div id="altair-cityasthma"></div>

## HvPlot Example

Lastly, the measles incidence produced using the HvPlot package:

<div id="hv-chart-1"></div>

## Notes

- See the [raw source code](https://raw.githubusercontent.com/MUSA-550-Fall-2020/github-pages-starter/master/_posts/2019-04-13-measles-charts.md) of this post for details on how these charts were embedded.
- See the [lecture 13A slides](https://github.com/MUSA-550-Fall-2020/week-13/blob/master/lecture-13A.ipynb) for the code that produced these plots.

**Important: When embedding charts, you will likely need to adjust the width/height of the charts before embedding them in the page so they fit nicely when embedded.**

# Example: Embedding Folium charts

This post will show examples of embedding interactive maps produced using [Folium](https://github.com/python-visualization/folium).

## OSMnx and Street Networks

The shortest route between the Art Museum and the Liberty Bell:

<div id="folium-chart-1"></div>

<br/>

## Percentage of Households without Internet

The percentage of households without internet by county:

<div id="folium-chart-2"></div>

See the [lecture 9B slides](https://musa-550-fall-2020.github.io/slides/lecture-9B.html) and the [lecture 10A slides](https://musa-550-fall-2020.github.io/slides/lecture-10A.html) for the code that produced these plots.
