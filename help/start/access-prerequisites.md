---
title: Prerequisites and guardrails for Federated Audience Composition
description: Learn prerequisites, permissions, and guardrails for Federated Audience Composition
exl-id: 661a838f-146e-4d68-bb2d-319827caee3a
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
* Google Big Query
* Snowflake
* Vertica Analytics

Learn how to create a connection with these systems in [this page](../connections/connections.md).

## Sandboxes

When purchasing the Federated Audience Composition add-on, you are entitled to two sandboxes. For any additional sandbox provisioning requests, contact your Adobe representative.

## Permissions {#permissions}

To access Federated Audience Composition, users must be added to the sandbox-specific product profile created upon purchase and assigned the **[!UICONTROL Manage Federated Data]** permission. [Learn more](feature-access.md)

## IP allow-listing {#ip}

To securely enable Federated Audience Composition to access your databases, you must authorize the IP addresses of the Federated Audience Composition servers that will access them. These IP addresses are displayed when adding a federated database in the Adobe Experience Platform user interface. [Learn more](../connections/connections.md)

Add these IP addresses to your allow list to grant access for Federated Audience Composition.

## Guardrails & limitations {#fac-guardrails}

* Federated Audience Composition is currently unavailable to customers [ingesting health data](https://experienceleague.adobe.com/en/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield){target="_blank"}. [Learn more](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/audiences-profiles-identities/audiences/about-audiences){target="_blank"}

<!--
* Federated Audience Composition is compatible with Privacy & Security Shield and can be used in all verticals except for healthcare industries. Currently, Federated Audience Composition cannot be licensed to customers looking to ingest health data. [Learn more](https://experienceleague.adobe.com/en/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield){target="_blank"}-->

* Entitlements, product limitations and performance guardrails listed in the [Adobe Real-Time Customer Data Platform documentation](https://experienceleague.adobe.com/en/docs/experience-platform/profile/guardrails){target="_blank"} apply to this add-on.
