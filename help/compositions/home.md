---
audience: end-user
title: Get started with compositions
description: Learn how to start with compositions
exl-id: 92142d16-3483-4f6e-afde-9f88d5d7d1c4
TQID: https://experienceleague.adobe.com/-SzMG0wJnEcqFJPJZqBWKD8y22d4Z525Obe5CnyhcfE
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
    internal-label: CX Enterprise
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Compositions overview

>[!AVAILABILITY]
>
>To access compositions, you'll need one of the following permissions:
>
>-**Manage Federated Compositions**
>-**View Federated Compositions**
>
>For more information on the required permissions, please read the [access control guide](/help/governance-privacy-security/access-control.md).

Federated Audience Composition lets you create compositions, where you can leverage various activities into a visual canvas to create audiences. After creating your composition, the resulting audiences are saved into Adobe Experience Platform and can be leveraged in Experience Platform destinations and Adobe Journey Optimizer to target customers. 

![A sample composition workflow is displayed within Federated Audience Composition.](/help/compositions/assets/home/composition-example.png){zoomable="yes"}{width="70%"}

## Composition components {#components}

A composition within Federated Audience Composition is made up of the following parts:

- **[!UICONTROL Activities]**: An activity is a task to be performed, and are represented within the composition by icons.
- **[!UICONTROL Transitions]**: Transitions link a source activity to a destination activity and define their sequence. The information contained in the transitions is stored within a work table. Each composition uses several worktables. The data conveyed in these tables can be used throughout the composition's life cycle.

## Access and manage compositions {#access}

>[!CONTEXTUALHELP]
>id="dc_composition_list"
>title="Compositions"
>abstract="In this screen, you can access the full list of compositions, check their current status, last/next execution dates, and create a new composition."

Compositions are accessible from the Adobe Experience Platform **[!UICONTROL Audiences]** menu, in the **[!UICONTROL Federated compositions]** tab within the **[!UICONTROL Customers]** section.

![The Federated compositions and Audiences buttons are highlighted, showing how to access the federated compositions section.](/help/compositions/assets/home/access-fac-compositions.png){zoomable="yes"}{width="70%"}

From this screen, you can view information about the compositions and create new compositions.

![The list of federated compositions is displayed.](/help/compositions/assets/home/composition-list.png){zoomable="yes"}{width="70%"}

| Field | Description |
| ----- | ----------- |
| **[!UICONTROL Name]** | The name of the composition. If you select the composition, you can edit the composition. For more information on creating and editing compositions, read the [create a composition guide](/help/compositions/create-composition.md). |
| **[!UICONTROL Status]** | The status of the composition. Possible values include [!UICONTROL Draft], [!UICONTROL In progress], [!UICONTROL Stopped], [!UICONTROL Paused], and [!UICONTROL Erroneous]. <ul><li>**[!UICONTROL Draft]**: The composition has been created and saved.</li><li>**[!UICONTROL In progress]**: The composition has been executed and is currently running.</li><li>**[!UICONTROL Stopped]**: The composition execution is complete and has stopped.</li><li>**[!UICONTROL Paused]**: The composition execution has been paused.</li><li>**[!UICONTROL Erroneous]**: The composition execution has encountered an error. To view more information about the error, open the composition and access the logs.</li></ul> To learn how to start or stop a composition, read the [create composition guide](./create-composition.md#monitor-logs). |
| **[!UICONTROL Created by]** | The name and email address of the person that created the composition. |
| **[!UICONTROL Modified]** | The date and time the composition was last updated. |

You can also perform quick actions to the compositions by selecting the ![ellipses](/help/assets/icons/more.png) button next to its name.

| Action | Description |
| ------ | ----------- |
| **[!UICONTROL Duplicate]** | Duplicates the selected composition. |
| **[!UICONTROL Delete]** | Deletes the selected composition. |
| **[!UICONTROL Add to package]** | Moves the composition between sandboxes. For more information on this feature, read the [sandbox tooling guide](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/ui/sandbox-tooling). |

To refine the list and find the composition you are looking for, you can search the list, and filter compositions by their statuses or last processing dates.

You can also customize the list by adding or removing columns. To do this, select the **[!UICONTROL Configure columns]** button and add or remove the desired output columns.

![A list of the available columns you can add to the compositions browse page are displayed.](/help/compositions/assets/home/compositions-columns.png){zoomable="yes"}{width="70%"}

### Apply access labels {#access-labels}

To apply access labels to a specific composition, select the composition, followed by **[!UICONTROL Manage access]**.

![The "Manage access" button is highlighted within the composition canvas.](/help/compositions/assets/home/select-manage-access.png){zoomable="yes"}{width="70%"}

The **[!UICONTROL Manage access]** popover appears. On this page, you can apply the applicable access and data governance labels to your composition.

![The Manage access popover is displayed. This shows a list of all the available labels you can apply to the composition.](/help/compositions/assets/home/manage-access.png){zoomable="yes"}{width="70%"}

| Label type | Description |
| ---------- | ----------- |
| Contract labels | Contract labels ("C" labels) are used to categorize data that has contractual obligations or is related to your organization's data governance policies. |
| Identity labels | Identity labels ("I" labels) are used to categorize data that can identify or contact a specific person. |
| Sensitive labels | Sensitive labels ("S" labels) are used to categorize you and/or your organization consider sensitive. |
| Partner Ecosystem labels | Partner Ecosystem labels are used to categorize data from sources external to your organization. |

For more information about access and data governance labels, please read the [data usage label glossary](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/reference).

## Create {#create}

You can create a composition for Adobe Experience Platform using Audience Composition. For more information, read the [create a composition guide](./create-composition.md).

## Next steps

After reading this guide, you've learned how to access, manage, and create access labels for your compositions. For more information on working with audiences as a whole, please read the [audiences guide](../start/audiences.md).
