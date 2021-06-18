---
title: Create a bot on Teams
---

Creating a bot on Microsoft Team is a simple process. This guide will help you create a new bot in Microsoft Teams and deploy the Haptik bot on Microsoft Teams.

**Pre-requisites -**

* Microsoft account for Teams
* Access to Haptik Platform

## Step 1: Navigate to App Studio

1. Login to Teams using organization account.
2. On the left sidebar click on **...**
3. Click on **App Studio**

![Screenshot from 2021-06-15 19-00-34](https://user-images.githubusercontent.com/75118325/122516563-8b59f900-d02c-11eb-8293-c3a4e4be4de6.png)

## Step 2: Create a bot on Teams

1. In the **App Studio**, select **Bot Management**

![Screenshot from 2021-06-15 19-01-11](https://user-images.githubusercontent.com/75118325/122521232-34efb900-d032-11eb-84a0-9f017bd4a211.png)

2. Create a new bot by providing a **bot name** and click on **Create**. 

![Screenshot from 2021-06-15 19-01-42](https://user-images.githubusercontent.com/75118325/122521340-581a6880-d032-11eb-86ee-6b65f157709c.png)

_If you already have a bot created, you can choose to select the bot from **Existing bot registrations**._

When the bot is created, a **Bot ID** and **App Password** are generated. You will have to provide these keys in the **Platform Deployments** section of the Haptik Platform.
* **Bot ID** - will already be visible.
* Click on **Generate new password** to create a new password.

_App Password is generated and visible only **once**. Please save the App Password in a safe file before closing the pop-up._

## Step 3: Create a bot on Conversation Studio tool of Haptik platform

On Conversation Studio tool, you can create the AI powered user journeys. Click [**here**](https://docs.haptik.ai/teams/on-cs) to know more about creating a bot on Haptik platform.

## Step 4: Provide Platform Deployment Keys

1. Navigate to **Platform Deployments** section on the Business Manager.
2. Here,
   * Select the **Platform** as **Microsoft Teams**.
   * Mark the Status as **Active**.
   * Provide the **Bot ID** (generated in Step 2) in the **Microsoft teams client id** field.
   * Provide the **App Password** (generated in Step 2) in the **Microsoft teams client secret** field.

![image](https://user-images.githubusercontent.com/75118325/121465269-1c98f200-c9d3-11eb-8248-769fcb62d37e.png)

## Step 5: Provide the Callback URL in Teams Bot

Copy the **Callback URL** from Platform Deployments section (step 4) and paste the URL in the **Bot endpoint address** section of the Teams Bot, as shown below  -

![Screenshot from 2021-06-15 19-03-04](https://user-images.githubusercontent.com/75118325/122527943-6d46c580-d039-11eb-8130-b1e36051b4b9.png)

## Step 6: Create an App in Microsoft Teams

Navigate to **App Studio** (refer Step 1). Click on **Create a new app**.

![Screenshot from 2021-06-15 19-04-23](https://user-images.githubusercontent.com/75118325/122528414-ed6d2b00-d039-11eb-9fb3-ff3fd8c31183.png)

To create a new app, provide these values - 
1. Short name
2. Fullname
3. App ID get generated automatically
4. Package name
   This can be any name such as `com.haptik.test`
5. Version number
6. Description about the bot
7. Developer information such as your organization name, website.
8. Partner information is optional
9. In the App URLs section
    * Provide your organizations privacy statement which users will have to agree to follow
    * The terms of use which users will have to follow
10. You can then select the icon for the bot from the options

## Step 7: Set up the bot

Once you have completed the steps mentioned above, in the left sidebar, navigate to **Bots** under capabilities section.

![image](https://user-images.githubusercontent.com/75118325/122566902-b57bdd00-d065-11eb-82ed-29db7505dd82.png)

Click on **Set up**.

You can set up the already created bot (step 2) from the dropdown. 

![image](https://user-images.githubusercontent.com/75118325/122567059-e2c88b00-d065-11eb-8c0d-1a364c0255e2.png)

Here mention the **scope** of the bot, i.e. how will the bot be used.

![image](https://user-images.githubusercontent.com/75118325/122567164-04c20d80-d066-11eb-900c-d1c9720d572c.png)

Click on **Save**.

## Step 8: Install the App

Once the bot is setup, navigate to **Test and distribute** under **Finish** section on the left sidebar.

![image](https://user-images.githubusercontent.com/75118325/122567460-5074b700-d066-11eb-9db0-00551c4122ef.png)

Click on **Install**.

A modal opens up, click on **Add** option.

![image](https://user-images.githubusercontent.com/75118325/122567619-79954780-d066-11eb-8214-888d7b7db421.png)

_This will add the bot icon on the left sidebar._

## Share the Bot

To share the bot link, so that users can start communicating with the bot, navigate to [**dev.botframework.com**](dev.botframework.com).

Here you will be able to see the bots that have been created.

Left click on the bot name and select **Copy link address option**. You can share this link with users so that users can start to communicate with the bot.
