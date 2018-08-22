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
Successful designs and data services are built to serve stakeholder driven use cases. 

The [Internet of Water][1] report highlights the following two relevant fundamental questions that we are currently unable to answer  in a timely fashion about our water systems.

1.	How much water is there? and
2.	How is water used (i.e., withdrawn, consumed or returned for different purposes)?

The Internet of Water report lists this use case to show the value of answering the questions
>"A water budget requires both types of data **water use in WaDE and natural systems in CUAHSI and EPA** to be integrated within a watershed.  A proof-in-concept that develops a shared platform of the relevant data needed to create a water budget at the location of power plants within one basin of interest could provide a powerful example of integrating open water data between hubs for sustainable water management."

WaDE has the ability to answer the data questions across its member states which already share their data. The next WaDE schema could support answering the questions as it   
i. enables time series syntax,   

ii. uses controlled vocabulary to map native and general terms (yet to be discussed on its possibility and use), and   

iii. uses longitude and latitude coordinates to reference the sites or centroid of polygons and enable their discovery through geospatial searches.   

The following are two motivating use cases that show the value of the interoperable WaDE schema which overcomes both the heterogeneous semantics (different terms to describe water rights and use across states) and syntax (different data structures across states). 

The purpose here is to enable the underlying capability to allow others to answer them at different spatial scales. The two questions serve as generics examples to other questions that could span geospatial areas across states boundary lines, many years, and many different variables of interest. 


### Example question 1: Aggregated   
What is the _annual_ _fresh_ water amount used for _thermoelectric_ purposes in the Bear River watershed that spans Utah, Wyoming, and Idaho for all the years we have data for?   

In the answer, list the unit, amount, beneficial use category, source of water (ground or surface water).  

* Annual or monthly
* fresh or saline
* thermoelectric, agriculture, or municipal
* withdrawn, returned, consumed, transferred out of, transferred into  

 ### Example question 2: Aggregated   
What is the annual amount of water that is imported or exported into or out of a basin (selected boundary)?   


### Example question 3: site_specific   
What is the water rights annual volume/flow for agriculture and municipal purposes in the Upper Colorado that spans Wyoming, Colorado, Utah, New Mexico, and Arizona all the years we have data for? list all water rights and their priority


Answering the questions within one state is easier using WaDE because of its standard and well described schema but the true power of WaDE or WaterUseML is to answer such questions across the boundaries of many states.  

## Prominent example water data services  
* [HydoClient](https://data.cuahsi.org/)
https://www.cuahsi.org/uploads/pages/img/ODM1.1DesignSpecifications_.pdf

* [RWISE](https://water.usbr.gov/RWISmap.php)
* [Ground water](https://cida.usgs.gov/ngwmn/index.jsp)  
https://cida.usgs.gov/ngwmn/doc/NGWMN_Data_Portal_Help_Documentation.pdf

* [WaDE](http://wade.westernstateswater.org/wade-by-datatype/)



## Steps to answer the questions   
The user provides selections in the following steps to answer the above use case questions    

1.	**Spatial boundary:** a user selects the Bear River Watershed or Upper Colorado boundary GIS layer to search for aggregated or site-specific water use data. The layer could exist within the portal as part of a larger shapefile for the US Major Watersheds, counties, states, or the user could import the layer to the Portal as a shapefile or a JSON file. The user could also draw a box within the map like HydroDekstop, or they could use the view boundary of the window as in HydroClient.

2.	**Time frame** a user provides the min and max time range in month/years or leave them blank to return all data for all existing years. The [Reclamation Water Information System (RWIS)][2] provides this specific or general time span search capability. 

3.	**Variable** from a drop-down menu, a user selects one or many controlled variables to search for their data values within the selected geospatial location and time range. 

The variables can be filtered or grouped like below. The user can query one or many at the same time. 

**Aggegated**
Water Use, Agriculture
Water Use, Public Supply	
Water Use, Thermoelectric power	
Water supply, wet 
Water supply, dry
Water supply, dry
etc.

**Site-Specific**
Water Use, Agriculture
Water Use, Public Supply	
Water Use, Thermoelectric power
Allocated water, Irrigation 
etc.


## Conceptual web-service steps to answer the data calls   
Data query is supported at two interactive stages. First, search variables and their "sites" or "Areas". Second download or potentially vislalize the data for one or many sites and variables. 

**WaDE Catalog** 
The first step needs to be supported by a Catalog similair to the existing WaDE portal but perhaps simpler to maintain. The Catalog is a centeral front end to all the seperate indivisual WaDE database implementation (i.e., node) for each state.

The catalog harvests two items, i) all the sites or areas and their "type", and ii) variables that have data for the sites. 
There are two benifets from excluding time in the form of months, years, or reporting years from the catalog  
* reduces the burden to maintain and update the catalog. the catalog will be updated only if new sites (or areas), or variables are added.  
* reduces the effort that users have to make to scroll through indivoiusal years. Interest in a specific time frame is handled as part of the next step to query data. the default is probably to return all the years   

1.  The web-service will first call the WaDE catalog to look up all the site-specific locations or aggregated polygons within the provided boundary area which have attributes as the selected ones. The user will look up a summary of the locations of the returned sites and their attributes and decide to select which ones to get data values for.     

2.  The web-service will call each WaDE-node that has the selected sites and attributes and return their time series data in a WaterUseML compliant format. Water rights or regaulatory data is an exception.    

3.  The user can post-process or visualize (e.g., sum up the time series aggregated consumptive use) agriculture and municipal uses in all the Bear River/upper Colorado areas for the three states for each year.      
 


[1]:https://www.aspeninstitute.org/publications/internet-of-water/
[2]:https://water.usbr.gov/RWISmap.php  

