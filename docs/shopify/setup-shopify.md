---
title: Connect Haptik & Shopify
---

In this guide, you will be able to complete the configuration required to integrate Shopify with Haptik.

What you'll need - 

- A Shopify account, register yourself a partner using the Shopify account. Read [**here**](https://help.shopify.com/en/partners/faq/partner-program#how-do-i-become-a-shopify-partner) to know more about becoming a partner on Shopify.
- Access to Haptik Platform

## Step 1: Register as a partner

Navigate to [**https://www.shopify.com/partners**](https://www.shopify.com/partners). Register your business as a partner on Shopify.

![image](https://user-images.githubusercontent.com/75118325/117311095-85a3bc00-aea1-11eb-8aae-c9cc989e794c.png)

Once you have provided the details, you will reach here - 

![image](https://user-images.githubusercontent.com/75118325/117383977-908d3980-aeff-11eb-9add-dc92c4baea0b.png)

## Step 2: Create a New App

Click on **Apps** in the left sidebar and then click on **Create App** button.

![image](https://user-images.githubusercontent.com/75118325/117384203-190bda00-af00-11eb-9c26-847764460f3d.png)

## Step 3: Setting up the Custom App

Select the app type to be **Custom App**

![image](https://user-images.githubusercontent.com/75118325/117385459-c8e24700-af02-11eb-9c88-98f9888e113e.png)

Here, provide the -
* **App name** - This can be any app name
* **App URL** and **Allowed redirection URL(s)** - The URLs will be provided by Haptik.

![image](https://user-images.githubusercontent.com/75118325/117385390-a2241080-af02-11eb-9021-c505b0b0ed5a.png)

You can check the new app in the **Apps** section.

![image](https://user-images.githubusercontent.com/75118325/119133312-5ec8b680-ba59-11eb-98a2-214e0a90748d.png)

## Step 4: Providing the keys on Haptik Platform

When you open the newly created app, you will find the **API key** and **API Secret Key**

![image](https://user-images.githubusercontent.com/75118325/117386868-46a75200-af05-11eb-8d01-d50544a4cf6d.png)

Copy these keys and provide it on the **Platform Deployments** section of the Business Manager on Conversation Studio tool.

## Step 5: Authenticate the App

Once the keys are provided, click on **Generate Link** button

![image](https://user-images.githubusercontent.com/75118325/117387110-d816c400-af05-11eb-9e27-f8d1aa9c3240.png)

Provide your domain name. This domain name gets created when you create your store on Shopify. 

> The domain name can be found from the **Stores** section.

For example, if the store name is `haptik`, then the domain name will be `haptik.shopify.com`

You can read more about Shopify domains, [**here**](https://help.shopify.com/en/manual/online-store/domains).

![image](https://user-images.githubusercontent.com/75118325/117389588-3645a600-af0a-11eb-90b9-cae5abc115a1.png)

A new link gets generated here. Copy the link and open it in a new tab of your browser for the authentication process. You will able to see the following screen.

![image](https://user-images.githubusercontent.com/75118325/119753849-1710b780-bebd-11eb-8023-438b3947577d.png)

* When you click on **Make it live** option, the bot will be deployed on your Shopify page.
* When you click on **Test IVA**, a dummy HTML page will open up where you can do a functional testing of the bot.


Voila! Once you have tested the bot, your users will then be able to communicate with the bot. Read [**here**](https://docs.haptik.ai/shopify/build-shopify) to know more about the use-cases you can implement on your bot.
