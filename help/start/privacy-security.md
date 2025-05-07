---
title: Privacy and Security in Federated Audience Composition
description: Learn how Federated Audience Composition deals with privacy and security for user data.
---

# Privacy and security in Federated Audience Composition

Federated Audience Composition complies with 

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