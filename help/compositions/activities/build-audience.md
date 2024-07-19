---
audience: end-user
title: Use the Build audience activity
description: Learn how to use the Build audience activity
badge: label="Limited availability" type="Informative"
---

# Build audience {#build-audience}

>[!CONTEXTUALHELP]
>id="dc_orchestration_build_audience"
>title="Build audience activity"
>abstract="The **Build audience** activity allows you to define the audience that will enter the composition."

The **Build audience** activity allows you to define the audience that will enter the composition.

To define the audience population, you can:
 
<!--* Select an existing audience, created as a list in the client console.-->
* Select an Adobe Experience Platform audience. 
* Build a new audience with the query modeler builder by defining and combining filtering criteria.

The **Build audience** activity can be placed at the beginning of the composition or after any other activity. Any activity can be placed after the **Build audience**.

## Configure the Build audience activity {#build-audience-configuration}

>[!CONTEXTUALHELP]
>id="dc_orchestration_build_audience_audienceselector"
>title="Audience"
>abstract="Select your audience."

Follow these steps to configure the **Build audience** activity:

1. Add a **Build audience** activity. 
1. Define a label.
1. Specfiy if you want to create an audiance or select an existing one.
1. Configure your audience by following the steps detailed in the tabs below.

>[!BEGINTABS]

>[!TAB Create audience]

To create your own audience, follow these steps:

1. Select **Create audience**.
1. Choose the **Schema**, also known as targeting dimension. The schema lets you define the population targeted by the operation: recipients, contract beneficiaries, operator, subscribers, etc. By default, the schema is selected from the recipients.
1. Click **Continue**.
1. Use the query modeler to define your query. [Learn how to work with the query modeler](../../query/query-modeler-overview.md)

>[!TAB Read audience]

To select an existing audience, follow these steps:

1. Select **Read audience**.
1. Click **Continue**.
1. Select your audience.

>[!ENDTABS]

<!--
## Examples{#build-audience-examples}

Here is an example of a workflow with two **Build audience** activities. The first one targets the poker players audience, followed by an email delivery. The second one targets the VIP clients audience, followed by an SMS delivery.

![](../assets/workflow-audience-example.png)
-->
