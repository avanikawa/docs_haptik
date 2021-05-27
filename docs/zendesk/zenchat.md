---
title: Zendesk Messaging
---

Zendesk Messaging uses inept synchronous API communication. Please refer the UI compatibility section [**here**](http://docs.haptik.ai/zendesk/zendesk-ui) to know the limitations.

This guide will help you to connect Haptik bot Zenchat Web SDK to handle live agent integration in Zenchat.

**What you'll need -** 
- Zendesk License
- Access to Haptik Platform

## Step 1: Create a New Bot on Haptik Platform

Firstly, you will have to create a new bot on the Haptik Platform.

To know more about how to create a new bot on Haptik Platform, click [**here**](https://docs.haptik.ai/bot-builder/basic/making-first-bot).

## Step 2: Create Chat Only account on Zendesk

Create an agent account and keep it reserved for a bot.

i. Click on the **+ Add** button on the top left corner to create a new User.

![image](https://user-images.githubusercontent.com/75118325/119138908-0cd75f00-ba60-11eb-9b8e-d39789993223.png)

ii. A pop-up will appear. Provide the name, email and role for the new user.

![image](https://user-images.githubusercontent.com/75118325/119139050-385a4980-ba60-11eb-8fb5-15a4c62fa710.png)

iii. You can check the create user in the **Manage** section.

![image](https://user-images.githubusercontent.com/75118325/119139333-866f4d00-ba60-11eb-8980-912133c0055e.png)

> You can create upto **5** agents.

 We have 2 agents here, `Haptik Human` and `Haptik Bot`. `Haptik Bot` is the agent for which you will carry out the following steps.
 
 `Haptik Bot` is being configured to respond back to the users on the actual bot.
 
## Step 3: Creating API and SDKs in Zenchat dashboard

On the Dashboard, click on the **Apps** option in the top right corner and select **Chat**.

![image](https://user-images.githubusercontent.com/75118325/116492749-af198200-a8ba-11eb-8ae4-bb36c16ab51e.png)

Navigate to **Settings -> Accounts -> API & SDKs** section

![image](https://user-images.githubusercontent.com/75118325/116492907-19322700-a8bb-11eb-9ef5-399abb27a9fc.png)

Click on **Add API client**. Here, provide the following details - 

* **Client Name**, example `Haptik IVA`
* **Company Name**, example `Jio`
* **Redirect URLs**

  * Here, provide the following link -
  
   `https://<BASE_URL>/third_party_integrations/v1/zendesk_live_chat/generate_token/<BUSINESS_ID>`
    * Replace the <BUSINESS_ID> with the bots business id. To know how to get the business id for your bot, click [**here**](https://docs.haptik.ai/bot-builder/basic/sharebot#what-does-the-share-option-do).
    * Haptik will provide the <BASE_URL>.
    
    * The URL would resemble this format - 
    
    `https://env.haptikapi.com/third_party_integrations/v1/zendesk_live_chat/generate_authorize_url/xxxx`

Once the API Client is added, a pop-up will appear. Copy these keys.

> These keys will be displayed only once, please copy these keys and store them.

![image](https://user-images.githubusercontent.com/75118325/116493400-4c28ea80-a8bc-11eb-841a-2bcef3215ef8.png)

## Step 4: Provide the keys on Haptik Platform

In the **Business Manager** section of the bot, you can now configure the keys acquired in Step 3.

Navigate to **Platform Deployment** on the Business Manager, under **Channels** section and select the Platform as **Zendesk Live Chat**.

Here, provide the following keys - 
* **ZD Client ID**: This is the **Client ID** from the Zendesk API Client, created in step 3.
* **Client Name**: This is the Client name provided in step 3.
* **Subdomain**: This will the Zendesk subdomain. Zendesk provides a domain name while signing up.
  * For example, if this value is `haptik`, the URL will be `https://haptik.zendesk.com/`
* **Client Secret**: This is the **Client Secret** from the Zendesk API Client, created in step 3.
* **Authorization URL**: This field is auto generated.

![image](https://user-images.githubusercontent.com/75118325/119141550-05fe1b80-ba63-11eb-99ad-0856464759be.png)

Open the **Authorization URL** in the browser. It will open up the authentication screen. Click on **Allow** here.

![image](https://user-images.githubusercontent.com/75118325/116494457-7c718880-a8be-11eb-8f74-57b8fdf6d55c.png)

After clicking on **Allow** it will be redirected to an empty screen. Now the OAuth flow is completed successfully.

### Step 3: Starting websocket connection

**This will be completed by Haptik.**

Once the steps are executed, you can now test the connection.
