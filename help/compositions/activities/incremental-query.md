---
audience: end-user
title: Use the Incremental query activity
description: Learn how to use the Incremental query activity
---
# Incremental query {#incremental-query}

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

The **Incremental query** activity allows you to query the database on a scheduled basis. Each time this activity is executed, the results from the previous executions are excluded. This allows you to target only new elements.

The **[!UICONTROL Incremental query]** activity can be used for various types of uses:

* Segmenting individuals to define the target of a message, audience, etc.
* Exporting data. For example, you can use the activity to regularly export new logs in files. It can be useful if you want to use your log data in external reporting or BI tools.

The population already targeted by previous executions is stored in the composition. This means that two compositions started from the same template do not share the same log. However, two tasks based on the same incremental query in the same composition use the same log.

If the result of an incremental query is equal to 0 during one of its executions, the composition is paused until the query's next programmed execution. The transitions and activities that follow the incremental query are therefore not processed before the following execution.

## Configure the Incremental query activity {#incremental-query-configuration} 

Follow these steps to configure the **Incremental query** activity:

![](../assets/incremental-query.png)

1. Add an **Incremental query** activity into your composition.

1. In the **[!UICONTROL Audience]** section, choose the **Targeting dimension** then click **[!UICONTROL Continue]**.

    The targeting dimension lets you define the population targeted by the operation: recipients, contract beneficiaries, operator, subscribers, etc. By default, the target is selected from the recipients. <!--[Learn more about targeting dimensions](../../audience/about-recipients.md#targeting-dimensions)-->

1. Use the query modeler to define your query, the same way you create an audience when designing a new email. <!--[Learn how to work with the query modeler](../../query/query-modeler-overview.md)-->

1. In the **[!UICONTROL Processed data]** section, select the incremental mode to use:

    * **[!UICONTROL Exclude results of previous execution]**: Each time the activity is executed, the results of the previous executions are excluded. 

        Records already targeted in previous executions can be logged a maximum number of days from the day they were targeted. To do this, use the **[!UICONTROL History in days]** field. If this value is zero, the recipients are never purged from the log.

    * **[!UICONTROL Use a date field]**: This option allows you to exclude results from previous executions based on a specific date field. To do this, choose the desired date field from the list of attributes available for the selected targeting dimension. On the next executions of the composition, only data that has been modified or created after the last execution date will be retrieved.

        After the first execution of the composition, the **[!UICONTROL Last execution date]** field becomes available. It specifies the date that will be used for the next execution, and is automatically updated every time the composition is executed. You still have the possibility to override this value by manually entering a new one so that it fits your needs.

    >[!NOTE]
    >
    >The **[!UICONTROL Use a date field]** mode allows more flexibility depending on the date field that is selected. For example, if the specified field corresponds to a modification date, the date field mode will allow you to retrieve data that were recently updated, while the other mode will simply exclude recordings that were already targeted in a previous execution, even if they have been modified since the last execution of the workflow.

<!-->
## Example {#incremental-query-example}

The following example shows the configuration of a workflow which filters every week the profiles in the Adobe Campaign database that are subscribed to the Yoga Newsletter service, to send them a welcome email.

![](../assets/incremental-query-example.png)

The workflow is made up of the following elements:

* A **[!UICONTROL Scheduler]** activity, to execute the workflow every Monday at 6 am.
* An **[!UICONTROL Incremental query]** activity, which targets all of the current subscribers during the first execution, then only the new subscribers of that week during the following executions.
* An **[!UICONTROL Email delivery]** activity.
-->
