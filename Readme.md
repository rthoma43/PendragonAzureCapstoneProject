Team:

  George Mason University 
  Data Analytics Engineering Capstone (DAEN 690) - Spring 2023

  Kathleen Hill - khill29@gmu.edu - SCRUM Master,
  Enkhjin Tsagaandash - etsagaan@gmu.edu - Product Owner,
  Daniel Miller - dmille46@gmu.edu - Developer,
  Andrew Simpson - asimps4@gmu.edu - Developer,
  Ryan Thomas - rthoma43@gmu.edu - Developer

Background:

   GMU The Center for Assurance Research and Engineering (CARE) is developing an Information Environment Assessment project for NATO named Project Merlin led by our project partners. Our capstone objective is a DevSecOps pilot to migrate a locally hosted solution such as Project Merlin’s IEA to a cloud environment. Azure was chosen specifically because NATO maintains a production software development environment called NATO Software Factory which is based on Microsoft’s Azure cloud-based environment. 

Problem Space:

  As adoption of social media has grown tremendously over the last several years, organizations are increasingly adopting narrative analysis to use this data to assess public opinion about their organization or a topic that is relevant to the organization. The use cases of this is limitless including strategy, marketing, sales etc. Maybe they want to know how people are reacting to their latest change or announcement, maybe they want to assess the organization’s public image or marketing strategy. 

  Such narrative analysis tools work with extensive amount of data in near real time. Hosting these systems in a cloud environment makes them scalable and gives access to higher computing and processing power.

Problem Statement and Goal:

  The goal of this project is to explore the best methods through which to deploy a cost-effective systems architecture utilizing Microsoft Azure in order to perform opinion mining. This project, which includes social media data ingestion, storage, analysis, and visualization, will compare iterations of proposed architecture and provide a recommendation to individuals attempting to convert local data analytic capabilities to a cloud environment. 
  
The Repository:

  This repository was cloned from out Azure DevOps repository which was linked to our Azure Synapse Workspace. The work we did in the Synapse Workspace was periodicly published to our Azure DevOps Repo. To 

Content of the Repository:

  The Final branch contains all of the necessary files to replicate our project in Azure Synapse Analytics.
  
  The pipeline folder contains the pipelines we developed throughout the project. GET Until No Next Token or MaxTweets.json is our main pipeline. NLP_Analysis.json is the pipeline used within the main pipeline to execute analysis spark notebooks and PauseResumeSQLPool.json is the pipeline used within the main pipeline to automaticly resume and pause the dedicated SQL pool used for data storage. The Archive_Analysis_Tables.json pipeline is also used within the main pipeline to execute spark notebooks which archive tweets and analytical results.
  
  The linkedServices folder contains the Synapse Analytics Linked Services resources for connecting to outside resources such as RESTful API, Azure Key Vault, Azure Data Lake Gen 2, Dedicated SQL Pool, Azure Cognitive Services, and Power BI Workspace.
  
  The dataset folder contains all of the dataset resources used throughout the pipeline and more. These are used to connect data to its appropriate Linked Service data storage resource.
  
  The dataflow folder contains the resources for the data flow activities within the pipeline. These resources are used for extracting meta data from API responses or mapping JSON files to CSV files.
  
  The notebook folder contains the Apache Spark Notebook resources used in our Azure Synapse Workspace. These include the Topic Modeling notebook using Scikit-Learn LDA, Sentiment Analysis notebook and Named Entity Recognition notebook using Azure Cognitive Services, and Summarization notebook using a combination of Azure Cognitive Services Extractive Summary and Azure Open AI for Abstractive Summarization. Also, ArchiveAnalysis and ArchiveTweets notebooks are used to archive the ingested tweets and analysis results into appropriate dedicated SQL pool tables.
  
  The sqlscripts folder contains SQL script used to create dedicated SQL pool tables with specific data schema, SQL script for creating a delete procedure, and SQL script for performing fast querying and analysis. 
  
  The integrationRuntime folder contains the default integration runtime for our Azure Synapse Workspace, AutoResolveIntegrationRuntime.json, and a custom integration runtime, WarmIntegrationRuntime.json, used for maintaining warm clusters and scaling compute power.
  
  The credentials folder contains managed identities credentials associated with our Azure Synapse Workspace. These resources were created experimentally and are not implemented throughout the final system. 
