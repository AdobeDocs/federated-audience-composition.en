---
audience: end-user
title: Activities overview
description: Learn about the different activities and transitions available for use within Federated Audience Composition.
exl-id: 6ef5c165-c4fa-437b-be16-d42cb2f7991b
---
# Activities overview

In Federated Audience Composition, you can add activities and transitions that help define your audience. 

## Activities {#activities}

Activities let you define the components within the audience.

There are **two** different types of activities for use within Federated Audience Composition: targeting activities and flow control activities.

### Targeting activities {#targeting}

Targeting activities let you define what makes up your audience for the composition.

#### Build audience {#build-audience}

>[!CONTEXTUALHELP]
>id="dc_orchestration_build_audience_audienceselector"
>title="Audience"
>abstract="Select your audience."

The **Build audience** activity lets you define your target population for the composition. You can either select an existing audience or use the query modeler to define your own query.

+++ Configuration details

After adding the **Build audience** activity to the composition canvas, give your audience a name. You can now specify if you want to create an audience or use an existing one.

>[!BEGINTABS]

>[!TAB Create new audience]

After selecting **Create audience**, choose the **Schema** for your audience. The schema lets you define the population targeted by the operation, such as recipients, contract beneficiaries, operators, or subscribers. By default, the schema is selected from the recipients.

![](./assets/activities/build-audience-create.png)

After choosing a schema, select **Continue**. You can now define your audience's definition within the Query Modeler. For more information on using the Query Modeler, read the [Query Modeler overview](../query/home.md).

>[!TAB Use existing audience]

After selecting **Read audience**, choose **Continue**. 

![](./assets/activities/build-audience-read.png)

You can now select which audience you want to use for your composition.

>[!ENDTABS]

After you've selected your options, you can choose to **Generate an outbound transition**. Selecting this lets you add an outbound transition that will be activated at the end of the execution of the activity if the audience population is empty. 

+++

#### Change data source {#change-data-source}

The **Change data source** activity lets you change which data source is being used by your composition.

+++ Configuration details

After adding the **Change data source** activity to your composition canvas, you can define the data source that will be used for the composition.

![The data source option is highlighted within the Federated Audience Composition workspace.](./assets/activities/configure.png){zoomable="yes"}{width="70%"}

| Source | Description |
| ------ | ----------- |
| FDA external account | An external cloud database connected to Federated Audience Composition. |

After selecting **[!UICONTROL FDA external account]**, you can choose which external account you want to connect with.

![The popover displaying the external account options is displayed.](./assets/activities/fda-external-account.png){zoomable="yes"}{width="70%"}

+++

#### Change dimension {#change-dimension}

>[!CONTEXTUALHELP]
>id="dc_orchestration_dimension_complement"
>title="Generate a complement"
>abstract="You can generate an additional outbound transition with the remaining population, which was excluded as a duplicate. To do this, toggle on the **[!UICONTROL Generate complement]** option"

>[!CONTEXTUALHELP]
>id="dc_orchestration_change_dimension"
>title="Change dimension activity"
>abstract="This activity allows you to change the schema, also known as targeting dimension, as you are building an audience. It shifts the axis depending on the data template and the input schema. For example, you can switch from the "contracts" schema to the "clients" schema."

The **Change dimension** activity lets you change the schema (also known as the targeting dimension) of your composition.

+++ Configuration details

After adding the **Change dimension** activity to your composition canvas, you can define a new schema to replace the previous schema. During this schema change, all records will be kept. 

![](./assets/activities/change-dimension.png)

After you execute the composition, your results will be updated.

+++

#### Combine {#combine}

>[!CONTEXTUALHELP]
>id="dc_orchestration_combine"
>title="Combine activity"
>abstract="The **Combine** activity allows you to perform segmentation on your inbound population. You can thus combine several populations, exclude part of it, or only keep data common to several targets."

>[!CONTEXTUALHELP]
>id="dc_orchestration_intersection_merging_options"
>title="Intersection merging options"
>abstract="The **intersection** allows you to keep only the elements common to the different inbound populations in the activity. In the **Sets to join** section, check all the previous activities you want you join."

>[!CONTEXTUALHELP]
>id="dc_orchestration_exclusion_merging_options"
>title="Exclusion merging options"
>abstract="The **Exclusion** allows you to exclude elements from one population according to certain criteria. In the **Sets to join** section, check all the previous activities you want you join."

>[!CONTEXTUALHELP]
>id="dc_orchestration_combine_options"
>title="Select the segmentation type"
>abstract="Select how to combine audiences: union, intersection, or exclusion."

>[!CONTEXTUALHELP]
>id="dc_orchestration_intersection_reconciliation_options"
>title="Intersection reconciliation options"
>abstract="Select the reconciliation type to define how duplicates are handled."

>[!CONTEXTUALHELP]
>id="dc_orchestration_combine_reconciliation"
>title="Reconciliation options"
>abstract="Select the **Reconciliation type** to define how to handle duplicates."

>[!CONTEXTUALHELP]
>id="dc_orchestration_exclusion_options"
>title="Exclusion rules"
>abstract="When necessary, you can manipulate inbound tables. Indeed, to exclude a target from another schema, also known as targeting dimension, this target has to be returned to the same schema as the main target. To do this, select **Add a rule** in the E**xclusion rules** section and specify the schema change conditions. Data reconciliation is carried out either via an attribute or a join."

>[!CONTEXTUALHELP]
>id="dc_orchestration_combine_sets"
>title="Select sets to combine"
>abstract="In the **Sets to join** section, select the **Primary set** from the inbound transitions. This is the set from which elements are excluded. The other sets match elements before being excluded from the primary set."

>[!CONTEXTUALHELP]
>id="dc_orchestration_combine_exclusion"
>title="Exclusion rules"
>abstract="When necessary, you can manipulate inbound tables. Indeed, to exclude a target from another schema, also known as targeting dimension, this target has to be returned to the same schema as the main target. To do this, select **Add a rule** in the **Exclusion rules** section and specify the schema change conditions. Data reconciliation is carried out either via an attribute or a join."

>[!CONTEXTUALHELP]
>id="dc_orchestration_combine_complement"
>title="Combine generate complement"
>abstract="Toggle on the **Generate complement** option to process the remaining population in an additional transition." 

>[!NOTE]
>
>The **Combine** activity **must** be placed after another activity and **cannot** be placed at the beginning of the composition.

The **Combine** activity lets you join multiple audiences in various ways - a union, intersection, or exclusion.

- **Union**: A union combines the different audiences into a single audience. This is equivalent to an OR operation.
- **Intersection**: An intersection combines the different audiences into a single audience with only the **shared** content being preserved. This is equivalent to an AND operation.
- **Exclusion**: An exclusion combines the different audiences into a single audience without the specified exclusion rules. This is equivalent to a XOR operation.

+++ Configuration details

After adding multiple activities to form at least **two** different branches, add the **Combine** activity to the end of one of the branches. You can now choose one of the combine options - Union, Intersection, or Exclusion.

![](./assets/activities/combine.png)

>[!BEGINTABS]

>[!TAB Union]

![](./assets/activities/combine-union.png)

If you select **Union**, you'll need to choose the **Reconciliation type** for the combine activity. The reconciliation type lets you define how duplicate entries are handled.

- **Keys only**: Selecting **Keys only** keeps **one** element when multiple elements have the same key. You can only use this option if the incoming populations are homogenous. 
- **A selection of columns**: Selecting **A selection of columns** lets you define a list of columns on which data reconciliation is applied. You can select the primary set of data that contains the source data, followed by the columns to be used for the join.

>[!TAB Intersection]

![](./assets/activities/combine-intersection.png)

If you select **Intersection**, you'll need to choose the **Reconciliation type** for the combine activity. The reconciliation type lets you define how duplicate entries are handled.

- **Keys only**: Selecting **Keys only** keeps **one** element when multiple elements have the same key. You can only use this option if the incoming populations are homogenous. 
- **A selection of columns**: Selecting **A selection of columns** lets you define a list of columns on which data reconciliation is applied. 

After configuring your reconciliation type, you can also select the **Generate complement** option. Generating a complement processes the remaining population and contains the data **not** included as part of the intersection. An additional outbound transition will be added to the activity.

>[!TAB Exclusion]

![](./assets/activities/combine-exclusion.png)

If you select **Exclusion**, you'll need to select the **Primary set** from your inbound transitions. This represents the sets from which the elements will be excluded.

After choosing your primary set, you can set up your **Exclusion rules**. You can either select **Match by attribute** or **Join**.

Once you've configured your exclusion rules, you can also select the **Generate complement** option. Generating a complement processes the remaining population and contains the data **not** included as part of the exclusion. An additional outbound transition will be added to the activity.

+++

#### Deduplication {#deduplication}

>[!CONTEXTUALHELP]
>id="dc_orchestration_deduplication_fields"
>title="Fields to identify duplicates"
>abstract="In the **[!UICONTROL Fields to identify duplicates]** section, select the **[!UICONTROL Add attribute]** button to specify the fields for which the identical values allow the duplicates to be identified, such as: email address, first name, last name, etc. The order of the fields allows you to specify those to process first."

>[!CONTEXTUALHELP]
>id="dc_orchestration_deduplication"
>title="Deduplication activity"
>abstract="The **Deduplication** activity allows you to delete duplicates in the results of the inbound activities. It is mostly used following targeting activities, and before activities that allow the use of targeted data."

>[!CONTEXTUALHELP]
>id="dc_orchestration_deduplication_complement"
>title="Generate a complement"
>abstract="You can generate an additional outbound transition with the remaining population, which was excluded as a duplicate. To do this, toggle on the **[!UICONTROL Generate complement]** option"

>[!CONTEXTUALHELP]
>id="dc_orchestration_deduplication_settings"
>title="Deduplication settings"
>abstract="To delete duplicates in the incoming data, define the deduplication method in the fields below. By default, only one record is kept. You should also select the deduplication mode based on an expression or an attribute. By default, the record to keep out of the duplicates is randomly selected."

The **Deduplication** activity removes any duplicate results within the audience.

+++ Configuration details

>[!NOTE]
>
>If you have multiple inbound transitions, you'll first need to select the **Primary set** from the dropdown.

After adding a **Deduplication** activity, you can choose the fields to identify duplicates. Select **Add attribute** to identify the fields where duplicates may occur.

![](./assets/activities/deduplication.png)

Once you've identified your fields, you can configure your deduplication settings. 

| Setting | Description |
| ------- | ----------- |
| Duplicates to keep | The number of duplicate records to keep. If the value is set to 0, **all** duplicate records will be kept. | 
| Deduplication method | The method to remove the duplicate records. <ul><li>**Random selection**: The removed record is randomly chosen.</li><li>**Using an expression**: The removed record is based off of the submitted expression. You can either sort in ascending or descending order, depending on what values you want to remove.</li><li>**Non-empty values**: The removed record is based off of the submitted expression. Records where the expression does not have a value will be removed.</li><li>**Following a list of value**: The removed record is based off of the submitted field or expression. You can sort the remaining values randomly, in ascending order, or descending order.</li></ul> |

Additionally, you can select the **Generate complement** option. Generating a complement processes the remaining population and contains the data **not** included as part of the deduplication. An additional outbound transition will be added to the activity.

+++

#### Enrichment {#enrichment}

>[!CONTEXTUALHELP]
>id="dc_orchestration_enrichment"
>title="Enrichment activity"
>abstract="The **Enrichment** activity allows you to enhance the targeted data with additional information from the database. It is commonly used in a composition after segmentation activities."

>[!CONTEXTUALHELP]
>id="dc_orchestration_enrichment_data"
>title="Enrichment activity"
>abstract="Once enrichment data has been added to the composition, it can be used in the activities added after the **Enrichment** activity to segment profiles into distinct groups based on their behaviors, preferences, and choices."

>[!CONTEXTUALHELP]
>id="dc_orchestration_enrichment_simplejoin"
>title="Link definition"
>abstract="Create a link between the working table data and the federated database."

>[!CONTEXTUALHELP]
>id="dc_orchestration_enrichment_reconciliation"
>title="Enrichment reconciliation"
>abstract="Set the reconciliation parameters."

>[!CONTEXTUALHELP]
>id="dc_targetdata_personalization_enrichmentdata"
>title="Enrichment data"
>abstract="Select the data to use to enrich your composition. You can select two types of enrichment data: a single enrichment attribute from the schema, also known as targeting dimension, or a collection link, which is a link with a 1-N cardinality between tables."

The **Enrichment** activity lets you enhance your composition by adding additional data from your federated database. 

If you have configured a connection to the Federated Audience Composition destination, you can use the Enrichment activity to enrich data coming Adobe Experience Platform with attributes from your external database. [Learn how to enrich Adobe Experience Platform audiences with external data](../connections/destinations.md)

+++ Configuration details

>[!NOTE]
>
>If you have multiple inbound transitions, you'll first need to select the **Primary set** from the dropdown.

After adding the **Enrichment** activity to your composition, you can select **Add enrichment data** to choose which attribute you want to use to enrich your composition. You can select **Edit expression** to build an advanced expression to select the attribute.

![](./assets/activities/enrichment.png)

+++

#### Reconciliation {#reconciliation}

>[!CONTEXTUALHELP]
>id="dc_orchestration_reconciliation"
>title="Reconciliation activity"
>abstract="The **Reconciliation** activity allows you to define the link between the data in the database and the data in a work table." 

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
>title="Schema"
>abstract="Select the new schema to apply to the data. A schema, also known as targeting dimension, lets you define the targeted population: recipients, app subscribers, operators, subscribers, etc. By default, the composition current schema is selected." 

>[!CONTEXTUALHELP]
>id="dc_orchestration_reconciliation_rules"
>title="Reconciliation rules"
>abstract="Select reconciliation rules to use for the deduplication. To use attributes, select the **Simple attributes** option and choose the source and destination fields. To create your own reconciliation condition using the query modeler, select the **Advanced reconciliation conditions** option."

>[!CONTEXTUALHELP]
>id="dc_orchestration_reconciliation_targeting_selection"
>title="Select the targeting dimension"
>abstract="Select the schema, also known as targeting dimension, for your inbound data to reconcile with." 

>[!CONTEXTUALHELP]
>id="dc_orchestration_keep_unreconciled_data"
>title="Keep unreconciled data"
>abstract="By default, non reconciled data are kept in the outbound transition and available in the worktable for future use. To remove unreconciled data, deactivate the **Keep unreconciled data** option." 

>[!CONTEXTUALHELP]
>id="dc_orchestration_reconciliation_attribute"
>title="Reconciliation attribute"
>abstract="Select the attribute to use to reconcile data, and confirm."

>[!NOTE]
>
>By default, non-reconciled data is kept in the outbound transition and is available in the worktable for future use. If you do **not** want reconciled data to be used, deactivate the **Keep unreconciled data** option.

The **Reconciliation** activity lets you define the link between data in your federated database to the data in a work table. 

+++ Configuration details

After adding the **Reconciliation** activity to your composition, you can choose what schema to use for the reconciliation.

Once you've chosen the schema, you'll need to set up your reconciliation rules. You can choose between **Simple attributes** or **Advanced reconciliation conditions**. 

>[!BEGINTABS]

>[!TAB Simple attributes]

After choosing **Simple attributes**, select **Add rule**. You can now set up your reconciliation by adding the **Source** and **Destination** fields. The **Destination** field corresponds to the fields of the selected schema.

![](./assets/activities/reconciliation-rules.png)

Data is reconciled when the source and destination are equal. You can add more reconciliation criteria by selecting **Add rule**. If multiple join conditions are specified, **all** of them must be verified so the data can be linked together.

>[!TAB Advanced reconciliation conditions]

After choosing **Advanced reconciliation conditions**, select **Create conditions**. You can now create your own reconciliation condition using the query modeler. For more information on using the Query Modeler, read the [Query Modeler overview](../query/home.md)

![](./assets/activities/reconciliation-advanced.png)

>[!ENDTABS]

You can also filter the reconciled data. Select **Create filter** to create a custom condition using the Query Modeler. For more information on using the Query Modeler, read the [Query Modeler overview](../query/home.md)

+++

#### Save audience {#save-audience}

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
>If your sandbox uses a **dataset precedence** merge policy, please contact Adobe Customer Care to add the `Halos UPS` dataset to your merge policy.
>
>For more information on merge policies, please read the [merge policies overview](https://experienceleague.adobe.com/en/docs/experience-platform/profile/merge-policies/overview).

The **Save audience** activity lets you create an audience based off of the composition. Once the audience has been created, you can use them within Audience Portal in Adobe Experience Platform. For more information on using audiences with Federated Audience Composition, read the [audiences overview](../start/audiences.md). For more information on audiences in Experience Platform, read the [Audience Portal overview](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/audience-portal){target="_blank"}.

+++ Configuration details

>[!IMPORTANT]
>
>The audience's name **must** be unique within the current sandbox and cannot have the same name as any existing audience. 

After adding the **Save audience** activity to your composition, you can specify the name of your newly created audience.

![](./assets/activities/save-audience.png){zoomable="yes" width="30%"}

Now, you can specify your mappings to select which fields you want to transfer to the newly created audience. Select **Add Audience Mapping** and choose the source and target audience fields, repeating as many times as necessary.

After adding your mappings, you can select the primary identity and namespace to identify the targeted profiles in the database. The primary identity field is used to identify the profiles while the identity namespace acts as a key to identify the identity.

Additionally, you can set the data expiration for the audience. The data expiration determines the number of days after which the audience membership will expire. The data expiration can range from 1 to 90 days. By default, this value is set to 30.

+++

#### Split {#split}

>[!CONTEXTUALHELP]
>id="dc_orchestration_split"
>title="Split activity"
>abstract="The **Split** activity allows you to segment incoming populations into multiple subsets based on different selection criteria, such as filtering rules or population size."

>[!CONTEXTUALHELP]
>id="dc_orchestration_split_segments"
>title="Segments for split activity"
>abstract="Add as many subsets as desired to segment the incoming population.<br/></br>When the **Split** activity is executed, the population is segmented across the different subsets in the order they are added to the activity. Before starting your composition, ensure that you have ordered the subsets in the order that suits your needs using the arrow buttons." 

>[!CONTEXTUALHELP]
>id="dc_orchestration_split_filter"
>title="Split activity filter"
>abstract="To apply a filtering condition to the subset, select **[!UICONTROL Create filter]** and configure the desired filtering rule using the query modeler. For example, include profiles from the incoming population whose email address exist in the database."

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
>abstract="Toggle the **[!UICONTROL Skip empty transition]** option on to disable the output transition for this subset if the incoming population is empty."

>[!CONTEXTUALHELP]
>id="dc_orchestration_split_enable_overlapping"
>title="Enable overlapping of output populations"
>abstract="The **[!UICONTROL Enable overlapping of output populations]** option lets you manage populations belonging to several subsets. When the box isn't checked, the split activity makes sure a recipient cannot be present in several output transitions, even if it meets the criteria of several subsets. They will be in the target of the first tab with matching criteria. When the box is checked, the recipients can be found in several subsets if they meet their filter criteria. "

The **Split** activity separates the incoming population into multiple parts, depending on the given criteria.

+++ Configuration details

>[!IMPORTANT]
>
>When the **Split** activity is executed, the population is separated across the different subsets in the **order they are added**. For example, if the first subset splits 70% of the initial population, the next subset will apply its selection criteria to the remaining 30%.
>
>Before executing your composition, make sure you have ordered the subsets in the order you want the splits to be run.

After adding the **Split** activity to your composition, you can now determine how to subset your audience. Select **Add segment** to create your different branching paths. 

You can now provide details for each of these sub-paths. You can give the sub-path a name as well as the filter conditions. To create a filtering condition, select **Create filter** and configure the filtering rule using the Query Modeler. For more information on using the Query Modeler, read the [Query Modeler overview](../query/home.md).

Once you've created your filtering condition, you can apply the following additional rules:

- **Enable limit**: Limits the number of profiles that are allowed to be split off into the subset. You can set this as either a number or a percentage of the population.
  - If you enable a limit, you can also rank the selected profiles based on a specific profile attribute. Turn on **Enable sorting**, and you can sort the attributes in ascending or descending order.
- **Skip empty transition**: Disables the transition if the incoming population is empty.

Now that the subsets have been configured, there are a few more additional options you can set.

| Options | Description |
| ------- | ----------- |
| **Generate complement** | Creates an outbound transition that contains the remaining population. |
| **Enable overlapping of output populations** | If enabled, the recipient **cannot** be present in multiple outbound transitions and will **only** be present in the first outbound transition. If disabled, the recipient **can** appear in multiple outbound transitions. |
| **Generate all subsets in the same table** | Groups all the subsets into a single outbound transition. |

+++

### Flow control activities {#flow-control}

Flow control activities let you define the organization and coordination of your composition.

#### And join {#and-join}

>[!CONTEXTUALHELP]
>id="dc_orchestration_and-join"
>title="AND-join activity"
>abstract="The **And-join** activity allows you to synchronize multiple execution branches of a composition. It is triggered once all of the preceding activities have finished. This allows you to make sure that certain activities are finished before continuing to execute the composition."

The **AND-join** activity lets you combine multiple branches of a composition together. This activity is only triggered once **all** the inbound transitions are activated.

+++ Configuration details

After you've added multiple activities to form at least two different branches, you can add the **AND-join** activity to the end of any of the branches.

![](./assets/activities/and-join.png)

Within the **Merging options** section, you can select all the activities you want to synchronize. Additionally, you can choose which inbound transition to keep within the **Primary set** dropdown.

+++

#### End {#end}

The **End** activity graphically marks the end of the composition and has no functional impact.

#### Fork {#fork}

>[!CONTEXTUALHELP]
>id="dc_orchestration_fork"
>title="Fork activity"
>abstract="The **Fork** activity allows you to create outbound transitions to start several activities at the same time."

>[!CONTEXTUALHELP]
>id="dc_orchestration_fork_transitions"
>title="Fork activity transitions"
>abstract="By default, two transitions are created with a **Fork** activity. Select the **Add transition** button to define an additional outbound transition, and enter its label."

The **Fork** activity lets you create multiple outbound transitions that simultaneously starts multiple activities.

+++ Configuration details

Once you've added the **Fork** activity to your composition, two outbound transitions are automatically generated. You can give these outbound transitions a name. Additionally, you can select **Add transition** to add another outbound transition. 

![](./assets/activities/fork.png)

+++

#### Scheduler {#scheduler}

>[!CONTEXTUALHELP]
>id="dc_orchestration_scheduler"
>title="Scheduler activity"
>abstract="The **Scheduler** activity allows you to schedule when the audience composition gets started. This activity should be considered as a scheduled start. It can only be used as the first activity of a composition."

>[!CONTEXTUALHELP]
>id="dc_orchestration_schedule_validity"
>title="Scheduler validity"
>abstract="You can define a validity period for the scheduler. It can be permanent (default), or can be valid until a specific date."

>[!CONTEXTUALHELP]
>id="dc_orchestration_schedule_options"
>title="Scheduler options"
>abstract="Define the frequency of the scheduler. It can be executed at a specific moment, once or several times a day, week or month."

The **Scheduler** activity lets you schedule when to start the composition's execution. You **must** use this as the first activity of the composition.

+++ Configuration details

After adding the **Scheduler** activity to your composition, you can set the **Execution frequency** for the composition. Options include **Once**, **Daily**, **Several times a day**, **Weekly**, and **Monthly**.

>[!BEGINTABS]

>[!TAB Once]

>[!NOTE]
>
>The time is set to UTC.

If you select **Once**, the composition is only executed once. You can select the date and time the composition is run.

>[!TAB Daily]

If you select **Daily**, the composition is executed once a day. However, you can which day of the month the composition is executed under the **Day of the month** section. Possible values include **Every day**, **On week days**, **Through a selected period**, and **Selected days of the week**.

| Day of the month | Description |
| ---------------- | ----------- |
| Every day | The composition is executed every day. |
| On week days | The composition is executed every weekday. |
| Through a selected period | The composition is executed every day throughout the selected period. You can set the length of the recurrence period as well as the date the period starts. |
| Selected days of the week | The composition is executed every day of the week that is selected. |

After choosing what day of the month the schedule will run, you can select **Preview launch times** to check the schedule of the next ten executions of your composition.

>[!TAB Several times a day]

If you select **Several times a day**, the composition is executed multiple times per day. You can choose whether the composition is executed at specific times per day or periodically at set times.

If you select **Selected hours**, you can choose the specific times the composition will run. If you select **Periodic**, you can choose how often the composition will run in either hours or minutes and between what times it will run. All the times are in UTC.

After select the hours, you can choose how often the execution is run under the **Day of the month** section.

| Day of the month | Description |
| ---------------- | ----------- |
| Every day of the week | The composition is executed every day. |
| On certain days of the week | The composition is executed every day of the week that is selected. |

After choosing what day of the month the schedule will run, you can select **Preview launch times** to check the schedule of the next ten executions of your composition.

>[!TAB Weekly]

If you select **Weekly**, the composition is executed on the weekly frequency that is set. If you set the weekly frequency as a number larger than 1, you can also choose the date the execution starts from.

After choosing the evaluation frequency, you can choose how often the execution is run under the **Day of the month** section.

| Day of the month | Description |
| ---------------- | ----------- |
| Every day of the week | The composition is executed every day. |
| On certain days of the week | The composition is executed every day of the week that is selected. |

After choosing what day of the month the schedule will run, you can select **Preview launch times** to check the schedule of the next ten executions of your composition.

>[!TAB Monthly]

If you select **Monthly**, the composition is executed on the monthly frequency that is set. You can either set it to be every month or on certain months.

After choosing the monthly frequency, you can choose the **Day of the month** the execution is run.

| Day of the month | Description |
| ---------------- | ----------- |
| Every day | The composition is executed every day. |
| On week days | The composition is executed every weekday. |
| Through a selected period | The composition is executed every day throughout the selected period. You can set the length of the recurrence period as well as the date the period starts. |
| Selected days of the week | The composition is executed every day of the week that is selected. |

Once you set the **Day of the month**, you can choose the start time. All the times are in UTC.

>[!ENDTABS]

After selecting the execution frequency, you can choose the **Validity period** of the schedule.

| Validity period | Description |
| --------------- | ----------- |
| **Permanent (never expires)** | The composition will never expire. |
| **Validity period** | The composition will run between the given dates. |

+++

#### Wait {#wait}

>[!CONTEXTUALHELP]
>id="dc_orchestration_wait"
>title="Wait activity"
>abstract="The **Wait** activity is used to delay the transition from an activity to another."

The **Wait** activity pauses the composition's execution for the specified amount of time.

+++ Configuration details

After you add the **Wait** activity to your composition, you can make it either a **Duration** or a **Fixed time** wait.

![](./assets/activities/wait.png)

If you select duration, you can set the period of time to wait. This period of time can be in seconds, minutes, hours, or days.

If you select fixed time, you can set the composition to wait until the given date and time. The time is set to your **local time zone**.

+++

## Transitions {#transitions}

In compositions, transitions show how data is transported from one activity to another. The transitions store the data in a temporary work table. If you select the transition, you can view the following information:

- **Preview schema**: You can select this to view the schema for the work table.
- **Preview results**: You can select this to visualize the data that's transported in the selected transition. This option is only available if **Keep the result of interim populations between two executions** is enabled.

![](assets/transition-preview.png)

## Next steps {#next-steps}

After reading this guide, you'll have a better understanding of the activities and transitions you can use within a composition. For more information on compositions in general, read the [composition overview](./create-composition.md).
