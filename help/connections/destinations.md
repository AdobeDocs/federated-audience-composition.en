---
audience: end-user
title: Enrich Adobe Experience Platform audiences with external data
description: Learn how to refine and enrich Adobe Experience Platform audiences with data from your federated databases using the Federated audience composition destination.
badge: label="Limited availability" type="Informative"
exl-id: 03c2f813-21c9-4570-a3ff-3011f164a55e
---
# Enrich Adobe Experience Platform audiences with external data {#connect-aep-fac}

>[!CONTEXTUALHELP]
>id="dc_new_destination"
>title="Create a destination"
>abstract="Enter the settings to connect to the new Federated Database. Use the **[!UICONTROL Connect to destination]** button to validate your configuration."

Adobe Experience Platform allows seamless integration of audiences from the Audience Portal with your external databases using the **Adobe Federated Audience Composition destination**. With this integration, you can leverage existing audiences into compositions and enrich or refine them using data from your external databases to create new audiences.

To do so, you need to setup a new connection in Adobe Experience Platform to the Adobe Federated Audience Composition destination. You can use a scheduler to send a given audience at regular frequencies, select specific attributes to include, such as IDs for data reconciliation. If you have applied governance and privacy policies to your audience, they will be kept and sent back to the audience portal once the audience has been updated.

For instance, if you store customer credit scores in your data warehouse and have an Adobe Experience Platform audience targeting customers interested in a specific product within the last two months, you can refine this audience based on credit scores using the Federated Audience Composition destination. This process allows you to filter the audience to include only profiles with high credit scores without transferring sensitive credit score data from your data warehouse.

The main steps to send Adobe Experience Platform audiences to Adobe Federated Audience Composition are as follows:

1. Access the Adobe Experience Platform Destinations catalog and select the Federated Audience Composition destination.

    In thre right pane, select **[!UICONTROL Configure new destination]**.

    ![](assets/destination-new.png)

1. Provide a name for the new connection and choose the **[!UICONTROL Connection type]** to use and the **[!UICONTROL Federated database]** you want to connect to and click **[!UICONTROL Next]**.

    ![](assets/destination-configure.png)

    The **[!UICONTROL Alerts]** section allows you to enable alerts to receive notifications on the status of the dataflow to your destination. For more information on alerts, see the guide on [subscribing to destinations alerts using the UI](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/alerts).

1. The **[!UICONTROL Governance policy & enforcement actions]** step, you can define your data governance policies and ensure that the data used is compliant when audiences are sent and active.

    When you are finished selecting the desired marketing actions for the destination, click **[!UICONTROL Create]**.

1. The new connection to the destination is created. You can now activate audiences to send over to the destination. To do so, select it from the list and click **[!UICONTROL Next]**

    ![](assets/destination-activate.png)

1. Select the desired audiences that you want to send and click **[!UICONTROL Next]**.

1. Configure the filename and an export schedule for the selected audience(s). 

    ![](assets/destination-schedule.png)

    >[!NOTE]
    >
    >Detailed information on how to configure schedule and filenames is available in Adobe Experience Platform documentation:
    >* [Schedule audience export](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/activate-batch-profile-destinations#scheduling)
    >* [Configure file names](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/activate-batch-profile-destinations#configure-file-names)

1. In the **[!UICONTROL Mapping]** step, select which attribute and identity fields to export for your audience(s). For more information, view the [mapping step](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/activate-batch-profile-destinations#mapping) in the Adobe Experience Platform documentation.

    ![](assets/destination-attributes.png)

1. Review the destination configuration and audience settings, then click **[!UICONTROL Finish]**.

    ![](assets/destination-review.png)

The selected audiences are now activated for the new connection. You can add more audiences to send with this connection by navigating back to the **[!UICONTROL Activate audiences]** page. You cannot remove audiences once they are activated.
