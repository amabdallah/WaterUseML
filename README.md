# WaterUseML
Draft description of the next WaterUseML

# Why WaterUseML?

http://www.westernstateswater.org/wp-content/uploads/2018/08/Dalton-WAUSP_WSWC_180802.pdf

http://wade.westernstateswater.org/


**WaterML2**  
http://www.waterml2.org/  
https://data.cuahsi.org/


**(GroundWaterML2) GWML2**  
http://www.opengeospatial.org/standards/gwml2
https://cida.usgs.gov/ngwmn/index.jsp


# Use Cases
Successful desgins and data services are built to serve stakeholder driven use cases. 

The [Internet of Water][1] report highlights the following two relevant fundamental questions that we are currently unable to answer  in a timely fashion about our water systems.

1.	How much water is there? and
2.	How is water used (i.e., withdrawn, consumed or returned for different purposes)?

The Internet of Water report lists this use case to show the value of answering the questions
>"A water budget requires both of these types of data **water use in WaDE and natural systems in CUAHSI and EPA** to be integrated within a watershed.  A proof-in-concept that develops a shared platform of the relevant data needed to create a water budget at the location of power plants within one basin of interest could provide a powerful example of integrating open water data between hubs for sustainable water management."

WaDE has the ability to answer the data questions across its member states which already share their data. The next WaDE schema could support answering the questions as it   
i. enables time series syntax,   
ii. uses controlled vocabulary to map native and general terms (yet to be discussed on its possibility and use), and   
iii. uses longitude and latitide coordinates to reference the sites or centroid of polygons and enable their discovery through geospatial searches.   

The following are two motivating use cases that show the value of the interoperable WaDE schema which overcomes both the heterogeneous semantics (different terms to describe water rights and use across states) and syntax (different data structures across states). 

The purpose here is to enable the underlying capability to allow others to answer them at different spatial scales. The two questions serve as generics examples to other questions that could span geospatial areas across states boundary lines, many years, and many different variables of interest. 


### Example question 1: Aggregated   
What is the _annual_ _fresh_ water ammout used for _thermoelectric_ purposes in the Bear River watershed that spans Utah, Wyoming, and Idaho for all the years we have data for?   

In the answer, list the unit, amount, beneficial use category, source of water (ground or surface water).  

* Annual or monthly
* fresh or saline
* thermoelectric, griculture, or municipal
* withdrawn, returned, consumed, transfered out of, transfered into  

 ### Example question 2: Aggregated   
What is the annaul amount of water that is imported or exported into or out of a basin (selected boubdary)?   


### Example question 3: site_specific   
What is the water rights annual volume/flow for for agriculture and municipal purposes in the Upper Colorado that spans Wyoming, Colorado, Utah, New Mexico, and Arizona all the years we have data for? list all water rights and their priority


Answering the questions within one state is easier using WaDE because of its standard and well described schema but the true power of WaDE or WaterUseML is to answer such questions across the boundaries of many states.  


## Use case steps to answer the questions   
A user could query the data for this answer using future version of the WaDE or HydroClient GIS Portals
1.	a user selects the Bear River Watershed or Upper Colorado boundary layer to search for aggregated or site-specific water use data. The layer could exist within the portal as part of a larger shapefile for the US Major Watersheds, or the user could import the layer to the Portal as a shapefile or a JSON file. The user could also draw a box within the map like HydroDekstop, or they could use their window view boundary as in HydroClient. 

2.	a user provides the min and max time range in month/years or leave them blank to return all existing data values  

3.	from a drop down menu, a user selects one or many controlled attributes to search for their data values within the selected geospatial location and time range. Example attributes which we need to come up are: withdrawn water, consumptive water use, return flow, allocated water. The trick is how also associate the purposes within these controlled terms  

4.	the web-service will first call the WaDE catalog to look up all the site-specific locations or aggregated polygons within the provided boundary area which have attributes as the selected ones. The user will look up a summary of the locations of the returned sites and their attributes and decide to select which ones to get data values for.    

5.	 The web-service will call each WaDE-node that has the selected sites and attributes and return their time series data in a WaterML complaint format.   

6.	the user can sum up the time series aggregated consumptive use for agriculture and municipal uses in all the Bear River/upper Colorado areas for the three states for each year.     



[1]:https://www.aspeninstitute.org/publications/internet-of-water/
