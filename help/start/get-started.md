---
title: Get Started with Federated Audience Composition
description: Learn what is Adobe Federated Audience Composition and how to use it in Adobe Experience Platform
badge: label="Limited availability" type="Informative"
---

# Get Started with Federated Audience Composition {#gs-fac}

Adobe Federated Audience Composition helps Adobe Experience Platform apps users to access their customer data which stored into their enterprise data warehouse. Customer data can live in multiple data warehouses and should be accessible instantly, without replication.

Adobe Experience Platform Federated Audience Composition brings an easy and powerful solution to connect your enterprise data warehouse directly within Adobe Real-Time Customer Data Platform, and perform queries on the tables of your data warehouse.

## Key steps {#gs-steps}

Adobe Federated Audience Composition lets you create and update Adobe Experience Platform audiences directly from your database, without any ingestion process.

![](assets/fac-diagram.png)


Key steps:

* **Configuration**

    1. Connect Adobe Experience Platform and your enterprise data warehouse. 
        The following databases are supported: Snowflake, Google Big Query, Azure Synapse, Redshift.
        Learn more in [this page](../connections/federated-db.md)
    1. Create schemas to select which data should be accessible from the user interface.
        Learn more in [this page](../customer/schemas.md)
    1. Create links for your datamodel.
        Learn more in [this page](../data-management/gs-models.md)

* **Compose audiences**

    1. Design and execute compositions to create audiences. 
        Learn more in [this page](../compositions/gs-compositions.md)
    1. Update or reuse existing audiences through Adobe Experience Platform Audience portal and Destinations. 
        Learn more in [this page](../connections/destinations.md)

## Learn more {#learn}

<!-- Workflow + Workflow activities-->



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
