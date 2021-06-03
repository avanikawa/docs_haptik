---
title: Setup and Implementation
---
 
Setting up a Telegram bot is a simple 2 step process followed by connecting it to a Haptik bot that you create.

This guide will help you create a new bot on Telegram and user journeys on the Haptik Platform.

## Step 1: Start creating a new bot on Telegram
 
To get started with the Telegram bot, you will first need to create a new bot on Telegram.
 
Open your Telegram account and search for **BotFather** in the search bar. **BotFather** will ask you some questions about the new bot want to create.
 
![image](https://user-images.githubusercontent.com/75118325/119954966-2bd47480-bfbd-11eb-8706-97cdb5be0511.png)
 
Click on **Start**.
 
The **BotFather** responds with the list commands that can be used to create a new bot.
 
## Step 2: Create the bot by providing bot details
 
### 1. Provide bot name
 
Once you start typing **/new** Telegram will auto-suggest the option to create a new bot, tap on the **/newbot** command. 
 
![image](https://user-images.githubusercontent.com/75118325/120011710-3cf0a600-bffc-11eb-90bb-dc347b5de65d.png)
 
### 2. Provide username for the bot

Once the bot name is accepted, Telegram will then ask you to enter a username.
 
The username should end with **__bot** and should be unique. If the username is already taken, it will ask you to provide the username again.
 
Once the username is accepted, you will receive a **Congratulations** message along with an **API token** for the bot.
 
> Copy this API token in a safe place, you will have to provide the key in the Platform Deployment section of Haptik Platform (covered in Step 4).
 
![image](https://user-images.githubusercontent.com/75118325/119957832-1280f780-bfc0-11eb-9685-cdd13dadf303.png)
 
Now the bot has been created on Telegram.
 
## Step 3: Build a new bot on Haptik Platform
 
Once the bot is created on Telegram, you can now build the user journeys on the Conversation Studio tool of Haptik Platform.
 
#### 1. Create a new bot on Conversation Studio
 
1. Go to [**Conversation Studio**](https://staging.hellohaptik.com/mogambo/#/bots)
2. Click on **New Bot**
3. Provide a **name**, select the **partner** from the dropdown, and provide some additional details (these are optional)
4. Click on **Create Bot**
 
![image](https://user-images.githubusercontent.com/75118325/114122315-a5c97500-990d-11eb-999f-425e88d6add9.png)
 
#### 2. Create SkillSet and Skills
 
A Skill Set is a collection of skills that enable your IVA to handle queries that need a complex conversational journey. These skills help the user to resolve their queries. A Skill Set aligns with the overall goals of the IVA.
 
Click [**here**](https://docs.haptik.ai/bot-builder/basic/create-your-first-bot) to know more about SkillSet and Skills.
 
 
#### 3. Create Nodes
 
Nodes are the interlinked building blocks of a bot. Each node acts like a gatekeeper which **detects user inputs**, sends out appropriate **responses**, and **directs users** to the next node. 
 
Nodes are composed of several important sub-components, which house important pieces of information - User Says, Bot Says, Entities, and APIs.
 
To know more about Nodes, click [**here**](https://docs.haptik.ai/bot-builder/basic/creating-nodes).
 
#### 4. Add User Says
 
User says are the inputs from the user that the agent needs to interpret the user’s goal. It is important to add and train the bot with a variety of different sample user says for each node to identify the correct intents and extract entities from the user utterance.
 
Whenever a user sends a message, we try to understand what the user is trying to say using various Machine Learning algorithms and find the corresponding node. One of the key modules which is used for node identification is **Intent Detection module**.
 
To know more about adding user says, click [**here**](https://docs.haptik.ai/bot-builder/basic/user-says-guidelines).
 
#### 5. Add Bot Says
 
Bot Says is where a Node stores the replies that are sent in response to the user's message. 
 
To know more about Bot Says, click [**here**](https://docs.haptik.ai/bot-builder/basic/bot-says)
 
> Click [**here**](docs.haptik.ai/telegram/telegram-ui) to see how different types of messages will get rendered on Telegram bot.
 
#### 6. Add Entities
 
An entity represents values that are collected from the user in a conversation. Depending on the context of the conversation, the required response can either be a single value or a group of specific values.
 
To know more about entities, click [**here**](https://docs.haptik.ai/bot-builder/basic/entities).
 
#### 7. Create Connections
 
Connections represent the path a conversation takes from node to node. Depending on the response a user inputs to the bot, they traverse down a different connection to the appropriate next node. Bot builders must modify every connection they create to indicate which user inputs correspond to which nodes.
 
To know more about connections, click [**here**](https://docs.haptik.ai/bot-builder/basic/connections).
 
#### 8. Setup Smart Agent Chat to handle human escalations (optional)
 
Smart Agent Chat is a tool on the Haptik Platform which allows agents to handle conversations with users to resolve their queries. 
 
To know more about setting up Smart Agent Chat, click [**here**](https://docs.haptik.ai/agent-chat/).
 
#### 9. Quality Assessment
 
Follow our [**Quality Assessment**](https://docs.haptik.ai/bot-builder/basic/testing-introduction) section to test the bot.
 
Once the bot is functionally tested, you can now provide the credentials on the **Platform Deployments** section of **Business Manager** section on the Conversation Studio tool.
 
## Step 4: Provide the Platform Deployment settings
 
Once the bot is created on the Conversation Studio tool, you will have to provide the **Telegram Access Token** (from Step 2) and **Telegram Base URL**.
 
Here,
* Mark the channel as **Active**, by enabling the toggle button
* Provide the **Telegram Base URL** as **api.telegram.com**
* Provide the **Telegram Access Token** which was generated on the Telegram bot.
 
![image](https://user-images.githubusercontent.com/75118325/119964976-60e5c480-bfc7-11eb-8256-64e0569a71f3.png)
 
After the credentials are provided, you can now test the bot on the Telegram bot.
