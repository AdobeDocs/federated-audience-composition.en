---
audience: end-user
title: Get started with schemas
description: Learn how to start with schemas
badge: label="Limited availability" type="Informative"
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

By creating a schema, you will have the possibility to manipulate a representation of your table in FAC : 

- Give it a friendly name and description to simplify the comprehension for the user
- Decide the visibility of each fields, according to their real use 
- Select its primary key, in order to link schemas between them, as needed in the [data model](../data-management/gs-models.md#data-model-start)

## Create a schema {#schema-create}

To create schemas in FAC, follow the steps below :
In **[!UICONTROL FEDERATED DATA]** section, go in the **[!UICONTROL Models]** link. You will find there the **[!UICONTROL Schema]** tab.
Click on **[!UICONTROL Create schema]** button.

![](assets/schema_create.png){zoomable="yes"}

You will have access to a new interface with a drop-down list where you will find 
all the databases connected to your application. Learn more on [database connection](../connections/connections.md#connections-fdb).
Select your source database in the list and click on **[!UICONTROL Add tables]** tab

![](assets/schema_tables.png){zoomable="yes"}

You will have access to the list of all the tables in the database.

By adding the tables, for which you want to create the schema, you will have access to their fields as below.

![](assets/schema_fields.png){zoomable="yes"}

For each table, you can :

- rename the schema label given
- add a description
- rename all the fields, and decide their visibility.
- select the schema primary key

For example, here is a table imported, just after the add : 

![](assets/schema_lumaorder.png){zoomable="yes"}

The schema can be defined like this : 

![](assets/schema_lumaorders.png){zoomable="yes"}

## Edit a schema {#schema-edit}

To edit a schema, click on the name of your schema in the schemas folder. You will have access to the page below.
Click on **[!UICONTROL Edit]** button.

![](assets/schema_edit.png){zoomable="yes"}

You will have access to the same possibility as when creating the schema :

- rename the schema label given
- add a description
- rename all the fields, and decide their visibility.
- select the schema primary key

![](assets/schema_edit_orders.png){zoomable="yes"}

## Preview data in a schema {#schema-preview}

To preview the data in the table represented by your schema, go to the **[!UICONTROL Data]** tab as below.
You can have the total number of recordings by clicking on the **[!UICONTROL Calculate]** link.

![](assets/schema_data.png){zoomable="yes"}

You can change the Data overview by clicking on the **[!UICONTROL Configure columns]** button.

![](assets/schema_columns.png){zoomable="yes"}

## Delete a schema {#schema-delete}

To delete a schema, click on **[!UICONTROL More]** button, then **[!UICONTROL Delete]**.

![](assets/schema_delete.png){zoomable="yes"}
