---
title: Access Control in Federated Audience Composition
description: Learn how to manage data access for users in Federated Audience Composition.
exl-id: 84138456-218b-4beb-ae7b-146213b03cc2
---
# Access Control in Federated Audience Composition

You can use access control to provide role-based access to sandboxes and Federated Audience Composition.

## Manage access to sandboxes {#access-sandboxes}

When you purchase Adobe Experience Platform Federated Audience Composition, a product profile is created for each active sandbox at that time. This product profile is created in the Admin Console under the **Adobe Experience Platform** product card and follows this naming convention: `ACP_FAC - <<SandboxName>> - admin.` To access the Federated Audience Composition for a specific sandbox, users must be added to the product profile created for that sandbox.

For example, if a new sandbox named "fac-test" is activated, a corresponding product profile "ACP_FAC - fac-test - admin" is created. In order to access Federated Audience Composition with this sandbox, users need to be added to this product profile.

## Manage access to Federated Audience Composition

To access **Federated Audience Composition**, you must first ensure that you assign the required permissions to access different aspects of Federated Audience Composition. These roles must then be assigned to users who need access to **Federated Audience Composition**.

Note that only administrators have the ability to assign permissions.

1. Navigate to the **[!UICONTROL Permissions]** menu.

1. From the **[!UICONTROL Roles]** menu, select the **[!UICONTROL Role]** you wish to update.

    ![](assets/access_fda_1.png)

1. Select **[!UICONTROL Edit]** to modify your role's permissions.

    ![](assets/access_fda_2.png)

1. Add the required permissions for the user. You can add the following permissions for access to Federated Audience Composition:

    | Permission | Description |
    | ---------- | ----------- |
    | Manage Federated Data | Use this permission to manage all aspects of Federated Audience Composition. This permission subsumes Manage Federate Database, Manage Federated Schema, Manage Federated Data Model, and Manage Federated Compositions. |
    | Manage Federated Database | Use this permission to add, view, update, and delete your connections to federated databases. |
    | View Federated Database | Use this permission to  view your connections to federated databases. |
    | Manage Federated Schema | Use this permission to create, view, update, delete, and refresh schemas. |
    | View Federated Schema Data | Use this permission to view the data tab within the schema section. |
    | View Federated Schema | Use this permission to view the schema tables. |
    | Manage Federated Data Model | Use this permission to create, view, update, and delete data models. |
    | View Federated Data Model | Use this permission to view the data models. |
    | View Federation Audit Trail | Use this permission to view the audit trail for Federated Audience Composition.  |
    | Manage Federated Compositions | Use this permission to create, view, update, and delete federated compositions. |
    | View Federated Compositions | Use this permission to view federated compositions. |

    ![](assets/permissions.png)

1. Once you've made the necessary changes, select **[!UICONTROL Save]**.

Any users already assigned to this role will have their permissions automatically updated and access to Federated Audience Composition.

To assign this role to new users:

1. Navigate to the **[!UICONTROL Users]** tab within your Role dashboard and select **[!UICONTROL Add Users]**.

    ![](assets/access_fda_4.png)

1. Enter the user's name or email address, or select from the available list. Once done, select **[!UICONTROL Save]**.

Alternatively, you can assign one of the pre-existing roles to the users, depending on what permissions they need. For more information on assigning pre-existing roles to a user, please read the [guide on managing users for a product profile](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/users).

| Role name | Permissions |
| --------- | ----------- |
| FAC Data Managers | <ul><li>Manage Federated Compositions</li><li>View Federated Databases</li><li>View Federated Schemas</li><li>View Federated Schema Data</li><li>View Federated Data Models</li></ul> |
| FAC Composition Managers | <ul><li>Manage Federated Compositions</li></ul> |
| FAC Administrators | <ul><li>Manage Federated Data</li></ul> |

The user will then receive an email with instructions to access your instance. If the user was not previously created, refer to the [this documentation](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/abac/permissions-ui/users).
