---
audience: end-user
title: Use the Save audience activity
description: Learn how to use the Save audience activity
exl-id: fa67b1ee-8de6-4a71-b597-ade3f5587a38
---
# Save audience {#save-audience}

>[!CONTEXTUALHELP]
>id="dc_orchestration_save_audience"
>title="Save an audience"
>abstract="Use this activity to create a new audience from the population computed upstream in the composition. The audiences created are added to the list of audiences, and available via the **Audiences** menu."

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveaudience_outbound"
>title="Generate outbound transition"
>abstract="Use this option option if you want to add a transition after the **Save audience** activity."

>[!CONTEXTUALHELP]
>id="dc_orchestration_save_audience_primary_identity"
>title="Primary identity field"
>abstract="Select the primary identity to use for profiles."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity#define-a-identity-field" text="Learn more in Experience Platform documentation"

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveaudience_namespace"
>title="Identity namespace"
>abstract="Select the namespace to use for profiles."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/namespaces" text="Learn more in Experience Platform documentation"

>[!IMPORTANT]
>
>To use the save audience activity, your audience must use a **timestamp ordered** merge policy. If your audience uses a **dataset precedence** merge policy, please contact Adobe Customer Care in order to proceed.
>
>For more information on merge policies, please read the [merge policies overview](https://experienceleague.adobe.com/en/docs/experience-platform/profile/merge-policies/overview).

The **[!UICONTROL Save audience]** activity allows you to create a new audience from the population computed upstream in a composition. The audiences created are added to the list of Adobe Experience Platform audiences, and are made available via the **Audiences** menu. [Learn how to work with audiences](../../start/audiences.md)

This activity is essentially used to keep population groups computed in the same composition, by converting them into reusable audiences. Connect it to other targeting activities such as a **Build audience** or a **Combine** activity. 

The **[!UICONTROL Save Audience]** activity generates a new audience schema and associated dataset, which may contain personally identifiable information (PII) or protected health information (PHI). After the audience is created, please work with your administrator to ensure the appropriate data governance labels are applied in accordance to your organization's data policies. For more information about how to apply data usage labels, please read the [data usage labels user guide](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/user-guide).

## Configure the Save audience activity {#save-audience-configuration}

Follow these steps to configure the **Save audience** activity:

1. Add a **Save audience** activity to your composition.

    ![](../assets/save-audience.png)

1. Specify the label of the audience to create.

    >[!IMPORTANT]
    >
    >The audience label must be unique within the current sandbox. It cannot be the same label as any existing audience. 

1. Use the Audience Mappings section to select the fields you want to bring over with the newly created audience. To do this, click **Add Audience Mapping** then choose the source and target audience fields.

    Repeat the operation to add as many audience mappings as needed.

1. Select the primary identity and namespace to use to identify the targeted profiles in the database:

    * **Primary identity field**: Select the field to use to identify the profiles. For example, its email address or phone number.
    * **Identity namespace**: Select the namespace to use to identity the profiles, i.e. the type of data to use as identification key. For example, if the email address has been selected as primary identity field, the identity namespace **Email** should be selected. If the unique identifier is the phone number, then the identity namespace **Phone** should be selected.

## Access your audience in Adobe Experience Platform {#access-audience}

After executing the composition, the resulting audience is saved in Adobe Experience Platform as an external audience, and available in Adobe Real-Time CDP and/or Adobe Journey Optimizer within Audience Portal. For more information on Audience Portal, please read the [Audience Portal overview](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/audience-portal){target="_blank"}.

The created audience includes all the fields selected in the Audience Mappings section. You can target this audience in Journey Optimizer or activate it to any destination supported by Adobe Experience Platform.

[Learn more in Adobe Experience Platform documentation](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/audience-portal){target="_blank"}

<!--

## Example{#save-audience-example}

The following example illustrates a simple audience update from targeting. A scheduler is added to run the workflow once a month. A query recovers all the profiles subscribed to the different application services available. The **Save audience** activity updates the audience by deleting profiles that have unsubscribed from the service since the last workflow execution and by adding the newly subscribed profiles.
-->
