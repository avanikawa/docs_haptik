---
title: Introduction
---

## What is Bot as an API?

Whenever you want to capture the events happening on the bot such as, what message is the bot sending, you can use **Bot as an API**. You can also use **Bot as an API** to connect to a channel which is not cuurently supported on Haptik Platform. Bot as an API uses webhooks to deliver these events to mentioned URL.

Example use case - 

1. When you want to generate a ticket in your CRM (Customer Relationship Management software) **after** the conversation between the user and bot is complete,
the webhook event will deliver this event to your mentioned endpoint.

2. When you already have a bot and you want to redirect the user to Smart Agent Chat tool of Haptik Platform.

Briefly, this is how the integration works:
1. Your application receives the message from the user.
2. It then sends a POST request with that message to the callback URL of Conversation Studio tool of Haptik Platform.
3. Conversation Studio tool processes the message and sends a response to the webhook URL of your application.
4. Your application listens to the webhook and responds to the user.

![Diagrams](https://user-images.githubusercontent.com/75118325/120749290-f5997680-c521-11eb-9859-7ffc339b8434.png)

## What is Webhook?

Webhooks provide functionality where a provider application can notify a client-side application when a new event has occurred on the provider's server.

Webhooks are "user-defined HTTP/S callbacks", that allows two applications to communicate automatically.

A key difference between an API endpoint and a webhook:

In APIs, the client-side application calls the server-side application to retrieve some sort of information. Whereas, in the case of webhooks it is the server-side that calls the client-side application when a particular server-side event occurs.
