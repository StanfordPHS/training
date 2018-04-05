# Beginner training: Generating a postpartum depression cohort
This example walks through the process of creating a cohort of individuals who have met the diagnostic criteria for postpartum depression.  

This document intentionally leaves out any mention of variable names for security purposes.


## Step 1: Identifying our tables
You can explore a variety of datasets offered by PHS at [phsdata.stanford.edu](phsdata.stanford.edu). For this example, we will be using two tables from the [Truven Dataset Group](https://redivis.com/StanfordPHS/Truven):

#### [Truven Inpatient Services](https://redivis.com/StanfordPHS/Truven/Truven-Inpatient-Services)
This table contains a record for every service event associated with an inpatient admission. Because deliveries are an inpatient occurrence; this is where we can find all individuals within Truven who have had a delivery.

#### [Truven Outpatient Services](https://redivis.com/StanfordPHS/Truven/Truven-Outpatient-Services)
Depression diagnoses are generally associated with outpatient care. We will use this table to link our delivery cohort with those individuals who have also had a depression diagnosis.


## Step 2: Create initial cohort
Using the Redivis project tool ([documentation](https://help.redivis.com/for-researchers/querying-data.html)), we will select all individuals who have the relevant ICD-9 and CPT codes for a delivery or depression event. These codes can be found in `Codes.csv` within this directory. We will then join all individuals who have a depression event in the `Inpatient` table with those who have a depression event in the `Outpatient` table.
**NB:** These code lists are not comprehensive, and are for demonstration purposes only. Do not use these lists for your research.

## Step 3: Apply diagnostic criteria
Next, we will apply certain inclusion and exclusion criteria to our cohort. Specifically, postpartum depression will be defined as depression that occurs any time during pregnancy, and up to four weeks after delivery _only_ when depression had not been diagnosed within the year preceding the pregnancy.

## Step 4: Augment our cohort   
We now have a set of identifiers for individuals who meet our criteria for postpartum depression alongside the date of their delivery. We can use this information to join in additional columns from the various Truven tables to augment our cohort and give us the information needed for further analysis.

## Step 5: Upgrade to the full sample and export our cohort
Once we have the table(s) that we want to export, we can [upgrade our project](https://help.redivis.com/for-researchers/querying-data/samples.html) to use the full data sample, and then [export](https://help.redivis.com/for-researchers/querying-data/exports.html) our final table. Truven data may only be exported to the [PHS compute environment](https://web.stanford.edu/group/phs-dc/cgi-bin/wordpress/phs-windows-server/) — once remote logging in to the server, just navigate to your project on Redivis in the Chrome browser, and click the export button. You will not be able to download or export Truven data to your computer at any time.


## Thank You!  
Our next training is on Thursday 19 April, 4-6pm, LKSC 304/305 ([sign up](https://calendly.com/phsdatacore/phs-training/04-05-2018?back=1)). Please help us spread the work by telling your friends and colleagues who may be interested in working with PHS data!

Questions? Comments? Feedback? Please consult the links in [this repo's README](https://github.com/StanfordPHS/training) to consult our varied support resources. If you have any specific feedback on how we might make these trainings better, you can email [Emma](mailto:emma.hallgren@stanford.edu) or [Ian](mailto:ian@redivis.com)
