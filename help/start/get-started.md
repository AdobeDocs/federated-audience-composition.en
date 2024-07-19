---
title: Get Started with Federated Audience Composition
description: Learn what is Adobe Federated Audience Composition and how to use it in Adobe Experience Platform
badge: label="Limited availability" type="Informative"
---

# Get Started with Federated Audience Composition {#gs-fac}

Adobe Experience Platform Federated Audience Composition brings an easy and powerful solution to connect your enterprise data warehouse directly within Adobe Real-Time Customer Data Platform and/or Adobe Journey Optimizer, and perform queries on the tables of your data warehouse.

Adobe Federated Audience Composition helps Adobe Experience Platform apps users to access their customer data which stored into their data warehouses and cloud storage platforms (such as Amazon Redshift, Azure Synapse Analytics, Google BigQuery, Snowflake). Customer data can live in multiple data warehouses and are now accessible instantly, without replication.


## Use cases {#rn-uc}

Through a marketing-friendly UI, create segment rules that query your data warehouse for a list of users that qualify for a specific segment needed for marketing campaigns, access existing audiences in the warehouse for activation, or enrich Adobe Experience Platform audiences with additional datapoints that exist in the warehouse. 

In this version, two use cases are available: Audience segmentation and Audience enrichment. Profile enrichment will be available in a future release.

![diagram](assets/fac-use-cases.png){zoomable="yes"}

## Key steps {#gs-steps}

Adobe Federated Audience Composition lets you create and update Adobe Experience Platform audiences directly from your database, without any ingestion process.

![diagram](assets/steps-diagram.png){zoomable="yes"}

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

## Frequently Asked Questions {#faq}

The following is a list of frequently asked questions regarding Federated Audience Composition. A global FAQ is also available for Adobe Experience Platform Segmentation Service in [this page](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/faq){target="_blank"}.


+++What are the permissions required to access Federated Audience Composition?

There are no specific permissions for Federated Audience Composition. The only prerequisite to access this capability is to have purchased the Federated Audience Composition add-on.

+++

+++What cloud warehouses are supported?

For this release, Federated Audience Composition is compatible with:

* Snowflake
* Google Big Query
* Azure Synapse
* Amazon Redshift

+++


+++Can multiple data warehouses be queried in the same composition?

Yes, multiple warehouses can be queried in the same composition, and can combine data from multiple sources.  Typically, each [composition activity](../compositions/orchestrate-activities.md) (Query, Enrichment, Split, etc.) executes one or several SQL statements depending on the activity configuration, the targeted databases (there can be multiple cases of federated data access), and outputs of one or more worktables with the result of the execution. Those worktables are used as the input for consecutive activities.

+++

+++ Can I access my entire database using Federated Audience Composition?

No, it is up to you to configure access to a dedicated or shared database/schema. We recommend you to create a dedicated schema for Federated Audience Composition, and copy/share business case datasets only. 
+++



+++Do I have access to all tables in the dedicated schema?

Yes, once connected, Federated Audience Composition can be used to discover all tables based on initial rights defined, then you can use the visual schema editor to:

* Discover columns and primary keys from your tables
* Create friendly labels to those tables
* Create friendly labels for each column
* Hide unnecessary columns
* Save those tables description
+++


+++Is there any temporary storage in Federated Audience Composition?

No, Federated Audience Composition only stores metadata (schema descriptions). No customer data is transiting. The Audience export flow is done directly from Adobe Experience Platform Audience Portal (via [Destination](../connections/destinations.md)) to the customer database. The creation and update flow is done directly from your data warehouse database to Adobe Experience Platform Audience Portal.

+++

+++Does Federated Audience Composition store a physical copy of that list of people to send to downstream systems?

Federated Audience Composition does not maintain a physical copy of the data. Frequency is configured in the composition to define how frequently this data will be refreshed. The resulting audience data is not stored by Adobe Experience Platform any longer than required by the customer's use cases or action.

For example:

* In the case of an Audience Segmentation, the audience is created in your warehouse, and you can use Federated Audience Composition for additional composition tasks and data manipulation before publishing the resulting audience and associated attributes via Adobe Experience Platform Audience Portal. The audience definition and associated attributes come over to Adobe Experience Platform.
    Note that the current data expiration for externally generated audiences is 30 days. This data expiration reduces the amount of excess data stored within an organization. After the data expiration period passes, the associated dataset is still visible within the dataset inventory, but you cannot activate the audience and the profile count will show as zero. Learn more in [Adobe Experience Platform documentation](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/faq#how-long-do-externally-generated-audiences-last-for){target="_blank"}.

* In the case of an Audience Enrichment, the starting point is an existing Adobe Experience Platform audience. One can look at two scenarios here:
    1. Bring additional audience payload attributes from the federated data warehouse: in this case, the additional attributes that get added will come over as a part of this audience definition. Data expiration for externally generated audiences is the same as described above, 30 days.
    1. Refine the existing Adobe Experience Platform audience based on additional attributes that exist in your data warehouse. For example, you have an audience of customers who have shown interest in a particular product on the website for the last two months. You now want to take this audience and further segment it using Federated Audience Composition to only include customers who have a high credit score. The credit score is deemed sensitive and individual credit score data points are not copied over from the data warehouse.
+++

+++If the data for Audience Segmentation and Audience Enrichment use cases patterns is not being persisted, how is it being temporarily stored?

The resulting Audience data do not persist indefinitely in Adobe Experience Platform or in Federated Audience Composition. It will not be retained any longer than required by your use case. The audience attributes brought as a part of the audience payload will persist only as a part of the audience definition. The duration of persistence is based on TTL for any audience, default is 30 days.

+++

+++Can I delete a custom uploaded audience?

You can delete audiences that are not used in downstream activation directly in Audience Portal by simply selecting delete from the actions menu. Learn more in [Adobe Experience Platform documentation](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/faq#how-do-i-put-an-audience-in-the-deleted-state){target="_blank"}.

+++

+++If I combine data from multiple sources, how are we joining the data? Are we using Identity service?

No, Identity Service is not being leveraged during a composition. The data between the various sources used in the composition is joined through user-defined logic (as expressed in the underlying model), e.g. CRM ID, User Account number, etc. You must to select the identity that is used as the identifier in the audience for selection in your data warehouse. On a resulting audience from Federated Audience Composition, you need to identify the identity namespace for the identity in the resulting dataset.

+++

<!--
+++If I want to combine federated data with datasets that live in Adobe Experience Platform, how is this done?

Likewise, the Identity Service is not being leveraged in this scenario either. The data model underpinning a composition needs to express how the data warehouse data and the audience to be enriched are related. e.g. assume an existing audience in Adobe Experience Platform contains several attributes, among which is the CRM ID. Assume transactional data is in the data warehouse containing purchases with various attributes, including the CRM ID of the purchaser. The end-user would have to specify that the CRM ID for both objects is used to stitch the two objects together.

+++
-->

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
