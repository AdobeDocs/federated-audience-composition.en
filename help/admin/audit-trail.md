---
audience: end-user
title: Audit Trail
description: Learn how actions and events are logged and accessible in the audit trail
exl-id: 97142f54-53ce-4c2a-9d89-fdcb2a47b159
---
# Audit Trail {#audit-trail}

>[!AVAILABILITY]
>
>To access the audit trail, you'll need the following permission:
>
>-**View Audit Trail**
>
>For more information on the required permissions, please read the [access control guide](/help/governance-privacy-security/access-control.md).

>[!CONTEXTUALHELP]
>id="dc_audit_trail"
>title="Audit trail"
>abstract="The Audit trail capability provides a detailed and chronological record of all actions and events that have been made to your Adobe Experience Platform Federated Audience Composition environment in real-time."

The **[!UICONTROL Audit trail]** feature constantly records a detailed log of actions and events taking place within the Adobe Federated Composition instance in real-time. It offers a convenient method to access a chronological record of data, addressing queries such as: the status of workflows, the latest individuals to modify them, or the activities performed by users within the instance.

+++ Learn more about Audit Trail available entities

* **Source Schema audit trail** allows you to monitor activities and recent modifications made to your schemas within the Adobe Federated Audience Composition instance. 

  For detailed information on schemas, refer to this [page](../data-modelling/schemas.md).

* **Workflow audit trail** allows you to keep track of activities and recent changes made to workflows, including their current states such as:

    * Start
    * Pause
    * Stop
    * Restart
    * Cleanup which equals to the action Purge history
    * Simulate which equals to the action Start in simulation mode
    * Wakeup which equals to the action Execute pending tasks now
    * Unconditional Stop

  For more information on workflows, refer to this [page](../compositions/compositions.md).

* **External Account** allows you to check modifications made to external accounts in Adobe Audience Composition instance.

  For more information on external account, refer to this [page](../connections/home.md).

+++

## Accessing Audit trail {#accessing-audit-trail}

To access your instance's **[!UICONTROL Audit trail]**:

1. Under the **[!UICONTROL Federated data]** menu, select **[!UICONTROL Audit trail]**.

1. The **[!UICONTROL Audit trail]** window opens with the list of your entities. Federated Audience Composition audits the create, edit and delete actions for workflows, options, deliveries and schemas.

    ![](assets/audit_trail.png)

1. The **[!UICONTROL Audit entity]** window gives you more detailed information on the chosen entity such as:

    * **[!UICONTROL Type]**: Workflow, Options, Deliveries or Schemas.
    * **[!UICONTROL Entity]**: Internal name of your activities.
    * **[!UICONTROL Modified by]**: Username of the last person who last modified this entity.
    * **[!UICONTROL Action]**: Last action performed on this entity, either Created, Modified or Deleted.
    * **[!UICONTROL Modification date]**: Date of the last action performed on this entity.
