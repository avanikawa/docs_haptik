---
title: Multilingual Virtual Assistants
---

A multilingual virtual assistant i.e. a bot that can converse with users in multiple languages, can be a tremendous asset to any organization. You can create these multilingual virtual assistants under the **Linguist Pro** plan.

## Why do we need a multilingual bot?

IVAs enable you to interact with your customers in a smarter, faster, and more engaging way. And when equipped with the ability to converse in multiple languages, they enable your brand to overcome geographical and linguistic barriers to open up new markets and reach a wider audience.

All online businesses which sell their products/services to a large customer base across the globe need to integrate a multi-lingual bot as it empowers you with benefits like -

- Provides solution in users’ native language
- Increases geographical boundary reach
- Provides personalized customer experience 
- Enhances customer base
- Improves business ROI

## Multiple IVAs vs one IVA

Creating a whole new IVA for each native language isn’t feasible nor pocket-friendly. A single chatbot that can operate effectively in all the languages is what is needed! 

We believe it would not be feasible to develop a new chatbot for every new language to be added. Particularly since any changes made to the chatbot in one language needed to be implemented across all languages. Maintaining and updating the bot would be far more efficient if changes could be made to a single bot and applied across all the languages it supported.

Essentially, this means that when our multilingual chatbot switches from one language to another, the only things that change are the User Responses, Bot Responses, and Entities – the elements that are directly concerned with language. The rest of the underlying bot framework stays the same. A system like this makes it significantly easier to scale up the number of languages a bot can support over time.

## How do Haptik's multilingual bots function?

When user sends a message in a non-english language, our **Translation layer** helps our ML model understand user's intent and go to the desired node to fetch the response in the user's language. Our **Clean-up layer** on top of our translation layer help us to achieve the desired results.

![Language15](assets/language1.png)

## How to create multilingual bots?

To start with, you would need to create an English bot. Add the desired languages on the bot and provide bot responses in these respective languages.

Follow these steps to create an end to end multilingual virtual assistant:

### Step 1

Under Edit Bot, add languages of your wish from the drop down. You can add multiple languages at once. There is no restriction in adding any number of languages.

![Language1](assets/language3.png)

If you want a language not present in the list, get in touch with your Haptik SPOC to enable it for your IVA.

> Default language of an IVA is English. If you want to make a language other than English as default language for the bot, you can use **initialize-language** configuration while integrating your bot on the website. You can read more about it [**here**](https://docs.haptik.ai/web-sdk/configuration-customisation#initialize-language).

### Step 2

Under a Node, provide **Bot Says** in the selected languages. 

![Language2](assets/language4.png)

Bot Says in all the languages should be provided before hitting SAVE. Languages with empty Bot Says will have a **Red dot** on them for identification.

![Language3](assets/language5.png)

> Bot Says is **NOT** auto translated in any language. You would need to provide Bot Says in all languages.

### Step 3

Under entities, provide language specific responses and Final response. 

![Language4](assets/language6.png)

You can add language specific **Entity Reprompts** too.

![Language5](assets/language7.png)

### Step 4

On your Business, add the language specific Taskboxes and Bot Break Messages under Content Management.

![Language7](assets/language9.png)

> Languages chosen under **Edit Bot** section are also visible under **Business Manager - General Settings** section.
  
### Step 5

You can also add language specific SDK configurations (If required).

![Language8](assets/language10.png)

> FAQ Nodes and Small talk are currently not supported in multilingual bots.

## Glossary

For words which you need some specific translation values, you can use **Glossary** to improve the understanding of those domain specific terms and increase the overall accuracy. This can be done for all selected languages.

![Language9](assets/language11.png)
    
The Glossary CSV will help you provide the specific translations. You can download it and provide your own translations of those specific terms and upload it back.

![Language10](assets/language12.png)
  
CSV Format -

![Language11](assets/language13.png)

## Entity Support

All types of entities are supported for multilingual bots, there is no restriction in its usage. 

There is no need to add dictionaries in multiple languages.

You only need to add **Entity Reprompts** in all selected languages and if there are any domain specific words, they need to be added to the **Glossary**.

## Testing multilingual bots

You can use the same debugging window for testing multilingual bots. Both original and translated messages will be shown so that you can verify the cause of a particular node being selected. 

![Language12](assets/language16.png)

## Whatsapp multilingual bots

When the user explicitly mentions **I want to switch to Hindi language**, you can use the **Language switching template** to handle it. You can find the template under the Generic category inside the template menu. You can open the template menu by clicking on the New from Template button on the LHS menu of the Conversation Studio graph builder.

![Language_wa_template](assets/language_template.png)

You can click on **Use template** to start using it.

![Language_wa_template2](assets/language_template2.png)

The template comes with a in-built logic and flow to switch between 10 languages. You can add the template to your bot and disable the languages that are not needed. It enables a user to switch language through the bot flow instead of using the UI.

Users can initiate the language change flow by saying something similar to "I want to change my language". Post this, the bot presents the users with options of which language to switch to.

## List of languages supported out of the box

**The SDK also supports the listed languages -**

- English
- Hindi
- Marathi
- Bengali
- Gujarati
- Tamil
- Telugu
- Kannada
- Malayalam
- Bahasa
- French
- Dutch
- German
- Spanish

> System messages are not available for any other languages except the ones in the list. For any other languages, reach out to your Haptik SPOC.

## How do multilingual bots look?

This is how the multilingual bots look like

![Language13](assets/language14.png)

You can change the language of the bot as shown in the below image

![Language14](assets/language15.png)

And you are ready, start having a conversation with the bot in your choice of language.

## Auto-Detect User Language

When the users to the bot and directly start conversing with the bot in any language other than English (default language of the bot), the bot does not change the language automatically. In case of WebSDK, the users have to change the language from the UI and in case of other channels such as WhatsApp, the users have to go through a user flow created on the bot.

Now, the bot will run a language detection API to identify which language the user is talking in and then automatically switch language and respond in that language. The bot will follow **first three** messages sent by the user and try to identify the language of the user, only if the user is not changing the language in the middle of the **first three** messages they are sending to the bot.

> If the language is supported on the bot, the bot will automatically switch the language and will respond in the chosen language.
> If the language is not supported on the bot, the bot will give a bot break message.
