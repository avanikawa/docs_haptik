---
title: Using Conversation Studio
---

Haptik Platform's **Conversation Studio** has pre made **Skills** built for your use-case that can be implemented for your Shopify bot. The **Haptik Bot** comes with these pre-built use-cases - 
* Track order status 
* Cancel order request
* Place a return and replacement request

You can build new use-cases apart from these usecases by following the Haptik guide, [**here**](https://docs.haptik.ai/bot-builder/basic/making-first-bot).

Haptik's Smart Skills uses Shopify APIs to provide real-time information to the users. These Smart Skills have all the APIs in-built. You can simply import these Smart Skills and start using using the bot by making few changes, such as modifying the Bot Resposes according to your business requirement.

## Step 1: Create a New Bot

We will start by creating a new bot on the platform. 

1. Go to [**Conversation Studio**](https://staging.hellohaptik.com/mogambo/#/bots)
2. Click on **New Bot**
3. Provide a **Name**, select the **Partner** from dropdown
4. Click on **Create Bot**

![image](https://user-images.githubusercontent.com/75118325/114122315-a5c97500-990d-11eb-999f-425e88d6add9.png)

## Step 2: Import the Smart Skills

Once the bot is created, you can create a [**Skill Set**](https://docs.haptik.ai/bot-builder/basic/create-your-first-bot). Within this Skill Set, you can now add the Shopify Skills.

Click on the **+ Add Skills** button to add required skills on the IVA. As soon as the button is clicked, a modal would open showcasing all skills available on the platform. Search for **Shopify** and you will be able to see the Shopify Smart Skills

![image](https://user-images.githubusercontent.com/75118325/119796968-725f9b80-bef7-11eb-9af8-85efc1f56b94.png)

Click on **Add Smart Skill** button to import the entire user journey on to your bot.

![image](https://user-images.githubusercontent.com/75118325/119797270-b3f04680-bef7-11eb-811c-77e86581b3bf.png)

### Skill 1: Shopify Track My Order

This skill is used to fetch orders from the user's account on Shopify and display them on the bot.

### Skill 2: Shopify Order Cancellation

This skill allows users to cancel their order using Shopify APIs.

### Skill 3: Shopify Return And Replacement

This skill allows user to either return their order or place a replacement request.

![image](https://user-images.githubusercontent.com/75118325/119783369-c3b55e00-beea-11eb-8d1a-a4d6aa275e7b.png)

> If you want to add customized skills, please contact your Haptik SPOC.

## Step 3: Changing the APIs

Once you have imported the Smart Skills, please contact your Haptik SPOC to update the Shopify credentails on the bot.

## Step 4: Train and Transfer the bot

After the credentials have been updated, you can now train the bot and Transfer the bot to Production environment. Dont forget to transfer the Business as well to Production environment.

## Step 5: Create a Team on Smart Agent Chat

In case where human intervention is required, you can set up a team of agents who can then handle escalations on the bot and help resolve user's queries faster.

Read [**here**](https://docs.haptik.ai/agent-chat/) to setup the team. This should be done on Production directly.

## Step 6: Connect Team with Haptik's Bot

Choose the **Team** created in the previous step on Haptik's bot Business Manager. This should be done on Production directly.

![Screenshot 2021-05-27 at 3 56 04 PM](https://user-images.githubusercontent.com/55389979/119810943-2b2bd780-bf04-11eb-9e55-18afe3f6ad82.png)

## Step 7: Provide Platform Deployment details

Provide the following on the **Platform Deployments** section of the Conversation Studio tool. These keys can be found in the Shopify account.
* Domain name
* API KEY
* API TOKEN

![image](https://user-images.githubusercontent.com/75118325/119798732-08e08c80-bef9-11eb-83da-ddaa8b78acbb.png)

You can provide these details under **Platform Deployments** section on the Business Manager page of Haptik's Bot. Choose the **Platform** as Shopify Connector and fill up the details.

![image](https://user-images.githubusercontent.com/75118325/119798192-89eb5400-bef8-11eb-9022-42221b2b9695.png)

> Provide the keys on **Production** environment.
