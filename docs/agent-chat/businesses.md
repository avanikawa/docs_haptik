---
title: Monitor Chats
---

As a TL, you can monitor the ongoing chats to taking place between the bot or the agent and the user. This will help you see if the chats are being handled properly by the agents or the bot. If you find a user who needs human assistance, you can directly reassing the chat to an agent using Chats section. There are two ways you can monitor the ongoing chats or completed chats - 
1. From Business (for all the conversations taking place between the user and the bot)
2. From Teams (for all the conversations taking place between the user and the agent)

**Chats** section is present in both **Business** and **Teams** section. The layout of the **Chats** screen is same too.

You can analyse **Chats** page from left to right in 3 sections. First you select a Business or Team Name, then you select the chat list (ex: Active, Queued). And then you could choose to access a chat detail view in third section. 

![image](https://user-images.githubusercontent.com/75118325/120474448-dc7bb300-c3c5-11eb-99c3-eda5d87ab32c.png)


![image](https://user-images.githubusercontent.com/75118325/120473357-907c3e80-c3c4-11eb-9920-4e9d0cde2dc2.png)


## Section 1: List of businesses / team name

This section lists the businesses against 2 metrics

1. **Total Live chats**: As the name suggests, you get the count of live chats for this business at any instant.
2. **Delayed chats**: This gives you the number of *Delayed chats* for a business. When you create a *Team* for any business, you set the time value for which a chat is supposed to be considered delayed.

> Delayed chat time can be different for any team in a business. Click [**here**](https://docs.haptik.ai/agent-chat/teams#how-to-make-changes-in-the-team-settings) to know more about delay timing.
       
You can click on any business or team name in this section, to render the chats for it, in the next section.

## Section 2: Chat lists

This section is divided into 5 sub-sections -

1. BOT / All Live Chats
2. Active
3. Queued
4. Waiting for User
5. Completed Chats

![Chat lists](assets/businesses_chats_sub_sections.png)

![image](https://user-images.githubusercontent.com/75118325/120472937-1f3c8b80-c3c4-11eb-92c6-bae826dc3dbd.png)

Within a selected sub-section view, you can filter by Team or Assignee (both Assigned and Unassigned chats).

    Tip: You can also filter and Chats list to show only new users or to show only delayed chats.
    
For any chat in a list view, you can click the *Reassign chat* view to reassign a specific chat to a Team or an Agent. 

![Chat assignment](assets/businesses_chat_assignment.png)

## Section 3: Chat detail view

![Selected chat](assets/businesses_selected_chat.png)

Here, you get the detailed chat window for the selected chat in above section 2.

You can now access some smart actions and mark the chat complete or you could send this selected chat to *Waiting for User*. Depending on the state of the chat, the TL can take different actions on the chat.

![image](https://user-images.githubusercontent.com/75118325/120473212-67f44480-c3c4-11eb-81dd-2c66a43ffeaf.png)

### Smart Actions 

![image](https://user-images.githubusercontent.com/75118325/120464608-bef51c00-c3ba-11eb-92c7-caf4b05c5557.png)

There are **5** Smart Actions available for the TL - 

#### **1. User Details**

The TLs can check the User Details which agents are able to see in the User Details section, on the right hand side of the screen.

#### **2. Report inappropriate**

TLs can mark a user as inappropriate by clicking on this icon.

We register/log a user being marked as inappropriate once every 2 hours per user. If the inappropriate count for a user is greater than 2, we send a blocked message to the user as shown below -

```
Hi <User Name>, this is a system generated message to inform you that your access to 
this chat service has been permanently disabled. You will not be able to use this 
chat service any more as you have been flagged multiple times for inappropriate messages 
sent to our Human assistants.
```

#### **3. Notes**

Notes section is used to save link of the product suggested or any other information given from any website. These notes are shared with other assistants for a particular user. It is helpful for another assistant to get the details quickly by just checking notes. Even numbers are saved in Notes for reference. Make sure that you save notes wherever and whenever required.

#### **4. User Info Link**

This tool will help you to get the link of the ongoing chat. As soon as you click on the tool, it will take you to the next tab where the User Info link will be visible. This is used for sharing chat link of users.

#### **5. Take an Action**

Depending on which state the chat is, TLs can take different action for a particular chat.

If the chat is in **Completed** or **Waiting for User** state, the TLs can choose to either - 
* Reassign chat
       * The TL can reassign the chat to themselves or to a specific agent from a team.
* Open chat
       * When the TL opens a chat, the chat will be added in the team queue and the chat will be assigned to a random agent from the team.

![image](https://user-images.githubusercontent.com/75118325/120464953-1d21ff00-c3bb-11eb-8571-dd86b3ed2b57.png)

If the chat is in **Queue** or **Active** or **BOT** state, the TLs can choose to either - 

* Reassign chat
       * The TL can reassign the chat to themselves or to a specific agent from a team.
* Send to waiting
       * This will send the user to **Waiting of User** state. If the user does not reply back within 8 mins, then the chat will be auto completed.
* Close chat
       * This will close the chat and mark the chat as **Complete**

![image](https://user-images.githubusercontent.com/75118325/120465407-928dcf80-c3bb-11eb-9890-8a93a47d9505.png)

> Team Leaders do not get **Closing Categories** on marking a chat complete from Businesses or Teams screen.
