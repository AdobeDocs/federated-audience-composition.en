---
audience: end-user
title: Work with audiences
description: Learn how to work with audiences
badge: label="Limited availability" type="Informative"
exl-id: c6507624-1dc9-43f9-a3ad-c3dc9689f8c7
---
# Work with audiences {#gs-audiences}

Experience Platform Federated Audience Composition allows you to [create compositions](../compositions/gs-compositions.md), where you can leverage various activities into a visual canvas to create audiences and store them into Adobe Experience Platform Audience Portal.

You can then target these audience in Journey Optimizer or activate them to any destination supported by Adobe Experience Platform.

## Audience creation using compositions {#creation}

To create audiences using Federated Audience composition, you need to create a composition including a **[!UICONTROL Save audience]** activity. This activity allows you to save the audience into Audience Portal, and to select fields from your external databases to include in the audience. [Learn how to configure a Save audience activity](../compositions/activities/save-audience.md)

Audience created using Adobe Federated Data Composition include all the fields selected in the **[!UICONTROL Save audience]** activity, and are stored in Audience Portal alongside all Adobe Experience Platform audiences. 

After executing the composition, the resulting audience is saved in Adobe Experience Platform as an external audience, and available into Adobe Real-Time Customer Data Platorm and/or Adobe Journey Optimizer. 

You can activate these audiences to any destination supported by Adobe Experience Platform. Learn how to work with destinations in [Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/home){target="_blank"} 

>[!NOTE]
>
>Audiences created using Adobe Federated Audience Composition cannot be edited. To make modifications to one of these audiences, you need to create a new audience using a composition.

## Access your audience in Adobe Experience Platform {#access-audience}

Audiences created using Federated Audience Composition are made accessible in Audience Portal, which is accessible from the **Audiences** menu.

The **[!UICONTROL Browse]** tab lists all existing audiences stored into Adobe Experience Platform. You can identify Federated Audience Composition audiences in the list using the **[!UICONTROL Origin]** column or the filters available in the left hand pane.

![](assets/audiences-list.png)

For more information on how to work with audiences in Adobe Experience Platform, refer to [Audience Portal documentation](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/audience-portal){target="_blank"} 

<!-- add link to this donc once published: https://jira.corp.adobe.com/browse/PLAT-198674-->