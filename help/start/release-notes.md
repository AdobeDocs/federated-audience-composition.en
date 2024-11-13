---
title: What's new in Experience Platform Federated Audience Composition
description: Latest updates and release notes
exl-id: d4dcaf31-93cd-4a4e-888a-cf1bbdc4ca03
---
# Release Notes {#rn-new}

[!DNL Federated Audience Composition] continuously delivers new features, enhancements to existing features, and bug fixes. All changes are consolidated in these release notes. [!DNL Federated Audience Composition] is built natively on [!DNL Adobe Experience Platform] and inherits from its latest innovations and improvements. Learn more about these changes in [Adobe Experience Platform Release Notes](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html){target="_blank"}.

## October '24 release {#fac-24-10}

>[!AVAILABILITY]
>
>Previously available for a set of organizations (LA), Adobe Experience Platform Federated Audience Composition is now available to all users (GA). This add-on is activated based on your offering, and only visible with the associated permissions. [Learn more](access-prerequisites.md)
>

### Compatibility {#fac-24-10-compat}

With this new release, Federated Audience Composition is now compatible with the systems listed below.

* **Databricks support**

    You can now establish connections to Databricks databases through Federated Audience Composition. [Learn more](../connections/federated-db.md#databricks)

* **Support for secure access to Snowflake through AWS PrivateLink**
    
    Secure access to your external Snowflake data warehouse through private link is now supported. Note that your Snowflake account must be hosted on Amazon Web Services (AWS) and located in the same region as your Federated Audience Composition environment. Please contact your Adobe representative for assistance in setting up secure access to your Snowflake account. [Learn more](../connections/federated-db.md#snowflake)

* **Amazon Redshift Serverless support**

    With this new release, Federated Audience Composition supports [Amazon Redshift Serverless](https://aws.amazon.com/redshift/redshift-serverless/){target="_blank"}.

### Improvements {#fac-24-10-improvements}

This release comes with the improvements listed below.

* **Refresh existing schemas**

    When a column is created, modified or deleted in a federated database, you can now detect and apply the changes by clicking on the **[!UICONTROL Refresh schema]** button in the corresponding schema. [Learn more](../customer/schemas.md#schema-refresh)

* **Associate a data model with a new composition**

    When creating a composition, you can now select the data model to associate to it. With this new option, the configuration of your activities is easier as only tables of the associated data model are available. [Learn more](../compositions/create-composition.md)

## July '24 release - Federated Audience Composition (LA) {#fac-la}

Federated Audience Composition is an add-on capability that equips businesses with flexible and expanded access to enterprise data warehouses to compose audiences using critical enterprise datasets and power brand-initiated and in-the-moment experiences. With this new approach, as an [Adobe Real-Time Customer Data Platform](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/home){target="_blank"} and/or [Adobe Journey Optimizer](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} user, you can federate audience data directly from your existing data warehouse to enrich Adobe Experience Platform audiences in one system.

Federated Audience Composition addresses growing market demands for enterprises who need the flexibility to compose audiences with warehouse datasets. This allows businesses to reduce data movement while making critical audience data available to marketing teams to meet use case requirements and power personalized experiences. 

Learn more about Federated Audience Composition capabilities in [this page](get-started.md) and in the [Frequently Asked Questions](faq.md).

Detailed information on the prerequisites to access Federated Audience Compositions and the current guardrails, refer to the [this page](access-prerequisites.md).

