---
audience: end-user
title: Schemas overview
description: Learn how to create and use schemas for Federated Audience Composition within the Adobe Experience Platform UI.
TQID: https://experienceleague.adobe.com/cpkFeiskYDpixNo01llqC3UKK8XfewN7XC2yAf1wOYQ
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
    internal-label: Experience Cloud
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Schemas overview {#schemas}

>[!AVAILABILITY]
>
>To access schemas, you'll need one of the following permissions:
>
>-**Manage Federated Schema**
>-**View Federated Schema**
>
>For more information on the required permissions, please read the [access control guide](/help/governance-privacy-security/access-control.md).

A schema is a representation of a table of your database. It is an object within the application that defines how the data are tied to database tables. 

By creating a schema, you can define a representation of your table in Experience Platform Federated Audience Composition: 

* Give it a friendly name and description to simplify the comprehension for the user
* Decide the visibility of each field, according to their real use 
* Select its primary key, in order to link schemas between them, as needed in the [data model](../data-modelling/models.md#data-model-start)

>[!CAUTION]
>
>When connecting multiple sandboxes with same database, you must use distinct working schemas.

## Create a schema {#create}

>[!CONTEXTUALHELP]
>id="platform_schemas_manageconfiguration"
>title="Manage configuration"
>abstract="Temporary blank content."

To create a schema in Federated Audience Composition, select **Schemas** within the **Data Management** section of the Experience Platform UI.

IMAGE

The Schemas UI appears. Select **Create schema**, followed by **Relational**, and **Discover schemas** to create a schema for Federated Audience Composition.

IMAGE

The **[!UICONTROL Select federated database]** popover appears. On this popover, you can select the [source database](/help/connections/home.md), followed by **[!UICONTROL Next]**.

![](assets/schemas/schema_tables.png){zoomable="yes"}

## Define schema {#define}

The **Select Table** popover appears. On this popover, you can select the tables which you want to use to create the schema.

![The Select Table popover is displayed.](assets/schemas/select-table.png){zoomable="yes"}

Each selected table generates a schema with the chosen columns. For each table, you can change the label of the schema, add a description, rename the field label, set the field label visibility, and select the schema primary key.

![](assets/schemas/schema-fields.png){zoomable="yes"}

>[!NOTE]
>
>If you enable **[!UICONTROL Use Composite Key]** but only select one key to be used, the key will be treated like a standard schema primary key.

Additionally, you can create a key that is made up of multiple schema columns. Turn on **[!UICONTROL Use Composite Key]**, and mark the keys you want to use as your composite key.

![](assets/schemas/composite-key.png){zoomable="yes"}

After completing your configuration, select **[!UICONTROL Done]** to finish creating your schema. 

## Edit a schema {#schema-edit}

To edit a schema, select the ICON next to your previously created schema on the **Schemas** page, followed by **Edit**.

IMAGE

On the **[!UICONTROL Edit schema]** window, you can access and configure the same options as when [creating a schema](#schema-create).

![](assets/schemas/schema_edit_orders.png){zoomable="yes"}

## Preview data in a schema {#schema-preview}

To preview the data in the table represented by your schema, browse to the **[!UICONTROL Data]** tab as below.

Select **[!UICONTROL Calculate]** link to preview the total number of recordings.

![](assets/schemas/schema_data.png){zoomable="yes"}

Select the **[!UICONTROL Configure columns]** button to change the data display.

![](assets/schemas/schema_columns.png){zoomable="yes"}

## Refresh a schema {#schema-refresh}

Tables in a federated database can be updated, added or removed. In such cases, you must refresh the schema in Adobe Experience Platform to align with the latest changes. To perform this, select the ![three dots icon](/help/assets/icons/more.png) next to the name of the schema followed by **[!UICONTROL Refresh schema]**. 

You can also update the schema definition when editing it.

![](assets/schemas/schema_refresh.png){zoomable="yes"}

## Delete a schema {#schema-delete}

To delete a schema, select the ![three dots icon](/help/assets/icons/more.png), followed by **[!UICONTROL Delete]**.

![](assets/schemas/schema_delete.png){zoomable="yes"}
