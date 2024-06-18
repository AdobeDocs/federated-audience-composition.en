---
audience: end-user
title: Use the AND-join activity
description: Learn how to use the AND-join activity
---
# AND-join {#join}

>[!CONTEXTUALHELP]
>id="dc_orchestration_and-join"
>title="AND-join activity"
>abstract="The **And-join** activity allows you to synchronize multiple execution branches of a composition. It is triggered once all of the preceding activities have finished. This allows you to make sure that certain activities are finished before continuing to execute the composition."

The **And-join** activity allows you to synchronize multiple execution branches of a composition.

This activity only triggers its outbound transition once all the inbound transitions are activated, in other words, once all of the preceding activities have finished. This allows you to make sure that certain activities have finished before continuing to execute the composition.

## Configure the And-join activity {#and-join-configuration}

>[!CONTEXTUALHELP]
>id="dc_orchestration_and-join_merging"
>title="Configure the AND-join activity"
>abstract="Select which activities you want to join. In the **Primary set** drop-down, choose which inbound transition population you want to keep."

Follow these steps to configure the **AND-join** activity:

1. Add multiple activities such as channel activities to form at least two different execution branches.
1. Add an **AND-join** activity to any of the branches.
1. In the **Merging options** section, check all the previous activities you wish you join. 
1. In the **Primary set** drop-down, choose which inbound transition population you want to keep. The outbound transition can only contain one of the inbound transition populations.

