---
title: What's new in Experience Platform Federated Audience Composition
description: Latest updates and release notes
exl-id: d4dcaf31-93cd-4a4e-888a-cf1bbdc4ca03
---
# Release Notes {#rn-new}

[!DNL Federated Audience Composition] continuously delivers new features, enhancements to existing features, and bug fixes. All changes are consolidated in these release notes. [!DNL Federated Audience Composition] is built natively on [!DNL Adobe Experience Platform] and inherits from its latest innovations and improvements. Learn more about these changes in [Adobe Experience Platform Release Notes](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html){target="_blank"}.

## May '25 release {#fac-25-5}

### New capabilities {#fac-25-05-feature}

<table>
<thead>
<tr>
<th><strong>Data model canvas view - General Availability</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Data model with Canvas view is now available for all customers!</p>
<p>The Canvas view for the Data Models section improves the experience by enabling the visualization of data models and their links in a canvas layout, alongside the existing tabular view. </p>
<p>For more information about canvas view, please read the <a href="../data-management/gs-models.md">data models overview</a>.</p>
</br>
</td>
</tr>
</tbody>
</table>

### Improvements {#fac-25-5-improvements}

This release comes with the following improvements.

* **Federated Audience Composition permissions**

    Starting with the May release, [!DNL Federated Audience Composition] will start enforcing the access of **Federated data management** and **Federated Compositions** interfaces to users with a more granular set of permissions.

    Please contact your administrators to add the required permissions to continue accessing the [!DNL Federated Audience Composition] user interface.

    To learn more about the new permissions, please read the [Federated Audience Composition access guide](feature-access.md).

## April '25 release {#fac-25-4}

### New capabilities {#fac-25-04-feature}

<table>
<thead>
<tr>
<th><strong>Data model canvas view - Beta</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The Canvas view for the Data Models section improves the experience by enabling the visualization of data models and their links in a canvas layout, alongside the existing tabular view. </p>
<p>Data model with Canvas view is currently available as a beta to select users only.</p>
<p>For more information, refer to the <a href="../data-management/gs-models.md">detailed documentation</a>.</p>
</br>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>AI Assistant support for Product Knowledge</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>AI Assistant is a user interface feature designed to help you navigate and understand Adobe concepts and get operational insights for your specific environment. It is available in several products across Adobe Experience Cloud, including Federated Audience Composition.</p>
<p>For more information, refer to the <a href="../start/ai-assistant.md">detailed documentation</a>.</p>
</br>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Save Profiles activity</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p> Federated Audience Composition now supports the profile enrichment use case, allowing customers to enhance existing Experience Platform profiles with data from their external data warehouses.
</p>
<p>For more information, refer to the <a href="../compositions/activities/save-profiles.md">detailed documentation</a>.</p>
</br>
</td>
</tr>
</tbody>
</table>

### Improvements {#fac-25-4-improvements}

This release comes with the improvements below.

* **Data Model Name**

    From the Audiences menu, the **Federated compositions** tab now displays the Data Model name instead of the ID, improving clarity and overall usability.

* **Audience**

    The Audience menu now displays the name or label of the selected data model when a user selects a data model with no associated audiences.

* **Large audiences export**

    Federated Audience Composition now supports the export of large audiences, with file sizes greater than 1 GB.

* **Save audience activity**
    
    A note has been added to the **Save Audience** activity, reminding users to collaborate with a data administrator to apply governance labels to new schemas and datasets created during audience creation and enrichment.
    [Learn more about data usage labels](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/user-guide)

### Compatibility {#fac-25-4-compat}

* **Amazon Redshift secure connection**
    
    With this new release, Federated Audience Composition supports secure private link connections to Amazon Redshift databases. [Learn more](../connections/federated-db.md#amazon-redshift)

* **Google Big Query**

    With this new release, Federated Audience Composition supports secure VPN connections to Google Big Query Databases. [Learn more](../connections/federated-db.md#google-big-query)

## March '25 release {#fac-25-3}

### Improvements {#fac-25-3-improvements}

This release comes with the improvements below.

* **Federated Audience Composition permissions**

    Starting March release, [!DNL Federated Audience Composition] will start enforcing the access of **Federated data management** and **Federated Compositions** interfaces to user who have been granted the **Manage Federated Data** permission. 

    We recommend users to contact the administrators to have this permission added to their role in order to continue accessing the [!DNL Federated Audience Composition] user interface.

    To learn how to assign this permission, refer to the [detailed documentation](feature-access.md).

<!--
* **Data model Canvas view**

    The Canvas view for the Data Models section improves the experience by enabling the visualization of data models and their links in a canvas layout, alongside the existing tabular view. [Learn more](../data-management/gs-models.md)

* **AI Assistant**

    AI Assistant is a user interface feature designed to help you navigate and understand Adobe concepts and get operational insights for your specific environment. It is available in several products across Adobe Experience Cloud, including Federated Audience Composition. 
-->


### Compatibility {#fac-25-3-compat}

* **Databricks connection**

    With this new release, Federated Audience Composition now supports private link connectivity for Databricks database connections. 
    This includes secure connections to Databricks databases hosted on Amazon Web Services (AWS) via private link and Databricks databases hosted on Microsoft Azure via VPN. [Learn more](../connections/federated-db.md#databricks)

* **Support for B2B CDP Customers**

    Federated Audience Composition is now available to Business-to-Business (B2B) Customer Data Platform (CDP) customers for people-based audience use cases.

* **Snowflake secure connection**
    
    With this new release, Federated Audience Composition supports secure private link connections to Snowflake databases hosted on Microsoft Azure. [Learn more](../connections/federated-db.md#snowflake)

## February '25 release {#fac-25-2}

This release comes with the changes listed below.

* **Microsoft Fabric support**

    You can now establish connections to Microsoft Fabric databases through Federated Audience Composition. [Learn more](../connections/federated-db.md)

* **Amazon Redshift Spectrum support**

    Amazon Redshift Spectrum is now supported for Amazon Redshift Database connections. [Learn more](../connections/federated-db.md#amazon-redshift)

* **Enhanced Schema Creation Experience**

    The process of creating schemas has been improved through an updated user interface, designed to be more intuitive and easier to navigate. These enhancements offer data practitioners a smoother and more efficient way to develop data models. [Learn more](../customer/schemas.md)

* **Audience Enrichment Support for Databricks**

    You can now use Databricks in the Read Audience flow, enabling activity for Databricks databases and allowing it to be set up as a new destination. [Learn more](../connections/destinations.md)

## November '24 release {#fac-24-11}

### Improvements {#fac-24-11-improvements}

This release comes with the improvement below.

* **IP address allow list**

    When adding a federated database in the Adobe Experience Platform user interface, you can now directly view the IP addresses associated with your Federated Audience Composition instances. This enables you to easily copy and authorize these IPs to connect to your database for improved security and flexibility. [Learn more](../connections/connections.md)

## October '24 release {#fac-24-10}

>[!AVAILABILITY]
>
>Previously available for a set of organizations (LA), Adobe Experience Platform Federated Audience Composition is now available to all users (GA). This capability is activated based on your offering, and only visible with the associated permissions. [Learn more](access-prerequisites.md)
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

Federated Audience Composition equips businesses with flexible and expanded access to enterprise data warehouses to compose audiences using critical enterprise datasets and power brand-initiated and in-the-moment experiences. With this new approach, as an [Adobe Real-Time Customer Data Platform](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/home){target="_blank"} and/or [Adobe Journey Optimizer](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} user, you can federate audience data directly from your existing data warehouse to enrich Adobe Experience Platform audiences in one system.

Federated Audience Composition addresses growing market demands for enterprises who need the flexibility to compose audiences with warehouse datasets. This allows businesses to reduce data movement while making critical audience data available to marketing teams to meet use case requirements and power personalized experiences. 

Learn more about Federated Audience Composition capabilities on [this page](get-started.md) and in the [Frequently Asked Questions](faq.md).

Detailed information on the prerequisites to access Federated Audience Compositions and the current guardrails, refer to the [this page](access-prerequisites.md).
