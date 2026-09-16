# GTM Outbound Automation

An n8n-based outbound prospecting workflow designed to automate company research, contact discovery, data enrichment, buying-signal analysis, lead scoring, and CRM processing.

## Overview

This project is a self-built GTM automation workflow created to understand and automate the early stages of an outbound sales process.

The workflow uses n8n as the automation layer and connects external APIs and tools to collect prospect information, enrich contact data, evaluate prospects, and process qualified leads.

The main goal was to understand how a GTM workflow can move from raw company data to qualified prospects through an automated and repeatable process.

---

## Problem Statement

Outbound prospecting often involves several repetitive steps:

- Finding relevant companies
- Identifying decision-makers
- Collecting contact information
- Enriching prospect data
- Researching companies
- Identifying relevant buying signals
- Prioritizing prospects
- Sending qualified prospects to a CRM

Performing these tasks manually can be time-consuming and difficult to scale.

This project explores how these processes can be connected into a single automated workflow using n8n and APIs.

---

## Project Objective

The objective of this project was to build an automated GTM prospecting pipeline that can:

1. Research target companies
2. Identify relevant contacts
3. Enrich prospect information
4. Collect additional company and contact data
5. Detect potential buying signals
6. Assign a lead score
7. Identify higher-priority prospects
8. Process qualified contacts
9. Send relevant contact information to HubSpot CRM

---

## Workflow Architecture

```text
                    TARGET COMPANIES
                           |
                           v
                  COMPANY RESEARCH
                           |
                           v
                 CONTACT PROSPECTING
                           |
                           v
                    DATA ENRICHMENT
                           |
                           v
                  BUYING-SIGNAL CHECK
                           |
                           v
                     LEAD SCORING
                           |
                           v
                  LEAD QUALIFICATION
                           |
                           v
                    HUBSPOT CRM

How the Workflow Works
1. Company / Prospect Research

The workflow begins with target company information and performs prospect research using external APIs.

The purpose of this stage is to identify companies and people that match the intended outbound targeting criteria.

2. Contact Identification

After identifying relevant companies, the workflow searches for appropriate contacts within those organizations.

The workflow focuses on finding people who could be relevant decision-makers or stakeholders rather than simply collecting random employee records.

3. Data Enrichment

The prospect information is enriched using external data sources.

The enrichment stage is used to collect additional information such as:

Contact details
Company information
Professional information
LinkedIn/company information
Other available prospect attributes

The workflow is designed so that different enrichment sources can be connected depending on the availability of data.

4. JavaScript Data Processing

JavaScript is used inside n8n to process and transform data between different stages of the workflow.

The JavaScript logic helps with tasks such as:

Processing API responses
Transforming incoming JSON data
Structuring prospect information
Applying conditions
Preparing data for subsequent nodes
Supporting lead qualification and scoring

This allowed the workflow to handle data programmatically instead of relying only on individual n8n node configurations.

5. Buying-Signal Detection

The workflow also explores the use of signals that may indicate potential business interest or a relevant sales opportunity.

Examples of signals considered during the project include:

Hiring activity
Job postings
Funding activity
Leadership changes
Company growth indicators

These signals can be used as additional context when prioritizing prospects.

6. Lead Scoring

A lead-scoring stage is used to prioritize prospects based on available company, contact, and signal information.

The purpose is not simply to collect the largest possible number of leads, but to identify prospects that may be more relevant according to the defined criteria.

The workflow therefore moves from:

Raw Prospect
     ↓
Enriched Prospect
     ↓
Signal Analysis
     ↓
Lead Score
     ↓
Prioritized Prospect
7. Data Merging

The workflow combines information coming from different stages and APIs before continuing to the next part of the process.

This allows information from company research, contact discovery, enrichment, and signal analysis to be consolidated into a more complete prospect record.

8. Lead Qualification

The workflow applies conditions to determine which prospects should continue through the pipeline.

This reduces unnecessary processing and allows higher-priority prospects to be separated from prospects that do not meet the defined criteria.

9. HubSpot CRM Processing

Qualified prospect information is passed into HubSpot CRM.

The workflow includes logic for processing contacts and checking whether contacts should be created or updated.

This helps connect the prospecting and enrichment process with the CRM stage.

Tools & Technologies
Automation
n8n – Workflow automation and orchestration
JavaScript – Data transformation and workflow logic
Prospecting & Research
Prospeo API – Company/contact prospecting and data retrieval
Exa – Web and company research
Surf / enrichment tools – Additional prospect data enrichment
CRM
HubSpot CRM – Contact processing and CRM management
Data
JSON
REST APIs
HTTP requests
API responses
Google Sheets – Used during workflow development and data handling
API & Automation Concepts Used

While building this project, I worked with several practical API and automation concepts, including:

REST APIs
HTTP requests
GET and POST requests
API authentication
Headers
JSON request bodies
JSON responses
Response codes
API rate limits
Data transformation
Conditional logic
Workflow branching
Batch processing
API integration
CRM integration
Example GTM Process

The workflow follows a simplified GTM process:

TAM
 |
 v
Target Companies
 |
 v
ICP Filtering
 |
 v
Account Research
 |
 v
Contact Identification
 |
 v
Enrichment
 |
 v
Buying Signals
 |
 v
Lead Scoring
 |
 v
Lead Qualification
 |
 v
CRM

The project helped me understand how different GTM activities can be connected into a single operational workflow.

##Technical Challenges

During development, I encountered and worked through several practical automation challenges.

**API Credit & Rate Limits**

Some external prospecting APIs have usage and credit limitations.This required understanding how API limits affect workflow execution and how to avoid unnecessary requests.

**Batch Processing**

When processing multiple prospects, the workflow needed to handle records in batches rather than treating the entire dataset as a single request.This helped me understand how batching can be used to control API requests and workflow execution.

**Data Structure Differences**

Different APIs return information in different JSON structures.The workflow therefore required data transformation and merging before the information could be used by downstream nodes.

**Conditional Branching**

The workflow uses conditional logic to determine whether prospects should continue through different stages of the pipeline.

**CRM Contact Handling**

The HubSpot stage required logic around whether a contact should be processed as a new contact or handled as an existing record.

## **My Technical Contribution**

I designed and built the workflow in n8n and worked on connecting the different stages of the outbound prospecting process.

My contribution included:

Designing the overall workflow architecture
Building the n8n workflow
Connecting external APIs
Working with REST API requests
Using JavaScript within n8n for data processing
Handling JSON data
Building conditional logic
Implementing prospect enrichment
Working with buying-signal data
Creating lead-scoring logic
Combining data from multiple sources
Connecting the workflow with HubSpot CRM
Testing workflow execution
Troubleshooting API and data-processing issues
Working with batch processing and API limitations

##**What I Learned**
This project helped me develop practical understanding of both GTM concepts and technical automation.

**GTM**
Ideal Customer Profile (ICP)
TAM, SAM and SOM
Account segmentation
Account prioritization
Contact identification
Prospect enrichment
Buying signals
Lead qualification
Lead scoring
Outbound prospecting
Sales pipeline concepts

**Technical**
n8n workflow automation
REST APIs
HTTP methods
JSON
API authentication
API response handling
JavaScript data processing
Conditional workflows
Data merging
Batch processing
CRM automation
API rate-limit handling

## **Project Outcome**

The project resulted in a working n8n-based outbound prospecting workflow that connects prospect research, enrichment, signal analysis, lead scoring, qualification, and CRM processing into a single automated pipeline.

The project was primarily built as a hands-on learning and portfolio project to understand how GTM processes can be supported through automation and APIs.
