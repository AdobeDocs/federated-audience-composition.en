---
audience: end-user
title: Use the Wait activity
description: Learn how to use the Wait activity
badge: label="Limited availability" type="Informative"
---
# Wait {#wait}

>[!CONTEXTUALHELP]
>id="dc_orchestration_wait"
>title="Wait activity"
>abstract="The **Wait** activity is used to delay the transition from an activity to another."

The **Wait** activity allow a certain amount of time to pass between two activities being executed. For example, to wait several days after an email delivery activity then analyze the opens and clicks generated during this period before performing any follow-up operations (reminder email, creating an audience, etc.).

## Configuration{#wait-configuration}

Follow these steps to configure the **Wait** activity:

1. Add a **Wait** activity into your composition.

1. Specify the **Duration** of the wait between the inbound and outbound transitions.

1. Select the time unit in the **Periods** field: seconds, minutes, hours, days.

 