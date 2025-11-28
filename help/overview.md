---
title: Federated Audience Composition overview
description: Learn about Adobe Federated Audience Composition and how to use it in downstream services such as Adobe Experience Platform and Adobe Journey Optimizer
exl-id: 43464aea-9c1d-4f1f-859f-82f209f350b7
---
# Federated Audience Composition overview

Federated Audience Composition lets you build and enrich audiences from your third-party data warehouses and import the audiences into Adobe Experience Platform. This brings an easy and powerful solution to connect your enterprise data warehouse directly within downstream services like Adobe Real-Time Customer Data Platform or Adobe Journey Optimizer, and perform queries on the tables of your data warehouse. As a result, you can access customer data that is stored in data warehouses and cloud storage platforms such as Amazon Redshift and Azure Synapse Analytics.

## Capabilities {#rn-capabilities}

Federated Audience Composition extends the value of Real-Time CDP and Journey Optimizer with a comprehensive approach to audience curation and activation:

* **Expand access to critical warehouse-based datasets to create high-value audiences**: You can use existing data warehouses as the main system of record, while leveraging best-in-class applications to power great customer experiences.

* **Comprehensive support to power engagement use cases**: Federated Audience Composition, paired with Real-Time CDP or Journey Optimizer, supports brand-initiated, personalized experiences with federated audiences and delivers in-the-moment experiences triggered by real-time events, combined with person attributes to meet use case requirements across teams.

* **Minimize data movement and duplication**: You can create audiences from datasets that live in enterprise data warehouses without copying underlying data to manage actionable marketing profiles and audiences.

* **Utilize a single system for experience-driven workflows**: You can curate both ingested and federated audiences in Adobe Experience Platform and coordinate outbound experiences across all channels.

* **Multi-edition support**: B2C and B2B CDP customers can leverage Federated Audience Composition to build people-based audiences by integrating data from supported enterprise data warehouses. Additionally, they can enrich existing Experience Platform people-based audiences by incorporating relevant attributes available in the enterprise data warehouse, enhancing their audience profiles for more personalized and targeted engagement. 

## Use cases {#use-cases}

Federated Audience Composition supports **three** categories of use cases: audience creation, audience enrichment, and customer profile enrichment. 

* **Audience creation**: You can create audiences from a data warehouse and federate those audiences into Experience Platform for use in either Real-Time CDP or Journey Optimizer through a marketer friendly drag-and-drop user interface. As a result, you can query your data warehouses without copying sensitive underlying data or duplicating existing data.
  * **Example:** Create an audience of high value past purchasers using historic transaction data in the warehouse, without copying those transactions into Experience Platform.

* **Audience enrichment**: You can add more detail to your existing audiences in Experience Platform by using additional datasets from your data warehouses and overlaying your audiences with this information - all without copying the underlying data into Experience Platform. With audience enrichment, you can deliver improved personalization with the enriched audience.
  * **Example:** Enrich an Experience Platform audience of cart abandoners with the Federated Audience Composition audience of high-value past purchasers to deliver a targeted offer.

* **Profile enrichment**: You can select individual customer attributes from your data warehouse to enhance Experience Platform profiles. With federated data added to these profiles, you can better power in-the-moment experiences that are triggered by inbound customer signals.
  * **Example:** Enrich an Experience Platform profile with information from the federated audience. You can now market to a site visitor who belongs to the high-value past purchasers federated audience with a targeted offer that is triggered by their on-site behavior. 

![diagram](assets/overview/fac-use-cases.png){zoomable="yes"}{width="75%" align="center"}

For more information on Federated Audience Composition use cases, please read the [Federated Audience Composition whitepaper](https://business.adobe.com/resources/sdk/flexibly-access-enterprise-data-with-federated-audience-composition.html).

## Key steps {#gs-steps}

Adobe Federated Audience Composition lets you create and update Adobe Experience Platform audiences directly from your database, without any ingestion process.

<!--![diagram](assets/steps-diagram.png){zoomable="yes"}{width="85%" align="center"}-->

1. **Create a connection**: Bring together data from various sources, and merge them into a unified dataset. For more information on connecting Adobe Experience Platform apps to your enterprise data warehouse, supported databases, and configuring your connection, read the [connections overview](../connections/home.md).

2. **Model your data**: Design and create schemas and data models that define the structure, relationships, and constraints of the data. For more information on schemas, read the [schema overview](../customer/schemas.md). For more information on data models, read the [data model overview](../data-management/models.md).

3. **Transform your data**: Apply data manipulation techniques to modify the format, structure, or values of data elements to make them compatible or suitable for specific analysis or applications.

4. **Compose your audience**: Create, orchestrate and build audiences. For more information on composing audiences, read the [composition overview](../compositions/compositions.md). You can also update or reuse existing audiences through Adobe Experience Platform Audience portal and Destinations. Learn more on [this page](../connections/destinations.md)

>[!NOTE]
>
>After executing the composition, the resulting audience is saved in Adobe Experience Platform as an external audience, and available into Adobe Real-Time Customer Data Platform and/or Adobe Journey Optimizer. It is made accessible in the **Audiences** menu. [Learn more](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/audience-portal){target="_blank"}

## Governance, privacy and security {#governance-privacy-security}

### Privacy requests {#gov-privacy-requests}

Once you created a composition, the resulting audiences are saved into Adobe Experience Platform.

You can then make privacy requests to access and/or delete profile data corresponding to these audiences through Adobe Experience Platform **Privacy Service**, which provides a [user interface](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html){target="_blank"} and [RESTful API](https://experienceleague.adobe.com/en/docs/experience-platform/privacy/api/overview){target="_blank"} to help you manage customer data requests.

>[!NOTE]
>
>For more information on Privacy Service, refer to the [Adobe Experience Platform documentation](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html){target="_blank"}.

You can create and manage individual requests to access and delete customer data from Adobe Federated Audience Composition. The steps to submit **access requests** and **delete requests** are detailed in the [Real-Time Customer Profile documentation](https://experienceleague.adobe.com/en/docs/experience-platform/profile/privacy){target="_blank"}.

### Audit trail {#gov-audit-trail}

The audit trail capability provides a detailed and chronological record of all actions and events that have been made to your environment in real-time. To learn more about the audit trail, please read the [audit trail overview](../admin/audit-trail.md).

## Learn more {#learn}

<!-- Workflow + Workflow activities-->

Learn how to access Federated Audience Composition, guardrails and limitations on [this page](access-prerequisites.md).

See also frequently asked questions on [this page](faq.md).

>[!CONTEXTUALHELP]
>id="dc_workflow_settings_execution"
>title="Execution settings"
>abstract="In this section, you can configure settings related to the execution of the workflow, such the number of days the composition history is kept."

>[!CONTEXTUALHELP]
>id="dc_orchestration_query_enrichment_noneditable"
>title="Activity non editable"
>abstract="When a **Query** or an **Enrichment** activity is configured with additional data in the console, the enrichment data is taken into account and passed into the outbound transition, but it cannot be edited."

<!-- Create a link --> 

>[!CONTEXTUALHELP]
>id="dc_federated_database_create_link"
>title="Create a link"
>abstract="Define the link settings."


<!-- incremental query IDs -->

>[!CONTEXTUALHELP]
>id="dc_orchestration_incrementalquery"
>title="Incremental query"
>abstract="The **Incremental query** activity allows you to query the database using the Query modeler. Each time this activity is executed, the results from the previous executions are excluded. This allows you to target only new elements."

>[!CONTEXTUALHELP]
>id="dc_orchestration_incrementalquery_history"
>title="Incremental query history"
>abstract="Incremental query history"

>[!CONTEXTUALHELP]
>id="dc_orchestration_incrementalquery_processeddata"
>title="Incremental query Processed data"
>abstract="Incremental query Processed data"

>[!CONTEXTUALHELP]
>id="dc_orchestration_incrementalmode_standard"
>title="Incremental query mode"
>abstract="The incremental query allows you to execute the same query several times by excluding the results of previous executions for each new execution."

>[!CONTEXTUALHELP]
>id="dc_orchestration_incrementalmode_custom"
>title="Incremental query mode"
>abstract="The incremental query allows you to execute the same query several times by only taking into account the results where the date field is later than or equal to the last execution date of the incremental query activity."

>[!CONTEXTUALHELP]
>id="dc_orchestration_build_audience_dimension"
>title="Select the targeting dimension"
>abstract="The targeting dimension lets you define the population targeted by the operation: recipients, contract beneficiaries, operator, subscribers, etc. By default, for emails and SMS, the target is selected from the Recipients built-in table. For Push notifications, the default target dimension is Subscriber applications."

