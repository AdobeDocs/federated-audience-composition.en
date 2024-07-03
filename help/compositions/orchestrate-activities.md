---
audience: end-user
title: Create compositions
description: Learn how to create compositions
---

# Orchestrate composition activities {#activities}

Once that you have created a composition, you can start orchestrating the differents tasks it will perform. To do this, a visual canvas is provided, allowing you to construct your composition diagram. Within this diagram, you can add various activities and connect them in a sequential order.

## Add activities {#add}

At this stage of the configuration, the diagram is displayed with a start icon, representing the beginning of your workflow. To add your first activity, click the **+** button connected to the start icon.

A list of activities that can be added to the diagram appears. The available activities depend on your position within the composition diagram. For example, when adding your first activity, you can start your composition by targeting an audience, splitting the workflow path, or setting a **Wait** activity to delay the workflow execution. On the other hand, after a **Build audience** activity, you can refine your target with targeting activities, send a delivery to your audience with channel activities, or organize the composition process with flow control activities.

Once an activity has been added to the diagram, a right pane appears, allowing you to configure the newly added activity with specific settings. Detailed information on how to configure each activity is available in [this section](activities/about-activities.md).

Repeat this process to add as many activities as desired depending on the tasks that you want your composition to perform. Note that you can also insert a new activity between two activities. To do this, click the **+** button on the transition between the activities, select the desired activity and configure it in the right pane.

To remove an activity, select it in the canvas and click the **Delete** icon in the activity properties.

>[!TIP]
>
>You have the option to personalize the name of the transitions between each activity. To do this, select the transition and change its label in the right pane.

## The toolbar {#toolbar}

The toolbar located in the upper-right corner of the canvas provides options to easily manipulate the activities and navigate in the canvas:

* **Multiple selection mode**: Select multiple activities to delete them all at once or copy and paste them. See [this section](#copy).
* **Rotate**: Switch the canvas vertically.
* **Fit to screen**: Adapt the canvas zoom level to your screen.
* **Zoom out** / **Zoom in**: Zoom out or in the canvas.
* **Display map**: Opens a snapshot of the canvas showing you are located.

![](assets/workflow-toolbar.png){zoomable="yes"}{width="50%"}

## Manage activities {#manage}

When adding activities, action buttons are available in the properties pane, allowing you to perform multiple operations. You can:

* **Delete** the activity from the canvas.
* **Disable/Enable** the activity. When the workflow is executed, disabled activities and the following activities on the same path are not executed and the workflow is stopped.
* **Copy** the activity. See [this section](#copy).
* Access the activity's **Logs and tasks**.
* **Pause/Resume** the activity. When the workflow is executed, it pauses at the paused activity. The corresponding task as well as all those that follow it in the same path are not executed.

Several **Targeting** activities, such as **Combine** or **Deduplication**, allow you to process the remaining population and include it into an additional outbound transition. For example, if you're using a **Split** activity, the complement consists of the population that did not match any of the previously defined subsets. To use this capability, activate the **Generate complement** option. 

## Copy activities {#copy}

You can copy workflow activities and paste them in any worflow. The destination workflow can be in a different browser tab. 

To copy activities, you have two choices:

* copy one activity using the action button.

* copy multiple acivities using the toolbar button.

To paste the copied activities, click the **+** button on a transition and select "Paste X activity". 

## Execution options {#execution}

All activities allow you to manage their execution options. Select an activity and click on the **Execution options** button. This lets you define the activity's execution mode and behavior in case of errors.

### Properties

The **Execution** field allows you to define the action to be carried out when the task is started.

The **Maximum execution duration** field allows you to specify a duration such as "30s" or "1h". If the activity is not finished after the duration specified has been elapsed, an alert is triggered. This has no impact on how the workflow functions.

The **Time zone** field allows you to select the time zone of the activity. Adobe Campaign allows you to manage the time differences between multiple countries on the same instance. The setting applied is configured when the instance is created.

**The Affinity** field allows you to force a workflow or a workflow activity to execute on a particular machine. To do this, you must specify one or several affinities for the workflow or activity in question.

The **Behavior** field allows you to define the procedure to follow if asynchronous tasks are used.

### Error management

The **In case of error** field allows you to specify the action to be carried out should the activity encounter an error.

### Initialization script

The **Initialization script** lets you initialize variables or modify activity properties. Click the **Edit code** button and type the snippet of code to execute. The script is called when the activity executes. Refer to the section related to [event variables](../workflows/event-variables.md).

## Example {#example}

Here is a workflow example designed to send an email to all customers (other than VIP customers) with an email who are interested in coffee machines.

![](assets/workflow-example.png){zoomable="yes"}{zoomable="yes"}

To achieve this, activities below have been added:

* A **[!UICONTROL Fork]** activity that divides the workflow into three paths (one for each set of customer),
* **[!UICONTROL Build audience]** activities to target the three sets of customers:

    * Customers with an email,
    * Customers belonging to the pre-existing "Interrested in Coffee Machine(s)" audience,
    * Customers belonging to the pre-existing "VIP ro reward" audience.

* A **[!UICONTROL Combine]** activity that groups together customers with an email and those interested in coffee machines,
* A **[!UICONTROL Combine]** activity that excludes VIP customers,
* An **[!UICONTROL Email delivery]** activity that sends an email to the resulting customers. 

Once you have completed the workflow, add en **[!UICONTROL End]** activity at the end of the diagram. This activity allow you to visually mark the end of a workflow and has no functional impact.

After successfully designing the workflow diagram, you can execute the workflow and track the progress of its various tasks. [Learn how to start a workflow and monitor its execution](start-monitor-workflows.md)
