---
audience: end-user
title: Use the Reconciliation activity
description: Learn how to use the Reconciliation activity
badge: label="Limited availability" type="Informative"
exl-id: 933c3cba-9120-4a93-a668-866fb65ee197
---
# Reconciliation {#reconciliation}
 
>[!CONTEXTUALHELP]
>id="dc_orchestration_reconciliation"
>title="Reconciliation activity"
>abstract="The **Reconciliation** activity allows you to define the link between the data in the database and the data in a work table." 

>[!CONTEXTUALHELP]
>id="dc_orchestration_reconciliation_field"
>title="Reconciliation select field"
>abstract="Reconciliation select field" 

>[!CONTEXTUALHELP]
>id="dc_orchestration_reconciliation_condition"
>title="Reconciliation create condition"
>abstract="Reconciliation create condition" 

>[!CONTEXTUALHELP]
>id="dc_orchestration_reconciliation_complement"
>title="Reconciliation generate complement"
>abstract="Reconciliation generate complement" 

The **Reconciliation** activity allows you to define the link between the data in the database and the data in a work table, for example data loaded from an external system.

<!--For example, the **Reconciliation** activity can be placed after a **Load file** activity to import non-standard data into the database. In this case, the **Reconciliation** activity lets you define the link between the data in the Adobe Campaign database and the data in the work table.-->

It allows you to link unidentified data to existing resources. Reconciliation operation implies that the data you are joining are already in the database. For example, if you want to reconciliate purchases information showing which product was purchased, at what time, by which client, etc., the product as well as the client must already exist in the database.

## Configure the Reconciliation activity {#reconciliation-configuration}

>[!CONTEXTUALHELP]
>id="dc_orchestration_reconciliation_targeting"
>title="Schema"
>abstract="Select the new schema to apply to the data. A schema, also known as targeting dimension, lets you define the targeted population: recipients, app subscribers, operators, subscribers, etc. By default, the composition current schema is selected." 

>[!CONTEXTUALHELP]
>id="dc_orchestration_reconciliation_rules"
>title="Reconciliation rules"
>abstract="Select reconciliation rules to use for the deduplication. To use attributes, select the **Simple attributes** option and choose the source and destination fields. To create your own reconciliation condition using the query modeler, select the **Advanced reconciliation conditions** option."

>[!CONTEXTUALHELP]
>id="dc_orchestration_reconciliation_targeting_selection"
>title="Select the targeting dimension"
>abstract="Select the schema, also known as targeting dimension, for your inbound data to reconcile with." 

>[!CONTEXTUALHELP]
>id="dc_orchestration_keep_unreconciled_data"
>title="Keep unreconciled data"
>abstract="By default, non reconciled data are kept in the outbound transition and available in the worktable for future use. To remove unreconciled data, desactivate the **Keep unreconciled data** option." 

>[!CONTEXTUALHELP]
>id="dc_orchestration_reconciliation_attribute"
>title="Reconciliation attribute"
>abstract="Select the attribute to use to reconciliate data, and confirm." 

Follow these steps to configure the **Reconciliation** activity:

1. Add a **Reconciliation** activity into your composition.

1. Select the **New schema**. A schema, also known as targeting dimension, lets you define the targeted population: recipients, app subscribers, operators, subscribers, etc.

1. Select the field(s) to use for the reconciliation. You can use one or more reconciliation criteria.

    1. To use attributes to reconcile data, select the **Simple attributes** option then click the **Add rule** button.
    1. Select the **Source** and **Destination** fields for the reconciliation. The **Source** field. The **Destination** field corresponds to the fields of the selected schema.
    
        Data are reconcilied when source and destination are equal. For example, select the **Email** fields to deduplicate profiles based on their email address. 
        
        To add another reconciliation criteria, click the **Add rule** button. If several join conditions are specified, they must ALL be verified so that the data can be linked together.    

        ![](../assets/reconciliation-rules.png)

    1. To use other attributes to reconcile data, select the **Advanced reconciliation conditions** option then click the **Create conditions** button. You can then create your own reconciliation condition using the query modeler. [Learn how to work with the query modeler](../../query/query-modeler-overview.md)

        ![](../assets/reconciliation-advanced.png)

1. You can filter data to reconciliate using the **Create filter** button. This lets you create a custom condition using the query modeler.

By default, non reconcilied data are kept in the outbound transition and available in the worktable for future use. To remove unreconciled data, desactivate the **Keep unreconciled data** option.

<!--
## Example {#reconciliation-example}

The following example demonstrates a workflow that creates an audience of profiles directly from an imported file containing new clients. It is made up of the following activities:

The workflow is designed as follows:

![](../assets/workflow-reconciliation-sample-1.0.png)

 
It is built with the following activities:

* A [Load file](load-file.md) activity uploads a file containing profiles data that were extracted from an external tool.

    For example:

    ```
    lastname;firstname;email;birthdate;
    JACKMAN;Megan;megan.jackman@testmail.com;07/08/1975;
    PHILLIPS;Edward;phillips@testmail.com;09/03/1986;
    WEAVER;Justin;justin_w@testmail.com;11/15/1990;
    MARTIN;Babe;babeth_martin@testmail.net;11/25/1964;
    REESE;Richard;rreese@testmail.com;02/08/1987;
    ```

* A **Reconciliation** activity which identifies the incoming data as profiles, by using the **email** and **Date of birth** fields as reconciliation criteria.

    ![](../assets/workflow-reconciliation-sample-1.1.png)

* A [Save audience](save-audience.md) activity to create a new audience based on these updates. You can also replace the **Save audience** activity by an **End** activity if no specific audience needs to be created or updated. Recipient profiles are updated in any case when you run the workflow.


## Compatibility {#reconciliation-compat}

The **Reconciliation** activity does not exist in the Client console. All **Enrichments** activities created in the Client console with the reconciliation options enabled are displayed as **Reconciliation** activities in Campaign Web user interface.
-->
