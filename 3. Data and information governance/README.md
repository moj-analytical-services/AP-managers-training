# 3. Data and information governance

## Data storage locations

Data on the Analytical Platform can be stored in:

* home directories
* Amazon S3

Curated databases are also stored in Amazon S3 but are accessed using a service called Amazon Athena.

### Home directories

Each user has their own home directory. Home directories should be used to store working copies of code and analytical outputs

They are not connected to storage on DOM1 or Quantum.

You can upload data directly from your local machine within RStudio or JupyterLab and can upload data to and download data from Amazon S3..

### Amazon S3

Data in Amazon S3 is stored in buckets or data sources. There are two different types of data source: warehouse data sources and app data sources.

#### Warehouse data source

Warehouse data sources are used to store data that is accessed by code you run yourself, for example, in RStudio or JupyterLab. You can create warehouse data sources yourself and can provide access to other users you need to collaborate with.

Users can create their own warehouse data sources from the Analytical Platform control panel. They will automatically be made an admin and can manage access for other users.

#### App data source

Webapp data sources are used to store data that is accessed by code run by the Analytical Platform, for example by deployed apps or by Airflow pipelines. You cannot create app data sources yourself – you must ask the Analytical Platform team to create one on your behalf.

App data sources should only contain the minimum data required for an app or Airflow pipeline to work.

App data sources should not be used for muliple apps or Airflow pipelines even if they require access to the same data.

#### Access a data source

By default, users do not have access to any data stored in Amazon S3. To get access to a data source, a user must request permission from the relevant admin user.

#### Upload and download data

Users can upload data to and download data from Amazon S3 using the online console.

#### Read and write data using analytical tools

Users can read data stored in Amazon S3 into analytical tools (RStudio and JupyterLab) using the `s3tools` and `boto3` packages.

### Amazon Athena

> Amazon Athena is an interactive query service that makes it easy to analyze data directly in Amazon Simple Storage Service (Amazon S3) using standard SQL. With a few actions in the AWS Management Console, you can point Athena at your data stored in Amazon S3 and begin using standard SQL to run ad-hoc queries and get results in seconds.
> 
> Source: AWS

You can use Amazon Athena to access and query curated databases on the Analytical Platform.

#### Curated databases

The following databases are currently available on the Analytical Platform:

* CREST
* LIBRA
* XHIBIT
* NOMIS

We are planning to make the following databases available in the future.

* NDelius
* OASys
* LAA MAAT
* SOP
* FamilyMan
* CaseMan

You can find more information on our [roadmap](https://trello.com/b/OIL5fFOx).

Each database has different access levels to ensure that access is provided on a need-to-know basis.

##### Get access to a curated database

To access all curated databases on the Analytical Platform, you __must__ have completed the baseline personnel security standard (BPSS).

In order to access a curated database, you must complete a [data access form](https://forms.office.com/Pages/ResponsePage.aspx?id=KEeHxuZx_kGp4S6MNndq2I8ebMaq5PFBoMAkkhrMYHBUODRaN1ZWVlhRUVMxQ0VIRVQ1MlRLRkM4NS4u).

##### Query a curated database

Curated databases can be queried using SQL. Amazon Athena uses a variety of SQL called Presto, which has some small synatical differences compared to standard SQL.

You can query a curated database in the Amazon Athena UI or within RStudio or JupyterLab using the `dbtools` or `pydbtools` packages.

### GitHub

You should not use GitHub to store any data or any other sensitive information, such as secrets or credentials.

## Information governance

You can move data classified as OFFICIAL (including OFFICIAL-SENSITIVE) onto the Analytical Platform. SECRET and TOP SECRET data is not allowed on the Analytical Platform.

### Data movements

For __all__ movements of data onto the Analytical Platform, you __must__:

* obtain approval from the relevant Information Asset Owner (IAO) and, in some cases, the Senior Information Risk Officer (SIRO)
* complete an Analytical Platform data movement form

#### Personal data

If you are working with personal data you have a responsibility to ensure that you are compliant with the requirements of the General Data Protection Regulation (GDPR) and the Data Protection Act (DPA) 2018. This responsibility applies regardless of whether you are processing the data on the Analytical Platform or another system, such as DOM1.

In practice, this means you must ensure that:

* you are processing personal data in accordance with the principles of the GDPR and the rights of individuals
* you have a lawful basis for processing the personal data
* you have fulfilled all necessary governance requirements

##### What is personal data?

Personal data is information that relates to an individual who can be identified or who is identifiable:

* directly from the information in question
* indirectly from the information in question in combination with other information

Personal data could include information such as:

* names
* personal identifiers
* dates of birth
* addresses

##### Anonymisation and pseudonymisation

Anonymisation is the process of removing personal information from data such that individuals can no longer be identified. Data that has been fully anonymised is not considered personal data and is not subject to the GDPR.

> The principles of data protection should therefore not apply to anonymous information, namely information which does not relate to an identified or identifiable natural person or to personal data rendered anonymous in such a manner that the data subject is not or no longer identifiable.
> 
> Source: GDPR

In practice, full anonymisation is often very hard to attain. If it is possible to identify an individual from the data by any reasonable means, the data will not have been fully anonymised but rather pseudonymised.

> Pseudonymisation means the processing of personal data in such a manner that the personal data can no longer be attributed to a specific data subject without the use of additional information, provided that such additional information is kept separately and is subject to technical and organisational measures to ensure that the personal data are not attributed to an identified or identifiable natural person.
> 
> Source: GDPR

Pseudonymisation may involve replacing names or other personal identifiers with reference numbers or other artificial identifiers, while maintaining a lookup enabling individuals to be re-identified.

Pseudonymised data is still considered personal data and is subject to the GDPR.

You should try to anonymise or pseudonymise personal data where possible in accordance with the GDPR principles of data minimisation and storage limitation.

##### Moving personal data

If you want to move personal data onto the Analytical Platform, you should check if a Data Protection Impact Assessment (DPIA) or Privacy Impact Assessment (PIA) already exists for the processing of the personal data. The Information Asset Owner (IAO) of the data should be able to advise you if a DPIA or PIA already exists.

If a DPIA or PIA already exists, you should update the document to reflect use of the Analytical Platform. You should ensure that any changes are reviewed and approved by the IAO.

If a DPIA or PIA does not already exist, you should complete a DPIA screening document and submit this to the Data Protection Officer (DPO). You should also submit a final copy of the document to the Analytical Platform team.

You should also check if a privacy notice already exists. A privacy notice provides information to individuals about how and why their personal data is being collected and processed.

If a privacy notice already exists, you should update it to reflect use of the Analytical Platform. In particular, you should ensure the privacy notice informs individuals that their data will be:

* shared with Amazon Web Services, Inc. (AWS)
* stored outside of the UK but within the EU

##### Retention

Personal data should not be retained for longer than required. When personal data is no longer required you should erase it or anonymise it.

Personal data can be kept for longer if it is solely required for public interest archiving, scientific or historical research, or statistical purposes.

### Further information

For further information and support regarding information governance, contact the Data Protection Officer (DPO).
