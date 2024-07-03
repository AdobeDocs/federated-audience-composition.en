---
audience: end-user
title: Create compositions
description: Learn how to create compositions
---

# Key principles of composition creation {#gs-composition-creation}

>[!CONTEXTUALHELP]
>id="dc_composition_creation_properties"
>title="Composition properties"
>abstract="In this screen, choose the template to use to create the composition and specify a label. Expand the ADDITIONAL OPTIONS section to configure more settings such as the composition internal name, its folder, timezone, and supervisor group. It is highly recommended to select a supervisor group so that operators are alerted if an error occurs."

Federated Data Composition provides a visual canvas that allows you to create audiences by leveraging various activities (split, enrich, etc.).

## What's inside a composition? {#gs-composition-inside}

The composition diagram is a representation of what is supposed to happen. It describes the various tasks to be performed and how they are linked together. 

![](assets/composition-example.png){zoomable="yes"} {zoomable="yes"}

Each composition contains:

* **Activities**: An activity is a task to be performed. The various activities are represented on the diagram by icons. Each activity has specific properties and other properties that are common to all activities.

    In a composition diagram, a given activity can produce multiple tasks, in particular when there is a loop or recurrent actions.

* **Transitions**: Transitions link a source activity to a destination activity and define their sequence. 

* **Worktables**: The worktable contains all the information carried by the transition. Each composition uses several worktables. The data conveyed in these tables can be used throughout the composition's life cycle.

## Key steps to create a composition {#gs-composition-steps}

The main steps to create a composition are as follows:

1. [Create the composition](#create)
1. [Configure the composition's settings](#starting-audience)
1. [Add & configure activities](#action-activities)
1. [Execute the composition and monitor its execution](#save)