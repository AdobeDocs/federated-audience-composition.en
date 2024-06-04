---
title: New file
description: Description
keywords: new file, add file, file
---

# New file {#new}

## Learn more {#learn}

<!-- Workflow + Workflow activities-->

>[!CONTEXTUALHELP]
>id="dc_workflow_creation_properties"
>title="Workflow properties"
>abstract="In this screen, choose the template to use to create the workflow and specify a label. Expand the ADDITIONAL OPTIONS section to configure more settings such as the workflow internal name, its folder, timezone, and supervisor group. It is highly recommended to select a supervisor group so that operators are alerted if an error occurs."

>[!CONTEXTUALHELP]
>id="dc_workflow_settings_error"
>title="Error management settings"
>abstract="In this section, you can define how the workflow should manage errors during its execution. You can choose to pause the process, ignore a certain number of errors, or stop the workflow execution."

>[!CONTEXTUALHELP]
>id="dc_workflow_settings_execution"
>title="Execution settings"
>abstract="In this section, you can configure settings related to the execution of the worklow, such the number of days the workflow history is kept."

>[!CONTEXTUALHELP]
>id="dc_workflow_settings_segmentation"
>title="Segmentation settings"
>abstract="In this section, you can select the targeting dimension to target profiles in the workflow, and choose to keep the worklow results between two executions. This option should be used for testing purposes only and must never be enabled in a production workflow."


<!-- Not Supported in FAC - to remove -->
<!--
>[!CONTEXTUALHELP]
>id="dc_orchestration_query_enrichment_noneditable"
>title="Activity non editable"
>abstract="When a **Query** or an **Enrichment** activity is configured with additional data in the console, the enrichment data is taken into account in Campaign Web and passed into the outbound transition, but it cannot be edited."
-->




<!-- Not Supported in FAC - to remove -->
<!--

>[!CONTEXTUALHELP]
>id="dc_orchestration_build_audience"
>title="Build audience activity"
>abstract="The **Build audience** activity allows you to define the audience that will enter the workflow. When sending messages in the context of a workflow, the message audience is not defined in the channel activity, but in the **Build audience** activity."

>[!CONTEXTUALHELP]
>id="dc_orchestration_build_audience_dimension"
>title="Select the targeting dimension"
>abstract="The targeting dimension lets you define the population targeted by the operation: recipients, contract beneficiaries, operator, subscribers, etc. By default, for emails and SMS, the target is selected from the Recipients built-in table. For Push notifications, the default target dimension is Subscriber applications."
-->


>[!CONTEXTUALHELP]
>id="dc_orchestration_and-join"
>title="AND-join activity"
>abstract="The **And-join** activity allows you to synchronize multiple execution branches of a workflow. It is triggered once all of the preceding activities have finished. This allows you to make sure that certain activities are finished before continuing to execute the workflow."

>[!CONTEXTUALHELP]
>id="dc_orchestration_and-join_merging"
>title="Configure the AND-join activity"
>abstract="Select which activities you want to join. In the **Primary set** drop-down, choose which inbound transition population you want to keep."



<!-- Not Supported in FAC - to remove -->
<!--

>[!CONTEXTUALHELP]
>id="dc_orchestration_email"
>title="Email activity"
>abstract="The Email activity facilitates email sending within your workflow, allowing for both one-time and recurring messages. It serves to automate the process of sending emails to a target calculated within the same workflow. You can combine channel activities into the workflow canvas to create cross-channel workflows that can trigger actions based on customer behavior and data."


>[!CONTEXTUALHELP]
>id="dc_orchestration_sms"
>title="SMS activity"
>abstract="The SMS activity facilitates SMS sending within your workflow, allowing for both one-time and recurring messages. It serves to automate the process of sending SMS to a target calculated within the same workflow. You can combine channel activities into the workflow canvas to create cross-channel workflows that can trigger actions based on customer behavior and data."

>[!CONTEXTUALHELP]
>id="dc_orchestration_push_ios"
>title="Push iOS activity"
>abstract="The Push iOS activity streamlines the process of sending iOS Push notifications as part of your workflow. It enables the delivery of both one-time and recurring messages, automating the sending iOS Push notifications to a predefined target within the same workflow. You can combine channel activities into the workflow canvas to create cross-channel workflows that can trigger actions based on customer behavior and data."

>[!CONTEXTUALHELP]
>id="dc_orchestration_push_android"
>title="Push Android activity"
>abstract="The Push Android activity streamlines the process of sending Android Push notifications as part of your workflow. It enables the delivery of both one-time and recurring messages, automating the sending Android Push notifications to a predefined target within the same workflow. You can combine channel activities into the workflow canvas to create cross-channel workflows that can trigger actions based on customer behavior and data."
-->


<!-- Not Supported in FAC - to remove -->
<!--
>[!CONTEXTUALHELP]
>id="dc_orchestration_fork"
>title="Fork activity"
>abstract="The **Fork** activity allows you to create outbound transitions to start several activities at the same time."


>[!CONTEXTUALHELP]
>id="dc_orchestration_fork_transitions"
>title="Fork activity transitions"
>abstract="By default, two transitions are created with a **Fork** activity. Click the **Add transition** button to define an additional outbound transition, and enter its label."

>[!CONTEXTUALHELP]
>id="dc_orchestration_wait"
>title="Wait activity"
>abstract="The **Wait** activity is used to delay the transition from an activity to another."
-->


<!-- Datamodels-->

>[!CONTEXTUALHELP]
>id="dc_model_menu"
>title="Work with models"
>abstract="Schemas and datamodels are listed in this screen. You can create schemas and datamodels from the Create button."

>[!CONTEXTUALHELP]
>id="dc_datamodel_add_schema"
>title="Select schemas"
>abstract="Select the schemas for the datamodel."


>[!CONTEXTUALHELP]
>id="dc_datamodel_add_audience"
>title="Select an audience"
>abstract="Select the audience for the datamodel."

>[!CONTEXTUALHELP]
>id="dc_datamodel_properties"
>title="Datamodel properties"
>abstract="Enter the label of the datamodel."

<!-- Schemas-->


>[!CONTEXTUALHELP]
>id="dc_schema_create_select_tables"
>title="Select tables"
>abstract="Select the tables to add for the datamodel."

>[!CONTEXTUALHELP]
>id="dc_schema_create_key"
>title="Key"
>abstract="Select a key for data reconciliation."

>[!CONTEXTUALHELP]
>id="dc_schema_edit_description"
>title="Schema description"
>abstract="The schema description lists columns, types and labels. You can also check the reconciliation key for the schema. To update the schema definition, click the pencil icon."

>[!CONTEXTUALHELP]
>id="dc_schema_filter_sources"
>title="Select the source database to filter"
>abstract="You can filter the schemas based on their source. Select one or several Federated Databases to displays their schemas."



<!-- Connections / Federated Databases-->


>[!CONTEXTUALHELP]
>id="dc_connection_federated_database_menu"
>title="Federated Databases"
>abstract="Existing connections to Federated Databases are listed in this screen. To create a new connection, click the **Add federated database** button."


>[!CONTEXTUALHELP]
>id="dc_connection_federated_database_properties"
>title="Federated Database properties"
>abstract="Enter the name of the new Federated Database, and select its type."


>[!CONTEXTUALHELP]
>id="dc_connection_federated_database_details"
>title="Federated Database details"
>abstract="Enter the settings to connect to the new Federated Database. Use the **Test connection** button to validate your configuration."

<!-- Destination -->


>[!CONTEXTUALHELP]
>id="dc_new_destination"
>title="Create a destination"
>abstract="Enter the settings to connect to the new Federated Database. Use the **Connect to destination** button to validate your configuration."
