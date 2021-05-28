---
title: Setup Zendesk and Sunshine Conversation
---

Zendesk and Sunshine Conversation provide powerful asynchronous conversations which is the ideal solution to integrate with an Intelligent Virtual Assistant.
The following setup will help you configure Haptik IVA within Zendesk and Sunshine Conversation ecosystem. Once the process is complete, your agents can start conversing with the users using the Zendesk Platform.

**What you'll need -** 
* **Zendesk** license
* **Sunshine Conversations** license
  * While buying Sunshine license, **reach out to Zendesk support** for connecting your Sunshine account with the Zendesk account. Zendesk will create an app within your Sunshine account and link it as well.
* Access to the **Haptik** Platform

> Ensure on the Sunshine Conversations account, if you are able to see the app created by Zendesk. This app will have **Zendesk** as a prefix.

![image](https://user-images.githubusercontent.com/75118325/119676057-2fe88100-be5b-11eb-86bf-b15e731ed63b.png)

## Setting up Zendesk and Sunshine Conversation

### Step 1: Build a New Bot on Haptik Platform

Firstly, you will have to create a new bot on the Haptik Platform. This bot will be connected to Zendesk + Sunshine Integration. 

To know more about how to create a new bot on Haptik Platform, click [**here**](https://docs.haptik.ai/bot-builder/basic/making-first-bot).

> Whenever there needs to be a transfer from bot to a human agent, on the bot add **Bot Says** containing the text `chat with an agent`. When the bot encounter this bot response, the chat will be handed over to a live agent on Zendesk.
> 
> ![image](https://user-images.githubusercontent.com/75118325/116491235-0d446600-a8b7-11eb-9ddd-4bdf7ff0af08.png)

### Step 2: Complete the OAuth process

Haptik will provide you with an authentication link that will complete the process of connecting your Haptik IVA with Sunshine Conversation.

To generate authentication link, reach out to your Haptik SPOC with a request to create the authentication link. Your SPOC will respond back with the link. The link will be in this format - 

`https://app.smooch.io/oauth/authorize?client_id=haptik&response_type=code&state=<state_code>`

Once you click on the link and the OAuth process is completed, you will get the following screen

![image](https://user-images.githubusercontent.com/75118325/116486922-5ba03780-a8ac-11eb-99a2-18941a976659.png)

Once the OAuth is successfully completed, the highlighted keys get auto populated in the **Business Manager** section of Conversation Studio tool on Haptik Platform.

![image](https://user-images.githubusercontent.com/75118325/119683787-907abc80-be61-11eb-8cb5-c81056a38ae7.png)

You can then provide the **App Key** and **App Secret key**, which can be found in the **Sunshine App**.

> On Sunshine App, you will be able to see an app created by **Zendesk**.
> 
> The app name will have Zendesk as a prefix.
> 
> ![image](https://user-images.githubusercontent.com/75118325/119684333-0da63180-be62-11eb-830e-69469203578e.png)
> 
> Once you click on the app name, navigate to **Settings** tab
> 
> ![image](https://user-images.githubusercontent.com/75118325/119684564-3b8b7600-be62-11eb-805d-0e2fa81f721d.png)
> 
> On scrolling down, you can find the **App ID** and **API Keys**
> 
> ![image](https://user-images.githubusercontent.com/75118325/119684857-79889a00-be62-11eb-96d2-bc0adc037c7c.png)
> 
> Provide the **App ID** as **App Key** and **API Keys** as **App Secret**
> 

As the authentication is complete, you will now be able to see **Haptik** as one of the intergration within your **Sunshine App**.

> _You should be seeing **Zendesk** and **Haptik** on this screen_
>
> ![image](https://user-images.githubusercontent.com/75118325/119686182-b43f0200-be63-11eb-8b32-dad5ea421f90.png)

### Step 3: Channel Integration on Sunshine Conversation

In this step, you can select the preferred channel you want to deploy the bot on.

Click on **Connect Channels** within your newly created app.

![image](https://user-images.githubusercontent.com/75118325/116487092-d0737180-a8ac-11eb-821d-4496fe107de7.png)

_You can add multiple channels within the Sunshine app._

### Step 4: Sunshine Switchboard Configuration

Whenever there is a human assistant involved, there needs to be a decision maker which passes the control between different parties. The decision maker will correctly route control to the widget either from a bot or a live agent. **Switchboard is the decision maker.**

Switchboard enables businesses to build a seamless integration between the chatbot solution and other Sunshine Conversations integrations, including the Zendesk Suite - enabling shared customers to take full advantage of the joint solution.

Switchboard delivers dedicated API endpoints to help your software pass, offer, and accept control of a given conversation and manage the flow of messages between a customer and various business systems.

Switchboard API configuration can be done by calling the open APIs provided by Sunshine.

The following is an overview of the switchboard setup process. Each step is covered with their cURL requests below:

**1. Create the switchboard**

Switchboards are created with an empty post body. They begin in a disabled state by default so as to not interfere with the delivery of messages while it is being configured.

```
POST /v2/apps/:app_id/switchboards

curl $SUNSHINE_CONV_ROOT/v2/apps/:app_id/switchboards \
     -X POST \
     -u app_keyid:app_secretkey
```

**2. Create the bot `switchboardIntegration`, specifying the existing custom integration or partner integration to be wrapped**

```
curl $SUNSHINE_CONV_ROOT/v2/apps/:app_id/switchboards/:switchboard_id/switchboardIntegrations \
     -X POST \
     -d '{"name": "bot", "integrationType": "CLIENT_ID", "deliverStandbyEvents": false}' \
     -H 'content-type: application/json' \
     -u app_keyid:app_secretkey
```

**3. Create the **agent** `switchboardIntegration`, specifying the existing custom integration or partner integration to be wrapped, AND the **bot’s** `switchboardIntegrationId` as `nextSwitchboardIntegration`**

You will get the `switchboard_integration_id` after calling the API in Step 2 which you will be using in step 4 (in the URL).

```
curl $SUNSHINE_CONV_ROOT/v2/apps/:app_id/switchboards/:switchboard_id/switchboardIntegrations \
     -X POST \
     -d '{"name": "ZD", "integrationType": "zd:agentWorkspace", "deliverStandbyEvents": false, "messageHistoryCount": 10, "nextSwitchboardIntegrationId": "BOT_SWITCHBOARD_INTEGRATION_ID" }' \
     -H 'content-type: application/json' \
     -u app_keyid:app_secretkey
```

You will receive an ID which should be placed as `nextSwitchboardIntegrationId` in step 4.

**4. Update the **bot** `switchboardIntegration` with the **agent** `switchboardIntegrationId` as `nextSwitchboardIntegration`**

```
curl $SUNSHINE_CONV_ROOT/v2/apps/:app_id/switchboards/:switchboard_id/switchboardIntegrations/:switchboard_integration_id \
     -X PATCH \
     -d '{"nextSwitchboardIntegrationId": "ZENDESK_AW_SWITCHBOARD_INTEGRATION_ID"}' \
     -H 'content-type: application/json' \
     -u app_keyid:appsecretkey
```

**5. Update the switchboard with the bot’s `switchboardIntegrationId` as `defaultSwitchboardIntegration`**

```
curl $SUNSHINE_CONV_ROOT/v2/apps/:app_id/switchboards/:switchboard_id \
     -X PATCH \
     -d '{"defaultSwitchboardIntegrationId": "BOT_SWITCHBOARD_INTEGRATION_ID", "enabled": true}' \
     -H 'content-type: application/json' \
     -u app_keyid:app_secretkey
```

**6. To activate, update the switchboard with `enabled: true`**

```
curl $SUNSHINE_CONV_ROOT/v2/apps/:app_id/switchboards/:switchboard_id \
     -X PATCH \
     -d '{"defaultSwitchboardIntegrationId": "BOT_SWITCHBOARD_INTEGRATION_ID", "enabled": true}' \
     -H 'content-type: application/json' \
     -u app_keyid:app_secretkey
```

> In case you need help with the configuration, please reach out to Haptik SPOC to complete this process.

## Setting up agents on Zendesk

When user wants to connect with an agent at Zendesk, you need to enable the **Agent Workspace** on Zendesk first. Navigate to **Settings** -> **Agents**

![image](https://user-images.githubusercontent.com/75118325/119787030-66bba700-beee-11eb-969b-1b56c6511fab.png)

To add a new agent, click on the **+Add** button, after providing the details, an email will be sent to the newly registered user

![image](https://user-images.githubusercontent.com/75118325/119787391-c7e37a80-beee-11eb-8b14-ce58194e36cd.png)

To check the agents, you can navigate to **People** section as shown below - 

![image](https://user-images.githubusercontent.com/75118325/119790821-dbdcab80-bef1-11eb-9775-f950e7ecc2b1.png)

## Integrating the Sunshine SDK or channels

To integrate the bot on your preffered channel (refer **Step 3** to add channel in your app) you can follow the guides prepared by Sunshine.

You will find the credentials, mentioned in the Sunshine guides, on the Zendesk-Sunshine app.

Click on the app which Zendesk created in your Sunshine account. 

<table>
  <th>Web Messenger</th>
  <th>WhatsApp</th>
  <th>Facebook Messenger</th>
  <th>LINE</th>
  <tr>
    <td><a href="https://docs.smooch.io/guide/web-messenger/" taregt="_blank"> Integrate a web bot</></td>
    <td><a href="https://docs.smooch.io/guide/whatsapp/" taregt="_blank"> Integrate a WhatsApp bot</></td> 
    <td><a href="https://docs.smooch.io/guide/facebook-messenger/" taregt="_blank"> Integrate a Facebook bot</></td>
    <td><a href="https://docs.smooch.io/guide/line/" taregt="_blank"> Integrate a Line bot</></td>
  </tr>
</table>

## Testing the connection

After you have completed the integration of bot, you can test the bot.

Once you send a message, for example - `connect me with an agent`, a new case should get added on the Zendesk.
