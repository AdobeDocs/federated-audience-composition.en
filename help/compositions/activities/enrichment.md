---
audience: end-user
title: Use the Enrichment activity
description: Learn how to use the Enrichment activity
---

# Enrichment {#enrichment}
 
>[!CONTEXTUALHELP]
>id="dc_orchestration_enrichment"
>title="Enrichment activity"
>abstract="The **Enrichment** activity allows you to enhance the targeted data with additional information from the database. It is commonly used in a composition after segmentation activities."

>[!CONTEXTUALHELP]
>id="dc_orchestration_enrichment_data"
>title="Enrichment activity"
>abstract="Once enrichment data has been added to the composition, it can be used in the activities added after the **Enrichment** activity to segment profiles into distinct groups based on their behaviors, preferences, and choices."

>[!CONTEXTUALHELP]
>id="dc_orchestration_enrichment_simplejoin"
>title="Link definition"
>abstract="Create a link between the working table data and the federated database."

>[!CONTEXTUALHELP]
>id="dc_orchestration_enrichment_reconciliation"
>title="Enrichment reconciliation"
>abstract="Set the reconciliation parameters."

>[!CONTEXTUALHELP]
>id="dc_targetdata_personalization_enrichmentdata"
>title="Enrichment data"
>abstract="Select the data to use to enrich your composition. You can select two types of enrichment data: a single enrichment attribute from the schema, also known as targeting dimension, or a collection link, which is a link with a 1-N cardinality between tables."

The **Enrichment** activity allows you to enhance the targeted data with additional information from the federated database. It is commonly used in a compositions after segmentation activities.

Enrichment data can come either:

* **From the same work table** as the one targeted into your composition:

    *Target a group of customers and add the "Birth date" field to the current work table*.

* **From another work table**:

    *Target a group of customers and add the "Amount" and "Type of product" fields coming from the "Purchase" table*.

Once the enrichment data has been added to the composition, it can be used in the activities added after the **Enrichment** activity to segment customers into distinct groups based on their behaviors, preferences, and choices.

<!--For instance, you can add to the working table information related to customers' purchases and use this data to personalize emails with their latest purchase or the amount spent on these purchases.-->

## Configure the Enrichment activity {#enrichment-configuration}

Follow these steps to configure the **Enrichment** activity:

1. Add activities such as **Build audience** and **Combine** activities.
1. Add an **Enrichment** activity.

    ![](../assets/enrichment.png)

1. If multiple transitions have been configured in your composition, you can use the **[!UICONTROL Primary set]** field to define which transition should be used as primary set to enrich with data.

1. Click **Add enrichment data** and select the attribute to use to enrich the data.

    ![](../assets/enrichment-add.png)

    >[!NOTE]
    >
    >The **Edit expression button** in the attribute selection screen allows you to build advanced expressions to select the attribute.

<!--PAS VU SUR INSTANCE: You can select two types of enrichment data: a single enrichment attribute from the target dimension, or a collection link. Each of these types is detailed in the examples below:

    * [Single enrichment attribute](#single-attribute)
    * [Collection lnk](#collection-link)-->

## Examples {#example}

### Single enrichment attribute {#single-attribute}

Here, we are just adding a single enrichment attribute, for example, the date of birth. Follow these steps:

1. Click inside the **Attribute** field.
1. Select a simple field from the schema, also known as targeting dimension, the date of birth in our example. 
1. Click **Confirm**.

<!--### Collection link {#collection-link}

In this more complex use case, we will select a collection link which is a link with a 1-N cardinality between tables. Let's retrieve the three latest purchases that are less than 100$. For this you need to define:

* an enrichment attribute: the **Total amount** field
* the number of lines to retrieve: 3
* a filter: filter out items that are greater than 100$
* a sorting: descendant sorting on the **Order date** field. 

#### Add the attribute {#add-attribute}

This is where you select the collection link to use as enrichment data.

1. Click inside the **Attribute** field.
1. Click **Display advanced attributes**.
1. Select the **Total amount** field from the **Purchases** table. 

#### Define the collection settings{#collection-settings}

Then, define how the data is collected and the number of records to retrieve.

1. Select **Collect data** in the **Select how the data is collected** drop-down.
1. Type "3" in the **Lines to retrieve (Columns to create)** field. 

If you want, for example, to get the average amount of purchases for a customer, select **Aggregated data** instead, and select **Average** in the **Aggregate function** drop-down.

#### Define the filters{#collection-filters}

Here, we define the maximum value for the enrichment attribute. We filter out items that are greater than 100$. [Learn how to work with the query modeler](../../query/query-modeler-overview.md)

1. Click **Edit filters**.
1. Add the two following filters: **Total amount** exists AND **Total amount** is less than 100. The first one filters NULL values as they would appear as the greatest value.
1. Click **Confirm**.

#### Define the sorting{#collection-sorting}

We now need to apply sorting in order to retrieve the three **latest** purchases.

1. Activate the **Enable sorting** option.
1. Click inside the **Attribute** field.
1. Select the **Order date** field.
1. Click **Confirm**. 
1. Select **Descending** from the **Sort** drop-down.-->
