---
title: Get Started with Federated Audience Composition
description: Learn what is Adobe Federated Audience Composition and how to use it in Adobe Experience Platform
badge: label="Limited availability" type="Informative"
exl-id: 43464aea-9c1d-4f1f-859f-82f209f350b7
---
# Get Started with Federated Audience Composition {#gs-fac}

Federated Audience Composition is an add-on for Adobe Real-Time Customer Data Platform and Adobe Journey Optimizer that allows you to build and enrich audiences from your third-party data warehouses and import the audiences into Adobe Experience Platform. Federated Audience Composition brings an easy and powerful solution to connect your enterprise data warehouse directly within Adobe Real-Time Customer Data Platform and/or Adobe Journey Optimizer, and perform queries on the tables of your data warehouse. 

Adobe Federated Audience Composition helps Adobe Experience Platform apps users to access their customer data which stored into their data warehouses and cloud storage platforms such as Amazon Redshift, Azure Synapse Analytics, and more. Customer data can live in multiple data warehouses and are now accessible instantly, without replication. Supported platforms are listed in [this page](../connections/federated-db.md#supported-db).

## Use cases {#rn-uc}

Through a marketing-friendly UI, create segment rules that query your data warehouse for a list of users that qualify for a specific segment needed for marketing campaigns, access existing audiences in the warehouse for activation, or enrich Adobe Experience Platform audiences with additional datapoints that exist in the warehouse. 

In this version, two use cases are available: Audience Creation and Audience Enrichment. 

![diagram](assets/fac-use-cases.png){zoomable="yes"}{width="75%" align="center"}

## Key steps {#gs-steps}

Adobe Federated Audience Composition lets you create and update Adobe Experience Platform audiences directly from your database, without any ingestion process.

![diagram](assets/steps-diagram.png){zoomable="yes"}{width="85%" align="center"}

Key steps:

1. **Data Integration**: Bring together data from various sources, and merge them into a unified dataset. Learn how to connect Adobe Experience Platform apps and your enterprise data warehouse, supported databases, and how to configure them are detailed in [this section](../connections/federated-db.md).

2. **Data Modeling**: Design and create data models and schemas that define the structure, relationships, and constraints of the data. Learn more about schemas in [this page](../customer/schemas.md). Learn how to create links for your datamodel in [this page](../data-management/gs-models.md).

3. **Data Transformation**: Apply data manipulation techniques to modify the format, structure, or values of data elements to make them compatible or suitable for specific analysis or applications.

4. **Data Usage**: Create, orchestrate and build audiences. Learn how to compose audiences in [this page](../compositions/gs-compositions.md). You can also update or reuse existing audiences through Adobe Experience Platform Audience portal and Destinations. Learn more in [this page](../connections/destinations.md)


>[!NOTE]
>
>After executing the composition, the resulting audience is saved in Adobe Experience Platform as an external audience, and available into Adobe Real-Time Customer Data Platorm and/or Adobe Journey Optimizer. It is made accessible in the **Audiences** menu. [Learn more](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/audience-portal){target="_blank"} 
>



## Learn more {#learn}

<!-- Workflow + Workflow activities-->

See Frequently Asked Questions in [this page](faq.md).

>[!CONTEXTUALHELP]
>id="dc_workflow_settings_execution"
>title="Execution settings"
>abstract="In this section, you can configure settings related to the execution of the worklow, such the number of days the composition history is kept."




>[!CONTEXTUALHELP]
>id="dc_orchestration_query_enrichment_noneditable"
>title="Activity non editable"
>abstract="When a **Query** or an **Enrichment** activity is configured with additional data in the console, the enrichment data is taken into account and passed into the outbound transition, but it cannot be edited."

<!-- Create a link --> 

>[!CONTEXTUALHELP]
>id="dc_federated_database_create_link"
>title="Create a link"
>abstract="Define the link settings."
