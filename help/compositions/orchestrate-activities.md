---
audience: end-user
title: Create compositions
description: Learn how to create compositions
---

# Orchestrate composition activities {#activities}

Once that you have created a composition, you can start orchestrating the differents tasks it will perform. To do this, a visual canvas is provided, allowing you to construct your composition diagram. Within this diagram, you can add various activities and connect them in a sequential order.

## Add activities {#add}

At this stage of the configuration, the diagram is displayed with a start icon, representing the beginning of your workflow. To add your first activity, click the **+** button connected to the start icon.

A list of activities that can be added to the diagram appears. The available activities depend on your position within the composition diagram. For example, when adding your first activity, you can start your composition by targeting an audience, splitting the workflow path, settings a scheduler to delay the workflow execution or setting a **Wait** activity to delay the workflow execution. On the other hand, after a **Build audience** activity, you can refine your target with targeting activities or organize the composition process with flow control activities.

Once an activity has been added to the diagram, a right pane appears, allowing you to configure the newly added activity with specific settings. Detailed information on how to configure each activity is available in [this section](activities/about-activities.md).

![](assets/composition-create-add.png)

Repeat this process to add as many activities as desired depending on the tasks that you want your composition to perform. Note that you can also insert a new activity between two activities. To do this, click the **+** button on the transition between the activities, select the desired activity and configure it in the right pane.

>[!TIP]
>
>You have the option to personalize the name of the transitions between each activity. To do this, select the transition and change its label in the right pane.

## The canvas toolbar {#toolbar}

The toolbar located in the upper-right corner of the canvas provides options to easily manipulate the activities and navigate in the canvas.

![](assets/canvas-toolbar.png)

Available actions are:

* **Multiple selection**: Select multiple activities to delete them all at once or copy and paste them. See [this section](#copy).
* **Rotate**: Switch the canvas vertically.
* **Fit to screen**: Adapt the canvas zoom level to your screen.
* **Zoom out** / **Zoom in**: Zoom out or in the canvas.
* **Display map**: Opens a snapshot of the canvas showing you are located.

## Manage activities {#manage}

When adding activities, action buttons are available in the properties pane, allowing you to perform multiple operations.

![](assets/activity-actions.png)

You can:

* **Delete** the activity from the canvas.
* **Disable/Enable** the activity. When the workflow is executed, disabled activities and the following activities on the same path are not executed and the workflow is stopped.
* **Pause/Resume** the activity. When the workflow is executed, it pauses at the paused activity. The corresponding task as well as all those that follow it in the same path are not executed.
* **Copy** the activity to paste it at another location in the composition. To do this, click the **+** button on a transition and select "Paste X activity". <!-- cannot copy multiple activities ? cannot paste in another composition?-->
* Configure **Execution options** for the selected activity. Expand the section below to learn more on the available options.

    +++Available execution options

    The **Properties** section allows you to configure generic settings regarding the execution of the activity:

    * **Execution**: Define the action to be carried out when the is started.
    * **Maximum execution duration**: Specify a duration such as "30s" or "1h". If the activity is not finished after the duration specified has been elapsed, an alert is triggered. This has no impact on how the workflow functions.
    * **Time zone**: Select the time zone of the activity. Federated Audience Composition allows you to manage the time differences between multiple countries on the same instance. The setting applied is configured when the instance is created.
    * **Affinity**: Force the composition activity to execute on a particular machine. To do this, you must specify one or several affinities for the activity in question.
    * **Behavior**: Define the procedure to follow if asynchronous tasks are used.

    The **Error management** section allows you to specify the action to be carried out should the activity encounter an error.

    The **Initialization script** section lets you initialize variables or modify activity properties. Click the **Edit code** button and type the snippet of code to execute. The script is called when the activity executes.

    +++

* Access the activity's **Logs and tasks**.
