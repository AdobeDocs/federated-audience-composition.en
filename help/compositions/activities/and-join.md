---
audience: end-user
title: Use the AND-join activity
description: Learn how to use the AND-join activity
exl-id: 9648f17b-e54c-4bc2-8dff-d35c438eeb8b
---
# AND-join {#join}

The **AND-join** activity allows you to synchronize multiple execution branches of a composition.

This activity only triggers its outbound transition once all the inbound transitions are activated, in other words, once all of the preceding activities have finished. This allows you to make sure that certain activities have finished before continuing to execute the composition.

## Configure the And-join activity {#and-join-configuration}

>[!CONTEXTUALHELP]
>id="dc_orchestration_and-join_merging"
>title="Configure the AND-join activity"
>abstract="Select which activities you want to join. In the **[!UICONTROL Primary set]** drop-down, choose which inbound transition population you want to keep."

Follow these steps to configure the **AND-join** activity:

1. Add multiple activities to form at least two different execution branches.
1. Add an **AND-join** activity to any of the branches.

    ![](../assets/and-join.png)

1. In the **[!UICONTROL Merging options]** section, check all the previous activities you wish to synchronize.
1. In the **[!UICONTROL Primary set]** drop-down, choose which inbound transition population you want to keep. The outbound transition can only contain one of the inbound transition populations. If the activity is not configured, the outbound transition will randomly select one of the inbound populations.
