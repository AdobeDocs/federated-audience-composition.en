---
audience: end-user
title: Activities overview
description: Learn about the different activities and transitions available for use within Federated Audience Composition.
---
# Activities overview

In Federated Audience Composition, you can add activities and transitions that help define your audience. 

## Activities {#activities}

Activities let you define the components within the audience.

There are **two** different types of activities for use within Federated Audience Composition: targeting activities and flow control activities.

### Targeting activities {#targeting}

Targeting activities let you define what makes up your audience for the composition.

#### Build audience

>[!CONTEXTUALHELP]
>id="dc_orchestration_build_audience_audienceselector"
>title="Audience"
>abstract="Select your audience."

The **Build audience** activity lets you define your target population for the composition. You can either select an existing audience or use the query modeler to define your own query.

+++ Configuration details

After adding the **Build audience** activity to the composition canvas, give your audience a name. You can now specify if you want to create an audience or use an existing one.

>[!BEGINTABS]

>[!TAB Create new audience]

After selecting **Create audience**, choose the **Schema** for your audience. The schema lets you define the population targeted by the operation, such as recipients, contract beneficiaries, operators, or subscribers. By default, the schema is selected from the recipients.

![](../assets/build-audience-create.png)

After choosing a schema, select **Continue**. You can now define your audience's definition within the Query Modeler. For more information on using the Query Modeler, read the [Query Modeler overview](../query/query-modeler-overview.md).

>[!TAB Use existing audience]

After selecting **Read audience**, choose **Continue**. 

![](../assets/build-audience-read.png)

You can now select which audience you want to use for your composition.

>[!ENDTABS]

After you've selected your options, you can choose to **Generate an outbound transition**. Selecting this lets you add an outbound transition that will be activated at the end of the execution of the activity if the audience population is empty. 

+++

#### Change data source

The **Change data source** activity lets you change which data source is being used by your composition.

+++ Configuration details

After adding the **Change data source** activity to your composition canvas, you can define the data source that will be used for the composition.

![The data source option is highlighted within the Federated Audience Composition workspace.](/help/compositions/assets/change-data-source/configure.png){zoomable="yes"}{width="70%"}

| Source | Description |
| ------ | ----------- |
| FDA external account | An external cloud database connected to Federated Audience Composition. |

After selecting **[!UICONTROL FDA external account]**, you can choose which external account you want to connect with.

![The popover displaying the external account options is displayed.](/help/compositions/assets/change-data-source/fda-external-account.png){zoomable="yes"}{width="70%"}

+++

#### Change dimension

>[!CONTEXTUALHELP]
>id="dc_orchestration_dimension_complement"
>title="Generate a complement"
>abstract="You can generate an additional outbound transition with the remaining population, which was excluded as a duplicate. To do this, toggle on the **[!UICONTROL Generate complement]** option"

>[!CONTEXTUALHELP]
>id="dc_orchestration_change_dimension"
>title="Change dimension activity"
>abstract="This activity allows you to change the schema, also known as targeting dimension, as you are building an audience. It shifts the axis depending on the data template and the input schema. For example, you can switch from the "contracts" schema to the "clients" schema."

The **Change dimension** activity lets you change the schema (also known as the targeting dimension) of your composition.

+++ Configuration details

After adding the **Change dimension** activity to your composition canvas, you can define a new schema to replace the previous schema. During this schema change, all records will be kept. 

![](../assets/change-dimension.png)

After you execute the composition, your results will be updated.

+++

#### Combine

>[!CONTEXTUALHELP]
>id="dc_orchestration_combine"
>title="Combine activity"
>abstract="The **Combine** activity allows you to perform segmentation on your inbound population. You can thus combine several populations, exclude part of it, or only keep data common to several targets."

>[!CONTEXTUALHELP]
>id="dc_orchestration_intersection_merging_options"
>title="Intersection merging options"
>abstract="The **intersection** allows you to keep only the elements common to the different inbound populations in the activity. In the **Sets to join** section, check all the previous activities you want you join."

>[!CONTEXTUALHELP]
>id="dc_orchestration_exclusion_merging_options"
>title="Exclusion merging options"
>abstract="The **exclusion** allows you to exclude elements from one population according to certain criteria. In the **Sets to join** section, check all the previous activities you want you join."

>[!CONTEXTUALHELP]
>id="dc_orchestration_combine_options"
>title="Select the segmentation type"
>abstract="Select how to combine audiences: union, intersection or exclusion."

The **Combine** activity lets you join multiple audiences in various ways - a union, intersection, or exclusion.



#### Deduplication

#### Enrichment

#### Reconciliation

#### Save audience

#### Split

### Flow control activities {#flow-control}

Flow control activities let you define the organization and coordination of your composition.

#### And join

#### End

#### Fork

#### Scheduler

#### Wait

## Transitions {#transitions}

