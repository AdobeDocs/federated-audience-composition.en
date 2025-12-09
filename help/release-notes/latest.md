---
title: Federated Audience Composition Release Notes
description: Latest updates and release notes for Federated Audience Composition.
exl-id: d4dcaf31-93cd-4a4e-888a-cf1bbdc4ca03
---
# Release notes {#rn-new}

[!DNL Federated Audience Composition] continuously delivers new features, enhancements to existing features, and bug fixes. All changes are consolidated in these release notes. [!DNL Federated Audience Composition] is built natively on [!DNL Adobe Experience Platform] and inherits from its latest innovations and improvements. Learn more about these changes in [Adobe Experience Platform Release Notes](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html){target="_blank"}.

## October '25 release {#fac-25-10}

### New capabilities {#fac-25-10-feature}

<!-- 
<table>
<thead>
<tr>
<th><strong>Availability for Adobe Experience Platform customers on Amazon Web Services (AWS)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now use Federated Audience Composition if your Experience Platform instance is on AWS.</p>
<p>For more information about Experience Platform on AWS, please read the <a href="https://experienceleague.adobe.com/en/docs/experience-platform/landing/multi-cloud">multi-cloud overview</a>.</p>
</br>
</td>
</tr>
</tbody>
</table> 
-->

<table>
<thead>
<tr>
<th><strong>OAuth authentication for Google BigQuery and Snowflake</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now connect to Google BigQuery and Snowflake using OAuth.</p>
<p>For more information about creating connections, please read the <a href="../connections/home.md#create">connections overview</a>.</p>
</br>
</td>
</tr>
</tbody>
</table>

## August '25 release {#fac-25-8}

### New capabilities {#fac-25-08-feature}

<table>
<thead>
<tr>
<th><strong>Composite key support in schema discovery</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now combine columns together to create a composite key for your schema.</p>
<p>For more information about schemas, please read the <a href="../data-modelling/schemas.md#create">schemas overview</a>.</p>
</br>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Adding multiple joins in a link for models</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now add multiple joins together in a single link for your models.</p>
<p>For more information about models, please read the <a href="../data-modelling/models.md#create">models overview</a>.</p>
</br>
</td>
</tr>
</tbody>
</table>

### Improvements {#fac-25-8-improvements}

This release comes with the following improvements:

* **Added `StringAgg` function**
  
  You can now use the `StringAgg` function for Amazon Redshift Spectrum Databases when. using the expression editor.

* **`Replace` function**
  
  The `Replace` function's description and syntax has been clarified within the documentation.

### Compatibility {#fac-25-8-compatibility}

* **Azure Synapse databases**

    You can now securely connect to Azure Synapse databases with PrivateLink or VPN. Please contact Adobe Customer Care for more information.

* **Oracle database**

    You can now securely connect to Oracle databases. Please contact Adobe Customer Care for more information.

For more information on the supported databases in Federated Audience Composition, please read the [connections overview](../connections/home.md).

## July '25 release {#fac-25-7}

### New capabilities {#fac-25-07-feature}

<table>
<thead>
<tr>
<th><strong>New connector - Oracle</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The Oracle connector is now available for use with Federated Audience Composition.</p>
<p>You can use the Oracle connector for audience creation and audience enrichment use cases.</p>
<p>For more information about the Oracle connection, please read the <a href="../connections/home.md#create">connections overview</a>.</p>
</br>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Composition alerts</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now subscribe to alerts to learn about your composition's successful and failed runs</p>
<p>For more information about subscribing to notifications for your composition's runs, please read the <a href="../compositions/start-monitor-composition.md#alerts">start and monitor your composition guide</a>.</p>
</br>
</td>
</tr>
</tbody>
</table>

### Improvements {#fac-25-07-improvements}

This release comes with the following improvement:

* **Increased server character length**

    When configuring your federated databases, you can now use up to 255 characters, rather than the previous 80 characters.

## June '25 release {#fac-25-6}

### Improvements {#fac-25-06-improvements}

This release comes with the following improvements:

* **General Availability for Adobe Healthcare Shield Customers**

    Federated Audience Composition will be available to Adobe Healthcare Shield customers for audience creation, enrichment and profile enrichment use cases by the end of June.

    More information about privacy and security in Federated Audience Composition can be found in the [Data governance, privacy, and security guide](/help/governance-privacy-security/home.md).

* **Object-level access control**

    Federated Audience Composition now supports object-level access control to apply access labels to your specified compositions.

    More information about using object-level access labels can be found in the [compositions guide](/help/compositions/home.md).

* **Default roles**
  
    You can now use one of the default roles to manage user permissions for Federated Audience Composition access.

    More information about the default roles can be found in the [access Federated Audience Composition guide](/help/governance-privacy-security/access-control.md).

* **Incremental Updates in profile enrichment use cases**

    The Save profiles activity now supports incremental updates. With incremental updates, you can query and update incremental data while enriching profiles with data from external data warehouses.

    More information on using the save profiles activity can be found in the [save profile section of the activities guide](/help/compositions/activities.md#save-profiles).

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
<p>For more information about canvas view, please read the <a href="../data-modelling/models.md">data models overview</a>.</p>
</br>
</td>
</tr>
</tbody>
</table>

### Improvements {#fac-25-5-improvements}

This release comes with the following improvements.

* **Role Based Access Control**

    Starting with the May release, [!DNL Federated Audience Composition] supports new granular permissions for access control. Users can assign these permissions to user roles for more precise access to [!DNL Federated Audience Composition].

    To learn more about the new permissions, please read the [Federated Audience Composition access guide](/help/governance-privacy-security/access-control.md).

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
<p>For more information, refer to the <a href="../data-modelling/models.md">detailed documentation</a>.</p>
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
<p>For more information, refer to the <a href="../compositions/activities.md#save-profiles">detailed documentation</a>.</p>
</br>
</td>
</tr>
</tbody>
</table>

### Improvements {#fac-25-4-improvements}

This release comes with the following improvements:

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
    
    With this new release, Federated Audience Composition supports secure private link connections to Amazon Redshift databases. [Learn more](../connections/home.md#amazon-redshift)

* **Google BigQuery**

    With this new release, Federated Audience Composition supports secure VPN connections to Google BigQuery Databases. [Learn more](../connections/home.md#google-bigquery)

## March '25 release {#fac-25-3}

### Improvements {#fac-25-3-improvements}

This release comes with the following improvements:

* **Federated Audience Composition permissions**

    Starting March release, [!DNL Federated Audience Composition] will start enforcing the access of **Federated data management** and **Federated Compositions** interfaces to user who have been granted the **Manage Federated Data** permission. 

    We recommend users to contact the administrators to have this permission added to their role in order to continue accessing the [!DNL Federated Audience Composition] user interface.

    To learn how to assign this permission, refer to the [detailed documentation](/help/governance-privacy-security/access-control.md).

### Compatibility {#fac-25-3-compat}

* **Databricks connection**

    With this new release, Federated Audience Composition now supports private link connectivity for Databricks database connections. 
    This includes secure connections to Databricks databases hosted on Amazon Web Services (AWS) via private link and Databricks databases hosted on Microsoft Azure via VPN. [Learn more](../connections/home.md#databricks)

* **Support for B2B CDP Customers**

    Federated Audience Composition is now available to Business-to-Business (B2B) Customer Data Platform (CDP) customers for people-based audience use cases.

* **Snowflake secure connection**
    
    With this new release, Federated Audience Composition supports secure private link connections to Snowflake databases hosted on Microsoft Azure. [Learn more](../connections/home.md#snowflake)

## February '25 release {#fac-25-2}

This release comes with the following changes:

* **Microsoft Fabric support**

    You can now establish connections to Microsoft Fabric databases through Federated Audience Composition. [Learn more](../connections/home.md)

* **Amazon Redshift Spectrum support**

    Amazon Redshift Spectrum is now supported for Amazon Redshift Database connections. [Learn more](../connections/home.md#amazon-redshift)

* **Enhanced Schema Creation Experience**

    The process of creating schemas has been improved through an updated user interface, designed to be more intuitive and easier to navigate. These enhancements offer data practitioners a smoother and more efficient way to develop data models. [Learn more](../data-modelling/schemas.md)

* **Audience Enrichment Support for Databricks**

    You can now use Databricks in the Read Audience flow, enabling activity for Databricks databases and allowing it to be set up as a new destination. [Learn more](../connections/destinations.md)
