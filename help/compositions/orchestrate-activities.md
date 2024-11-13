---
audience: end-user
title: Create compositions
description: Learn how to create compositions
exl-id: 7b9acfc0-99b6-4f83-b774-3652c811868c
---
# Orchestrate composition activities {#activities}

Once that you have created a composition, you can start orchestrating the differents tasks it will perform. To do this, a visual canvas is provided, allowing you to construct your audience composition diagram. Within this diagram, you can add various activities and connect them in a sequential order.

## Add activities {#add}

At this stage of the configuration, the diagram is displayed with a start icon, representing the beginning of your composition. To add your first activity, click the **+** button connected to the start icon.

A list of activities that can be added to the diagram appears. The available activities depend on your position within the composition diagram. For example, when adding your first activity, you can start your composition by targeting an audience, splitting the composition path, settings a scheduler to delay the composition execution or setting a **Wait** activity to delay the composition execution. On the other hand, after a **Build audience** activity, you can refine your target with targeting activities or organize the composition process with flow control activities.

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

* **[!UICONTROL Multiple selection]**: Select multiple activities to delete them all at once or copy and paste them. See [this section](#copy).
* **[!UICONTROL Rotate]**: Switch the canvas vertically.
* **[!UICONTROL Fit to screen]**: Adapt the canvas zoom level to your screen.
* **[!UICONTROL Zoom out]** / **[!UICONTROL Zoom in]**: Zoom out or in the canvas.
* **[!UICONTROL Display map]**: Opens a snapshot of the canvas showing you are located.

## Manage activities {#manage}

When adding activities, action buttons are available in the properties pane, allowing you to perform multiple operations.

![](assets/activity-actions.png)

You can:

* **[!UICONTROL Delete]** the activity from the canvas.
* **[!UICONTROL Disable]/[!UICONTROL Enable]** the activity. When the composition is executed, disabled activities and the following activities on the same path are not executed and the composition is stopped.
* **[!UICONTROL Pause]/[!UICONTROL Resume]** the activity. When the composition is executed, it pauses at the paused activity. The corresponding task as well as all those that follow it in the same path are not executed.
* **[!UICONTROL Copy]** the activity to paste it at another location in the composition. To do this, click the **+** button on a transition and select **[!UICONTROL Paste X activity]**. <!-- cannot copy multiple activities ? cannot paste in another composition?-->
* Configure **[!UICONTROL Execution options]** for the selected activity. Expand the section below to learn more on the available options.

    +++Available execution options

    The **[!UICONTROL Properties]** section allows you to configure generic settings regarding the execution of the activity:

    * **[!UICONTROL Execution]**: Define the action to be carried out when the is started.
    * **[!UICONTROL Maximum execution duration]**: Specify a duration such as "30s" or "1h". If the activity is not finished after the duration specified has been elapsed, an alert is triggered. This has no impact on how the composition functions.
    * **[!UICONTROL Time zone]**: Select the time zone of the activity. Federated Audience Composition allows you to manage the time differences between multiple countries on the same instance. The setting applied is configured when the instance is created.
    * **[!UICONTROL Affinity]**: Force the composition activity to execute on a particular machine. To do this, you must specify one or several affinities for the activity in question.
    * **[!UICONTROL Behavior]**: Define the procedure to follow if asynchronous tasks are used.

    The **[!UICONTROL Error management]** section allows you to specify the action to be carried out should the activity encounter an error.

    The **[!UICONTROL Initialization script]** section lets you initialize variables or modify activity properties. Click the **[!UICONTROL Edit code]** button and type the snippet of code to execute. The script is called when the activity executes.

    +++

* Access the activity's **Logs and tasks**.
