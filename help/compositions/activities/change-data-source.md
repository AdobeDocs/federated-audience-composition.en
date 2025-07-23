---
audience: end-user
title: Change Data Source activity
description: Learn how you can use the change data source activity to change the data source used by your composition, providing more flexibility in managing your data in a composition.
exl-id: 8f8e627a-fef9-42b8-a42a-bfa1c421b202
---
# Change data source

>[!IMPORTANT]
>
>The **[!UICONTROL Change dimension]** and **[!UICONTROL Change data source]** activities should **not** be added in one row. If you need to use both activities consecutively, include an **[!UICONTROL Enrichment]** activity in between them. This ensures proper execution and prevents potential conflicts or errors.

The **[!UICONTROL Change data source]** activity lets you change the data source used by your composition.

## Configure {#configure}

After adding a **[!UICONTROL Change data source]** activity to the canvas, you can define the data source for the workflow.

![The data source option is highlighted within the Federated Audience Composition workspace.](/help/compositions/assets/change-data-source/configure.png){zoomable="yes"}{width="70%"}{align="center"}

| Source | Description |
| ------ | ----------- |
| FDA external account | An external cloud database connected to Adobe Campaign through Federated Audience Composition. |

After selecting **[!UICONTROL FDA external account]**, you can choose which external account you want to connect with.

![The popover displaying the external account options is displayed.](/help/compositions/assets/change-data-source/fda-external-account.png){zoomable="yes"}{width="70%"}{align="center"}
