---
audience: end-user
title: Get started with compositions
description: Learn how to start with compositions
---
# Get started with compositions {#compositions}

>[!CONTEXTUALHELP]
>id="dc_workflow_settings_properties"
>title="Composition properties"
>abstract="This section provides generic composition properties that are also accessible when creating the composition."

>[!CONTEXTUALHELP]
>id="dc_workflow_settings_segmentation"
>title="Composition segmentation"
>abstract="By default, only the working tables of the last execution of the composition are kept. You can enable this option to keep working tables for testing purposes. It must be used **only** on development or staging environments. It must never be checked in a production environment."




## What is a composition? {#compositions-start}


>[!CONTEXTUALHELP]
>id="dc_workflow_list"
>title="Compositions"
>abstract="In this screen, you can access the full list of compositions, check their current status, last/next execution dates, and create a new composition."


## Error management settings  {#error-settings}

>[!CONTEXTUALHELP]
>id="dc_workflow_settings_error"
>title="Error management settings"
>abstract="In this section, you can define how to manage errors during the execution. You can choose to pause the process, ignore a certain number of errors, or stop the composition execution."

* **[!UICONTROL Error management]**: This field lets you define the actions to be taken if a composition activity has errors. 
    There are three possible options:
    
    * **[!UICONTROL Suspend the process]**: The composition is automatically paused and its status changes to **[!UICONTROL Failed]**. Once the issue is solved, resume the composition using the **[!UICONTROL Resume]** buttons.
    * **[!UICONTROL Ignore]**: The status of the task that triggered the error changes to **[!UICONTROL Failed]**, but the composition keeps the **[!UICONTROL Started]** status.
    * **[!UICONTROL Abord the process]**: The composition is automically stopped and its status changes to **[!UICONTROL Failed]**. Once the issue is solved, restart the composition using the **[!UICONTROL Start]** button.

* **[!UICONTROL Consecutive errors]**: This field becomes available when the **[!UICONTROL Ignore]** value is selected in the **[!UICONTROL In case of errors]** field. You can specify the number of errors that can be ignored before the process is stopped. Once this number is reached, the composition status changes to **[!UICONTROL Failed]**. If the value of this field is 0, the composition will never be stopped regardless of the number of errors.
