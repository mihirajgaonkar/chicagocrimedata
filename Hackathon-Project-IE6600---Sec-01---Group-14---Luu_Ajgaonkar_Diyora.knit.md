---
title: "Hackathon Project"
author: "Group 14 - Justin Luu, Mihir Ajgaonkar, Vraj Diyora"
date: '2023-02-08'
output: 
  cleanrmd::html_document_clean:
    theme: new.css
    toc : true
    toc_float : true
---






```r
setwd("D:/COURSEWORK/COMP VIZ/Hakcathon")
getwd()
```

```
## [1] "D:/COURSEWORK/COMP VIZ/Hakcathon"
```

```r
chicago <- read.csv("chicago crime (2).csv", na.strings = "")
```
<img src="chicgologo.png" width="310" style="display: block; margin: auto;" />

# INTRODUCTION & PROBLEM STATEMENT

The City of Chicago's Police Department stores their city's reported crimes in their database called CLEAR (Citizens Law Enforcement Analysis and Reporting) system. With the exception of omitted personal information in order to protect the privacy of crime victims, the data set is organized by address locations where the reported crimes occurred. The data set also includes the descriptions and types of crimes committed, along with whether an arrest was made or not.

The data set presents data from 2001 to Present. Using the original data set, our team cleaned the data and primarily focused on the reported crime data within the past five years between 2018-2022. We chose to focus on this segment of time because we wanted to look at the most recent data and analyze the trend of crime (especially during the COVID-19 pandemic, for example). By breaking down the different types of crimes, we hope to understand the effects of the analyzed data on what the City of Chicago could hope to lawfully change to make the city a safer place. Of course, any city would want to keep the level of crime relatively low.

Throughout our analysis, our team has put together visualizations using the data set intending to address certain questions. We take a look at different types of crimes, the specific time and location occurrences of crimes, what types of weapon-related crimes occurred, whether arrests were made, etc. We hope the information provided will be of great value in addressing the City of Chicago's crime data.

# SECTION 1 - CRIME SETTINGS

## 1: Heat map of number of incidents reported based on district

```
## OGR data source with driver: ESRI Shapefile 
## Source: "D:\COURSEWORK\COMP VIZ\Hakcathon", layer: "geo_export_f92ce0c1-50fe-4875-b937-cbbc9fdf18c8"
## with 77 features
## It has 9 fields
```

```{=html}
<div class="leaflet html-widget html-fill-item-overflow-hidden html-fill-item" id="htmlwidget-6121f49a8ddf0f94a708" style="width:960px;height:672px;"></div>
```
Output shows the number of incidents reported in Chicago. The map displays the distribution of incidents in Chicago, aggregated into different areas of the city.it also includes a legend and labels showing the number of incidents. The incidents are then binned into ranges and color-coded using the 'colorBin' function. then we set the coordination reference system for the longitude and latitude which is important in mapping. The map also includes a legend and labels showing the number of incidents.


## 2: What types of weapons were related to assault crimes?

```{=html}
<div class="plotly html-widget html-fill-item-overflow-hidden html-fill-item" id="htmlwidget-fd04aa7c9bf0eda5e335" style="width:960px;height:672px;"></div>
<script type="application/json" data-for="htmlwidget-fd04aa7c9bf0eda5e335">{"x":{"visdat":{"1a60772178ed":["function () ","plotlyVisDat"]},"cur_data":"1a60772178ed","attrs":{"1a60772178ed":{"x":{},"y":{},"marker":{"color":"#e5383b"},"alpha_stroke":1,"sizes":[10,100],"spans":[1,20],"type":"bar"}},"layout":{"margin":{"b":40,"l":60,"t":25,"r":10},"title":"NUMBER OF ASSAULTS BASED ON IUCR CODE","xaxis":{"domain":[0,1],"automargin":true,"title":"Type of Weapon","type":"category","categoryorder":"array","categoryarray":["FIREARM","HANDGUN","KNIFE","WEAPON"]},"yaxis":{"domain":[0,1],"automargin":true,"title":"Count"},"plot_bgcolor":"#161a1d","hovermode":"closest","showlegend":false},"source":"A","config":{"modeBarButtonsToAdd":["hoverclosest","hovercompare"],"showSendToCloud":false},"data":[{"x":["HANDGUN","FIREARM","KNIFE","WEAPON","HANDGUN","FIREARM","KNIFE","WEAPON"],"y":[54,2,40,72,45,5,63,92],"marker":{"color":"#e5383b","line":{"color":"rgba(31,119,180,1)"}},"type":"bar","error_y":{"color":"rgba(31,119,180,1)"},"error_x":{"color":"rgba(31,119,180,1)"},"xaxis":"x","yaxis":"y","frame":null}],"highlight":{"on":"plotly_click","persistent":false,"dynamic":false,"selectize":false,"opacityDim":0.2,"selected":{"opacity":1},"debounce":0},"shinyEvents":["plotly_hover","plotly_click","plotly_selected","plotly_relayout","plotly_brushed","plotly_brushing","plotly_clickannotation","plotly_doubleclick","plotly_deselect","plotly_afterplot","plotly_sunburstclick"],"base_url":"https://plot.ly"},"evals":[],"jsHooks":[]}</script>
```
For the number of assaults based on IUCR codes, we summarised the IUCR and split the list count number with the help of a filter, on the bases of that table we add the new column and there data with the help of 'mutate' variable which is actually a replica of description from dataset Chicago crime.after we moved to the final plotting for that I have used the Plot_ly codes for the bar plot and for the color we used the MARKER variable . From the output, we can see that number of weapons used in Chicago as per the IUCR .



## 3: What was the frequency of crimes in the top 5 types of locations?
<img src="Hackathon-Project-IE6600---Sec-01---Group-14---Luu_Ajgaonkar_Diyora_files/figure-html5/Task 3-1.png" width="576" />
This is the graphical representation of top 5 crime location in the chicago , and it also cleared that street is the place with highest number of crimes occured . lets see about that graph. firstly,we used the filter for the top location from the location description column from chicago dataset . then we used the ggplot to show the arial view.




## 4: What time of day did the most crimes occur?

```{=html}
<div class="plotly html-widget html-fill-item-overflow-hidden html-fill-item" id="htmlwidget-154f369c02bd65c84c8d" style="width:960px;height:672px;"></div>
<script type="application/json" data-for="htmlwidget-154f369c02bd65c84c8d">{"x":{"visdat":{"1a60434a119d":["function () ","plotlyVisDat"]},"cur_data":"1a60434a119d","attrs":{"1a60434a119d":{"x":{},"y":{},"marker":{"color":"#e5383b"},"alpha_stroke":1,"sizes":[10,100],"spans":[1,20],"type":"bar"}},"layout":{"margin":{"b":40,"l":60,"t":25,"r":10},"title":"CRIMES COMMITTED MOST IN A DAY","xaxis":{"domain":[0,1],"automargin":true,"title":"Time in 24 Hour Format"},"yaxis":{"domain":[0,1],"automargin":true,"title":"Count of Crimes Committed"},"plot_bgcolor":"#161a1d","hovermode":"closest","showlegend":false},"source":"A","config":{"modeBarButtonsToAdd":["hoverclosest","hovercompare"],"showSendToCloud":false},"data":[{"x":[0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23],"y":[670,583,540,409,302,220,192,221,336,349,423,502,518,469,506,605,577,613,675,793,761,770,824,758],"marker":{"color":"#e5383b","line":{"color":"rgba(31,119,180,1)"}},"type":"bar","error_y":{"color":"rgba(31,119,180,1)"},"error_x":{"color":"rgba(31,119,180,1)"},"xaxis":"x","yaxis":"y","frame":null}],"highlight":{"on":"plotly_click","persistent":false,"dynamic":false,"selectize":false,"opacityDim":0.2,"selected":{"opacity":1},"debounce":0},"shinyEvents":["plotly_hover","plotly_click","plotly_selected","plotly_relayout","plotly_brushed","plotly_brushing","plotly_clickannotation","plotly_doubleclick","plotly_deselect","plotly_afterplot","plotly_sunburstclick"],"base_url":"https://plot.ly"},"evals":[],"jsHooks":[]}</script>
```

This graphical representation provides us with crucial information regarding the peak hours of criminal activity, allowing us to allocate our most capable officers to duty during those times and maintain heightened vigilance. By having this understanding of the pattern of criminal incidents, we can implement effective preventive measures and ensure the safety of the community. This chart is an essential tool in crime management and helps law enforcement agencies allocate their resources more efficiently.

# SECTION 2 - CRIME TYPES

## 1: How many weapon-related crimes occurred in the last 5 years (2018-2022)?
<img src="Hackathon-Project-IE6600---Sec-01---Group-14---Luu_Ajgaonkar_Diyora_files/figure-html5/Task 5-1.png" width="960" />

Looking at the donut chart, we can see the data sorted into three types of weapon-related crimes: Gun, Knife, and Other. The category "Other" refers to any other dangerous weapon-related crimes (e.g., bombs, explosives, crowbars, sticks, and any other handheld/tangible items). Between 2018-2022, there were a total of 31,892 weapon-related crimes reported, which consisted of 19,031 gun-related crimes; 5,465 knife-related crimes; and 7,396 other dangerous weapon-related crimes. 

## 2: How efficiently is the City of Chicago's Police department handeling crime?

```
## `summarise()` has grouped output by 'Weapon'. You can override using the
## `.groups` argument.
## No trace type specified: Based on info supplied, a 'scatter' trace seems
## appropriate. Read more about this trace type ->
## https://plotly.com/r/reference/#scatter
## No trace type specified: Based on info supplied, a 'scatter' trace seems
## appropriate. Read more about this trace type ->
## https://plotly.com/r/reference/#scatter
## No trace type specified: Based on info supplied, a 'scatter' trace seems
## appropriate. Read more about this trace type ->
## https://plotly.com/r/reference/#scatter
```

```{=html}
<div class="plotly html-widget html-fill-item-overflow-hidden html-fill-item" id="htmlwidget-cc1450e6af441c0bcb42" style="width:960px;height:672px;"></div>
<script type="application/json" data-for="htmlwidget-cc1450e6af441c0bcb42">{"x":{"visdat":{"1a60699d74b7":["function () ","plotlyVisDat"]},"cur_data":"1a60699d74b7","attrs":{"1a60699d74b7":{"x":{},"alpha_stroke":1,"sizes":[10,100],"spans":[1,20],"y":{},"name":"GUN","mode":"lines","line":{"width":3,"color":"#fff0f3"},"inherit":true},"1a60699d74b7.1":{"x":{},"alpha_stroke":1,"sizes":[10,100],"spans":[1,20],"y":{},"name":"KNIFE","mode":"lines","line":{"width":3,"color":"#e5383b"},"inherit":true},"1a60699d74b7.2":{"x":{},"alpha_stroke":1,"sizes":[10,100],"spans":[1,20],"y":{},"name":"OTHER","mode":"lines","line":{"width":3,"color":"#fbc4ab"},"inherit":true}},"layout":{"margin":{"b":40,"l":60,"t":25,"r":10},"hovermode":"x unified","title":"NUMBER OF INCIDENTS BY YEAR","plot_bgcolor":"#161a1d","xaxis":{"domain":[0,1],"automargin":true,"title":"Year"},"yaxis":{"domain":[0,1],"automargin":true,"title":"Total Incidents"},"showlegend":true},"source":"A","config":{"modeBarButtonsToAdd":["hoverclosest","hovercompare"],"showSendToCloud":false},"data":[{"x":[2018,2019,2020,2021],"y":[13403,4840,631,138],"name":"GUN","mode":"lines","line":{"color":"#fff0f3","width":3},"type":"scatter","marker":{"color":"rgba(31,119,180,1)","line":{"color":"rgba(31,119,180,1)"}},"error_y":{"color":"rgba(31,119,180,1)"},"error_x":{"color":"rgba(31,119,180,1)"},"xaxis":"x","yaxis":"y","frame":null},{"x":[2018,2019,2020,2021],"y":[3846,1459,141,19],"name":"KNIFE","mode":"lines","line":{"color":"#e5383b","width":3},"type":"scatter","marker":{"color":"rgba(255,127,14,1)","line":{"color":"rgba(255,127,14,1)"}},"error_y":{"color":"rgba(255,127,14,1)"},"error_x":{"color":"rgba(255,127,14,1)"},"xaxis":"x","yaxis":"y","frame":null},{"x":[2018,2019,2020,2021],"y":[5337,1897,144,18],"name":"OTHER","mode":"lines","line":{"color":"#fbc4ab","width":3},"type":"scatter","marker":{"color":"rgba(44,160,44,1)","line":{"color":"rgba(44,160,44,1)"}},"error_y":{"color":"rgba(44,160,44,1)"},"error_x":{"color":"rgba(44,160,44,1)"},"xaxis":"x","yaxis":"y","frame":null}],"highlight":{"on":"plotly_click","persistent":false,"dynamic":false,"selectize":false,"opacityDim":0.2,"selected":{"opacity":1},"debounce":0},"shinyEvents":["plotly_hover","plotly_click","plotly_selected","plotly_relayout","plotly_brushed","plotly_brushing","plotly_clickannotation","plotly_doubleclick","plotly_deselect","plotly_afterplot","plotly_sunburstclick"],"base_url":"https://plot.ly"},"evals":[],"jsHooks":[]}</script>
```

This chart presents a visual representation of the trend in crime over the years. It is evident that there has been a substantial decrease in crime from 2018 to 2020, and this decrease can be attributed to the restructuring of the Chicago Crime Department, as reported in the accompanying news article. The further drop from 2020 to 2021 is likely due to the impact of the COVID-19 pandemic on crime rates. This trend suggests that these efforts to address crime have been successful, and that the pandemic has had a profound effect on crime rates across the city.

## 3: How did the number of arrests based on crime type look like during the height of the COVID-19 pandemic (2020)?
<img src="Hackathon-Project-IE6600---Sec-01---Group-14---Luu_Ajgaonkar_Diyora_files/figure-html5/Task 7-1.png" width="960" />

The stacked bar chart compares the level of arrests made after a reported crime occurred during the specific year of 2020. Each set of bars is categorized under the type of crime committed. The reason we chose to only look at 2020 was because it was during the peak of the COVID-19 pandemic, a time when there was a stay-at-home/lock down order. Looking at the height of each type of crime, we can see that there were high level of crimes involving assault, battery, robbery, and weapons violations. The minuscule heights of the crimes involving concealed carry license violations, criminal sexual assault, other offenses, and public peace violations occurred rarely, therefore we can barely see the bar graphs. Regarding the legend for colors, we see that red means that an arrest was made versus tan meaning there was no arrest made (perhaps due to just a warning or suspect escape, for example). Focusing on just the higher crime type occurrences, we can see that there were a higher rate of no arrest versus arrests as a result of a reported crime during 2020. The result that jumps out most is the weapons violations occurrences, as it is the highest bar; however, it is reassuring that at least more than half of the reported instances resulted in an arrest. On the other hand, the robbery crime type was mostly tan colored, which means there were almost no arrests made (the data for 2020 indicated that there was only a single arrest out of the total reported robberies).

# CONCLUSION

We have learned a lot from this data set of the City of Chicago's reported crimes. Our goal aims to hopefully provide a helpful analysis for the City of Chicago's Police Department in understanding what measures they can take to make the city a safer place. By using our findings, perhaps they can develop a strategy to manage the crime rate by combating against specific types of crimes. We split up our analysis into two parts: Crime Settings and Crime Types.

In the first section, we chose to analyze Crime Settings. We chose to highlight a number of factors from the data set used to describe the occurring crimes reported. We started with the number of crimes per area. By looking at this number, we can pinpoint which areas of Chicago had higher crime rates than others. Next, we looked at the crime descriptions and their locations to determine what types of crimes were more frequent than others and where. We grouped the type of crimes by IUCR code, and found that assault occurred most. We then chose to look into which types of weapons were involved in these assaults. We picked the top 5 location description types, so perhaps the police can patrol along those areas more prominently. Lastly in this section, we looked at the most frequent occurrences of crime throughout a typical day. Again, the police can perhaps send patrols out more during these times of higher crime activity.

In the second section, we chose to analyze Crime Types. We chose to focus on different types of crimes based on types of weapons involved. We started with the types of weapon-related crimes, with the totaling up of each kind reported (i.e., Gun, Knife, Other) within the last 5 years. We then used this info and looked at the trend of crimes involving these weapons. To our surprise, there seemed to be a drastic decrease in terms of weapon-based crimes. We did some additional research and according to a source we came across, Chicago had experienced one of the deadliest years of gun violence (back in 2016) in nearly two decades. As a result, efforts to drive down murder rates and other weapons-related crimes were made a top priority, which explains the decrease in our graphs. The last factor we looked at was the arrest statuses of reported crimes based on primary types during the peak of COVID-19 pandemic (2020). We specifically wanted to see this year in order to determine if it was an outlier since people were ordered to stay at home. We found that out of the crimes reported, most committed crimes did not result in arrests (possibly due to warning or suspects getting away). We may perhaps conclude that with most people in lockdown, more crimes were likely to occur with less people, such as police, out stopping them.

Overall, it seems that the City of Chicago's Police Department has more than enough information from our analysis to strategize and tackle the issue of high crime rates in their city. By focusing on even the smaller crimes, the police can eventually narrow down the crime rate and reduce violence even. It seems that most reported weapon-related crimes involved guns, so maybe a tighter gun control policy could help make the city a safer place. The access to these types of weapons is a whole different story entirely, but we hope that our data can provide the necessary means to drive down crime rate.

# REFERENCES

https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-Present/ijzp-q8t2/data
https://amp.cnn.com/cnn/2019/12/31/us/chicago-murders-drop-2019/index.html
https://www.cnn.com/2017/01/02/us/chicago-murder-rate-2016-visual-guide/index.html
https://youtu.be/oJhvoXjeyso?list=PLaZuFfQk5gXMaQVhYkGwM0tlg9kHDZ7Pm

