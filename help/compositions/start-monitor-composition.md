---
audience: end-user
title: Create compositions
description: Learn how to create compositions
---

# Start and monitor your composition {#start-monitor}

Once that you have created your composition and designed the tasks to perform in the canvas, you can launch it and monitor how it is being executed. 

## Start the composition {#start}

To start the composition, navigate to the **[!UICONTROL Compositions]** menu or the associated campaign and click the **[!UICONTROL Start]** button in the upper-right corner of the canvas.

Once the composition is running, each activity in the canvas is executed in a sequential order, until the end of the composition is reached.

You can track the progress of targeted profiles in real-time using a visual flow. This allows you to quickly identify the status of each activity and the number of profiles transitioning between them.

![](assets/composition-execution.png){zoomable="yes"}

## Composition transitions {#transitions}

In compositions, data transported from one activity to another through transitions is stored in a temporary work table. This data can be displayed for each transition. To do this, select a transition to open its properties in the right hand side of the screen.

* Click **[!UICONTROL Preview schema]** to display the schema of the work table.
* Click **[!UICONTROL Preview results]** to visualize the data transported in the selected transition.

![](assets/transition.png){zoomable="yes"}

## Monitor activity execution {#activities}

Visual indicators in the upper-right corner of each activity box allows you to check their execution:

|Visual indicator | Description | 
|-----|------------|
|![](assets/activity-status-pending.png){zoomable="yes"}{width="70%"}| The activity is currently being executed. |
|![](assets/activity-status-orange.png){zoomable="yes"}{width="70%"}| The activity requires your attention. This may involve confirming the sending of a delivery or taking a necessary action. |
|![](assets/activity-status-red.png){zoomable="yes"}{width="70%"}|The activity has encountered an error. To resolve the issue, open the composition logs for more information.|
|![](assets/activity-status-green.png){zoomable="yes"}{width="70%"}|The activity has been succesfully executed. | 

## Monitor logs and tasks {#logs-tasks}

Monitoring compositions logs and tasks is a key step to analyze your compositions and make sure they are running properly. They are accessible from the **[!UICONTROL Logs]** icon which is available in the action tool bar, and in each activity's properties pane.

The **[!UICONTROL Logs and tasks]** menu provides an history of the composition execution, recording all user actions and encountered errors. This history is saved for the duration specified in the composition [execution options](composition-settings.md). During this duration, all the messages are saved, even after a restart of the composition. If you do not want to save the messages from a previous execution, click the **[!UICONTROL Purge history]** button.

![](assets/composition-logs.png){zoomable="yes"}

Two types of information are available:

* The **[!UICONTROL Log]** tab contains the execution history of all the composition activities. It indexes the operations carried out and execution errors by chronological order.
* The **[!UICONTROL Tasks]** tab details the execution sequencing of the activities. 

In both tabs, you can choose the displayed columns and their order, apply filters, and use the search field to quickly find the desired information.

## Composition execution commands {#execution-commands}

The action bar in the upper-right corner provides commands that allow you to manage the composition execution. You can:

* **[!UICONTROL Start]** / **[!UICONTROL Resume]** the execution of the  composition, which then takes on the In progress status. If the composition was paused, it is resumed, otherwise it is started and the initial activities are then activated.

* **[!UICONTROL Pause]** the execution of the composition, which then takes on the Paused status. No new activities will be activated until it is resumed, but operations in progress are not suspended.

* **[!UICONTROL Stop]** a composition that is being executed, which will then take on the Finished status. The operations in progress are interrupted if possible. You cannot resume from the composition from the same place that it was stopped.
