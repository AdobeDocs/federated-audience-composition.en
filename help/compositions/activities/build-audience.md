---
audience: end-user
title: Use the Build audience activity
description: Learn how to use the Build audience activity
exl-id: 6fad3e49-e654-4f68-a125-50056c4ae980
---
# Build audience {#build-audience}

>[!CONTEXTUALHELP]
>id="dc_orchestration_build_audience"
>title="Build audience activity"
>abstract="The **Build audience** activity allows you to define the audience that will enter the composition."

The **Build audience** activity allows you to define the audience that will enter the composition. To define the audience population, you can:
 
* Select an existing Adobe Experience Platform audience. 
* Create a new audience with the query modeler by defining and combining filtering criteria.

## Configure the Build audience activity {#build-audience-configuration}



Follow these steps to configure the **Build audience** activity:

1. Add a **Build audience** activity. 
1. Define a label.
1. Specify if you want to create an audience or select an existing one.
1. Configure your audience by following the steps detailed in the tabs below.

>[!BEGINTABS]

>[!TAB Create audience]

To create your own audience, follow these steps:

1. Select **Create audience**.
1. Choose the **Schema**, also known as targeting dimension. The schema lets you define the population targeted by the operation: recipients, contract beneficiaries, operator, subscribers, etc. By default, the schema is selected from the recipients.

    ![](../assets/build-audience-create.png)

1. Select **Continue**.
1. Use the query modeler to define your query then confirm. [Learn how to work with the query modeler](../../query/query-modeler-overview.md)

>[!TAB Read audience]

To select an existing audience, follow these steps:

1. Select **Read audience**.
1. Select **Continue**.

    ![](../assets/build-audience-read.png)

1. Select your audience.

>[!ENDTABS]

>[!NOTE]
>
>The **Generate an outbound transition** option allows you to add an outbound transition that will be activated at the end of the execution of the activity if the audience population is empty. 

<!--
## Examples{#build-audience-examples}

Here is an example of a workflow with two **Build audience** activities. The first one targets the poker players audience, followed by an email delivery. The second one targets the VIP clients audience, followed by an SMS delivery.

![](../assets/workflow-audience-example.png)
-->
