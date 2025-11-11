---
layout: page
title: Cyber Funding
description: Exploring the impacts that cyber and charter school tuition has on public school districts in Pennsylvania.
# img: cyber pic.jpg
importance: 1
category: work
related_publications: true
---

##Project Overview
There is a lot of discussion on the impacts that charter school per student tuition rates have had on public school districts and their consituents as shown by this [presentation to the PA House Democratic Policy Committee](https://www.pahouse.com/files/Documents/Testimony/2022-04-04_112445__040422%20Merged%20Agenda%20Testimony.pdf) and this [Pennsylvania State audit of Cyber Charter School funding](https://paauditor.b-cdn.net/wp-content/uploads/speCyberCharters022025.pdf). State Representatives, education organizations and impacted school districts have been working together to make adjustments to this formula to create a more equitable tuition rate that would benefit all students in Pennsylvania resulting in this [proposed legislation to create an equitable funding formula for PA Charter Schools](https://pahouse.com/InTheNews/NewsRelease/?id=138406). These data explore the specific financial impacts that cyber charter school tution rates have had on public school districts in Pennsylvania during the 2022-2023 school year.

##Exploratory Data Analysis
I collected raw data from the Pennsylvania Department of Education website. I wanted to identify what percentage of district budgets were allocated for cyber charter school tuition. I created a helper table combining these data from two data sets (tuition.xlsx) and created a table to visualize the school districts that paid higher vs. lower percentages (public school expenses for cyber tuition.xlsx).

#Insights
The school district most impacted is Aliquippa School District in Western PA. 15% of their budget went to cyber charter school tuition in the 2022-2023 school year. All of the districts that paid at least 10% of their budget to cyber charter school tuition were midsized school districts with budgets between $20M and $50M. Most districts in PA allocated 8% or less of their budgets to cyber charter school tuition. The largest districts in PA, Philadelphia (5B budget) and Pittsburgh (800M budget) spent 5% of their budget on cyber charter school tuition.

<iframe width="98" height="120" src="https://1drv.ms/x/c/7426DB25AA193AE9/IQRUhu-eQmFPQoHRhYX5ypX-AfwIYUEi2robyi8ef-HmOHY" frameborder="0" scrolling="yes"></iframe>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="<iframe width="98" height="120" src="https://1drv.ms/x/c/7426DB25AA193AE9/IQRUhu-eQmFPQoHRhYX5ypX-AfwIYUEi2robyi8ef-HmOHY" frameborder="0" scrolling="yes"></iframe>" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

##SQL
I imported all of the raw data and EDA to SQL to dig deeper into the impacts of cyber charter school tuition on public school districts. I identified some remaining questions I had, particularly what populations of people are most affected by the tuition rates paid to the cyber charter schools. To explore this, I found additional data on the PA Department of Education website on the racial make up of the states' districts and which counties are designated rural and urban. I was really hoping to find data also identifying suburban school districts, but I was unable to find these data. I also wanted to look at the impacts of cyber funding on special education students, both enrolled in cyber charter schools and the funding for public school districts but I was unable to find the data that I needed.

#Insights
Looking at the impacts on rural vs. urban districts, these data showed minimal differences. The average percentage of tution for rural schools was 0.034 and for urban districts, 0.027. Looking at the racial makeup of the school districts that are paying a greater percentage of their annual budget to cyber charter schools vs. districts that paid less was more distinct. Most of the minority majority school districts paid 5% of their annual budget to cyber charter schools, as well as Aliquippa and Chester-Upland, the schools paying the highest and 4th highest percentages.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="cyber pic.jpg" title="Cyber Funding" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images, even citations {% cite einstein1950meaning %}.
Say you wanted to write a bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, _bled_ for your project, and then... you reveal its glory in the next row of images.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
