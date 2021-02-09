# 5. Reproducibility and automation

## What does it mean for analysis to be reproducible?
For analysis to be reproducible it should produce the same results consistently when ran against the same source data. This should be applicable regardless of where, when or by whom it is being ran. 

## What is a reproducible analytical pipeline (RAP)?
A reproducible analytical pipeline is a means of automating statistical publications across Government. The pipeline encompasses all steps from the injestion and cleansing of the source data to the production of the finished publication.

Through proper allocation of RAP principles the finished pipeline should have:
* Increased accuracy - By translating a process into code it can be guaranteed that the same steps are used each and every time it is ran.
* Reduced workload - By automating the manual stages of a process more time can be freed to examine and verity its output.
* Improved adaptability - Modular coding allows individual stages of a process to be altered without needing to rework the entire process.
* More transparency - All changes to the pipeline are tracked and a history of changes can be easily viewed.
* Built in documentation - Code should be clearly documented to convey the rationale behind its implementation. Pipelines should also include the overarching purpose as well as guidance on running, testing and modification.
* Built in versioning - Tools such as git allow the pipeline to be rolled back to a previous version as and when it is needed.
* Built in package management - Tools such as venv and Conda should be used to allow users to recreate the exact environment in which the code was developed and prevent any inaccuracies being introduced.
* Built in unit-test - Tests should be implemented in sensible places across the pipeline to ensure each step is working as intended.

## What support is available to implement a RAP?
There are a number of resources available to help teams implement RAP processes in MoJ:
### RAP specific
* RAP champions - This is a cross MoJ group who are involved in creating RAP publications. They meet on a regular basis to discuss the future of RAP, share best practice and peer review RAP processes. [Aidan Mews](https://peoplefinder.service.gov.uk/people/aidan-mews) leads the group.
* [DEDS/Automation team](https://peoplefinder.service.gov.uk/teams/automation ) - The automation team in DEDS can offer support and resource towards developing and implementing RAP processes within MoJ.
* RAP repos - RAP specific repositories can be found by searching [moj-analytical-services](https://github.com/moj-analytical-services). Some of these, like [mojrap](https://github.com/moj-analytical-services/mojrap), contain quality assured, generalised functions which can used when implementing a RAP. 
* Cross gov - Reproducible Analytical Pipelines are being implemented Government wide. As a result other departments have published guidance and online courses around RAPs.
    * [GSS RAP champions](https://gss.civilservice.gov.uk/about-us/champion-networks/reproducible-analytical-pipeline-rap-champions/)
    * [GDS RAP companion](https://ukgovdatascience.github.io/rap_companion/)
    * [RAP using R course](https://www.udemy.com/course/reproducible-analytical-pipelines/)

### General 
* Slack - Slack channels are great sources of knowledge and advice on individual elements of implementing a RAP process such as understanding git or coding in R and Python. Some useful channels include:
    * #git
    * #python
    * #r
    * #conda
* [Analytical Platform guidance](https://user-guidance.services.alpha.mojanalytics.xyz/#content ) - Most RAP processes will make use of the Analytical Platform. Guidance on how to get started using it can be found here.
* [Coding standards guidance](https://moj-analytical-services.github.io/our-coding-standards/) - MoJ has a set of coding standards which should be adhered to during the creation of a Reproducable Analytical Pipeline. Guidance on the standards can be found here.

