---
title: What's new in Federated Audience Composition
description: Latest updates and release notes
badge: label="Limited availability" type="Informative"
---

# What's new {#rn-new}

The Federated Audience Composition is an add-on offers a flexible access and expanded reach into enterprise data warehouses to power personalization use-cases.

## What is Federated Audience Composition {#rn-fac}

Federated Audience Composition allows enterprises to compose data for better utilization across various use cases. With this new approach, as a Adobe Real-Time CDP and/or Adobe Journey Optimizer user, you can federate datasets directly from your existing data warehouse to enrich Adobe Experience Platform audiences and attributes all in one system.

Instead of ingesting datasets and/or audiences into Adobe Experience Platform, you can use Federated Audience Composition to reduce the volume of data copied from your data warehouse into Adobe Experience Platform by pulling specific audiences and attributes out of the warehouse that are needed for certain segmentation or activation use cases, and ensure sensitive data is not persisted outside the warehouse.


>[!AVAILABILITY]
>
>Federated Audience Composition is currently only available for a set of organizations (Limited Availability). To gain access, contact your Adobe representative.
>
>For now, the feature is unavailable for customers who have purchased the Adobe **Healthcare Shield** and **Privacy and Security Shield** add-on offerings.

## Use cases {#rn-uc}

Through a marketing-friendly UI, create segment rules that query your data warehouse for a list of users that qualify for a specific segment needed for marketing campaigns, access existing audiences in the warehouse for activation, or enrich Adobe Experience Platform audiences with additional datapoints that exist in the warehouse.

![diagram](assets/fac-use-cases.png)


## Prerequisites and guardrails {#rn-guardrails}

* Your IP addresses must be added to the allow list to enable access to your data warehouse and use Federated Audience Composition. To add your IP addresses to the allow list, contact your Adobe representative.

* Entitlements, product limitations and performance guardrails are listed in the [Guardrails for Real-time Customer Profile data before starting](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html){target="_blank"}.

## Frequently Asked Questions  {#rn-faq}

+++ What are the permissions required to access Federated Audience Composition?

There are no specific permissions for Federated Audience Composition. The only prerequisite to access this capability is to have purshased the Federated Audience Composition add-on.

+++

+++ What cloud warehouses are supported?

For this release, Federated Audience Composition is compatible with:

* Snowflake
* Google Big Query
* Azure Synapse
* Amazon Redshift

+++


+++ Can multiple data warehouses be queried in the same composition?

Yes, multiple warehouses can be queried in the same composition, and can combine data from multiple sources.  Typically, each [composition activity](../compositions/orchestrate-activities.md) (Query, Enrichment, Split, etc.) executes one or several SQL statements depending on the activity configuration, the targeted databases (there can be multiple cases of federated data access), and outputs of one or more worktables with the result of the execution. Those worktables are used as the input for consecutive activities.

+++

+++ Can I access my entire database using Federated Audience Composition?

No, it is up to you to configure access to a dedicated or shared database/schema. We recommend you to creates a dedicated schema for Federated Audience Composition, and copy/share business case datasets only. 
+++



+++ Do I have access to all tables in the dedicated schema?

Yes, once connected, Federated Audience Composition can be used to discover all tables based on initial rights defined, then you can use the visual schema editor to:

* Discover columns and primary keys from your tables
* Create friendly labels to those tables
* Create friendly labels for each column
* Hide unnecessary columns
* Save those tables description
+++


