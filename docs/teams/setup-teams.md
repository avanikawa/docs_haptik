---
title: Create a bot on Teams
---

Creating a bot on Microsoft Team is a simple 2 step process. This guide will help you create a new bot in Microsoft Teams and deploy the Haptik bot in Teams.

What you'll need - 
* Microsoft account for Teams
* Access to Haptik Platform

## Step 1: Navigate to App Studio

1. Login to Teams using organization account.
2. On the left sidebar click on **...**
3. Click on **App Studio**

## Step 2: Create a bot on Teams

1. In the **App Studio**, select **Bot Management**

![image](https://user-images.githubusercontent.com/75118325/121464389-6e407d00-c9d1-11eb-9f55-5a1af9c24a2f.png)

2. Create a new bot by providing a bot name and click on **Create**. 

![image](https://user-images.githubusercontent.com/75118325/121464554-b2cc1880-c9d1-11eb-925f-c14252a477fb.png)

_If you already have a bot created, you can choose to select the bot from **Existing bot registrations**._

When the bot is created, a **Bot ID** and **App Password** are generated. You will have to provide theses keys in the **Platform Deployments** section of the Haptik Platform.

## Step 3: Create a bot on Conversation Studio tool of Haptik platform

On Conversation Studio tool, you can create the AI powered user journeys. Click [**here**] to know more about creating a bot on Haptik platform.

## Step 3: Provide Platform Depployment Keys

1. Navigate to **Platform Deployments** section on the Business Manager.
2. Here,
   * Select the **Platform** as **Microsoft Teams**.
   * Mark the Status as **Active**.
   * Provide the **Bot ID** (generated in Step 2) in the **Microsoft teams client id** field.
   * Provide the **App Password** (generated in Step 2) in the **Microsoft teams client secret** field.

![image](https://user-images.githubusercontent.com/75118325/121465269-1c98f200-c9d3-11eb-8248-769fcb62d37e.png)


Once you have developed the bot on Conversation Studio and provided the credentials, you can now test the bot on Teams.
