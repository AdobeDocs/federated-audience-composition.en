---
title: New file
description: Description
keywords: new file, add file, file
---

# New file {#new}

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



>[!CONTEXTUALHELP]
>id="dc_orchestration_reconciliation_field"
>title="Reconciliation select field"
>abstract="Reconciliation select field" 

>[!CONTEXTUALHELP]
>id="dc_orchestration_reconciliation_condition"
>title="Reconciliation create condition"
>abstract="Reconciliation create condition" 

>[!CONTEXTUALHELP]
>id="dc_orchestration_reconciliation_complement"
>title="Reconciliation generate complement"
>abstract="Reconciliation generate complement" 


>[!CONTEXTUALHELP]
>id="dc_orchestration_reconciliation_targeting"
>title="Targeting dimension"
>abstract="Select the new targeting dimension. A dimension lets you define the targeted population: recipients, app subscribers, operators, subscribers, etc. By default, the current targeting dimension is selected." 

>[!CONTEXTUALHELP]
>id="dc_orchestration_reconciliation_rules"
>title="Reconciliation rules"
>abstract="Select reconciliation rules to use for the deduplication. To use attributes, select the **Simple attributes** option and choose the source and destination fields. To create your own reconciliation condition using the query modeler, select the **Advanced reconciliation conditions** option."

>[!CONTEXTUALHELP]
>id="dc_orchestration_reconciliation_targeting_selection"
>title="Select the targeting dimension"
>abstract="Select the targeting dimension for your inbound data to reconcile with." 

>[!CONTEXTUALHELP]
>id="dc_orchestration_keep_unreconciled_data"
>title="Keep unreconciled data"
>abstract="By default, non reconciled data are kept in the outbound transition and available in the worktable for future use. To remove unreconciled data, desactivate the **Keep unreconciled data** option." 

>[!CONTEXTUALHELP]
>id="dc_orchestration_reconciliation_attribute"
>title="Reconciliation attribute"
>abstract="Select the attribute to use to reconciliate data, and click Confirm." 



<!-- Not Supported in FAC - to remove -->
<!--
>[!CONTEXTUALHELP]
>id="dc_orchestration_query_enrichment_noneditable"
>title="Activity non editable"
>abstract="When a **Query** or an **Enrichment** activity is configured with additional data in the console, the enrichment data is taken into account in Campaign Web and passed into the outbound transition, but it cannot be edited."
-->

>[!CONTEXTUALHELP]
>id="dc_orchestration_change_dimension"
>title="Change dimension activity"
>abstract="This activity allows you to change the targeting dimension as you are building an audience. It shifts the axis depending on the data template and the input dimension. For example, you can switch from the "contracts" dimension to the "clients" dimension."


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
>id="dc_orchestration_combine"
>title="Combine activity"
>abstract="The **Combine** activity allows you to perform segmentation on your inbound population. You can thus combine several populations, exclude part of it, or only keep data common to several targets."

>[!CONTEXTUALHELP]
>id="dc_orchestration_combine_options"
>title="Select the segmentation type"
>abstract="Select how to combine audiences: union, intersection or exclusion."

>[!CONTEXTUALHELP]
>id="dc_orchestration_combine_reconciliation"
>title="Reconciliation options"
>abstract="Select the **Reconciliation type** to define how to handle duplicates."

>[!CONTEXTUALHELP]
>id="dc_orchestration_combine_sets"
>title="Select sets to combine"
>abstract="In the **Sets to join** section, select the **Primary set** from the inbound transitions. This is the set from which elements are excluded. The other sets match elements before being excluded from the primary set."

>[!CONTEXTUALHELP]
>id="dc_orchestration_combine_exclusion"
>title="Exclusion rules"
>abstract="When necessary, you can manipulate inbound tables. Indeed, to exclude a target from another dimension, this target has to be returned to the same targeting dimension as the main target. To do this, click Add a rule in the Exclusion rules section and specify the dimension change conditions. Data reconciliation is carried out either via an attribute or a join."

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

>[!CONTEXTUALHELP]
>id="dc_orchestration_enrichment"
>title="Enrichment activity"
>abstract="The **Enrichment** activity allows you to enhance the targeted data with additional information from the database. It is commonly used in a workflow after segmentation activities."


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

>[!CONTEXTUALHELP]
>id="dc_orchestration_split"
>title="Split activity"
>abstract="The **Split** activity allows you to segment incoming populations into multiple subsets based on different selection criteria, such as filtering rules or population size."


>[!CONTEXTUALHELP]
>id="dc_orchestration_split_segments"
>title="Segments for split activity"
>abstract="Add as many subsets as desired to segment the incoming population.<br/></br>When the **Split** activity is executed, the population is segmented across the different subsets in the order they are added to the activity. Before starting your workflow, ensure that you have ordered the subsets in the order that suits your needs using the arrow buttons." 

>[!CONTEXTUALHELP]
>id="dc_orchestration_split_filter"
>title="Split activity filter"
>abstract="To apply a filtering condition to the subset, click **[!UICONTROL Create filter]** and configure the desired filtering rule using the query modeler. For example, include profiles from the incoming population whose email address exist in the database."

>[!CONTEXTUALHELP]
>id="dc_orchestration_split_limit"
>title="Split activity limit"
>abstract="To limit the number of profiles selected by the subset, toggle on the **[!UICONTROL Enable limit]** option, and specify the number or percentages of the population to include."

>[!CONTEXTUALHELP]
>id="dc_orchestration_split_sorting"
>title="Split activity sorting"
>abstract="When setting a population limit for a subset, you can rank the selected profiles based on a specific profile attribute, in ascending or descending order. To do this, toggle on the **Enable sorting** option. For instance, you can restrict a subset to include only the top 50 profiles with the highest purchase amount."

>[!CONTEXTUALHELP]
>id="dc_orchestration_split_complement"
>title="Split generate complement"
>abstract="Once that you have configured all the subsets, you can select the remaining population that did not match any of the subsets and include them into an additional outbound transition. To do this, toggle on the **Generate complement** option." 

>[!CONTEXTUALHELP]
>id="dc_orchestration_split_generatesubsets"
>title="Generate all subsets in the same table"
>abstract="Toggle on this option to group all the subsets into a single output transition."

>[!CONTEXTUALHELP]
>id="dc_orchestration_split_emptytransition"
>title="Skip empty transition"
>abstract="Skip empty transition."

<!-- Not Supported in FAC - to remove -->
<!--
>[!CONTEXTUALHELP]
>id="dc_orchestration_end"
>title="End activity"
>abstract="The **End** activity allows you to graphically mark the end of a workflow. This activity has no functional impact and is therefore optional."

>[!CONTEXTUALHELP]
>id="dc_orchestration_scheduler"
>title="Scheduler activity"
>abstract="The **Scheduler** activity allows you to schedule when the workflow gets started. This activity should be considered as a scheduled start. It can only be used as the first activity of the workflow."

>[!CONTEXTUALHELP]
>id="dc_orchestration_schedule_options"
>title="Scheduler options"
>abstract="Define the frequency of the scheduler. It can be executed at a specific moment, once or several times a day, week or month."

>[!CONTEXTUALHELP]
>id="dc_orchestration_schedule_validity"
>title="Scheduler validity"
>abstract="You can define a validity period for the scheduler. It can be permanent (default), or can be valid until a specific date."

--> 
>[!CONTEXTUALHELP]
>id="dc_orchestration_deduplication"
>title="Deduplication activity"
>abstract="The **Deduplication** activity allows you to delete duplicates in the results of the inbound activities. It is mostly used following targeting activities, and before activities that allow the use of targeted data."

>[!CONTEXTUALHELP]
>id="dc_orchestration_reconciliation"
>title="Reconciliation activity"
>abstract="The **Reconciliation** activity is a **Targeting** activity which allows you to define the link between the data in the Adobe Campaign database and the data in a work table. For example, the **Reconciliation** activity can be placed after a **Load file** activity to import non-standard data into the database. In this case, the **Reconciliation** activity lets you define the link between the data in the Adobe Campaign database and the data in the external table." 

>[!CONTEXTUALHELP]
>id="dc_orchestration_save_audience"
>title="Save an audience"
>abstract="Use this activity to update an existing audience or create a new audience from the population computed upstream in the workflow. The audiences created are added to the list of audiences, and available via the **Audiences** menu."

>[!CONTEXTUALHELP]
>id="dc_orchestration_enrichment_data"
>title="Enrichment activity"
>abstract="Once enrichment data has been added to the workflow, it can be used in the activities added after the Enrichment activity to segment customers into distinct groups based on their behaviors, preferences, and needs, or to create personalized marketing messages and campaigns that are more likely to resonate with your target audience."

>[!CONTEXTUALHELP]
>id="dc_orchestration_deduplication_fields"
>title="Fields to identify duplicates"
>abstract="In the **Fields to identify duplicates** section, click the **Add attribute** button to specify the fields for which the identical values allow the duplicates to be identified, such as: email address, first name, last name, etc. The order of the fields allows you to specify those to process first."


>[!CONTEXTUALHELP]
>id="dc_orchestration_deduplication_complement"
>title="Generate a complement"
>abstract="You can generate an additional outbound transition with the remaining population, which was excluded as a duplicate. To do this, toggle on the **Generate complement** option"

>[!CONTEXTUALHELP]
>id="dc_orchestration_deduplication_settings"
>title="Deduplication settings"
>abstract="To delete duplicates in the incoming data, define the deduplication method in the fields below. By default, only one record is kept. You should also select the deduplication mode based on an expression or an attribute. By default, the record to keep out of the duplicates is randomly selected."

>[!CONTEXTUALHELP]
>id="dc_orchestration_dimension_complement"
>title="Generate a complement"
>abstract="You can generate an additional outbound transition with the remaining population, which was excluded as a duplicate. To do this, toggle on the **Generate complement** option"


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
