---
title: What is a Webhook
---

## What is Bot as an API?

Whenever you want to capture the events happening on the bot such as what message is the bot sending, if the chat is being handed over to an agent and so on  you can user the Bot as an API. Bot as an API uses webhooks to deliver these events to mentioned URL.

```
Example use case - 

1. When you want to generate a ticket in your CRM after the conversation between the user and bot is complete,
the webhook event will deliver this event to your mentioned endpoint.

2. When you already have a bot and you want to redirect the user to Smart Agent Chat tool of Haptik Platform.
```

![image](https://user-images.githubusercontent.com/75118325/120746319-8ff6bb80-c51c-11eb-873e-5e7f87cd1ff4.png)


## What is Webhook?

Webhooks provide functionality where a provider application can notify a client-side application when a new event has occurred on the provider's server.

Webhooks are "user-defined HTTP/S callbacks", that allows two applications to communicate automatically.

A key difference between an API endpoint and a webhook:

In APIs, the client-side application calls the server-side application to retrieve some sort of information. Whereas, in the case of webhooks it is the server-side that calls the client-side application when a particular server-side event occurs.
