> **Note:** This module is currently unreleased, and is dependent on the OEA framework v0.8rc1

<img align="right" height="75" src="https://github.com/microsoft/OpenEduAnalytics/blob/main/docs/pics/oea-logo-nobg.png">

# Canvas Module

[Canvas](https://www.instructure.com/canvas) is a K-12 and higher education Learning Management System (LMS), which offers a web-based solution to organizing student courses, learning progress and outcomes. This OEA Canvas module, originally developed by [Tasmania Department of Education](https://www.decyp.tas.gov.au/) in Tasmania, Australia, allows you to source data from the [Canvas Data v2 API](https://portal.inshosteddata.com/docs/api) <strong><em>[<- CHECK IF THIS IS STILL RELEVANT]</strong></em>. This enables administrators to retrieve data on course information, user activity data, assignment results, etc. The scope of this module is directed to pulling learning progress/outcomes and digital activity for analysis, through the use of the tables defined below.


<p align="center">
  <img src="https://github.com/cstohlmann/oea-canvas-module/blob/main/docs/images/canvas_module_v0.2_overview.png" alt="Clever Module v0.2 Overview Visual"/>
</p>

## Problem Statement and Module Impact
Education instutions increasingly rely on virtual learning environments (VLEs) such as Canvas to deliver course content to students, perform both formative and summative assessments, and to support communication between staff and students when studying remotely. For many institutions, this became even more relevent with the COVID-19 pandemic given the need to support study-from-home scenarios where students may no longer be physically present in a classroom. Although the need for digital learning is no longer as necessary, there is still demand and significance for alternative forms of learning (e.g. website-use, digital application uses, etc.)

This OEA Canvas module can aid any Canvas-using education systems in bringing the data types described below to their Azure data lake for analysis. The [module Synapse pipeline](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Canvas/pipeline) will connect to the [Canvas API](https://canvas.instructure.com/doc/api/index.html) and pull JSON files for multiple student learning-related data tables. The [module Power BI template](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Canvas/powerbi) allows users to immediately explore the data and start developing custom dashboards enabling education systems to better understand the learning progress of students. <strong><em>[CHECK TO SEE WHETHER THIS IS STILL RELEVANT ->]</strong></em> This module will also give you access to all tables present in [Canvas Data v1](https://portal.inshosteddata.com/docs) including user activity, course information, assessment results, etc. Examples where you might use this data include:
- Student/course engagement reporting - e.g. are students particpating in courses, do they need additional support, etc.
- Assessment reporting - average grades across schools, regions, or other boundaries (perhaps correlated with other data).
- VLE usage across teachers/school/region etc. - are some areas 'championing' digital learning, or do others need additional training & support.

## Module Setup Instructions
<strong><em>[WHAT TASMANIA HAD; PROB WILL CHANGE SIGNIFICANTLY]</strong></em>

- To use the module, you will require:
  - An instance of Canvas with the data API's enabled.
  - An Azure Subscription where we can deploy the Azure Durable Function used to download files.
  - [Terraform CLI](https://www.terraform.io/cli) and [Azure Core Function Tools](https://docs.microsoft.com/en-us/azure/azure-functions/functions-run-local?tabs=v4%2Cwindows%2Ccsharp%2Cportal%2Cbash) installed on your machine for the initial deployment.
  - A Synapse environment as deployed by the base OEA install where the pipeline can be configured.

Please see the [Setup docs](https://github.com/microsoft/OpenEduAnalytics/blob/main/modules/module_catalog/Canvas_Data/docs/Setup.md) for deployment instructions.

<p align="center">
  <img src="https://github.com/cstohlmann/oea-canvas-module/blob/main/docs/images/canvas_module_v0.2_setup_instructions.png" alt="Canvas v2.0 Setup Instructions"/>
</p>

<ins><strong>Preparation:</ins></strong> This module currently leans on v0.8rc1 of the OEA framework. Ensure you have proper [Azure subscription and credentials](https://github.com/microsoft/OpenEduAnalytics/tree/main/framework) and setup of the [OEA framework](https://github.com/microsoft/OpenEduAnalytics/tree/main/framework#setup-of-framework-assets). This will include v0.8rc1 of the [OEA python class](https://github.com/microsoft/OpenEduAnalytics/blob/main/framework/synapse/notebook/OEA_py.ipynb). 

<ins><strong>Note:</ins></strong> 
All the steps outlined below are applicable to deployment of this module with [test data](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Canvas/test_data). However, if you are doing a production deployment, this module currently does not provide guidance and assets will be need to be elevated for interactions with production data, depending on the Canvas database structure for an education system.

1. Run the [setup.sh script](https://github.com/Microsoft/OpenEduAnalytics/blob/main/modules/module_catalog/Canvas/setup.sh)
    * Open cloud shell in your Azure subscription (use ctrl+click on the button below to open in a new page)\
[![Launch Cloud Shell](https://azurecomcdn.azureedge.net/mediahandler/acomblog/media/Default/blog/launchcloudshell.png "Launch Cloud Shell")](https://shell.azure.com/bash)
    * Download the module release to your Azure clouddrive \
`cd clouddrive`\
`wget https://github.com/microsoft/OpenEduAnalytics/releases/download/module_Canvas_v0.2ar/module_Canvas_v0.2ar.zip`\
`unzip ./module_Canvas_v0.2ar.zip`
    * Run the setup script like this (substitute "mysynapseworkspacename" with your synapse workspace name, which must be less than 13 characters and can only contain letters and numbers - e.g. syn-oea-cisd3v07kw1): \
`./module_Canvas_v0.2ar/setup.sh mysynapseworkspacename`) to install this package into your own environment.
2. Run the [Canvas module main pipeline template](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Canvas/pipeline) or the [Canvas_example notebook](https://github.com/microsoft/OpenEduAnalytics/blob/main/modules/module_catalog/Canvas/notebook/Canvas_example.ipynb) into your Synapse workspace to see the functionality of module assets.
     * It is recommended that you first run the module example notebook to understanding the methods of data processing, before running the pipeline. Although, running either the example notebook or the main pipeline accomplish the same processes.
3. Verify that the module pipeline landed data into stage 1 and 2, and SQL and lake databases were created. See the [module pipeline page](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Canvas/pipeline) for detailed instructions.
4. Download the [module Power BI template file](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Canvas/powerbi). Module test data is already imported into the Power BI. See the [module Power BI page](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Canvas/powerbi) page for details and instructions for switching the Power BI template data source, to import from your Synapse workspace data source.
   * <strong>Note</strong>: This step is still under development (that is, this module currently does not contain a specific Power BI dashboard). 
 
#### OEA Learning Analytics Schema:

After completing the setup of this module, the Canvas activity schema can be transformed into the [OEA schema standard for learning analytics](https://github.com/microsoft/OpenEduAnalytics/tree/main/schemas/schema_catalog/Learning_Analytics). Refer to the documentation and assets to see how this module can be extended and standardized for OEA package-use.

## Data Sources

This module imports digital activity, learning outcomes, and roster data for an education system via queries from the Canvas API.
- [Canvas API Table-Schemas Information](https://data-access-platform-api.s3.amazonaws.com/index.html#tag/Query) provides a reference of the schemas for all tables that can be queried from the Canvas API.
- The Canvas API data source is used for ingesting Moodle digital activity, learning outcomes and SIS data, as explained above. There are also additional Canvas tables that can be ingested upon creating your own pipeline, or adding to the pipeline template provided.
- The data ingested is expected to be formatted as JSON files (per table) from the Canvas API.

See the [module test data page](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Canvas/test_data) for details on data format and contents.
  
## Module Components
<strong><em>[WHAT TASMANIA HAD]</strong></em>

The nature of the Canvas Data API makes it difficult to query directly from Synapse in a reliable and repeatable way. As such, this module makes use of several Azure Services outside of the standard notebook/pipeline structure. Components include:

1. An [Azure Durable Function](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Canvas_Data/function) instance that provides:
   - Functions to compare Canvas Data to stage1np data and identify missing files (deltas).
   - Functions to download new files and delete old (obsolete) ones.
   - Type translation generators that provide type translators for the ADF Copy Activity.
2. Several [Pipelines](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Canvas_Data/pipeline) for orchestrating & scheduling the data load into the lake, and the transform into stage2np.
3. A sample [notebook](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Canvas_Data/notebook) that creates a user activity table in stage3np.

<strong><em>[CLEVER MODULE EX.]</strong></em>

Out-of-the box assets for this OEA module include: 
1. [Test Data](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Clever/test_data): Artificially generated test data which supports the module pipeline and Power BI template. Test data matches the Clever [Participation Reports](https://support.clever.com/hc/s/articles/360049642311) format exactly.
2. [Pipeline Template](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Clever/pipeline): One main pipeline template which lands data into the Stage 1 data lake (for raw data) and processes into the Stage 2 data lake (for structured, queryable data). Stage 2 data is then made available via a serverless SQL endpoint.
3. [Notebooks](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Clever/notebook): 
    - [Clever_py.ipynb](https://github.com/microsoft/OpenEduAnalytics/blob/main/modules/module_catalog/Clever/notebook/Clever_py.ipynb): A module python class notebook that defines the data schemas and basic functions of data ingestion and processing from Stage 1 to Stage 2.
    - [Clever_module_ingestion.ipynb](https://github.com/microsoft/OpenEduAnalytics/blob/main/modules/module_catalog/Clever/notebook/Clever_module_ingestion.ipynb): Module data ingestion notebook which depends on the module class. The pipeline template incorporates this notebook. 
4. [PowerBI template](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Clever/powerbi): A Power BI template which explores data in a basic way. The Power BI file is pre-loaded with test data making it easy to quickly interact with Clever data. See instructions on the [module PowerBI page](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Clever/powerbi) to switch the dashboard data source to direct query from your Synapse workspace. Screenshots of the Power BI template are below.

Dashboard Explanation  | Dashboard Usage Summary
:-------------------------:|:-------------------------:
![](https://github.com/microsoft/OpenEduAnalytics/blob/main/modules/module_catalog/Clever/docs/images/Clever%20Module%20Explanation%20Page.png) |  ![](https://github.com/microsoft/OpenEduAnalytics/blob/main/modules/module_catalog/Clever/docs/images/Clever%20Module%20Dashboard%20Sample.png)  

## Additional Information

<strong><em>[WHAT TASMANIA HAD]</strong></em>

### **Approximate Hosting Costs**

The Azure Durable Function does come with a hosting cost in Azure however it is generally fairly minimal when using the consumption model (which is the default).

In our environment, most days did not exceed $0.20 USD per day. A full reload of the Canvas data cost ~$0.30 USD. For most use cases we anticipate the Azure Function and associated function storage would not exceed ~$5-10 USD per month. Costs for your environment will vary based on number of active staff/students in the platform.

Note the pricing does not consider the cost of hosting data in your Data Lake, Synapse overheads, spark pools, etc. - just the additional function and associated storage.

As always, it is suggested you monitor and review costs within your own environment.

### **Performance**

The Azure Durable Function has been designed with asynchronous I/O and scalability in mind. It does not download files directly, and instead invokes [start_copy_from_url](https://docs.microsoft.com/en-us/azure/developer/python/sdk/storage/azure-storage-blob/azure.storage.blob.blobclient?view=storage-py-v12#start-copy-from-url-source-url--metadata-none--incremental-copy-false----kwargs-) using the Python SDK.

In our testing, the function was able to download ~7 years worth of data (200 GB) in under 10 minutes. Processing the data into stage2 took 1-2 hours total due to the type conversion from CSV (strings) to Parquet.

Loads are incremental (only new/changes files are processed), so subsequent runs are significantly quicker - typically in the order of minutes.

<strong><em>[CLEVER MODULE EX.]</strong></em>

While this module leverages Clever [Participation Reports](https://support.clever.com/hc/s/articles/360049642311), more data is available via the [Clever API](https://dev.clever.com/docs/api-overview) feed.

| Resource | Description |
| --- | --- |
| [Overview of Clever API](https://dev.clever.com/docs/api-overview) | Intro to Clever API, what it can do, and how it can be used. |
| [Clever API v3.0 Data Schema](https://docs.google.com/spreadsheets/u/1/d/e/2PACX-1vTY8WSC--TBok-cHjG8itGyqnrj7sCkfyWVzIxeLybwzryW01L9qD8xwhoJDBlWrjOkciOXV34G9ejH/pubhtml) | Landing page of documentation on the v3.0 Clever data schema. |

## Contributions from the Community

The OEA Canvas module [welcomes contributions.](https://github.com/microsoft/OpenEduAnalytics/blob/main/docs/license/CONTRIBUTING.md) 

This module was developed by [Tasmania Department of Education](https://www.decyp.tas.gov.au/) in Tasmania, Australia, and [Kwantum Analytics](https://www.kwantumedu.com/). The architecture and reference implementation for all modules is built on [Azure Synapse Analytics](https://azure.microsoft.com/en-us/services/synapse-analytics/) - with [Azure Data Lake Storage](https://docs.microsoft.com/en-us/azure/storage/blobs/data-lake-storage-introduction) as the storage backbone,  and [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory/) providing the role-based access control.

# Legal Notices

Microsoft and any contributors grant you a license to the Microsoft documentation and other content
in this repository under the [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode),
see the [LICENSE](LICENSE) file, and grant you a license to any code in the repository under the [MIT License](https://opensource.org/licenses/MIT), see the
[LICENSE-CODE](LICENSE-CODE) file.

Microsoft, Windows, Microsoft Azure and/or other Microsoft products and services referenced in the documentation
may be either trademarks or registered trademarks of Microsoft in the United States and/or other countries.
The licenses for this project do not grant you rights to use any Microsoft names, logos, or trademarks.
Microsoft's general trademark guidelines can be found at http://go.microsoft.com/fwlink/?LinkID=254653.

Privacy information can be found at https://privacy.microsoft.com/en-us/

Microsoft and any contributors reserve all other rights, whether under their respective copyrights, patents,
or trademarks, whether by implication, estoppel or otherwise.
