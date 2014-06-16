#CHIP-SET Requirements Gathering 

CHIP-SET aims to support the exchange and reuse of electronic healthcare data and methodology.  

##3 Use cases.

Expected outcomes for each use case: 

- Example Research Object/s for each use case. 
- Minimum Information Checklist describing an archetypal Research Object for the given “purpose”.   
- Recommendation of vocabularies to use to describe annotations for each type of RO. 
- Identification of any core subset of features for a CHIP-SET research object


### STELAR ###
####Owner: Phil Couch  Philip.Couch@manchester.ac.uk 

STELAR is an e-lab bringing together data from 5 asthma cohort studies. 

The STELAR use-case is primarily concerned with capturing the materials and methodology of the Atopic March (AM) study. 

The AM study has been conducted on 2 cohorts - goal is to create research object such that we can:
1) Repeat the study on existing two cohorts. 
2) Reproduce the study for the other three cohorts. 


### Clinicalcodes.org ###

####Owner: David david.springate@manchester.ac.uk 

Clinical codes aims to be a repository of the structured code lists for all published electronic medical record studies.

The Clinicalcodes use-case is primarily concerned with the ***exchange*** of code lists between FARSITE and clinicalcodes.org. 

I want to export a code list from clinicalcodes.org as a Research Object. 

I want to import a code list into FARSITE  in the form of a Research Object 



### Text-Mining / CPRD - ###
####Owners: George Karystiansis, Goran Nenadic, Will Dixon. 

Goal for Goran is a record of the piece of software that can be advertised and discovered.

Subsequent goal is to then is a record of the investigation that can be reused.
This is a record of the process of Will’s investigation - where the “software research object” is a component. 

Key feature for these types of RO is the record of method. Can we use/extend PROV to capture this record of process/method? What form does this need to come in? Machine readable? Human readable? Both? 

Materials used for Text-mining use-case.

Input - Current :text files sets of prescription data, one prescription per line. 

Future: Document which *may* have prescription data 

Parent script (python) -  sub scripts. No parameters to George’s scripts. 

Data Folder holds input data. 

Result is detailed structured representation of prescription information 

Result feeds into Will’s “research object”. 

Method 
It is a simple execution of the script given the input file


Determining the purpose of a Research Object with user stories.

User Story: 

As a <type of user>, I want <some goal> so that <some reason>.

Feature-oriented: 

<action> <result> <object>. 

Clinicalcodes.org User Stories

Code lists are CSV files 

As a clinical researcher, 

I want to export a study so that I can import the cohort descriptions into FARSITE.  




###Text mining User Stories

As an informatician I want to discover software tools relevant to my needs so that I can reuse those tools as part of my investigation. 




###STELAR User Stories


As an --- I want to publish the material and processes involved in the Atopic March study so that I can get credit for any reuse of the material or processes. 

As a --- I want to gather the materials and processes involved in the Atopic March study for one cohort so that I can repeat the process on the same cohort

As a --- I want to gather the materials and processes involved in the Atopic March study for one cohort so that I can repeat the process on a different cohort


###Overarching CHIP-SET User Stories?

As an Epidemiologist, 

I want to export a data set so that I can -----

I want to export data with its provenance  so that I can understand where it came from

I want to export data with its associated files 

I want to export data with its annotations 

***TODO:*** Add the EuroScore, BMI study and Kidney Function/Heart Failure overarching use-cases from Iain Buchan. 


