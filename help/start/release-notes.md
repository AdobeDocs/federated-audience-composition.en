---
title: What's new in Federated Audience Composition
description: Latest updates and release notes
badge: label="Limited availability" type="Informative"
---

# What's new {#rn-new}

## What is Federated Audience Composition {#rn-fac}


Federated Audience Composition is a capability that allows enterprises to compose data for better utilization across various use cases. With this new approach, customers of Adobe Real-Time CDP and/or Adobe Journey Optimizer federate datasets directly from their existing data warehouse to enrich Adobe Experience Platform audiences and attributes all in one system.
* This differs from the traditional approach of ingesting raw datasets and/or audiences into Adobe Experience Platform, which requires a copy of data from the data warehouse. With Federated Audience Composition, customers can reduce the volume of data copied from the warehouse into Adobe Experience Platform by pulling specific audiences and attributes out of the warehouse that are needed for certain segmentation or activation use cases and ensure sensitive data is not persisted outside the warehouse.
* Through a marketing-friendly UI, customers can create segment rules that query the warehouse for a list of users that qualify for a specific segment needed for marketing campaigns, access existing audiences in the warehouse for activation, or enrich Adobe Experience Platform audiences with additional datapoints that exist in the warehouse

>[!AVAILABILITY]
>
>Federated Audience Composition is currently only available for a set of organizations (Limited Availability). To gain access, contact your Adobe representative.
>
>For now, the feature is unavailable for customers who have purchased the Adobe **Healthcare Shield** and **Privacy and Security Shield** add-on offerings.

## Use cases {#rn-uc}



![diagram](assets/fac-use-cases.png)



## Prerequisites 

* Your IP addresses must be added to the allow list to enable access to your data warehouse and use Federated Audience Composition. To add your IP addresses to the allow list, contact your Adobe representative.


## Guardrails and limitations {#guardrails}


Entitlements, product limitations and performance guardrails are listed in the [Guardrails for Real-time Customer Profile data before starting](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html){target="_blank"}.