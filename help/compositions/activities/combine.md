---
audience: end-user
title: Use the Combine activity
description: Learn how to use the Combine activity
badge: label="Limited availability" type="Informative"
---

# Combine {#combine}

>[!CONTEXTUALHELP]
>id="dc_orchestration_combine"
>title="Combine activity"
>abstract="The **Combine** activity allows you to perform segmentation on your inbound population. You can thus combine several populations, exclude part of it, or only keep data common to several targets."

The **Combine** activity allows you to perform segmentation on your inbound population. You can thus combine several populations, exclude part of it or only keep data common to several targets.

The **Combine** activity can be placed after any other activity, but not at the beginning of the composition. Any activity can be placed after the **Combine**.

## Configure the Combine activity {#combine-configuration}

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

Follow these common steps to start configuring the **Combine** activity:

1. Add multiple activities to form at least two different execution branches.

1. Add a **Combine** activity to any of the previous branches.

1. Select the segmentation type: [Union](#union), [Intersection](#intersection) or [Exclusion](#exclusion), and click **Continue**.

    ![](../assets/combine.png)

1. In the **Sets to join** section, check all the previous activities you want to join. 

## Union {#combine-union}

>[!CONTEXTUALHELP]
>id="dc_orchestration_intersection_reconciliation_options"
>title="Intersection reconciliation options"
>abstract="Select the reconciliation type to define how duplicates are handled."

>[!CONTEXTUALHELP]
>id="dc_orchestration_combine_reconciliation"
>title="Reconciliation options"
>abstract="Select the **Reconciliation type** to define how to handle duplicates."

In the **Combine** activity, you can configure a **Union**.

![](../assets/combine-union.png)

For this, you need to select the **Reconciliation type** to define how duplicates are handled:

* **Keys only**: this is the default mode. The activity only keeps one element when elements from the different inbound transitions have the same key. This option can only be used if the inbound populations are homogeneous.
* **A selection of columns**: select this option to define the list of columns on which the data reconciliation is applied. You must first select the primary set (that which contains the source data), then the columns to use for the join.

## Intersection {#combine-intersection}

In the **Combine** activity, you can configure an **Intersection**.

![](../assets/combine-intersection.png)

For this, follow the extra steps below:

1. Select the **Reconciliation type** to define how duplicates are handled. See the [Union](#union) section.
1. You can check the **Generate complement** option if you wish to process the remaining population. The complement will contain the union of the results of all inbound activities minus the intersection. An additional outbound transition will then be added to the activity.

## Exclusion {#combine-exclusion}

>[!CONTEXTUALHELP]
>id="dc_orchestration_exclusion_options"
>title="Exclusion rules"
>abstract="When necessary, you can manipulate inbound tables. Indeed, to exclude a target from another schema, also known as targeting dimension, this target has to be returned to the same schema as the main target. To do this, click **Add a rule** in the E**xclusion rules** section and specify the schema change conditions. Data reconciliation is carried out either via an attribute or a join."

>[!CONTEXTUALHELP]
>id="dc_orchestration_combine_sets"
>title="Select sets to combine"
>abstract="In the **Sets to join** section, select the **Primary set** from the inbound transitions. This is the set from which elements are excluded. The other sets match elements before being excluded from the primary set."

>[!CONTEXTUALHELP]
>id="dc_orchestration_combine_exclusion"
>title="Exclusion rules"
>abstract="When necessary, you can manipulate inbound tables. Indeed, to exclude a target from another schema, also known as targeting dimension, this target has to be returned to the same schema as the main target. To do this, click **Add a rule** in the **Exclusion rules** section and specify the schema change conditions. Data reconciliation is carried out either via an attribute or a join."

>[!CONTEXTUALHELP]
>id="dc_orchestration_combine_complement"
>title="Combine generate complement"
>abstract="Toggle on the **Generate complement** option to process the remaining population in an additional transition." 

In the **Combine** activity, you can configure an **Exclusion**.

![](../assets/combine-exclusion.png)
    
For this, you need to follow the extra steps below:

1. In the **Sets to join** section, select the **Primary set** from the inbound transitions. This is the set from which elements are excluded. The other sets match elements before being excluded from the primary set.

1. When necessary, you can manipulate inbound tables. Indeed, to exclude a target from another schema, this target has to be returned to the same schema as the main target. To do this, click **Add a rule** in the **Exclusion rules** section and specify the schema change conditions. Data reconciliation is carried out either via an attribute or a join. <!-- pas compris-->
1. You can check the **Generate completement** option if you wish to process the remaining population. See the [Intersection](#intersection) section.

<!--
## Examples{#combine-examples}

In the following example, we are using a **Combine** activity and we add a **union** to retrieves all the profiles of the two queries: persons between 18 and 27 years old and persons between 34 and 40 years old.

![](../assets/workflow-union-example.png)

The following example shows the **intersection** between two query activities. It is being used here to retrieve profiles who are between 18 to 27 years old and whose email address has been provided.

![](../assets/workflow-intersection-example.png)

The following **exclusion** example shows two queries configured to filter profiles who are between 18 and 27 years old and have an Adobe email domain. The profiles with an Adobe email domain are then excluded from the first set. 

![](../assets/workflow-exclusion-example.png)
-->
