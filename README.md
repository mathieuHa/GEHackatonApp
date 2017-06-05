# minds-machines-europe

## Challenge details
The hackathon challenge and all logistics can be found here: https://mindsmachinesberlin.devpost.com/ 
Completed projects are due at 2pm Tuesday June 13th and must be submitted here: https://mindsmachinesberlin.devpost.com/submissions
This requires you create a devpost account in order to be eligble for a prize. 
Electrification

Europe is looking to lead the way to decarbonizing its economy and setting a global example. From the energy sector to advanced manufacturing and sustainable energy use, Europe is pushing the boundaries to drive sustainability and deliver better value. Develop new solutions on Predix to take decarbonization to the next level.

### 2 categories:

### 1.	Electrification 
Presented by EURELECTRIC, EHPA
Europe’s energy sector is poised for disruption and decarbonization.  Electric Vehicles, distributed renewable energy, and electric building heating can drive decarbonization and economic value.  The grid needs to keep up!  Build a solution on Predix to help drive electrification and evaluate the impact on the electric grid & decarbonization. 

Examples:  
- Grid infrastructure mapping
- Rooftop PV siting
- Load forecasting & temperature correction on distribution circuits
- Electric heating & conversion to heat pumps 
- Renewable energy integration 
 
### Grid Infrastructure Mapping
To adapt to and enable the decarbonization of Europe’s electric sector, grid infrastructure will require investment from basic modification and expansion to modernization and digitization.  The electric grid has been built up over more than a century into today’s network of infrastructure.  Utilities themselves don’t have full visibility into the details of the vast infrastructure that has been deployed over the years.  Help utilities like ESB leverage modern data sources and automation to evaluate their physical infrastructure to enable greater penetration of electric vehicles, renewables, and electrification.

##### Data and services provided:
- ESB data set describing infrastructure and locations
- GE geospatial and mapping services
- Images of infrastructure
- The world wide web (hint:  think streetview)

##### Approach:
- Load ESB data into GE geospatial platform
- “Drive” through region using streeview
- Identify ESB infrastructure in streetview
- Confirm location and inclusion in ESB data set
- Display an alarm where there is a mismatch between streetview images and ESB records
- Create the capability to add the identified infrastructure to the ESB data set by the identification of ESB assets on the street such as Low Voltage poles and Vaulted Minipillars (e.g. by using ‘facial ‘recognition)

### Rooftop PV Siting
As costs of solar energy continue to plummet, more and more households are going solar.  This puts additional stress on the grid.  Use google maps to identify where PV is installed, and add these assets as a layer of data in a system to help utilities visualize energy generation and consumption on their grid.

##### Data and services provided:
- GE geospatial and mapping services
- The world wide web (hint:  satellite mapping images)

##### Approach
- Use satellite data to identify existing roof mounted solar installations
- Identify coordinates  to facilitate addition to ESB GIS system
- Represent solar installations as a data layer in the GE geospatial and mapping services, and calculate the peak power production on a daily basis based on roof orientation, amount of solar installed and weather data.

### Load Forecasting & Temperature Correction on Distribution Circuits
Adding renewables, electric vehicles, electric heating and other loads to the electric grid to drive decarbonization will increase congestion on the grid.  It will become more and more critical to have accurate forecasting of demand for power and load on circuits.  Help ESB develop an algorithm that can more accurately predict load based on how heating demands are impacted by the weather.

##### Data and services provided
- ESB historic time series data on load at medium-voltage outlets – outlets are categorized as mainly residential, mainly industrial/Commerical or a mixture of load categories
- Historic meteorological data

##### Approach
-Show time series meteorological data and load data
-Control for distribution of consumer types
-Determine relationship between meteorological data and load, accounting for consumer types and time lag between weather and energy consumption
-Back test algorithm
-Apply algorithm to forecasts


### Heat Pump Penetration & Impact on Electric Load

Driving toward a low-carbon future will require the conversion of building heating to electricity, and driving electricity generation to renewables.  Create a tool that determines the increased electric load from the operation of a heat pump, and from increased penetration of heat pumps in a given region.

##### Data provided:
- Heat pump data 
- Weather sources from the world wide web

##### Approach:
- Create an algorithm that correlates energy consumption and instantaneous power consumed with ambient temperature using the data set provided (which columns?)
- Apply the algorithm to statistical distributions of ambient temperature for areas of interest to estimate the increased energy consumption and peak power consumption for increasing the penetration of heat pumps from the EU average of 10% to penetration levels specified by user input

##### Other ideas:

- Predication tool that integrates weather data, comfort level of the user, and behavior of the heat pump under different climate conditions
- Improve or maximize/minimize consumption or the comfort level of the user
- Detect precursor signals before an incident on the equipment (predictive maintenance) or monitor a potential decrease in the equipment performance.
- Heat pump penetration & impact on load
- Demand response potential (TBD)

