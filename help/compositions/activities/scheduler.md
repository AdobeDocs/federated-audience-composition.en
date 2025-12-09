---
audience: end-user
title: Use the Scheduler activity
description: Learn how to use the Scheduler activity
exl-id: 3e8be2a2-2227-42f4-a512-b9e686ba0f66
---
# Scheduler {#scheduler}

The **Scheduler** activity is a **Flow control** activity. It allows you to schedule when the composition gets started. This activity should be considered as a scheduled start. It can only be used as the first activity of the composition. 

If you have configured a connection to the Federated Audience Composition destination, you can use this activity to send over Adobe Experience Platform audiences at regular frequencies. [Learn how to enrich Adobe Experience Platform audiences with external data](../../connections/destinations.md)

![](../assets/scheduler.png)

## Configure the Scheduler activity {#scheduler-configuration}

Follow these steps to configure the **Scheduler** activity:

1. Add a **Scheduler** activity to your composition.

1. Configure the **Execution frequency**:

   * **Once**: the composition is executed a single time.
   * **Daily**: the composition is executed at a specific time, once a day.
   * **Several times a day:** the composition is regularly executed several times a day. You can set up executions at specific times or periodically.

        >[!NOTE]
        >
        >Do not schedule a composition to run more than every 15 minutes as it may impede overall system performance and create blocks in the database.

   * **Weekly**: the composition is executed at a specified moment, once or several times a week.
   * **Monthly**: the composition is executed at a specified moment, once or several times a month. You can select months, when you need the composition to be executed. You can also set up executions on specified week days of the month, such as the second Tuesday of the month.

1. Define the execution details according to the frequency selected. The detail fields may vary depending on the frequency used (time, repetition frequency, specified days, etc.).

1. Select **Preview launch times** to check the schedule of the next ten executions of your composition.

1. Define the validity period of the scheduler:

   * **Permanent (never expires)**: the composition is executed, according to the frequency specified, without any limits to the time frame or number of iterations.

   * **Validity period**: the composition is executed according to the frequency specified, up until a specific date. You need to specify start and end dates. 

>[!NOTE]
>
>If you want to start the composition right away, you can select the **Execute pending task** in the scheduler's top action bar. This button is only available when you have started the composition.

<!--## Example{#scheduler-example}

In the following example, the activity is configured so that the composition runs several times a day at 9 and 12 AM, every day of the week from October 1st, 2023 to January 1st, 2024.-->
