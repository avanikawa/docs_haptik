---
title: Using Conversation Studio
---

Haptik Platform's **Conversation Studio** has pre made **Skills** built for your use-case that can be implemented for your Shopify bot. The **Haptik Bot** comes with these pre-built use-cases - 
* Track order status 
* Cancel order request
* Place an return and replacement request

You can built use-cases apart from these usecases by following the Haptik guide, [**here**](https://docs.haptik.ai/bot-builder/basic/making-first-bot).

Haptik Smart Skills uses Shopify APIs to provide real-time information to the users. These Smart Skills have all the APIs in-built. You can simply import these Smart Skills and start using using the bot by making few changes to bot, such as modifying the Bot Resposes according to your business requirement.

## Step 1: Create a New Bot

We will start by creating a new bot on the platform. 

1. Go to [**Conversation Studio**](https://staging.hellohaptik.com/mogambo/#/bots)
2. Click on **New Bot**
3. Provide a **name**, select the **partner** from dropdown and provide some additional details (these are optional)
4. Click on **Create Bot**

![image](https://user-images.githubusercontent.com/75118325/114122315-a5c97500-990d-11eb-999f-425e88d6add9.png)

## Import the Smart Skills

Once the bot is created, you can create a [**Skill Set**](https://docs.haptik.ai/bot-builder/basic/create-your-first-bot). Within this Skill Set, you can now add the Shopify Skills.

Click on the **+ Add Skills** button to add required skills on the IVA. As soon as the button is clicked, a modal would open showcasing all skills available on the platform. Search for **Shopify** and you will be able to see the Shopify Smart Skills

Click on **Add Smart Skill** button to import the entire user journey on to your bot.

### Track order status (Skill name -> **Shopify Track My Order**)

This Skill is used to fetch the orders from Shopify and display them to users on the bot.

### Cancel order request (Skill name -> **Shopify Order Cancellation**)

This Skill allows users to to cancel their order using Shopify APIs.

### Place an return and replacement request (Skill name -> Shopify Return And Replacement)

This Skill will allow user to either return their order to place a replacement request.

![image](https://user-images.githubusercontent.com/75118325/119783369-c3b55e00-beea-11eb-8d1a-a4d6aa275e7b.png)

## Changing the APIs

Once you have imported the Smart Skills, please contact your Haptik SPOC to update the Shopify credentails on the bot.

## Create a Team on Smart Agent Chat

In case where human intervention is required, you can set up a team of agents who can then handle escalationson the bot and help resolve user's queries faster.

Read [**here**](https://docs.haptik.ai/agent-chat/) to setup the team.

## Train and Transfer the bot

After the credentials have been updated, you can now train the bot and Trasnfer the bot to production environment.
