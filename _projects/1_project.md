---
layout: page
title: Cyber Funding
description: Exploring the impacts that cyber and charter school tuition has on public school districts in Pennsylvania.
img: assets/img/cyber pic.jpg
importance: 0
category: work
related_publications: true
---

## Project Overview

There is a lot of discussion on the impacts that charter school per student tuition rates have had on public school districts and their consituents as shown by this [presentation to the PA House Democratic Policy Committee](https://www.pahouse.com/files/Documents/Testimony/2022-04-04_112445__040422%20Merged%20Agenda%20Testimony.pdf) and this [Pennsylvania State audit of Cyber Charter School funding](https://paauditor.b-cdn.net/wp-content/uploads/speCyberCharters022025.pdf). State Representatives, education organizations and impacted school districts have been working together to make adjustments to this formula to create a more equitable tuition rate that would benefit all students in Pennsylvania resulting in this [proposed legislation to create an equitable funding formula for PA Charter Schools](https://pahouse.com/InTheNews/NewsRelease/?id=138406). These data explore the specific financial impacts that cyber charter school tution rates have had on public school districts in Pennsylvania during the 2022-2023 school year.

## Exploratory Data Analysis

I collected raw data from the Pennsylvania Department of Education website. I wanted to identify what percentage of district budgets were allocated for cyber charter school tuition. I created a [helper table](https://github.com/kelsipage/Tuition_Impacts/blob/main/excel_EDA/tuition.csv) combining these data from two data sets and created a [table](https://github.com/kelsipage/Tuition_Impacts/blob/main/excel_EDA/public%20school%20expenses%20for%20cyber%20tuition.xlsx) to visualize the school districts that paid higher vs. lower percentages.

### Insights

The school district most impacted is Aliquippa School District in Western PA. 15% of their budget went to cyber charter school tuition in the 2022-2023 school year. All of the districts that paid at least 10% of their budget to cyber charter school tuition were midsized school districts with budgets between 20M and 50M. Most districts in PA allocated 8% or less of their budgets to cyber charter school tuition. The largest districts in PA, Philadelphia (5B budget) and Pittsburgh (800M budget) spent 5% of their budget on cyber charter school tuition.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <iframe src="https://1drv.ms/x/c/7426DB25AA193AE9/IQR8pSd3gGmmQbIQepgEiS7AAWr8onAOA6uabwSamwQnVd0" width="100%" height="600" frameborder="0" scrolling="no" class="rounded z-depth-1"></iframe>
    </div>
</div>
<div class="caption">
    This sheet shows the percentage of each school districts' 2022-2023 budget that is allocated for Cyber Charter School tuition. Raw data from <a href="https://www.pa.gov/content/dam/copapwp-pagov/en/education/documents/schools/grants-and-funding/school-finances/summary-of-afr-data/afr-data-detailed/finances%20afr%20majorobject%201415-2324.xlsx" target="_blank" rel="noopener noreferrer">PA Department of Education</a> and <a href="https://www.pa.gov/agencies/education/programs-and-services/schools/grants-and-funding/school-finances/financial-data/summary-of-annual-financial-report-data/afr-data-detailed" target="_blank" rel="noopener noreferrer">AFR Data</a>.
</div>

## SQL

I imported all of the raw data and EDA to SQL to dig deeper into the impacts of cyber charter school tuition on public school districts. I identified some remaining questions I had, particularly what are the demographics of the school districts that pay a greater percentage of their annual budget to cyber charter school tuition vs. less. To explore this, I found additional data on the PA Department of Education's website on the racial make up of the states' districts and which counties are designated rural and urban. In the future, I would like to find data identifying suburban school districts as well as the impacts of cyber tuition on the funding of special education programs, both in cyber charter schools and public school districts.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <iframe src="https://1drv.ms/u/c/7426DB25AA193AE9/IQT1awcGpOwsSJTtOq9Ooew6AQrx6P4ZsR0urea59fD33qc" width="100%" height="600" frameborder="0" scrolling="no" class="rounded z-depth-1"></iframe>
    </div>
</div>

### Insights

Looking at the impacts on rural vs. urban districts, these data showed minimal differences. The average percentage of tuition for rural schools was 0.034 and for urban districts, 0.027.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <iframe src="https://1drv.ms/x/c/7426DB25AA193AE9/IQTIdrPEStiJQ7FsA6XLy6kJAXVqkHs0g866QCV_qbu143Y" width="100%" height="300" frameborder="0" scrolling="no" class="rounded z-depth-1"></iframe>
    </div>
</div>

Looking at the racial makeup of the school districts that are paying a greater percentage of their annual budget to cyber charter schools vs. districts that paid less was more distinct. Most of the minority majority school districts paid 5% of their annual budget to cyber charter schools, as well as Aliquippa and Chester-Upland; the schools paying the highest and 4th highest percentages.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <iframe src="https://1drv.ms/x/c/7426DB25AA193AE9/IQROVIswlVizSptDsewlPU2FAf4HKJ9E8VtaA_GDBAJa9mA" width="100%" height="600" frameborder="0" scrolling="no" class="rounded z-depth-1"></iframe>
    </div>
</div>

Finally, I looked at the PA Counties, averaging the percentage of payment to cyber charter schools to identify if some counties were impacted more than others. These data show that there is a slightly greater imapct on rural counties compared to urban counties.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <iframe src="https://1drv.ms/x/c/7426DB25AA193AE9/IQSejhOpfEzIQIxo7Zhhx8LoARP51Zi_Zr11RQyjFxAGlrs" width="100%" height="600" frameborder="0" scrolling="no" class="rounded z-depth-1"></iframe>
    </div>
</div>

## Tableau

I took the most interesting datasets from SQL and imported them into Tableau to see the data visually. I created the following visualizations to show the impact of cyber charter school tuition on PA school districts by County, District and the racial majorities of each district. One issue I ran into is that Tableau does not provide axis breaks for outliers. I would like to recreate the District visualization in R to get better insights on the Districts that fall in the cluster. You can view all of my visualizations on my [Tableau Public page](https://public.tableau.com/app/profile/kelsi.page/vizzes)

### County Data

I started with the County data. Knowing where some of the different major regions are in Pennsylvania such as the Philly suburbs, the coal region, the greater Pittsburgh area, and the Appalachian Mountains. I wanted to see if these data showed any regions that were impacted more. The most idenfitiable impacted area was the significantly darker strip that goes from the northeast coal region all the way down through the Appalachian Mountain region. These regions combined have paid a larger percentage of their annual budgets for cyber charter school tuition than other regions in the state. You can also see that the suburbs around Philadelphia combined are paying a much lower percentage of their annual budget than the rest of the regions in the state.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <div class='tableauPlaceholder' id='viz1763523360965' style='position: relative'>
            <noscript><a href='#'><img alt='County Impacts ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Co&#47;CountyImpacts&#47;CountyImpacts&#47;1_rss.png' style='border: none' /></a></noscript>
            <object class='tableauViz'  style='display:none;'>
                <param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' />
                <param name='embed_code_version' value='3' />
                <param name='site_root' value='' />
                <param name='name' value='CountyImpacts&#47;CountyImpacts' />
                <param name='tabs' value='no' />
                <param name='toolbar' value='yes' />
                <param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Co&#47;CountyImpacts&#47;CountyImpacts&#47;1.png' />
                <param name='animate_transition' value='yes' />
                <param name='display_static_image' value='yes' />
                <param name='display_spinner' value='yes' />
                <param name='display_overlay' value='yes' />
                <param name='display_count' value='yes' />
                <param name='language' value='en-US' />
            </object>
        </div>
        <script type='text/javascript'>
            var divElement = document.getElementById('viz1763523360965');
            var vizElement = divElement.getElementsByTagName('object')[0];
            vizElement.style.width='100%';
            vizElement.style.height=(divElement.offsetWidth*0.75)+'px';
            var scriptElement = document.createElement('script');
            scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';
            vizElement.parentNode.insertBefore(scriptElement, vizElement);
        </script>
    </div>
</div>

I compared this visualization to the [Niche Schools map](https://www.niche.com/k12/search/best-public-high-schools/s/pennsylvania/?map=true) of the top schools in PA to see if there were any similarities. Most of the top rated schools in the state are in the suburbs where districts are paying the least amount in cyber charter school tuition.

### District Data

Next I dug into District data. I wanted to see specifically how varied percentages of payments to cyber charter schools were and what affects they have had on school districts. Most schools are paying 8% of their annual budget or less on cyber charter school tuition. The data points greater than 8% were most interesting to me.

**Aliquippa District** is the most impacted. Prior to these data, this school district had already struggled financially according to the [S&P Rating System](https://www.spglobal.com/ratings/en/regulatory/article/-/view/type/HTML/id/1080947). The same year that these data were released, a PA judge ruled that the state's system of funding public schools is unconstitutional. The Superintendent of Aliquippa was [interviewed](https://www.wtae.com/article/pa-school-funding-unconstitutional-aliquippa-superintendent/42805527) about this ruling.

**Steelton-Highspire School District** has also been greatly impacted by cyber charter school tuition. After years of operating in a defecit, they were placed in a [financial recovery program](https://www.pa.gov/agencies/education/newsroom/shapiro-administration-appoints-chief-recovery-officer-to-steelt) offered by the state to lead them into financial solvency.

**West Perry School District** has also faced challenges both with [funding and declining enrollment](https://www.wgal.com/article/west-perry-school-district-holds-town-hall-about-elementary-school-consolidation-proposal/64910612). Both of these issues have caused the school district to look into merging all of their elementary schools into one building on the High School's campus.

This year, the state of PA passed a [new budget](https://www.pa.gov/agencies/education/newsroom/shapiro-administration-secures-major-policy-wins-in-2025-2026-budget-expanding-educator-workforce-strengthening-literacy-initatives-reforming-cyber-charter-law#:~:text=It%20also%20reforms%20Pennsylvania's%20cyber,at%20least%20once%20per%20week.) including a redefinition of the cyber charter school funding formula. This new budget will save $175 million for school districts across the state moving forward.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <div class='tableauPlaceholder' id='viz1763607946571' style='position: relative'>
            <noscript><a href='#'><img alt='District Impacts ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Di&#47;DistrictImpacts&#47;DistrictImpacts&#47;1_rss.png' style='border: none' /></a></noscript>
            <object class='tableauViz'  style='display:none;'>
                <param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' />
                <param name='embed_code_version' value='3' />
                <param name='site_root' value='' />
                <param name='name' value='DistrictImpacts&#47;DistrictImpacts' />
                <param name='tabs' value='no' />
                <param name='toolbar' value='yes' />
                <param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Di&#47;DistrictImpacts&#47;DistrictImpacts&#47;1.png' />
                <param name='animate_transition' value='yes' />
                <param name='display_static_image' value='yes' />
                <param name='display_spinner' value='yes' />
                <param name='display_overlay' value='yes' />
                <param name='display_count' value='yes' />
                <param name='language' value='en-US' />
            </object>
        </div>
        <script type='text/javascript'>
            var divElement = document.getElementById('viz1763607946571');
            var vizElement = divElement.getElementsByTagName('object')[0];
            vizElement.style.width='100%';
            vizElement.style.height=(divElement.offsetWidth*0.75)+'px';
            var scriptElement = document.createElement('script');
            scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';
            vizElement.parentNode.insertBefore(scriptElement, vizElement);
        </script>
    </div>
</div>

### District Data by Racial Majority

This last set of data looks at which school districts are paying more in cyber charter school tuition as well as which of those districts are minority majority districts and majority white districts. Most of the majority minority school districts are paying at least 5% of their annual budget in cyber charter school tuition.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <div class='tableauPlaceholder' id='viz1763654194138' style='position: relative'>
            <noscript><a href='#'><img alt='Impact on District by Racial Majority ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Im&#47;ImpactonDistrictbyRacialMajority&#47;RacialMajority&#47;1_rss.png'
            style='border: none' /></a></noscript>
            <object class='tableauViz'  style='display:none;'>
                <param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' />
                <param name='embed_code_version' value='3' />
                <param name='site_root' value='' />
                <param name='name' value='ImpactonDistrictbyRacialMajority&#47;RacialMajority' />
                <param name='tabs' value='no' />
                <param name='toolbar' value='yes' />
                <param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Im&#47;ImpactonDistrictbyRacialMajority&#47;RacialMajority&#47;1.png' />
                <param name='animate_transition' value='yes' />
                <param name='display_static_image' value='yes' />
                <param name='display_spinner' value='yes' />
                <param name='display_overlay' value='yes' />
                <param name='display_count' value='yes' />
                <param name='language' value='en-US' />
            </object>
        </div>
        <script type='text/javascript'>
            var divElement = document.getElementById('viz1763654194138');
            var vizElement = divElement.getElementsByTagName('object')[0];
            vizElement.style.width='100%';
            vizElement.style.height=(divElement.offsetWidth*0.75)+'px';
            var scriptElement = document.createElement('script');
            scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';
            vizElement.parentNode.insertBefore(scriptElement, vizElement);
        </script>
    </div>
</div>

Final question: Is the increasing enrollment in cyber charter schools due to a desire to participate in a virtual education or due to lack of funding for some of our state's poorest and underfunded districts?

<!--
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img src="assets/img/cyber pic.jpg" alt="Cyber Funding" class="img-fluid rounded z-depth-1" loading="eager" />
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img src="assets/img/3.jpg" alt="example image" class="img-fluid rounded z-depth-1" loading="eager" />
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img src="assets/img/5.jpg" alt="example image" class="img-fluid rounded z-depth-1" loading="eager" />
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img src="assets/img/5.jpg" alt="example image" class="img-fluid rounded z-depth-1" loading="eager" />
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images, even citations (Einstein, 1950).
Say you wanted to write a bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, _bled_ for your project, and then... you reveal its glory in the next row of images.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img src="assets/img/6.jpg" alt="example image" class="img-fluid rounded z-depth-1" />
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        <img src="assets/img/11.jpg" alt="example image" class="img-fluid rounded z-depth-1" />
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    <img src="assets/img/6.jpg" alt="example image" class="img-fluid rounded z-depth-1" />
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    <img src="assets/img/11.jpg" alt="example image" class="img-fluid rounded z-depth-1" />
  </div>
</div>
```

-->
