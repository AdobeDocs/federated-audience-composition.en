---
audience: end-user
title: Create compositions
description: Learn how to create compositions
---

# Create and execute a composition {#create-compositions}

>[!CONTEXTUALHELP]
>id="dc_workflow_creation_properties"
>title="Workflow properties"
>abstract="In this screen, choose the template to use to create the workflow and specify a label. Expand the ADDITIONAL OPTIONS section to configure more settings such as the workflow internal name, its folder, timezone, and supervisor group. It is highly recommended to select a supervisor group so that operators are alerted if an error occurs."

## Create the composition {#create}

To create a composition, follow these steps:

1. Access the **[!UICONTROL Audiences]** menu and select the **[!UICONTROL Federated compositions]** tab.

1. Click the **[!UICONTROL Create composition]** button.

1. In the **[!UICONTROL Properties]** section, specify a label for your compositon and click **[!UICONTROL Create]**.

1. The composition canvas displays. You can now configure your composition by adding as many activities as needed to suit your needs before executing it. You can also configure additional settings such as the composition's label or options related to error management at the composition's execution.

Learn more in these sections:

* [Configure the composition's settings](#starting-audience)
* [Add activities](#action-activities)
* [Execute the composition and monitor its execution](#save) 

## Configure the composition's settings {#settings}

>[!CONTEXTUALHELP]
>id="dc_workflow_settings_properties"
>title="Composition properties"
>abstract="This section provides generic composition properties that are also accessible when creating the composition."

>[!CONTEXTUALHELP]
>id="dc_workflow_settings_segmentation"
>title="Composition segmentation"
>abstract="By default, only the working tables of the last execution of the composition are kept. You can enable this option to keep working tables for testing purposes. It must be used **only** on development or staging environments. It must never be checked in a production environment."

>[!CONTEXTUALHELP]
>id="dc_workflow_settings_error"
>title="Error management settings"
>abstract="In this section, you can define how to manage errors during the execution. You can choose to pause the process, ignore a certain number of errors, or stop the composition execution."

Click the **Settings** button to access additional options for the composition:

* **[!UICONTROL Label]**: Change the composition's label.

* **[!UICONTROL Keep the result of interim populations between two executions]**: By default, only the working tables of the last execution of the composition are kept. Working tables from previous executions are purged by a technical workflow, which runs on a daily basis.

    If this option is enabled, working tables will be kept even after the composition has been executed. You can use it for testing purposes and hence must be used **only** on development or staging environments. It must never be checked in a production workflow.

* **[!UICONTROL Error management]**: This section lets you define the actions to be taken if a composition activity has errors. There are three possible options:
    
    * **[!UICONTROL Suspend the process]**: The composition is automatically paused and its status changes to **[!UICONTROL Failed]**. Once the issue is solved, resume the composition using the **[!UICONTROL Resume]** buttons.
    * **[!UICONTROL Ignore]**: The status of the task that triggered the error changes to **[!UICONTROL Failed]**, but the composition keeps the **[!UICONTROL Started]** status.
    * **[!UICONTROL Abord the process]**: The composition is automically stopped and its status changes to **[!UICONTROL Failed]**. Once the issue is solved, restart the composition using the **[!UICONTROL Start]** button.

* **[!UICONTROL Consecutive errors]**: Specify the number of errors that can be ignored before the process is stopped. Once this number is reached, the composition status changes to **[!UICONTROL Failed]**. If the value of this field is 0, the composition will never be stopped regardless of the number of errors.

## Add activities {#activities}

The composition canvas allows you to configure to add as many activities as needed in the composition to suit your needs.

To do this, click the + button on the composition path then add the desired activity. The right pane opens, allowing you to configure the newly added activity. [Learn more on the activities in compositions and how to configure them](../compositions/activities/about-activities.md)

To remove an activity from the canvas, select it and click the delete button in the right pane. If the activity that you want to delete is a parent of other activities in the composition, a message displays, allowing you to specify if you want to delete the selected activity only, or all its child activities.

## Execute the composition {#execute}

Once your composition is ready, click the **[!UICONTROL Start]** button to execute it and save the resulting audiences into Adobe Experience Platform. ``
You can monitor the execution of the workflow using the **Logs** button. Three tabs are available to help you monitor the execution:

* **[!UICONTROL Logs]**: 
* **[!UICONTROL Tasks]**: 
* **[!UICONTROL Variables]**: 
