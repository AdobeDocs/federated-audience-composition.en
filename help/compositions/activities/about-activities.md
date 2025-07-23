---
audience: end-user
title: Work with activities
description: Learn how to work with activities
exl-id: 1e4e5f53-636f-4f1c-bf2f-cc3b5d6d6dda
---
# Work with activities {#activities}

In Federated Audience Composition, you can create compositions using two types of activities:

* **Targeting activities** let you build one or more targets by defining an audience and splitting or combining these audiences using intersection, union or exclusion operations.
* **Flow control** activities are specific to organizing and executing compositions. Their main task is to coordinate the other activities.

## Targeting activities

* [Build audience activity](build-audience.md): Define your target population. You can either select an existing audience or use the query modeler to define your own query.
* [Change data source](./change-data-source.md): Change the data source used by your composition.
* [Change dimension](change-dimension.md): Change the schema, also known as targeting dimension, as you are building your composition.
* [Combine](combine.md): Perform segmentation on your inbound population. You can use a union, an intersection or an exclusion.
* [Deduplication](deduplication.md): Delete duplicates in the result(s) of the inbound activities.
* [Enrichment](enrichment.md): Define additional data to process in your composition. With this activity, you can leverage the inbound transition and configure the activity to complete the output transition with additional data.
* [Reconciliation](reconciliation.md): Define the link between the data in the database and the data in a work table, for example data loaded from an external file.
* [Save audience](save-audience.md): Update an existing audience or create a new audience from the population computed upstream in a composition.
* [Split](split.md): Segment incoming population into several subsets.

## Flow control activities

* [AND-join](and-join.md): Synchronize multiple execution branches of a composition.
* **End**: Graphically mark the end of a composition. This activity has no functional impact and is therefore optional.
* [Fork](fork.md): Create outbound transitions to start several activities at the same time.
* [Scheduler](scheduler.md): Schedule when the composition gets started.
* [Wait](wait.md): Momentarily pause execution of a part of a composition.
