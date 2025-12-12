---
title: Frequently Asked Questions
description: Frequently Asked Questions about Adobe Experience Platform Federated Audience Composition
exl-id: 68cc0ae5-5c41-425f-8b10-ab3515294006
---
# Frequently asked questions {#faq}

The following is a list of frequently asked questions regarding Adobe Experience Platform Federated Audience Composition. A global FAQ is also available for Adobe Experience Platform Segmentation Service on [this page](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/faq){target="_blank"}.

## What permissions are required to access Federated Audience Composition?

+++ Answer

Federated Audience Composition requires Adobe Real-Time Customer Data Platform and Adobe Journey Optimizer Prime or Ultimate packages. You also need to have purchased Federated Audience Composition.

In order to use Federated Audience Audience Composition, each user must be added to a specific profile created for each sandbox. For more information, refer to the [Access Federated Audience Composition](./start/access-prerequisites.md) page.

+++

## What cloud warehouses are supported?

+++ Answer

Currently, the following cloud warehouses are supported:

* Amazon Redshift
* Azure Synapse Analytics
* Databricks
* Google BigQuery
* Microsoft Fabric
* Oracle
* Snowflake
* Vertica Analytics

For more information on connecting to a data warehouse, read the [connections overview](./connections/home.md).

+++

## Can multiple data warehouses be queried in the same composition?

+++ Answer

Yes, multiple warehouses can be queried in the same composition, and can combine data from multiple sources.  Typically, each [composition activity](./compositions/activities.md) (Query, Enrichment, Split, etc.) executes one or several SQL statements depending on the activity configuration, the targeted databases (there can be multiple cases of federated data access), and outputs of one or more worktables with the result of the execution. Those worktables are used as the input for consecutive activities.

+++

### Can I access my entire database using Federated Audience Composition?

+++ Answer

No, it is up to you to configure access to a dedicated or shared database/schema. We recommend you to create a dedicated schema for Federated Audience Composition, and copy/share business case datasets only. 
+++

## Do I have access to all tables in the dedicated schema?

+++ Answer

Yes, once connected, Federated Audience Composition can be used to discover all tables based on initial rights defined, then you can use the visual schema editor to:

* Discover columns and primary keys from your tables
* Create friendly labels to those tables
* Create friendly labels for each column
* Hide unnecessary columns
* Save those tables description
+++

## Is there any temporary storage in Federated Audience Composition?

+++ Answer

No, Federated Audience Composition only stores metadata (schema descriptions). No customer data is transiting. <!--The Audience export flow is done directly from Adobe Experience Platform Audience Portal (via [Destination](../connections/destinations.md)) to the customer database. The creation and update flow is done directly from your data warehouse database to Adobe Experience Platform Audience Portal.-->

+++

## Does Federated Audience Composition store a physical copy of that list of people to send to downstream systems?

+++ Answer

Federated Audience Composition does not maintain a physical copy of the data. Frequency is configured in the composition to define how frequently this data will be refreshed. The resulting audience data is not stored by Adobe Experience Platform any longer than required by the customer's use cases or action.

For example:

* In the case of an Audience Creation, the audience is created in your warehouse, and you can use Federated Audience Composition for additional composition tasks and data manipulation before publishing the resulting audience and associated attributes via Adobe Experience Platform Audience Portal. The audience definition and associated attributes come over to Adobe Experience Platform.
    Note that the current data expiration for externally generated audiences is 30 days. This data expiration reduces the amount of excess data stored within an organization. After the data expiration period passes, the associated dataset is still visible within the dataset inventory, but you cannot activate the audience and the profile count will show as zero. Learn more in [Adobe Experience Platform documentation](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/faq#how-long-do-externally-generated-audiences-last-for){target="_blank"}.

* In the case of an Audience Enrichment, the starting point is an existing Adobe Experience Platform audience. One can look at two scenarios here:
    1. Bring additional audience payload attributes from the federated data warehouse: in this case, the additional attributes that get added will come over as a part of this audience definition. Data expiration for externally generated audiences is the same as described above, 30 days.
    1. Refine the existing Adobe Experience Platform audience based on additional attributes that exist in your data warehouse. <!--For example, you have an audience of customers who have shown interest in a particular product on the website for the last two months. You now want to take this audience and further segment it using Federated Audience Composition to only include customers who have a high credit score. The credit score is deemed sensitive and individual credit score data points are not copied over from the data warehouse.-->
+++

## If the data for Audience Creation and Audience Enrichment use cases patterns is not being persisted, how is it being temporarily stored?

+++ Answer

The resulting Audience data do not persist indefinitely in Adobe Experience Platform or in Federated Audience Composition. It will not be retained any longer than required by your use case. The audience attributes brought as a part of the audience payload will persist only as a part of the audience definition. The duration of persistence is based on TTL for any audience, default is 30 days.

+++

## Can I delete an audience?

+++ Answer

No, in the current version you cannot delete Federated Audience Composition audiences.

+++

## If I combine data from multiple sources, how are we joining the data? Are we using Identity service?

+++ Answer

No, Identity Service is not being leveraged during a composition. The data between the various sources used in the composition is joined through user-defined logic (as expressed in the underlying model), e.g. CRM ID, User Account number, etc. You must to select the identity that is used as the identifier in the audience for selection in your data warehouse. On a resulting audience from Federated Audience Composition, you need to identify the identity namespace for the identity in the resulting dataset.

+++

## How can I create and manage privacy requests with Federated Audience Composition?

+++ Answer

You can submit individual requests to access and delete customer data from Adobe Federated Audience Composition in two ways:

* Through the Adobe Experience Platform **Privacy Service UI**. [Learn more](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html){target="_blank"}
* Through the Adobe Experience Platform **Privacy Service API**. [Learn more](https://experienceleague.adobe.com/en/docs/experience-platform/privacy/api/overview){target="_blank"}

All the steps to create and manage **access requests** and **delete requests** are detailed in the [Real-Time Customer Profile documentation](https://experienceleague.adobe.com/en/docs/experience-platform/profile/privacy){target="_blank"}.

+++

<!--
+++How are customer consent preferences honored for externally generated audiences that are imported into Federated Audience Composition?

As customer data is captured from multiple channels, identity stitching and merge policies allow this data to be consolidated in a single Real-Time Customer Profile. Information on the customers' consent preferences are stored and evaluated at the profile level.

Downstream Real-Time CDP and Journey Optimizer destinations check each profile for consent preferences prior to activation. Each profile's consent information is compared against consent requirements for a particular destination. If the profile does not satisfy the requirements, that profile is not sent to a destination.

When an external audience is ingested into Federated Audience Composition, it is reconciliated with existing profiles using a primary ID such as email or ECID. As a result, the existing consent policies will remain in force throughout activation.

>[!NOTE]
>
>Since the payload variables are not stored in the profile but in the data lake, you should not include consent information in externally generated audiences. Instead, use other Adobe Experience Platform ingestion channels where profile data is imported.

+++
-->
