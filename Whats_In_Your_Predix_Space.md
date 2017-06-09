# Minds and Machines Europe Hackathon 2017
# What's in your Predix space?

With your predix account, you have access to one of these orgs :
- predixbuilders2
- predixbuilder3
- predixbuilder4  

And your team space is : team#

In order to help you to quickly start the challenge, we already deployed services and apps in your space.

## APP

### MMEurope-ui

We deployed a 'MMEurope-ui' app to show you how to request and plot time series data from the heatpump timeseries instance. Please note that another timeseries instance is available with ESB load & weather data. You just need to bind your app with another timeseries instance to start working with it.

You can try it (replace # with your team number):
- App URL:
https://mmeurope-ui-team#.run.aws-usw02-pr.ice.predix.io
- UserID: TEAM_#
- User Secret: TEAM_#

### MMEurope-ui-intelligent-mapping

We deployed a 'MMEurope-ui-intelligent-mapping' app to show you how to request and plot GIS data stored in the Intelligent Mapping service instance deployed in your team space.

You can try it (replace # with your team number):
- App URL:
https://mmeurope-ui-intelligent-mapping-team#.run.aws-usw02-pr.ice.predix.io
- UserID: TEAM_#
- User Secret: TEAM_#

## SERVICES

In your space you are going to see multiple services :
* **MMEurope-uaa**
* **MMEurope-analyticsFramework**
* **MMEurope-intelligentMapping**
* **MMEurope_timeseries_heatPump**
* **MMEurope_timeseries_loadData**
* **MMEurope_uaa_admin**

### MMEurope-uaa

The User Account and Authentication Service (UAA) is a OAuth2 server that can be used for centralized identity management. You can see the [documentation here](https://docs.predix.io/en-US/content/service/security/user_account_and_authentication/).

We already created 1 UAA client and 1 user :
* **Client ID** : client
* **Client Secret** : Secret
* **User ID**:  TEAM_#
* **User Secret** : TEAM_#

### MMEurope-analyticsFramework

If you want to use analytics from Predix Catalog, you can see the [documentation here](https://docs.predix.io/en-US/content/service/analytics_services/analytics_framework/get-started)

### MMEurope-intelligentMapping

GE Energy Connections provides a mapping service on Predix: Intelligent Mapping that stores the location and properties of static assets

We already ingested GIS GeoJSON data from ESB into the Intelligent Mapping service instance in your team space. You can find the original [ESB data here](https://github.com/PredixDev/minds-machines-europe/tree/GIS_geojson_data/Electrification%20Challenge/Grid%20GIS%20Dataset).

You can find the Intelligent Mapping service API [documentation here](https://sw-intelligent-mapping.github.io/smallworld-mapping-services/#MappingServices/IMSapis.htm%3FTocPath%3DGetting%2520started%2520with%2520Intelligent%2520Mapping%2520and%2520Dynamic%2520Mapping%2520services%7C_____8)

**NB:** 'x-subtenant-id' or 'subtenantId' is the same id that your intelligent Mapping service ZoneId.

### MMEurope_timeseries_heatPump

We store all data from heat pump into a Time Series instance ([documentation](https://docs.predix.io/en-US/content/service/data_management/time_series/) about Time Series)

You have access our Time Series instance only in read only.You’ll find how to access to this data and an example [here](https://github.com/PredixDev/minds-machines-europe/tree/master/Electrification%20Challenge/Heatpump%20Timeseries%20Dataset)

**NB:** The time series instance is **not in your space** space but in an admin space. The service you can see in your space is a [**cups**](https://docs.cloudfoundry.org/devguide/services/user-provided.html)  

**NB2:** MMEurope_timeseries_heatPump & MMEurope_timeseries_loadData are not the same TimeSeries instance.

### MMEurope_timeseries_loadData

We store all data from load data and weather data into a Time Series instance ([documentation](https://docs.predix.io/en-US/content/service/data_management/time_series/) about Time Series)

You have access our Time Series instance only in read only.You’ll find how to access to this data and an example [here](https://github.com/PredixDev/minds-machines-europe/tree/master/Electrification%20Challenge/Grid%20Timeseries%20Dataset)

**NB:** The time series instance is **not in your space** but in an admin space. The service you can see in your space is a [**cups**](https://docs.cloudfoundry.org/devguide/services/user-provided.html)  

**NB2:** MMEurope_timeseries_heatPump & MMEurope_timeseries_loadData are not the same TimeSeries instance.

#### MMEurope_uaa_admin
To access to our two Admin TimeSeries instances, you need credentials and token. So, we have create a [**cups**](https://docs.cloudfoundry.org/devguide/services/user-provided.html) in order to easily bind this UAA for TimeSeries with your app.

**NB:** With this cups you can only get informations to request data on our two TimeSeries instances. For app authentification, analytics framework, intelligent-mapping,..., you have to use your own UAA **MMEurope-uaa**.
