---
title: FAQ
---

### 1. What happens to the new chat if the user's previous conversation was auto-completed?

```
The unread messages and time is tracked within the scope of a conversation. 
The count of unread messages is reset and when the users comes up to bot and chat with an agent, 
the chat will marked as a new chat.
```

### 2. Agents are not able to receive chats

There are multiple scenarios that lead to agents not receiving the chat on their screen. Some of the following errors are observed -  

* **The MyChats page keeps reloading, a yellow bar appears on the top of page**
* **Messages are not being sent to the user, a Resend option appears**
* **There are chats in the agent’s queue but the chats are not pinned on the MyChats page**
* **A lot of exception errors appear on the screen**


```
If resend or yellow bar appears you need to enable or whitelist the below IPs

For Haptik CAS: wss://mqtt.haptik.me (Port: 443)

For Jio-Azure CAS: wss://jio-prod-mqtt.haptikapi.com (Port: 443)

For Singapore CAS: wss://haptik-singapore-mqtt.haptikapi.com (Port: 443)

For US CAS: wss://haptik-us-mqtt.haptikapi.com (Port: 443)
```

<code>If there is partial connectivity observed, then whitelist all IPs with <b>ap-south-1</b>, mentioned here, [**https://ip-ranges.amazonaws.com/ip-ranges.json**](https://ip-ranges.amazonaws.com/ip-ranges.json)</code>
