# 1. Overview and vision

 - [What is the Analytical Platform?](#what-is-the-analytical-platform?)
 - [What is the purpose of the Analytical Platform?](#what-is-the-purpose-of-the-analytical-platform?)
 - [Why is it better than using legacy methods?](#why-is-it-better-than-using-legacy-methods?)
 - [Some more technical details about the Analytical Platform](#some-more-technical-details-about-the-analytical-platform)

## What is the Analytical Platform?

The Analytical Platform ('the AP', or 'the Platform') is a set of cloud-based technologies, all linked together behind a single sign-on.

[There are further technical details below.](#some-more-technical-details-about-the-analytical-platform)

## What is the purpose of the Analytical Platform?

Analysts in the Ministry of Justice produce excellent work to inform decisions in almost every corner of the MoJ's business.

However, much of this work is being done using legacy software such as Microsoft Excel and SAS. This software is hard to use collaboratively, limits what analytical techniques are possible, and limits what data can be used. Data has to be shared between teams by email, resulting in multiple copies and no clear audit trail.

The purpose of the Analytical Platform is to remedy this situation.

## Why is it better than using legacy methods?

The Analytical Platform has a number of benefits which will be covered in more detail in later sections of this course, but here we briefly mention a few.

### Three aspects to analytical work

There are three aspects to analytical work:
 - the data that forms the input to the work;
 - the model or analytical process that transforms that data into output; and
 - the environment in which that process occurs.

The Analytical Platform separates these three things, and ensures that each is explicitly defined. Changes can be made to any of them independently, without affecting the others. This modular way of working is potentially very powerful, as it makes it much easier to reproduce old work precisely, or run updated models on old data, or run old models on updated data, or move everything to a newer, better-provisioned environment.

By contrast, legacy ways of working usually fail to distinguish between these three areas, and don't allow them to be independently altered (for example, in Excel both the data and the model are defined in the same place, within the cells of the spreadsheet). This means that it is much harder to keep data and model separate, and people often forget about the environment entirely. The effect is that analysis is harder to reproduce and therefore harder to be certain of.

### The Platform's provision for those three areas

#### Modern tools
The Analytical Platform lets analysts write code in state-of-the-art modern coding languages R (using RStudio) and Python (using JupyterLab).

This means that analysts gain access to open source tools with huge global user communities: almost any query an analyst has will have been answered, and the details will be a simple search engine query away.

Additionally, almost any analytical technique that an analyst wants to use will very likely have an open source implementation in R or Python (or both): no more waiting for a proprietary language to support the technique.

#### Central data storage
The Analytical Platform provides a secure central location in which teams can store their data. This means teams will not have to email round copies of the data, but rather can access it from one central location.

The central data storage has excellent access controls in place. When a user sets up a new storage folder (called a 'bucket') for themselves, by default they are the only ones who can access it. They can then add (or remove) other users themselves. All access to data within buckets is centrally logged. This means that DASD is now in control of and has a record of who is accessing its data.

Additionally, the Platform team are working with the DPO's office to get a clear set of processes and policies to ensure that the AP is fully GDPR compliant. For the first time analysts will have clarity and reassurance about storing and processing data.

Finally, the Data Engineering team are creating the 'curated data' offering on the Platform. Datasets used by multiple teams within DASD (for example prisoners data, or data on criminal courts) are now available from the Data Engineering team. The team gets this data from as close to the source systems as possible, and then does all of the cleaning and manipulation required to transform that raw data into the tables that analysts use. All of this cleaning and automation is done in code and the process is fully automated, with built-in testing and checks. The output is a timely, reliable, reproducible dataset that can be used for analysis straight away.

#### Defined environments
Ever written a model in code and tried to get someone else to run it on their computer, only to find that it fails because of some obscure difference between their computer's environment and yours? This is a frequent difficulty people experience when working with R on dom1, for example.

The Analytical Platform solves this because all the processing of the data is done in the cloud in a 'containerised environment'. This means that we go to the remote machine on which our code _really_ runs, and we tell it to block out a section of itself for our work. Within this defined area we tell it to create a _virtual_ computer according to our defined specifications. This means that we are totally in control of the environment in which our code is running.

In particular, because the environment is explicitly declared, we can also reproduce it exactly whenever we like. This means we can be flexible in choosing the right environment for the right job, and we can always know exactly what is in our environment, which helps with debugging.

(Note that on the Platform, users are not expected to have to define all of this themselves, but there is flexibility to allow them to control it to some degree.)

### Reproducibility
The transformative effects of working on the Analytical Platform really take hold when we combine the above technologies, because we get analytical results that are fully reproducible.

Suppose we are challenged to reproduce some analysis we did last year, for example by a judicial review.

Using the Platform, we could recreate the exact data on which the analysis was done (if it was part of the curated data offering). We could find the exact code-based model that was applied to the data (even if the modelling has since changed). We could apply this model to the data in the exact same environment that was originally used. Thus, since all three aspects of the analysis are identical, we will reproduce our results precisely.

Compare this with pre-Platform ways of working. The data may no longer be available, unless someone has kept an old copy  somewhere on dom1 or in their local storage. If it hasn't been kept, it may not be reproducible because there may be no audit trail for the data's provenance, or the process to create it in the required format may involve lots of time and effort and manual steps.

In the pre-Platform way of working, the model may not be reproducible either - it may be that the old version that was previously used has been overwritten, or that (because of version control confusion) it's hard to tell exactly which one of several models was actually used.

Finally, in the pre-Platform way of working the environment in which the modelling was run may not be recoverable - if someone has updated their operating system, added some packages, or changed computer since the work was previously done then there may be some crucial differences between then and now.

Of course it may be the case that despite the above, the work could still be reproduced using pre-Platform ways of working: analysts do fantastic work putting procedures in place to minimise the problems mentioned. But the Analytical Platform makes this reproducibility much easier without so much time and effort.

### Improved ways of working

In addition to the improvements above in how analytical work itself can be done, there are also benefits in using the Platform when it comes to ways of working within an analytical team.

#### Collaboration
When working on the Analytical Platform, analysts store their code in GitHub repositories. This means that multiple analysts can work on the codebase simultaneously.

This will improve efficiency and speed when having to make rapid modelling changes or work collaboratively to tight deadlines.

#### Version control
Storing code in GitHub means that there is clear, unambiguous version control for projects. No longer will you have to email round Excel sheets called something like `model_v2_final_v4_FINAL.xlsx`. Instead there is a single canonical `master` version of the project, and a defined process for updating that version, even when working collaboratively.

This will improve clarity and efficiency when working in teams.

#### Automation
If a model or analytical process is defined in code, it can be run automatically according to a schedule. This means no more time and effort spent copying and pasting numbers from one spreadsheet to another, or creating pivot tables. Analysts' time can be freed up to look at the numbers and draw out key messages for their customers, or in digging into the numbers and uncovering the reasons behind them. In general it means analysts can focus on increasing the impact of the analysis, rather than doing repetitive tasks that a computer can do faster and with less chance of error.

Note that this automation is not restricted to running models: quality assurance can be automated too. A lot of QA is checking that outputs look as expected. This checking process can be automated, with procedures put in place to prevent the outputs being shared if the tests fail. The role of the analyst in QA then becomes the crucial one of defining what tests ought to be run, and implementing them in code, rather than repetitively carrying out those tests.


#### Sharing results
The Analytical Platform provides options for analysts to share their results directly with their customers. The customers will not need AP accounts, nor any special software; they will be able to access the outputs directly in their web browser (usually Firefox is required because of limitations with Internet Explorer/Edge).

Depending on the requirements, analysts can produce automated reports with embedded charts and graphs, dashboards that allow customers to self-serve and dig into the data on display, or full apps.

These outputs are hosted in the AP, so customers will be given a web address to go to. There are a couple of layers of security that analysts can use for their apps to make sure the results are not getting in the wrong hands.

## What next?

This has been a brief overview. The rest of the course focusses on some of the above aspects in more detail, starting with a look at what coding and analytical tools are available on the Analytical Platform.

## Appendix: some more technical details about the Analytical Platform

### What does 'cloud-based' mean?

Everything on the Analytical Platform is running on computers located elsewhere (e.g. not on Ministry of Justice premises). In particular, at the time of writing, the Analytical Platform is based on Amazon Web Services (AWS) and runs in their EU-west-1 region, located in Dublin.

From the users' perspective this means the Platform is accessed via web browser (ideally Mozilla Firefox or Google Chrome).

Using the cloud means we don't have to worry about the purchase and management of computer hardware ourselves; rather we can treat hardware as a flexible resource. Our storage space is effectively unlimited, and we can define our infrastructure (the things that we run everything on) in code. This is what allows us to have our environment as a separated, defined aspect of analytical work.

As an additional point, the [Government 'Cloud First' Policy](https://www.gov.uk/guidance/government-cloud-first-policy), [renewed in October 2019](https://technology.blog.gov.uk/2019/10/31/cloud-first-is-here-to-stay/), advises use of cloud-based solutions first when looking at IT infrastructure.

### What technologies does the Analytical Platform feature?

Some more detail about the AP's provision in each area.

#### Data storage
The Platform provides data storage in the cloud via Amazon Simple Storage Service ('S3').

#### Tooling
The AP hosts RStudio and Jupyterlab instances in dockerised containers run on a Kubernetes ('k8s') cluster managed by the AP team. Users' home storage directories are in SoftNAS. 

#### Apps
Apps are typically written in RShiny, reports in RMarkdown, although Python options also exist. Again they are hosted on our k8s cluster.

#### GitHub
We have our own GitHub organisation: https://github.com/moj-analytical-services.
