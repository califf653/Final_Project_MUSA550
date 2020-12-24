---
layout: default
altair-loader:
  altair-asthma: "1cityasthma.json", "500"
  altair-teeth: "2cityteeth.json", "500"
  altair-cancer: "cancer.json", "500"
  altair-diabetes: "diabetes.json", "500"
  altair-mh: "mentalhealth.json", "500"
  altair-asthmac: "asthmac.json", "500"
  altair-teethc: "teethc.json", "500"
  altair-cancerc: "cancerc.json", "500"
  altair-diabetesc: "diabetesc.json", "500"
  altair-mhc: "mhc.json", "500"
hv-loader:
  hv-chart-1: ["charts/measlesHvplot.html", "500"] # second argument is the desired
folium-loader:
  folium-chart-1: ["charts/foliumChart.html", "400"] # second argument is the desired height
  folium-chart-2: ["charts/percent_no_internet.html", "400"] # second argument is the desired height
---

# Understanding the relationship between trees, health, and wealth in Philadelphia

Through altair plots, maps, and holoviz maps, I wanted to visualze whether there was an overlap between health, wealth, and nature.

I used data from [the CDC](https://chronicdata.cdc.gov/500-Cities-Places/500-Cities-Census-Tract-level-Data-GIS-Friendly-Fo/k86t-wghb).

## Part 1 - Understanding Health: Looking statewide

To understand health, I wanted to start by investigating the relationship between access to healthcare and health issues. To find this relationship, I used scatterplots. If the dots are generally trending up and right, it means that the more people without access to healthcare there are, the more incidence of that disease. I assume that a higher lack of healthcare means higher unemployment and higher poverty rates. Below I will show those relationships.

### Asthma

The first relationship I plotted was that of the prevalence of asthma and a lack of healthcare. The scatter plot shows that a larger population without healthcare also generally implies a higher population with asthma. However, there are some outliers, particularly in smaller cities. Perhaps ashtma is more related to an environmental issue or genetics than it is to healthcare access.

<div id="altair-asthma"></div>
<div id="altair-asthmac"></div>


### Tooth Loss

The second relationship I looked at was between access to healthcare and tooth loss. Half of all Americans don't have access to dental helathcare. The reason for poor dental health is often from [sugary food being more affordable](https://plutusfoundation.org/2020/healthy-eating-budget/#:~:text=Unhealthy%20food%20choices%20tend%20to,purchase%20cheap%20premade%20frozen%20dinners) than organic produce (not to mention more time saving). The effects of this [range from](https://longreads.com/2017/05/18/rich-teeth-poor-teeth-life-along-the-dental-divide/) reinforcing the cycle of poverty to opiod addiction and life-threatening antibiotic resistance. Dental health is an often overlooked indicator of wealth and a pressing issue in the US. Let's see if the numbers tell the same story.

<div id="altair-teeth"></div>
<div id="altair-teethc"></div>

Here, the numbers much more strongly show a correlation between tooth loss and access to healthcare. There is a linear relationship between the two in every city.

### Cancer

<div id="altair-cancer"></div>
<div id="altair-cancerc"></div>

From the charts, cancer seems to be a much less discriminating illness. Its incidence has little to do with access to healthcare; incidence seems to cluster and even trend downwards as access to healthcare decreases.

### Diabetes

Diabetes has a similar relationship to healthcare access as asthma. Firstly, it is pretty highly occuring, and it's very related to healthcare access particularly in the larger cities of Philadelphia and Pittsburgh.

<div id="altair-diabetes"></div>
<div id="altair-diabetesc"></div>


### Mental Health

Access to mental healthcare and the amount of people with more than 2 weeks of poor mental health are highly related, similar to dental health. Mental health is exacerbated by stress, which can be a consequence of not being able to pay healthcare bills or even access a healthcare provider.

<div id="altair-mh"></div>
<div id="altair-mhc"></div>


## Part 2 - Mapping health indicators in Philadelphia, including trees


## Part 3 - Layering historic redlining data: Does historic racial descrimination matter?


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
