---
audience: end-user
title: Get started with schemas
description: Learn how to start with schemas
badge: label="Limited availability" type="Informative"
exl-id: 2c939185-f1c1-4f2b-ae1b-e2539e121eff
---
# Get started with schemas {#schemas}


>[!CONTEXTUALHELP]
>id="dc_schema_create_select_tables"
>title="Select tables"
>abstract="Select the tables to add for the data model."

>[!CONTEXTUALHELP]
>id="dc_schema_create_key"
>title="Key"
>abstract="Select a key for data reconciliation."

>[!CONTEXTUALHELP]
>id="dc_schema_create_schema_name"
>title="Name of the schema"
>abstract="Enter the name of the schema."


>[!CONTEXTUALHELP]
>id="dc_schema_edit_description"
>title="Schema description"
>abstract="The schema description lists columns, types and labels. You can also check the reconciliation key for the schema. To update the schema definition, click the pencil icon."

>[!CONTEXTUALHELP]
>id="dc_schema_filter_sources"
>title="Select the source database to filter"
>abstract="You can filter the schemas based on their source. Select one or several Federated Databases to displays their schemas."


## What is a schema? {#schema-start}

A schema is a representation of a table of your database. It is an object within the application that defines how the data are tied to database tables. 

By creating a schema, you can define a representation of your table in Experience Platform Federated Audience Composition: 

* Give it a friendly name and description to simplify the comprehension for the user
* Decide the visibility of each field, according to their real use 
* Select its primary key, in order to link schemas between them, as needed in the [data model](../data-management/gs-models.md#data-model-start)

## Create a schema {#schema-create}

To create schemas in Federated Audience Composition, follow the steps below:

1. In **[!UICONTROL FEDERATED DATA]** section, go in the **[!UICONTROL Models]** link. Browse to the **[!UICONTROL Schema]** tab and click on the **[!UICONTROL Create schema]** button.

    ![](assets/schema_create.png){zoomable="yes"}

    This step lets you access to a new screen with a drop-down list where you can find the database(s) connected to your environment. Learn more about database connection in [this section](../connections/connections.md#connections-fdb).

1. Select your source database in the list, and click on the **[!UICONTROL Add tables]** tab.

    ![](assets/schema_tables.png){zoomable="yes"}

    You can then see the list of all the tables in the database.

1. By adding the tables, for which you want to create the schema, you have access to their fields as below:

    ![](assets/schema_fields.png){zoomable="yes"}

    For each table, you can:

    * change the label of the schema
    * add a description
    * rename all the fields, and set their visibility
    * select the schema primary key

    For example, for the following table imported:

    ![](assets/schema_lumaorder.png){zoomable="yes"}

    The schema can be defined like this: 

    ![](assets/schema_lumaorders.png){zoomable="yes"}

## Edit a schema {#schema-edit}

To edit a schema:

1. Click on the name of your schema in the schemas folder. 

1. Click on **[!UICONTROL Edit]** button.

    ![](assets/schema_edit.png){zoomable="yes"}

    You can access the same options as when [creating a schema](#schema-create).

    ![](assets/schema_edit_orders.png){zoomable="yes"}

## Preview data in a schema {#schema-preview}

To preview the data in the table represented by your schema, browse to the **[!UICONTROL Data]** tab as below.

Click on the **[!UICONTROL Calculate]** link to preview the total number of recordings.

![](assets/schema_data.png){zoomable="yes"}

Click on the **[!UICONTROL Configure columns]** button to change the data display.

![](assets/schema_columns.png){zoomable="yes"}

## Delete a schema {#schema-delete}

To delete a schema, click on **[!UICONTROL More]** button, then choose **[!UICONTROL Delete]**.

![](assets/schema_delete.png){zoomable="yes"}
