---
title: Teams
---

## What is a team?

A team is a group of agents who are trained to handle user queries related to a specific topic. The team can be divided based on the subject matter/location of a user/expertise of agents. The logic for team routing can be defined as per the business requirement. 

## How to create a team?

Navigate to **Teams** section of **Smart Agent Chat** tool to create a new Team.

![image](https://user-images.githubusercontent.com/75118325/120099718-b4d4e280-c15a-11eb-8736-8a86044273dc.png)

### Step 1 - Provide a Team name

The team name is used for internal purpose for the Team Leaders & Agents. A user will never be able to see the team name on the chat window.

### Step 2 - Select Team Owner (Client)

Select the Partner(Client) to which the team belongs.

![image](https://user-images.githubusercontent.com/75118325/120099783-08473080-c15b-11eb-8773-d73babb71dc0.png)

### Step 3 - Click on _Save_ 

Now your Team has been created. You can select this Team as the **Default Team** in the **Business Manager**.

## How to Manage Agents of a Team?

In the **Manage Agents** section of Team, you can - 
1. Add agents
2. Remove agents
3. View no. of queues, active, waiting for user chats
4. Set chat concurrency
5. View agent status
6. View agent chats

### Add/Remove Agents

In the **Manage Agents** section, click on **Add Agents** button to add agents in the team.

![image](https://user-images.githubusercontent.com/75118325/120189521-17021600-c235-11eb-84c9-43f67ff4d1c8.png)

Once the agent accounts have been created on the Haptik Platform, you can search for their username and add them in the team by clicking on the green tick icon. 

![image](https://user-images.githubusercontent.com/75118325/120189869-7cee9d80-c235-11eb-8ae5-c71943866b60.png)

**_Remove an agent from the Team_** - 

To remove the agent from the Team, you can click on the delete icon, as shown below - 

![image](https://user-images.githubusercontent.com/75118325/120190060-b6270d80-c235-11eb-90e7-4db5cf4ab2fd.png)

### View no. of queues, active, waiting for user chats

You can check the current chats in different states which have been to the agents, once the agents start to receive the chats.

![image](https://user-images.githubusercontent.com/75118325/120190249-f5edf500-c235-11eb-99ea-1511fbfa7e1a.png)

### Set chat concurrency

You can set the chat concurrency for the agents i.e., the number of chats an agent will recieve at a particular moment. If an agent named **gogo** has a concurrency set at **3**, then **gogo** will be responsible to handle 3 different user chats at a given moment of time.

> If **gogo** is a part of **2** different teams and has a chat concurrency of **3** on both the teams, then **gogo** might also receive **6 (3+3)** chats from 6 different users.

The chat concurrency ranges from **1 to 5** and **3** is the default chat concurrency.

![image](https://user-images.githubusercontent.com/75118325/120190803-b83d9c00-c236-11eb-83e6-33f455f4c43c.png)

### View agent status

You can check if the agents are online or offline from the same section.

![image](https://user-images.githubusercontent.com/75118325/120190906-d86d5b00-c236-11eb-8f35-aba8f3a7bb12.png)

### View agent chats

To see the chats handled by a particular agent, you can click on the **View Chats** button, this will redirect you to **Chats** tab in the Teams section.

![image](https://user-images.githubusercontent.com/75118325/120191076-15d1e880-c237-11eb-9f39-da5c0ae44cf8.png)

## Change Team Settings

### **Step 1 - Select a language (Optional)**

If you have multilingual IVA, you can first select the language from the dropdown to configure the following messages.

![language_for_messages](assets/TeamsLanguage.png)

### **Step 2 - Setup Team Offline message**

If a team status id is defined as offline, the team should configure it. When users send a message and all agents have logged out, you can setup a default message for the end user. For example, this message could say `"Sorry, no agents are available at the moment. We will respond to you as soon an agent is online".`

![Offline message](assets/Teams1.png)

This message will come when none of the agents assigned to that business is Online. This is also customizable and also we can adjust whether we want to complete the chat in this case or not.

> Ideally, we suggest agents to go offline first and then logout. So, first an agent closes chats in their queue. And then they logout as soon as they're to end their daily shifts. 

There is a toggle of Marking Chat as complete. This means -

- If the Toggle is **ON**, i.e Green colour - All the chats will be completed when agents are Offline.

- If the Toggle is **OFF**, i.e Red colour - All the chats will remain in Pending/Queued State when agents are Offline.

### **Step 3 - Setup Team Delay Message and Delay Time**

Similar to the Team Offline message, you can configure the delay message that is sent to users with a set delay time. This message will be sent to the user when all agents are busy will other chats. This is customizable and we can adjust the time after which this message will be sent.

![Delay message](assets/Teams2.png)

> Note: Offline message will appear immediately after the user has initiated an agent chat, whereas Delay Message will appear after the specified time interval.

### **Step 4 - Setup User Recall Message and Recall Time**

Similar to the Delay message, you can configure the recall message to get the user back in the conversation. This message is sent once the chat has started with the agent but the user has stopped replying in between to the Agent. The time can be configured between 0s to 8m. 

![Recall message](assets/Teams3.png)

After making all the adjustments, Don't forget to Save all the changes which you have done.
