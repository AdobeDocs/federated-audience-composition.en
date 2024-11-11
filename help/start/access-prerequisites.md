---
title: Prerequisites and guardrails for Federated Audience Composition
description: Learn prerequisites, permissions, and guardrails for Federated Audience Composition
badge: label="Limited availability" type="Informative"
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

## Permissions {#permissions}

When you purchase the Federated Audience Composition add-on, a product profile is created for each active sandbox at that time. This product profile is created in the Admin Console under the **Adobe Experience Platform** product card and follows this naming convention: `ACP_FAC - <<SandboxName>> - admin.` To access the Federated Audience Composition for a specific sandbox, users must be added to the product profile created for that sandbox.

For example, if a new sandbox named "fac-test" is activated, a corresponding product profile "ACP_FAC - fac-test - admin" is created. In order to access Federated Audience Composition with this sandbox, users need to be added to this product profile.

## IP allow-listing {#ip}

To securely enable Federated Audience Composition to access your databases, contact your Adobe representative to get the IP addresses of the Federated Audience Composition servers that will access them.

Add these IP addresses to your allow list to grant access for Federated Audience Composition.

## Guardrails & limitations {#fac-guardrails}

* Federated Audience Composition is currently unavailable to customers [ingesting health data](https://experienceleague.adobe.com/en/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield){target="_blank"} and to Adobe Journey Optimizer Privacy and Security Shield customers. [Learn more](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/audiences-profiles-identities/audiences/about-audiences){target="_blank"}.

<!--
* Federated Audience Composition is compatible with Privacy & Security Shield and can be used in all verticals except for healthcare industries. Currently, Federated Audience Composition cannot be licensed to customers looking to ingest health data. [Learn more](https://experienceleague.adobe.com/en/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield){target="_blank"}-->

* Entitlements, product limitations and performance guardrails listed in the [Adobe Real-Time Customer Data Platform documentation](https://experienceleague.adobe.com/en/docs/experience-platform/profile/guardrails){target="_blank"} apply to this add-on.
