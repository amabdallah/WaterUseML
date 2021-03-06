# WaterUseML  
Draft description of the next WaterUseML  

# Why WaterUseML?    

Mindi Dalton from the USGS explains the importance and need for national water use data at the WSWC Summer Meeting 2018    
http://www.westernstateswater.org/wp-content/uploads/2018/08/Dalton-WAUSP_WSWC_180802.pdf    

See WaDE goals   
http://wade.westernstateswater.org/   

Water use and availability data have common metadata with WaterML and GWML2 time series data with also unique metadata. The goal here is to build on the commonality of WaterML and GWML2 and add unique needed water use metadata into a new WaterUseML schema.    


**WaterML2**    
- Description: http://www.waterml2.org/ and https://www.cuahsi.org/uploads/pages/img/ODM1.1DesignSpecifications_.pdf 
* Application 1 for hydrology and weather observations at https://data.cuahsi.org/   
* Application 2 for reservoirs at https://water.usbr.gov/RWISmap.php  

**(GroundWaterML2) GWML2**    
- Description: http://www.opengeospatial.org/standards/gwml2  
* Application for groundwater levels and water quality: https://cida.usgs.gov/ngwmn/index.jsp  


# WaterUseML Use Cases   
A successful data services design is built to serve stakeholder driven use cases.  

The [Internet of Water][1] report highlights the following two relevant fundamental questions that we are currently unable to answer  in a timely fashion about our water systems.

1.	How much water is there? and
2.	How is water used (i.e., withdrawn, consumed or returned for different purposes)?

The Internet of Water report lists this use case to show the value of answering the questions
>"A water budget requires both types of data **water use in WaDE and natural systems in CUAHSI and EPA** to be integrated within a watershed.  A proof-in-concept that develops a shared platform of the relevant data needed to create a water budget at the location of power plants within one basin of interest could provide a powerful example of integrating open water data between hubs for sustainable water management."

The following questions motivate use cases that show the value of the interoperable WaDE schema which overcomes both the heterogeneous semantics (different terms to describe water rights and use across states) and syntax (different data structures across states). 

## Example question 1: Aggregated (for each use type)  
What is the water amount used for _thermoelectric_  [Variable]  in the Bear River watershed [Space] that spans Utah, Wyoming, and Idaho for all the years we have data for [time]?   

In the answer, list the unit, amount, beneficial use category, source of water (ground or surface water).  

### Potentially optional filters that can selected   
* specific years
* Annual or monthly
* fresh or saline
* surface or groundwater (i.e,. source type)   

### Variables   
Water Use, Agriculture   
Water Use, Public Supply	  
Water Use, Thermoelectric power	  
Water supply, wet   
Water supply, dry  
Water supply, dry  
Withdrawal, Agriculture
Withdrawal, Public Supply	  
Withdrawal, Thermoelectric power	 
Transfer, Agriculture
Transfer, Public Supply	  
Transfer, Thermoelectric power	

### Use types (each type has its seperatre API Get call)   

* withdrawn  
* returned    
* consumed   
* transferred out of, transferred into      

One reason for seperating the calls is that each use type has its own seperate tables and thus has its unique metadata.   


 ### Example question 2: Aggregated   
What is the annual amount of water that is imported or exported into or out of a basin (selected boundary)?   
 (e.g., the Upper Colorado that spans Wyoming, Colorado, Utah, New Mexico, and Arizona?


### Example question 3: Site_specific   
What are the water rights for _agriculture_ in an area? list all water rights and their priority

Answering the questions within one state is easier using WaDE because of its standard and well described schema but the true power of WaDE or WaterUseML is to answer such questions across the boundaries of many states.  

## Prominent example water data services  
* [HydoClient](https://data.cuahsi.org/)   
https://www.cuahsi.org/uploads/pages/img/ODM1.1DesignSpecifications_.pdf

* [RWISE](https://water.usbr.gov/RWISmap.php)  
* [Ground water](https://cida.usgs.gov/ngwmn/index.jsp)    
https://cida.usgs.gov/ngwmn/doc/NGWMN_Data_Portal_Help_Documentation.pdf   

* [WaDE](http://wade.westernstateswater.org/wade-by-datatype/)   

WaDE has the ability to answer the data questions across its member states which already share their data. The next WaDE schema could support answering the questions as it   
i. enables time series syntax,   

ii. uses controlled vocabulary to map native and general terms (yet to be discussed on its possibility and use), and   

iii. uses longitude and latitude coordinates to reference the sites or centroid of polygons and enable their discovery through geospatial searches.   


The purpose here is to enable the underlying capability to allow others to answer them at different spatial scales. The two questions serve as generics examples to other questions that could span geospatial areas across states boundary lines, many years, and many different variables of interest. 

## Steps to answer the questions   
The user provides selections in the following steps to answer the above use case questions    

1.	**Spatial boundary:** a user selects the Bear River Watershed or Upper Colorado boundary GIS layer to search for aggregated or site-specific water use data. The layer could exist within the portal as part of a larger shapefile for the US Major Watersheds, counties, states, or the user could import the layer to the Portal as a shapefile or a JSON file. The user could also draw a box within the map like HydroDekstop, or they could use the view boundary of the window as in HydroClient.  
Selecting a layer (larger boundary than the site or the area) will send the coordinates to the catalog to use them to look up the Area or site code. [this is how HydroClient, GW network, and RWISS portals seems to behave]

2.	**Time frame** a user provides the min and max time range in month/years or leave them blank to return all data for all existing years. The [Reclamation Water Information System (RWIS)][2] provides this specific or general time span search capability. 

3.	**Variable** from a drop-down menu, a user selects one or many controlled variables to search for their data values within the selected geospatial location and time range.   

The variables can be filtered or grouped like below. The user can query one or many varaibles at the same time. 

In my opinion, the two fundamental and important parts that define the variable is the estimate type and its beneficial use or sub-estimate. See here for hydrology  https://github.com/amabdallah/WaterUseML/blob/master/fundamental_characteristics.PNG

Other info like the water source type (ground water or surface water), fresh or saline, etc are more details that perhaps can be filtered by option to the requested data. Perhaps, it can be implemented in a where-clause in the query.  

The use cases should help us decide on the granularity of search capabilities. Right now in WaDE we have a search for "e.g., withdrawal" which can return all withdrawal water for all sorts of beneficial use.    
A more granular search that would useful too is "withdrawal" for "irrigation". It still would potentially come with a mix of metadata like saline/fresh, surface/ground water, crop types. Two options to deal with such data 

a. post process the resulting table into many groups (e.g., withdrawal water for irrigation -surface water)   
b. provide upfront capability to send an optional filter request to add on the data values query. 


**Aggregated**    
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


Check out this idea for a single WaDE portal for both select by data type and by location and for both aggregate and site-specific data. I'm not sure how it could be implemented but I think its possible based on what I've seen in other applications.         
https://github.com/amabdallah/WaterUseML/blob/master/Merged_portal.PNG

First the user can toggle between site-specific and aggregate data. Within one of them, the user can select a data type which is Select by data type. If they select "All" data types, then that would become "search by location". With "All" selected, the user can see all data types for each location (e.g., Cache County)    


**WaDE Catalog** 
The first step needs to be supported by a Catalog similar to the existing WaDE portal but perhaps simpler to maintain. The Catalog is a central front end to all the separate individual WaDE database implementation (i.e., node) for each state.

The catalog harvests two items, i) all the sites or areas and their "type", and ii) variables that have data for the sites. 
There are two benefits from excluding time in the form of months, years, or reporting years from the catalog  
* reduces the burden to maintain and update the catalog. the catalog will be updated only if new sites (or areas), or variables are added.  
* reduces the effort that users have to make to scroll through individual years. Interest in a specific time frame is handled as part of the next step to query data. the default is probably to return all the years   


## Conceptual web-service steps to answer the data calls   
Data query is supported at two interactive stages. First, search variables and their "sites" or "Areas". Second download or potentially visualize the data for one or many sites and variables. 

revise these   
1.  The web-service will first call the WaDE catalog to look up all the site-specific locations or aggregated polygons within the provided boundary area which have attributes as the selected ones. The user will look up a summary of the locations of the returned sites and their attributes and decide to select which ones to get data values for.     

2.  The web-service will call each WaDE-node that has the selected sites and attributes and return their time series data in a WaterUseML compliant format. Water rights or regulatory data is an exception.    

3.  The user can post-process or visualize (e.g., sum up the time series aggregated consumptive use) agriculture and municipal uses in all the Bear River/upper Colorado areas for the three states for each year.      
 


[1]:https://www.aspeninstitute.org/publications/internet-of-water/
[2]:https://water.usbr.gov/RWISmap.php  

