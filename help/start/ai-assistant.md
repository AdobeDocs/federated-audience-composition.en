---
title: AI Assistant Overview
description: Learn how to use AI Assistant, including product knowledge, operational insights, and creating federated audience compositions.
exl-id: f7493a57-e42d-43f9-b20a-1b9b90477a74
---
# AI Assistant overview {#ai-assistant}

AI Assistant is a user interface feature designed to help you navigate and understand Adobe concepts. You can use AI Assistant to better understand product knowledge use cases in several products across Adobe Experience Cloud, including Federated Audience Composition.

>[!CAUTION]
>
>You must agree the Adobe Experience Cloud Generative AI User Guidelines before you can use AI Assistant. Learn more about the agreement in the [AI Assistant (legacy) overview](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/home){target="_blank"}.

In Federated Audience Composition, you can access product knowledge to learn about Adobe concepts related to different parts of the process. AI Assistant supports four types of use cases: **Open discovery** (explore product concepts based on Experience League documentation), **Targeted learning and troubleshooting** (ask questions about specific features or functionality), **Operational insights** (ask questions about your objects within Federated Audience Composition), and **Creating federated audience compositions**.

## Access {#access}

To access AI Assistant, select ![the AI Assistant icon](/help/start/assets/ai-assistant/icon.png) on the top bar. AI Assistant displays on the right section of the screen. You can select ![Dive image alt text](assets/do-not-localize/Smock_FullScreen_18_N.svg "the Expand icon") to expand the AI Assistant window.

![The AI Assistant icon is highlighted, showing how to access AI Assistant.](/help/start/assets/ai-assistant/access.png)

## Using AI Assistant {#using}

Once you've opened AI Assistant, enter your question in the field at the bottom of the screen and press enter. The answer to your question is now displayed. You can use thumbs up or thumbs down to rate your answer.

![A sample question and answer within AI Assistant is displayed.](/help/start/assets/ai-assistant/sample-question-answer.png)

## Sample questions {#sample-questions}

The following queries show the available types of questions you can ask AI Assistant:

| Query type | Sample question |
| ---------- | --------------- |
| Open discovery | <ul><li>What is Federated Audience Composition?</li></ul> |
| Targeted learning | <ul><li>How can I configure a Snowflake Federated database account?</li><li>How can I create a federated composition?</li></ul> |
| Operational insights | <ul><li>How many federated databases do I have in my sandbox?</li><li>How many schemas have I created in the last 30 days?</li></ul> |
| Creating a federated audience composition | <ul><li>Create a federated audience of customers living in the UK.</li></ul> | 

Additionally, you can use AI Assistant to autonomously create a federated audience composition.

## Create an audience {#create-audience}

You can use AI Assistant to create a federated audience composition using natural-language prompts. When you use AI Assistant to create an audience, AI Assistant comes up with a plan based off of your prompt and executes it within your browser using AI-powered automation.

For example, if you ask AI Assistant to "Create a federated audience of customers living in UK using the schema CUSTOMERS_Table", AI Assistant will lay out the plan it will undertake to create the audience, including steps such as navigating to the Federated compositions page, how the agent will create the composition, and saving the audience once it's completed. 

![A sample question and response is displayed.](/help/start/assets/ai-assistant/ask-create.png)

If the plan looks accurate, you can select **[!UICONTROL Execute]** to let the agent go through its automation. The agent will, within the browser, autonomously go through the steps of creating your requested composition within the Federated Audience Composition UI. If, at any point, you want to stop the automation, select **[!UICONTROL Stop]**. 

![The plan has been executed, and the agent is autonomously running the plan.](/help/start/assets/ai-assistant/execute-plan.png)

Currently, the audience creation skill supports the following additional features:

- Scheduler
  - You can create federated compositions that run on a recurring schedule. Supported values include **Once** and **Daily**.
- Deduplication
  - You can deduplicate the federated data records during data reconciliation

## Next steps

For more information about AI Assistant, including example objectives you can accomplish with AI Assistant, and learning how AI Assistant works, read the [AI Assistant overview](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/home){target="_blank"}.

For a full list of the Operational Insight questions you can ask for Federated Audience Composition, read the [operational insights section](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/home#operational-insights){target="_blank"}.
