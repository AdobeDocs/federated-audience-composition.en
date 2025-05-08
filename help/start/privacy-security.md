---
title: Privacy and Security in Federated Audience Composition
description: Learn how Federated Audience Composition deals with privacy and security for user data.
---

# Privacy and security in Federated Audience Composition

Federated Audience Composition complies with numerous security practices to ensure your data is kept as securely as possible.

## Privacy Service {#privacy}

Federated Audience Composition provides the federated data for Adobe Experience Platform and Adobe Journey Optimizer to use. However, Federated Audience Composition does **not** store any of the customer data from any of the data warehouses. As a result, you can use Adobe Experience Platform Privacy Service to comply with data subject and data delete requests.

For example, after creating an audience by using the save activity block in the composition canvas, the resulting audience is stored in the data lake in Adobe Experience Platform as an external audience. This external audience is marked with its identity field and identity namespace. As a result, you can use Privacy Service to access and remove those profiles with an external audience.

Alternatively, after creating a profile enrichment by using the save profile activity in the composition canvas, the resulting enrichment is stored in Adobe Experience Platform as a profile-enabled schema and profile-enabled dataset. This enrichment data is marked with an identity field and identity namespace. As a result, you can use Privacy Service to access and clean these profiles.

For more information on Privacy Service, please read the [Privacy Service overview](https://experienceleague.adobe.com/en/docs/experience-platform/privacy/home){target="_blank"}.

## Consent policy enforcement {#consent}

Federated Audience Composition, through Adobe Experience Platform, offers tools that let you automate your consent enforcement, ensuring you are activating audiences based on the consent provided to your customers.

For example, after creating an audience by using the save activity block in the composition canvas, the resulting audience is stored in the data lake in Adobe Experience Platform as an external audience. Experience Platform automatically supports consent validation during activation. For more information, please read the [Segmentation Service FAQ](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/faq#consent){target="_blank"}.

Alternatively, after creating a profile enrichment by using the save profile activity in the composition canvas, the resulting enrichment is stored in Adobe Experience Platform as a profile-enabled schema and profile-enabled dataset. For existing profiles, the available consent attributes will automatically be honored during activation. For new profiles, consent attributes that are provided during the profile ingestion will automatically be honored during activation. For more information on applying consents to profiles, please read the [consents and preferences field group guide](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/profile/consents){target="_blank"}.

For more information on applying consents, please read the [manage policies UI guide](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/policies/user-guide#consent-policy){target="_blank"}.

## Data Lifecycle {#data-lifecycle}

Since Federated Audience Composition does **not** store any of the customer data from any of the data warehouses, you can use Adobe Experience Platform to handle the data lifecycle. With Advanced Data Lifecycle Management, you can manage your data lifecycle at both a dataset and record level.

For example, after creating an audience by using the save activity block in the composition canvas, the resulting audience is stored in the data lake in Adobe Experience Platform as an external audience. Since this data is **not** stored in Federated Audience Composition, the audience data and the corresponding datasets will automatically be deleted when the audience is delete in Audience Portal.

Alternatively, after creating a profile enrichment by using the save profile activity in the composition canvas, the resulting enrichment is stored in Adobe Experience Platform as a profile-enabled schema and profile-enabled dataset. As a result, you can Data Lifecycle to access and clean the profiles.

For more information on using Data Lifecycle, please read the [Data Lifecycle overview](https://experienceleague.adobe.com/en/docs/experience-platform/data-lifecycle/home){target="_blank"}.

## Data usage labels {#data-usage-labels}

Data usage labels let you categorize datasets and fields based on the governance policies that apply to that data. After you've created an audience using compositions, you can apply the appropriate data labels on the resulting schema to ensure it abides to the required usage restrictions.

For more information on using data labels, please read the [data usage labels overview](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview){target="_blank"}.

## Encryption {#encryption}

Flexible Audience Composition provides encryption through data-at-rest encryption, data-in-transit encryption, and customer-managed keys.

### Data-at-rest encryption {#data-at-rest}

Data at rest refers to the customer data that is used within Federated Audience Composition.

The data is encrypted by the cloud service provider, and is used in Federated Audience Composition in its encrypted form.

For more information on how Adobe handles encryption, please read the guide on [data encryption in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/encryption){target="_blank"}.

### Data-in-transit encryption {#data-in-transit}

Data in transit refer to the customer data as it moves from one component to another in Federated Audience Composition.

The data is kept encrypted throughout Federated Audience Composition components using TLS 1.3 over HTTPS.

For more information on how Adobe handles encryption, please read the guide on [data encryption in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/encryption){target="_blank"}.

### Customer managed keys {#customer-managed-keys}

Customer managed keys let you have control of your data, by letting you use your own encryption keys to encrypt your data. Since Federated Audience Composition does **not** store any of the customer data, you can use customer managed keys directly on the resulting audiences and enrichments, since they'll be stored in the data lake on Adobe Experience Platform.

For more information on customer managed keys, please read the [customer managed keys guide](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys/overview){target="_blank"}.

## Audit log {#audit-log}

All create, read, update, and delete operations performed in Federated Audience Composition are logged in the audit trail.

For more information, please read the [Audit Trail overview](/help/admin/audit-trail.md){target="_blank"}.

## Access control {#access-control}

You can control access to Federated Audience Composition at both a field and role based level.

For more information on access control in Federated Audience Composition, please read the [Access Federated Audience Composition guide](/help/start/feature-access.md){target="_blank"}.

## Data localization {#data-localization}

Federated Audience Composition does **not** store any customer data. As a result, you need to ensure that you **only** connect your external databases with the matching sandbox region to keep your data in the same region. If you connect a different region's database to a sandbox, Adobe is **not** responsible for data localization.

## Next steps {#next-steps}

After reading this guide, you have a better understanding about privacy and security features in use for Federated Audience Composition.