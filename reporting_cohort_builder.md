## Cohort Builder 
**What is a cohort?**

* In statistics and demography, a cohort is a group of subjects who have shared a particular experience during a particular time span (e.g. people born in Uganda between 1980 and 1999, truck drivers between age 30 and 40 who smoke, Patients Started on ART in a given Month). 

* Cohorts may be tracked over extended periods of time in a cohort study.

* Cohort (builder),  is an OpenMRS capability that provides a group of proximate data, and/or operations  and produce  an aggregation of individuals
 who experience the same event within the same time interval  

**Why use cohort builder?**

* The cohort builder is a strong tool in OpenMRS which is used answer and create Ad-hoc reports i.e. number of patients seen last week in your clinic and are between the age of 0- 24  

**How to access the cohort builder:**

* Step 1: Click on the Cohort Builder link on the top level form. This will show you the Cohort Builder page as shown below.


![](ch.png)

**How to query OpenMRS database based on either the concept ID or concept name:**

This section enables the user to search for concepts or observations existing in the system.

Step 1: **Click on the Cohort Builder** link on the top level form.  This will show you the **Cohort Builder** page as shown below.

Step 2: Click on the **Concept/Observation** tab to show the page to be used in searching. 

![](ch1.png)

Step 3: Type in the concept name or ID of the variable you are looking for. E.g.Cd4
![](ch2.png)

Step 4: In case you typed in the concept name, click on the one that matches what you desire otherwise click on the only matching entry displayed.

The above action will show you a page with further settings/options for the chosen concept as shown and explained below:

![](ch3.png)

**1** Allows you to query for the variable using the following options:
* **Any:** will return all matching entries,
* **None:** will return those patients without this valuable entered on them.
* **Earliest** will return the first variable to be entered. 
* **Most Recent:** will return the most recent variable entered.
* **Lowest:** will return the lowest value for this variable.
* **Highest:** will return the highest value for this variable.
* **Average** turns the average value from with the eligible results.

**2.** is optional and adds conditional options to filter the results this includes <, >, <=,>= i.e. less than, greater than, less or equal to or greater or equal to the value specified in the right hand box.

**3.** Is optional and adds another filter based on months or days 

**4**. is optional and adds another filter for based on date ranges

**5.** Is the link to commences the query process

**6.** Is the link to cancel the query process.
****
