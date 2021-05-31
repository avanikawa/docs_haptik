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
* language_code

There is a small **Show More** option which expands the User Details section. You can use this section to display details which were collected from the user in the bot, apart from above mentioned ones.

![image](https://user-images.githubusercontent.com/75118325/119975610-b1631f00-bfd3-11eb-8f23-01c918b6f0f8.png)


### When will you need to show extra details?

There are two instances when you would require to display additional user details.

#### Displaying specific information

The agents may need access to see the custom user details on the RHS of the user who is assigned/initiated/pinned to that agents screen.

##### How can the information be displayed?

- For signed-in user
  - You can provide custom parameters during signup process.
  - These details need to be stored in the **UserDetails** table, as a key and value pair (this is done from the code node on Conversation Studio tool).
    - The value of “Key” will appear as the label for that user property.

- For guest user
  - You can collect for information from the user in the bot flow and store in **UserDetails** table (this is done from the code node on Conversation Studio tool).
  
- For guest user with no bot
  - You will have to provide custom parameters during signup process.

#### When agents require the information for creating CRM tickets

Whenever agent is required to create a ticket on some CRM tool, they might need extra user details.

- External CRM Tool integration
  - You will have to create an HTML file which has a button the save the information in the CRM.
    - That HTML file would have access to the [**AthenaSDK**](https://docs.haptik.ai/agent-chat/adding-custom-tools#using-athena-sdk), via which you can fetch user details and pre-load the HTML page if required.


### Where will the User Details be available?

The User Details will be visible to them who have approriate access to see personal details of the users. To know more about the access, click [**here**](https://docs.haptik.ai/bot-analytics/chat-links).

These User Details are available on  - 
* Raw Chat Link 
* [User Info Links](https://docs.haptik.ai/agent-chat/action-toolbars#user-info-link)
* [Business/Teams in the view user details section](https://docs.haptik.ai/agent-chat/businesses#section-3-chat-detail-view)


