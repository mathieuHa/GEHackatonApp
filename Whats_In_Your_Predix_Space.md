# Minds-Machines-Europe

## What's in your space ?

With your predix account, you have access to one of these orgs :
* predixbuilders2
* predixbuilder3
* predixbuilder4  

And your team space is : team#

In order to help you to quickly start the challenge, we already deployed services and app in each space.

## APP
#### MMEurope-ui
We also deployed MMEurope-ui app to show you how to request and plot time series data & intelligent-mapping data.

## SERVICES

In your space you are going to see multiple services :
* **MMEurope-uaa**
* **MMEurope-analyticsFramework**
* **MMEurope-intelligentMapping**
* **MMEurope_timeseries_heatPump**
* **MMEurope_timeseries_loadData**
* **MMEurope_uaa_admin**

#### MMEurope-uaa

The User Account and Authentication Service (UAA) is an OAuth2 server that can be used for centralized identity management. You can see the [documentation](https://docs.predix.io/en-US/content/service/security/user_account_and_authentication/).

We already created one client and one user :
* **Client ID** : client
* **Client Secret** : Secret
* **User ID**:  TEAM_#
* **User Secret** : TEAM_#

#### MMEurope-analyticsFramework

If you want to use analytics from Predix Catalog, you can see the [documentation](https://docs.predix.io/en-US/content/service/analytics_services/analytics_framework/get-started)

#### MMEurope-intelligentMapping

GE Energy Connections provides a mapping services on Predix:
* Intelligent Mapping — stores the location and properties of static assets

We already ingest GIS geojson [data](https://github.com/PredixDev/minds-machines-europe/tree/GIS_geojson_data/Electrification%20Challenge/Grid%20GIS%20Dataset).

If you want to access to this data, you can read this [documentation](https://sw-intelligent-mapping.github.io/smallworld-mapping-services/#MappingServices/IMSapis.htm%3FTocPath%3DGetting%2520started%2520with%2520Intelligent%2520Mapping%2520and%2520Dynamic%2520Mapping%2520services%7C_____8)

**NB:** x-subtenant-id or subtenantId is the same id that your intelligent Mapping service Zone Id

#### MMEurope_timeseries_heatPump

We store all data from heat pump into a Time Series instance ([documentation](https://docs.predix.io/en-US/content/service/data_management/time_series/) about Time Series)

You have access our Time Series instance only in read only.You’ll find how to access to this data and an example [here](https://github.com/PredixDev/minds-machines-europe/tree/master/Electrification%20Challenge/Heatpump%20Timeseries%20Dataset)

**NB:** The time series instance is **not in your space** space but in an admin space. The service you can see in your space is a [**cups**](https://docs.cloudfoundry.org/devguide/services/user-provided.html)  

**NB2:** MMEurope_timeseries_heatPump & MMEurope_timeseries_loadData are not the same TimeSeries instance.

#### MMEurope_timeseries_loadData

We store all data from load data and weather data into a Time Series instance ([documentation](https://docs.predix.io/en-US/content/service/data_management/time_series/) about Time Series)

You have access our Time Series instance only in read only.You’ll find how to access to this data and an example [here](https://github.com/PredixDev/minds-machines-europe/tree/master/Electrification%20Challenge/Grid%20Timeseries%20Dataset)

**NB:** The time series instance is **not in your space** but in an admin space. The service you can see in your space is a [**cups**](https://docs.cloudfoundry.org/devguide/services/user-provided.html)  

**NB2:** MMEurope_timeseries_heatPump & MMEurope_timeseries_loadData are not the same TimeSeries instance.

#### MMEurope_uaa_admin
To access to our two Admin TimeSeries instances, you need credentials and token. So, we have create a [**cups**](https://docs.cloudfoundry.org/devguide/services/user-provided.html) in order to easily bind this UAA for TimeSeries with your app.

**NB:** With this cups you can only get informations to request data on our two TimeSeries instances. For app authentification, analytics framework, intelligent-mapping,..., you have to use your own UAA **MMEurope-uaa**.
