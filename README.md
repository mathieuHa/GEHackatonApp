# minds-machines-europe

## Challenge details
The hackathon challenge and all logistics can be found here: https://mindsmachinesberlin.devpost.com/ 
Completed projects are due at 2pm Tuesday June 13th and must be submitted here: https://mindsmachinesberlin.devpost.com/submissions
This requires you create a devpost account in order to be eligble for a prize. 


## Time Series Data for Hackathon
A predix time series instance is set up and contains the data that can be used during the hackathon to build applications. For more information about time series, follow the documentation on predix.io (https://docs.predix.io/en-US/content/service/data_management/time_series/). This data available for hackathon is readonly.


## Environment Details for Accessing Time Series Data
Time series data can be accessed programatically using Time Series Client Library and the documentation is provided under https://docs.predix.io/en-US/content/service/data_management/time_series/using-the-time-series-client-library. To access the time series instance, we need the following information.

* UAA to perform authentication and to get authentication token
* Time Series Instance details to access time series using the obtained authentication token.

The following UAA and Time Series details are needed for the data retrieval.

* **UAA URL**: https://mmberlin.predix-uaa.run.aws-usw02-pr.ice.predix.io/oauth/token
* **Client Name**: timeseries_client_readonly
* **Client Password**: MMBerlin
* **TimeSeries Query URL**: https://time-series-store-predix.run.aws-usw02-pr.ice.predix.io/v1/
  * **Query tags**: https://time-series-store-predix.run.aws-usw02-pr.ice.predix.io/v1/tags
  * **Query datapoints**: https://time-series-store-predix.run.aws-usw02-pr.ice.predix.io/v1/datapoints
* **Timeseries Predix-Zone-Id**: cd7efa2c-881c-4d12-9e80-ceb03d4499ee

The time series connection can be verified quickly using the predix starter kit (https://predix-toolkit.run.aws-usw02-pr.ice.predix.io), prior to using the predix client libraries in the code.

## Time Series Query
The following is a sample query to retieve the data using one of the tags


{  

  "start":"2y-ago",

   "tags":[

      {  

         "name":"LoadForecasting/LoadData/Knockroe/DC14",

         "order":"desc",

      }

   ]

}


The following are the available tags in time series for the query:
* LoadForecasting/LoadData/Knockroe/DC14
* LoadForecasting/LoadData/Knockroe/LE17
* LoadForecasting/LoadData/Knockroe/TC12
* LoadForecasting/LoadData/Letterkenny_Dromore/CC15
* LoadForecasting/LoadData/Letterkenny_Dromore/CC18
* LoadForecasting/LoadData/Letterkenny_Dromore/GC13
* LoadForecasting/LoadData/Malahide_Castle/MC14
* LoadForecasting/LoadData/Malahide_Castle/MC18
* LoadForecasting/LoadData/Malahide_Castle/MC21
* LoadForecasting/LoadData/Mullingar/MC12
* LoadForecasting/LoadData/Mullingar/MC13
* LoadForecasting/LoadData/Mullingar/MC14
* LoadForecasting/LoadData/Mullingar/MC18
* LoadForecasting/LoadData/Mullingar/MC19
* LoadForecasting/LoadData/Mullingar/MC21
* LoadForecasting/LoadData/Mullingar/MC24
* LoadForecasting/LoadData/Mullingar/MC25
* LoadForecasting/LoadData/Shannon_Airport_Area/RC11
* LoadForecasting/LoadData/Shannon_Airport_Area/RC14
* LoadForecasting/LoadData/Shannon_Airport_Area/RC15
* LoadForecasting/LoadData/Shannon_Airport_Area/RC16
* LoadForecasting/LoadData/Shannon_Airport_Area/RC17
* LoadForecasting/LoadData/Shannon_Airport_Area/RC19
* LoadForecasting/LoadData/Shannon_Airport_Area/RC20
* LoadForecasting/LoadData/Shannon_Airport_Area/RC22
* LoadForecasting/LoadData/Shannon_Airport_Area/SC14
* LoadForecasting/LoadData/Shannon_Airport_Area/SC15
* LoadForecasting/LoadData/Shannon_Airport_Area/SC16
* LoadForecasting/LoadData/Shannon_Airport_Area/SC17
* LoadForecasting/LoadData/Shannon_Airport_Area/SC18
* LoadForecasting/LoadData/Shannon_Airport_Area/SC22
* LoadForecasting/LoadData/Shannon_Airport_Area/SC24
* LoadForecasting/WeatherData/Knockroe/dewpt
* LoadForecasting/WeatherData/Knockroe/irain
* LoadForecasting/WeatherData/Knockroe/itemp
* LoadForecasting/WeatherData/Knockroe/iwb
* LoadForecasting/WeatherData/Knockroe/iwddir
* LoadForecasting/WeatherData/Knockroe/iwdsp
* LoadForecasting/WeatherData/Knockroe/msl
* LoadForecasting/WeatherData/Knockroe/rain
* LoadForecasting/WeatherData/Knockroe/rhum
* LoadForecasting/WeatherData/Knockroe/temp
* LoadForecasting/WeatherData/Knockroe/vappr
* LoadForecasting/WeatherData/Knockroe/wddir
* LoadForecasting/WeatherData/Knockroe/wdsp
* LoadForecasting/WeatherData/Knockroe/wetb
* LoadForecasting/WeatherData/Letterkenny_Dromore/dewpt
* LoadForecasting/WeatherData/Letterkenny_Dromore/irain
* LoadForecasting/WeatherData/Letterkenny_Dromore/itemp
* LoadForecasting/WeatherData/Letterkenny_Dromore/iwb
* LoadForecasting/WeatherData/Letterkenny_Dromore/iwddir
* LoadForecasting/WeatherData/Letterkenny_Dromore/iwdsp
* LoadForecasting/WeatherData/Letterkenny_Dromore/msl
* LoadForecasting/WeatherData/Letterkenny_Dromore/rain
* LoadForecasting/WeatherData/Letterkenny_Dromore/rhum
* LoadForecasting/WeatherData/Letterkenny_Dromore/temp
* LoadForecasting/WeatherData/Letterkenny_Dromore/vappr
* LoadForecasting/WeatherData/Letterkenny_Dromore/wddir
* LoadForecasting/WeatherData/Letterkenny_Dromore/wdsp
* LoadForecasting/WeatherData/Letterkenny_Dromore/wetb
* LoadForecasting/WeatherData/Malahide_Castle/dewpt
* LoadForecasting/WeatherData/Malahide_Castle/irain
* LoadForecasting/WeatherData/Malahide_Castle/itemp
* LoadForecasting/WeatherData/Malahide_Castle/iwb
* LoadForecasting/WeatherData/Malahide_Castle/iwddir
* LoadForecasting/WeatherData/Malahide_Castle/iwdsp
* LoadForecasting/WeatherData/Malahide_Castle/msl
* LoadForecasting/WeatherData/Malahide_Castle/rain
* LoadForecasting/WeatherData/Malahide_Castle/rhum
* LoadForecasting/WeatherData/Malahide_Castle/temp
* LoadForecasting/WeatherData/Malahide_Castle/vappr
* LoadForecasting/WeatherData/Malahide_Castle/wddir
* LoadForecasting/WeatherData/Malahide_Castle/wdsp
* LoadForecasting/WeatherData/Malahide_Castle/wetb
* LoadForecasting/WeatherData/Mullingar/dewpt
* LoadForecasting/WeatherData/Mullingar/irain
* LoadForecasting/WeatherData/Mullingar/itemp
* LoadForecasting/WeatherData/Mullingar/iwb
* LoadForecasting/WeatherData/Mullingar/iwddir
* LoadForecasting/WeatherData/Mullingar/iwdsp
* LoadForecasting/WeatherData/Mullingar/msl
* LoadForecasting/WeatherData/Mullingar/rain
* LoadForecasting/WeatherData/Mullingar/rhum
* LoadForecasting/WeatherData/Mullingar/temp
* LoadForecasting/WeatherData/Mullingar/vappr
* LoadForecasting/WeatherData/Mullingar/wddir
* LoadForecasting/WeatherData/Mullingar/wdsp
* LoadForecasting/WeatherData/Mullingar/wetb
* LoadForecasting/WeatherData/Shannon_Airport_Area/dewpt
* LoadForecasting/WeatherData/Shannon_Airport_Area/irain
* LoadForecasting/WeatherData/Shannon_Airport_Area/itemp
* LoadForecasting/WeatherData/Shannon_Airport_Area/iwb
* LoadForecasting/WeatherData/Shannon_Airport_Area/iwddir
* LoadForecasting/WeatherData/Shannon_Airport_Area/iwdsp
* LoadForecasting/WeatherData/Shannon_Airport_Area/msl
* LoadForecasting/WeatherData/Shannon_Airport_Area/rain
* LoadForecasting/WeatherData/Shannon_Airport_Area/rhum
* LoadForecasting/WeatherData/Shannon_Airport_Area/temp
* LoadForecasting/WeatherData/Shannon_Airport_Area/vappr
* LoadForecasting/WeatherData/Shannon_Airport_Area/wddir
* LoadForecasting/WeatherData/Shannon_Airport_Area/wdsp
* LoadForecasting/WeatherData/Shannon_Airport_Area/wetb"
