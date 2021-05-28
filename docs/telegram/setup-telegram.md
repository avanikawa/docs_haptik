---
title: Setup Telegram Bot
---

## Step 1: Start creating a new bot on Telegram

To get started with Telegram bot, you will first need to create a new bot on Telegram.

To create a new bot on Telegram, open your Telegram account and search for **BotFather** in the search bar. **BotFather** will ask you some questions with respect to the new bot want to create.

![image](https://user-images.githubusercontent.com/75118325/119954966-2bd47480-bfbd-11eb-8706-97cdb5be0511.png)

Click on **Start**.

The **BotFather** responds with the list commands that can be used to create a new bot.

## Step 2: Create the bot by providing bot details

### Provide not name

Once you start typing **/new** it will auto suggest the option to create a new bot **/newbot**. 

![image](https://user-images.githubusercontent.com/75118325/119955885-21ff4100-bfbe-11eb-9ab3-477c1170d474.png)

### Provide username for the bot

The username should end with **__bot** and should be unique. If the username is already take, it will ask you to provide the username again.

Once the username is accepted, you will receive a **Congratulations** message along with an **API token** for the bot.

> Copy this API token in a safe place, you will have to provide the key in the Platform Deployment section of Haptik Platform.

![image](https://user-images.githubusercontent.com/75118325/119957832-1280f780-bfc0-11eb-9685-cdd13dadf303.png)

Now the bot has been created on Telegram.

## Step 3: Build a new bot on Haptik Platform

Once the bot is created on Telegram, you can now build the user journeys on the COnversation Studio tool of Haptik Platform.

To know more about how to create a new bot on Haptik Platform, click [**here**](https://docs.haptik.ai/bot-builder/basic/making-first-bot).

> Click [**here**](docs.haptik.ai/telegram/telegram-ui) to see how different types of messages will get rendered on Telegram bot.

## Step 4: Provide the Platform Deployment settings

Once the bot is created on Conversation Studio tool, you will have to provide the **Telegram Access Token** (from Step 2) and **Telegram Base URL**.

Here,
* Mark the channel as **Active**, by enabling the toggle button
* Provide the **Telegram Base URL** as **api.telegram.com**
* Provide the **Telegram Access Token** which was generated on the Telegram bot.

![image](https://user-images.githubusercontent.com/75118325/119964976-60e5c480-bfc7-11eb-8256-64e0569a71f3.png)
