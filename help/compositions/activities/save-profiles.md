---
audience: end-user
title: Use the Save Profiles activity
description: Learn how to use the Save Profiles activity
exl-id: 1c840838-32d5-4ceb-8430-835a235b7436
---
# Save profiles {#save-profile}

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile"
>title="Save Profiles"
>abstract="The Save Profiles activity allows you to enrich Experience Platform profiles by federating data from external warehouses, allowing you to enhance customer profiles with additional attributes. "

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile_aepschemalist"
>title="Select Experience Platform Schema"
>abstract="Choose the Experience Platform schema for the profiles."

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile_primaryidentitynamespace"
>title="Select the Primary identify field"
>abstract="Select the Primary identity to use to identify the targeted profiles in the database."

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile_selectaepschema"
>title="Select Experience Platform Schema"
>abstract="Choose the Experience Platform schema for the profiles."

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile_updatemode"
>title="Save Profile update mode"
>abstract="The available update modes for the save profile activity include full update and incremental update."

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile_updatemode_full"
>title="Full update"
>abstract="The full update mode updates the full set of profiles for enrichment."

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile_updatemode_incremental"
>title="Incremental update"
>abstract="The incremental update mode updates the profiles that have been modified since the last enrichment ran."

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile_primaryidentityfield"
>title="Primary identity field"
>abstract="The primary identity field indicates the source of truth when merging profiles together for the enrichment."

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile_requiredfieldscheck"
>title="Required fields criteria"
>abstract="A required field is an attribute that must be filled out for every profile or record when exporting data. If a required field is missing, the export will not be complete or valid."

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile_primaryidentitycheck"
>title="Primary identity field criteria"
>abstract="The unique identifier for each profile or record. This ensures that every record can be distinctly recognized and matched, preventing the duplication of data."

The **[!UICONTROL Save Profiles]** activity allows you to enrich Adobe Experience Platform profiles with data federated from external warehouses.

This activity is typically used to enhance customer profiles by bringing in additional attributes and insights without physically moving or duplicating the data into the platform.

## Configure the [!UICONTROL Save Profiles] activity {#save-profile-configuration}

>[!IMPORTANT]
>
>The **Save Profiles** activity requires a Profile-enabled schema and dataset. To learn how to enable your dataset to be Profile-enabled, please read the [dataset user guide](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/user-guide#enable-profile){target="_blank"}.

Follow these steps to configure the **[!UICONTROL Save Profiles]** activity:

1. Add a **[!UICONTROL Save Profiles]** activity to your composition.

    ![The Save Profiles button is highlighted within the activities.](../assets/save-profiles/save-profiles.png){width="1500" zoomable="yes"}

1. Specify the label of the profiles to create.

    >[!IMPORTANT]
    >
    >The audience label must be unique within the current sandbox. It cannot be the same label as any existing audience. 

1. Select the Adobe Experience Platform schema you want to use.

    ![The available schemas are displayed.](../assets/save-profiles/select-schema.png){width="1500" zoomable="yes"}

1. Select the dataset that you want to save the enrichment to.

    ![The dataset dropdown is highlighted.](../assets/save-profiles/select-dataset.png){width="300" zoomable="yes"}

1. After selecting the dataset, you can see the primary identity field that will be used to identify profiles in the database.

1. Select **[!UICONTROL Add Fields]** to add the primary and required identity fields.

    ![The Add Fields button is highlighted.](../assets/save-profiles/add-fields.png){width="300" zoomable="yes"}

    You can specify the **Source** field (external data) and the **Destination** field (schema field) for each attribute you want to map.

    ![The Source and Destination fields are highlighted, showing where to create the mapping between the fields](../assets/save-profiles/specify-mapping.png){width="300" zoomable="yes"}

1. You can also specify the update mode for the enrichment.

    ![The update mode types are displayed.](../assets/save-profiles/select-update-mode.png){width="300" zoomable="yes"}

    | Update mode | Description |
    | ----------- | ----------- |
    | Full updates | The full set of profiles is updated for enrichment. |
    | Incremental updates | Only the profiles that have been modified since the last enrichment ran are updated for the enrichment. |

    If you select [!UICONTROL Incremental updates], you also need to choose the last modified date to determine what data is sent.

1. Once configured, select **Start**.
