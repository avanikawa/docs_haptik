---
title: FAQ
---

### 1. What happens to the new chat if the user's previous conversation was auto-completed?

```
The unread messages and time is tracked within the scope of a conversation. 
The count of unread messages is reset and when the users comes up to bot and chat with an agent, 
the chat will marked as a new chat.
```

### 2. Why are agents are not able to receive chats?

There are multiple scenarios that relate to agents not receiving the chat on their screen. Some of the following the observed scenarios -  

* **The MyChats page keeps reloading, a yellow bar appears on the top of page**
* **Messages are not being sent to the user, a Resend option appears**
* **There are chats in the agent’s queue but the chats are not assigned on the MyChats page**
* **A lot of exception errors appear on the screen**


```
If your agents are not able to recieve chats then please contact Haptik to get the list of IPs to be whitelisted. 
```

### 3. How to manage offline hour chats?

In the Team settings, you can turn the toggle to complete all chats when no agent is online. 
But there can be an edge case as mentioned below. We need to understand when this edge case occurs, and assign a specific permission to all agents.

A chat would get assigned first to the last agent who took this user's chat. Assuming the agent is available. We mandate agents to go offline before 30 minutes of their shift closure time, and then logout on shift end. This works in sync with our assignment so that logged out agents are not considered for assignment. For when agents are going offline, but not actively logging out, the chats that come in offline hours get assigned but the agents in reality are not available. We should use the `Inactivity_logout` permission that logs out agents on no activity for 15 minutes. 

### 4. How do the users know when an agent has entered the chat and when the chat has ended?

Once the chat is assigned to an agent, the user can see the handover to the agent on the SDK UI.

![image](https://user-images.githubusercontent.com/75118325/121811569-6c511500-cc82-11eb-8435-44015ea2a11c.png)

Once the chat is marked as complete/closed, the user can see the completion message on the SDK UI. 

![image](https://user-images.githubusercontent.com/75118325/121811627-96a2d280-cc82-11eb-97ed-aae2d6471adc.png)

Chats are automatically closed if:
- No messages are exchanged between the agent and the user and the chat is either with the bot or is in **Waiting for user** state for **8 minutes**.
- If all agents were offline, and [**chat auto-complete**](https://docs.haptik.ai/agent-chat/teams#step-2---setup-team-offline-message) setting was enabled for the team.

