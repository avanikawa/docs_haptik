---
title: FAQs
---

### 1. Is 8 minutes inactivity window for calculating one conversation configurable?

No, 8 minutes inactivity window is not configurable. After 8 minutes of inactivity, the conversation is marked completed. However, the IVA remembers the context for 2 hours. So if the user comes back within 2 hours, the IVA will be able to help him with the saved context of the user's previous conversation.

### 2. If the conversation is assigned to an agent, do we still close the conversation if there are no interactions for 8 minutes?

It depends on the conversation state, if the conversation is in an Agents Queue or Assigned to an agent, it will not be auto completed.
However if the chat is in "waiting for user" state, as marked by an agent, it will auto complete after 8 minutes of inactivity.

### 3. How much data is visible in the Analytics tool?

You can view upto **90** days of data from the present date on the tool.

### 4. If the customer is using a third-party agent chat tool (e.g. Salesforce, Zendesk, etc), is there a possibility to get a Conversation Split in that case?

If the implementation to the third party is done using [**TRACT**](https://docs.haptik.ai/external-chat-tool/), then Conversation Split number should be visible.
