# Minds and Machines Europe Hackathon 2017
# Advanced Manufacturing Challenge - Stelia Aerospace Dataset

## Who is Stelia?
STELIA Aerospace offers global solutions for aeronautical manufacturers and airlines. STELIA Aerospace designs and produces aerostructures, pilot seats and business and first class passenger seats.
More info: http://www.stelia-aerospace.com/en/stelia-aerospace/p10-group/

## What is the challenge?
Stelia main activity is to produce Elementary Parts (EP) to be assembled in workpackages of aircraft production programs. One workpackage can involve more than 6000 different EP references. A sequence of 5 activities are involved in EP preparation cycles, each with a specific delivery milestone date:

1.	Design – Designing the definition of the reference - “date_reception_OMP""
2.	Manufacturing / Engineering – Preparation of the industrialization file for the reference - “date_transmission_proc”
3.	Procurement – Purchasing the reference from the supplier - “date_affectation”
4.	Industrialization - Industrialization by the supplier – “date_reelle_livraison_indus”
5.	Production – Production of the reference by the supplier - "date_liberation"

This challenge is about on time delivery (OTD) management. Stelia would strongly benefit from new tools and services to improve the accuracy of Elementary Parts preparation schedules.
Each EP requires a different processing time depending on its geometrical complexity. The geometrical complexity is measured with an index.

You can choose between two problematics:
1. Basic: Build a model to estimate the EP references preparation milestone dates.
2. Advanced: Build a tool to compute the optimal EP preparation schedule. This is a queue management optimization problem. Please note that to solve this advanced challenge you will need to use the kind of model built from the first sub-challenge (delay estimation model).

## Basic - EP preparation milestone date forecast

**Problem description**

Your mission is to build a regression model that will predict the time required to prepare each EP reference. This duration is defined as the time elapsed between the design start (date_reception_OMP) and delivery date (date_liberation).

```
estimated duration = date_liberation - date_reception_OMP
```


Currently Stelia is using the last realized preparation delays for each EP and each step to estimate future delays and shape the preparation schedule. Building a model with EP characteristics and full historical delay data as an input could be a first advance for better EP preparation scheduling.

**Data**

The dataset is made of 3 tables and a data description file.
A data dictionary and several tables (references, 1st industrialization) with realized dates and EP characteristics.
You are provided with two datasets: a train set and a test set. The date_liberation variable have been removed from the test set.

**Submission evaluation**

Your submission must include:
1. Your prototype app deployed on Predix
2. A CSV file with your output estimate for the references in the testset

You CSV file should have the following format (comma separated):
```
ID,estimate
1,3.4
2,9.3
3,5.0
4,1.7
...

```

The error function to be considered for regression model is the standard MSE on duration.

*Bonus point:*
Use the non-symetric function defined below for regression error. Its purpose is to penalize differently late estimations from early estimations (early is worst).
```
error = sum[[(Yrealized - Yestimate) / Yestimate]^2 * alpha]

With:
- alpha = 100 if (Yrealized - Yestimate) > 0
- alpha = 1 if (Yrealized - Yestimate) < 0
```

Hint: you can implement a gradient descent model search with this error function using Pytorch or Tensorflow for a gradient descent.


### How to access the dataset?
- The dataset is made of 2 CSV files (train set / test set) that you can download from the Hackathon GitHub repo.
- These files have been loaded in a blobstore instance that you can access from your app using the following information:
  - Blobstore URL: https://mmeurope-blob.run.aws-usw02-pr.ice.predix.io
  - *Get* list of files in blobstore : https://mmeurope-blob.run.aws-usw02-pr.ice.predix.io/v1/list
  - *Get* specific file in blobstore : https://mmeurope-blob.run.aws-usw02-pr.ice.predix.io/v1/blob/{FILENAME}


## Advanced - EP preparation schedule optimization
Stelia current challenge is a queue management optimization problem. Your mission is to implement a tool that can simulate different scenarios to find the best plan.
Stelia has 4 levels to optimize its operations, with increasing activation cost:
1. Priorization between references
2. Modification of planned capacity
3. Use a fast-lane (very limited capacity)
4. Inform the client of a delivery date revision

The optimization problem can be stated as follows:

**Assumptions**
- each EP preparation step can be modeled with a queue
- the timestep granularity is 1 day
- you can define any initial set of references to be produced
- fast-lane capacity is fixed equal to 20$ references per day
- cost of revising one date is 1000$ * delay

**Constraints**
- preparation steps can depend on each other XXX
- each queue has a given processing capacity expressed in number of references processed per week

**Variable**

For each each preparation step queue and each timestep:
- list of references in the queue with their priority order
- the processing capacity
=======
  - URL : https://mmeurope-blob.run.aws-usw02-pr.ice.predix.io
  - You can also do queries on this URL :
    - **List files**

      Returns list of files in blobstore.

      * **URL**

        /v1/list

      * **Method:**

        `GET`

    - **Get file**

      Returns file.

       * **URL**

          /v1/blob/:filename

      * **Method:**

        `GET`

      *  **URL Params**

         **Required:**

         `filename=[string]`
   - For more information about interacting with Blobstore : [tutorial](https://www.predix.io/resources/tutorials/tutorial-details.html?tutorial_id=1931&tag=1922&journey=Exploring%20Blobstore) & [documentation](https://docs.predix.io/en-US/content/service/data_management/blobstore/)
