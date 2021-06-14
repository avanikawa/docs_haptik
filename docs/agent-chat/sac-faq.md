---
title: FAQs
---

### 1. What happens to the new chat if the user's previous conversation was auto-completed?

```
The unread messages and time is tracked within the scope of a conversation. 
The count of unread messages is reset and when the users comes up to bot and chat with an agent, 
the chat will marked as a new chat.
```

### 2. Why are we not able to receive chats?

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

### 4. How to open Haptik Reports ZIP file on Windows system?

Windows has built-in support for zip files. It can create, extract, browse through zip files which is a nice feature but this feature can also give you troubles in some situations.

When you try to open a .zip file you’ve downloaded using Windows Explorer, you might receive the following error:

![image](https://user-images.githubusercontent.com/75118325/121531470-0d8a6200-ca1c-11eb-9541-3a4973402d45.png)

> By default, Windows will extract the files into the temp folder when you double-click on a .zip file to open it for viewing. This error means there is a problem with the permissions of the temp folder.

Here is a workaround:

* Move the .zip file into one of your user profile sub-folders, like Downloads, Documents, Pictures, etc.
* Right-click on the .zip file and select “Extract All”. This allows you to decompress all of the files into a folder of your choice.

This problem has been faced by lots of Windows users. If you open the zip file with some third-party tools such as 7-zip or WinRAR, every file could be opened without error.

