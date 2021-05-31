---
title: Adding User Details
---

On the **MyChats** page, agents can check the **User Details** tab on the right hand side of the screen. These details are collected from the user in the user journey on the bot.

The following user details are visible to the agents - 
* Name
* Email
* Phone
* Country
* Timezone
* Platform

There is a small **Show More** option which expands the User Details section. You can use this section to display details which were collected from the user in the bot, apart from above mentioned ones.

![image](https://user-images.githubusercontent.com/75118325/119975610-b1631f00-bfd3-11eb-8f23-01c918b6f0f8.png)


### When will you need to show extra details?

There are two instances when you would require to display additional user details.

#### 1. Displaying specific information

The agents may need extra information about the user for providing better & faster resolution.

**How can the information be displayed?**

- For signed-in user
  - You can provide custom parameters during signup process.
  - These details need to be stored in the **UserDetails** table, as a key and value pair (this is done from the Code node on Conversation Studio tool).
    - The value of “Key” will appear as the label for that user property.

- For guest user
  - You can collect for information from the user in the bot flow and store in **UserDetails** table (this is done from the Code node on Conversation Studio tool).
  
- For guest user with no bot
  - You will have to provide custom parameters during signup process.

#### 2. When agents require the information for creating CRM tickets

Whenever agent is required to create a ticket on some CRM tool, they might need extra user details. For that, an HTML file is required which has a button to save the information on the CRM. That HTML file would have access to the [**AthenaSDK**](https://docs.haptik.ai/agent-chat/adding-custom-tools#using-athena-sdk), via which you can fetch user details and pre-load the HTML page if required.

### Where will the User Details be available?

The User Details will be visible to them who have approriate access to see personal details of the users. To know more about the access, click [**here**](https://docs.haptik.ai/bot-analytics/chat-links).

These User Details are available on  - 
* Raw Chat Link 
* [Chat Links](https://docs.haptik.ai/bot-analytics/chat-links)
* Business/Teams in the View user details section (Refer the GIF below)

![user details](https://user-images.githubusercontent.com/55389979/120199468-e58f4780-c240-11eb-9f6b-c54f564afebd.gif)
