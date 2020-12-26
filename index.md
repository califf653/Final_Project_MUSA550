---
layout: default
altair-loader:
  altair-asthma: "charts/1cityasthma.json"
  altair-teeth: "charts/2cityteeth.json"
  altair-cancer: "charts/cancer.json"
  altair-diabetes: "charts/diabetes.json"
  altair-mh: "charts/mentalhealth.json"
  altair-asthmac: "charts/asthmac.json"
  altair-teethc: "charts/teethc.json"
  altair-cancerc: "charts/cancerc.json"
  altair-diabetesc: "charts/diabetesc.json"
  altair-mhc: "charts/mentalc.json"
hv-loader:
  hv-chart-1: ["charts/healthdash.html", "500"] # second argument is the desired
---

# Understanding the relationship between trees, health, and wealth in Philadelphia

Through altair plots, maps, and holoviz maps, I wanted to visualze whether there was an overlap between health, wealth, and nature.

I used data from [the CDC](https://chronicdata.cdc.gov/500-Cities-Places/500-Cities-Census-Tract-level-Data-GIS-Friendly-Fo/k86t-wghb).

## Part 1 - Understanding Health: Looking statewide

To understand health, I wanted to start by investigating the relationship between access to healthcare and health issues. To find this relationship, I used scatterplots. If the dots are generally trending up and right, it means that the more people without access to healthcare there are, the more incidence of that disease. I assume that a higher lack of healthcare means higher unemployment and higher poverty rates. Below I will show those relationships with Altair. Altair is best suited for this kind of analysis because it's interactive and cross-referential, which is helpful here when wanting to dive deeper into multiple cities and lots of points that are near each other.

To 

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


## Part 2 - Mapping health indicators in Philadelphia

To better understand how access to healthcare and distribution of the prevalence of cancer, mental health, diabetes, tooth loss, and asthma present in Philadelphia specifically, I created an HVplot dashboard to show how each census tract relats to each health problem on a map. You may use the dropdown menu to look at each.

<div id="hv-chart-1"></div>

To make these maps, I had to join my health data frame, which's geometry was in points, with my census tract shape file's polygons. I used a "within" spatial join to achieve this. Once joined, I had to merge the new spatially joined DF to the existing geodataframe. To make the hvplot map, I was running into problems with trying to represent strings and integers, so I had to make sure I converted 'value' to a numerical value. I chose an ESRI basemap because I like the natural look for this kind of polygon map. I could have chosen from a pool of others, like a street map.

Access to healthcare is most limited in North Philadelphia, in an area with a large Puerto Rican population. Asthma is widespread across the city, but most visibly on the Schuyllkill River, likely due to the amount of industry historically in that area. 14+ mental health days are more common in the city, but seem to be least in the outter rings of Philadelphia and Center City.  Tooth loss, diabetes, poverty, and race seem to overlap in West Philly, North and Northeast Philly, and is less pronounced in Center City and other Whiter neighborhoods.  Cancer is relatively low-prevalence, but has some high-occuring census tracts in the north.

Race and poverty are variables I haven't mapped in this project but are easily verified elsewhere. If I were to add to this project, I would map current race makeup and poverty to add robustness. 

## Part 3 - Layering historic redlining data: Does historic racial descrimination matter?

To investigate whether there was a relationship between redlining and access healthcare and subsequent health outcomes, I overlayed the health map onto the redlined map of Philadelphia.


Trees and redlining

