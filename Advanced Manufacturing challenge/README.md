# Minds and Machines Berlin Hackathon 2017
# Advanced Manufacturing Challenge - Stelia Aerospace Dataset

## Who is Stelia?
STELIA Aerospace offers global solutions for aeronautical manufacturers and airlines. STELIA Aerospace designs and produces aerostructures, pilot seats and business and first class passenger seats.
More info: http://www.stelia-aerospace.com/en/stelia-aerospace/p10-group/

## What is the challenge?
Stelia main activity is to produce Elementary Parts (EP) to be assembled in workpackages of aircraft production programs. One workpackage can involve more than 6000 different EP references. A sequence of 5 activities are involved in EP preparation cycles, each with a specific delivery milestone date:

1.	Design – “OMP Date”
2.	Manufacturing / Engineering – “Transmission Proc Date”
3.	Procurement – “Notification Date”
4.	Industrialization – “End of Industrialization Date”
5.	Production – “Delivery Date”    


This challenge is about on time delivery (OTD) management. Stelia would strongly benefit from new tools and services to improve the accuracy of Elementary Parts preparation schedules.
Each EP requires a different processing time depending on its geometrical complexity. The geometrical complexity is measured with an index.

Your objective is to build a model to estimate the delivery milestone dates for EPs.


## What's in the dataset?
The dataset is made of 3 tables and a data description file.
A data dictionary and several tables (references, 1st industrialization) with realized dates and EP characteristics

## How to access the dataset?
- The dataset is a CSV file that you can download from the Hackathon GitHub repo.
- This file has been loaded in a blobstore instance that you can access from your app using the following information:
  - URL : https://mmeurope-blob.run.aws-usw02-pr.ice.predix.io
  - *Get* list of files in blobstore : https://mmeurope-blob.run.aws-usw02-pr.ice.predix.io/v1/list
  - *Get* file in blobstore : https://mmeurope-blob.run.aws-usw02-pr.ice.predix.io/v1/blob/{FILENAME}
