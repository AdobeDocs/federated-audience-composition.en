---
title: Prerequisites and guardrails for Federated Audience Composition
description: Learn prerequisites, permissions, and guardrails for Federated Audience Composition
exl-id: 661a838f-146e-4d68-bb2d-319827caee3a
TQID: https://experienceleague.adobe.com/VBIotVn1VyiFJChb3mM0VDLUSbG9aQOmbfGnfGgqvhU
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
    internal-label: Experience Cloud
feature_v2:
  - id: fdbb8fc9-ffa3-4b86-88fe-aa4c5a3e1bc6
    internal-label: Administration
subfeature_v2:
  - id: b75843fa-0a67-4a44-a6b1-cc627b0481dc
    internal-label: Support
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Prerequisites and guardrails {#fac-access}

Federated Audience Composition requires Adobe Real-Time Customer Data Platform and/or Adobe Journey Optimizer **Prime** or **Ultimate** packages. To access this capability, you must have purchased the Federated Audience Composition add-on.

>[!AVAILABILITY]
>
>After your received the welcome email notification from Adobe, it might take a few more hours for the interface to be updated and features available to you.

## Supported systems {#supported-systems}

Federated Audience Composition supports the following cloud warehouses:

* Amazon Redshift
* Azure Synapse
* Databricks
* Google BigQuery
* Snowflake
* Vertica Analytics
* Microsoft Fabric

You can learn how to create a connection with these systems on the [connections overview](../connections/home.md).

## Sandboxes

When purchasing Federated Audience Composition, you are entitled to two sandboxes. For any additional sandbox provisioning requests, contact your Adobe representative.

To view the list of your active Federated Audience Composition sandboxes, follow the steps below:

1. From Federated Audience Composition, access the **[!UICONTROL License usage]** menu under **[!UICONTROL Administration]**.

1. Select the ![](assets/do-not-localize/Smock_InfoOutline_18_N.svg) icon from **[!UICONTROL Total volume of data egress]** to access your sandbox properties.

    ![](assets/sandbox_1.png)

1. Information about your sandbox is shown in the Properties popover.

    ![](assets/sandbox_2.png)

## Permissions {#permissions}

To access Federated Audience Composition, users must be added to the sandbox-specific product profile created upon purchase and assigned the **[!UICONTROL Manage Federated Data]** permission. [Learn more](/help/governance-privacy-security/access-control.md)

## IP allow-listing {#ip}

To securely enable Federated Audience Composition to access your databases, you must authorize the IP addresses of the Federated Audience Composition servers that will access them. These IP addresses are displayed when adding a federated database in the Adobe Experience Platform user interface. [Learn more](../connections/home.md)

Add these IP addresses to your allow list to grant access for Federated Audience Composition.

## Merge policies {#merge-policies}

If your sandbox uses a **dataset precedence** merge policy, please contact Adobe Customer Care to add the `Halos UPS` dataset to your merge policy.

For more information on merge policies, please read the [merge policies overview](https://experienceleague.adobe.com/en/docs/experience-platform/profile/merge-policies/overview).

## Guardrails and limitations {#fac-guardrails}

* Entitlements, product limitations and performance guardrails listed in the [Adobe Real-Time Customer Data Platform documentation](https://experienceleague.adobe.com/en/docs/experience-platform/profile/guardrails){target="_blank"} apply to Federated Audience Composition.

* Federated Audience Composition supports the export of large audiences, with file sizes greater than 1 GB. For optimal performance, the maximum recommended file size is up to 20 GB.
