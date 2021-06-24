---
title: Conversation Design FAQs
---

## What is an FAQ bot?

Before we start designing, let's start by asking what is an FAQ bot? Why do clients need it?

To start with companies want to botify existing FAQs often represented on corresponding sections on a website. They want to absorb an FAQ section of a website and convert that into a bot, one which is easily accessible and quickly developed and deployed.

**Scope of a typical FAQ content**

1. Provide instant answers to customers
2. Offer an engaging and interactive journey to conversion
3. Pass a chat to a live operator at any time (Subjective to use-cases)
4. Collect customer preferences you can use to send follow-up messaging (Leadgen: Subjective to the brand and use-cases)

**Scale of FAQ bots**

FAQ bots can range from 50 to 300. An ideal FAQ bot should not have more than 300 FAQs, a bot trained with more than that will develop challenges in training it. In our experience, we have noticed if the bot has more than 300 FAQs only 80 to 100 nodes are hit by the users on a regular basis.

Since the range of these questions and answers is so diverse we need to understand how to deal with each of them. The approach and technique you use to design will depend on the number of FAQs you are solutioning.

## Types of FAQ Bots
At Haptik we have we look at  FAQs which can be categorized into three types
1. Structured
2. Unstructured
3. Hybrid

**Type 1**: Structured FAQ Bot
A structured bot will always have guided flows that will help users find an answer with ease. Let’s say your client wants all of its 50 FAQs on a bot, having them build out as use-cases and presented it to the users with options, to begin with, it is easier for the user to click on a category for which they are looking for an answer and get it answered. 

**Type 2**: Unstructured
FAQs ranging from 100 to 300 can be unstructured, which means the bot will be completely open-ended.
We will only have an introduction for the users to know what this bot is about and what it has to offer. The users here will ask their questions in free form. 

**Type 3**: Hybrid
Hybrid bots come into play when you are dealing with 200FAQs or more. It is difficult to convert all the responses into a flow. Here you can consult with the client and choose intents that their users ask often, design journeys for these and the rest can go in freeform 

Now since we have very well understood what an FAQ bot is, Let’s look at phase 1 of designing it.

## Phase 1: Information Gathering
In this phase, you ask your client to provide all the content in the format given below. This format has been formulated basis our experience of creating 50+ IVAs keeping the user experience in focus. This format will set the base of your design, make it easier for you to go through the content which will be trained in the bot. At this phase, you can ask questions to the clients which will help you understand their product/brand better, get clarifications for any answers required.

![Screenshot 2021-03-11 at 11 32 29 PM](https://user-images.githubusercontent.com/85490713/123210207-5132a080-d4df-11eb-893c-a76bb06ed647.png)

This format will essentially be in an excel sheet format

**1. Node Name**: This will be filled by the bot builder since it will be the same node name that is going to be used on the bot builder for that node.

**2. Category**: Category is an important field as it will be used to create sections in the bot. Let’s say you have about 100 FAQs, you will categorize them into at least 5 use-cases to design the guided flow for a structured bot.

**3. Question**:  The question needs to be clear and precise. It should be generic and not specific to a particular user's query. We need to understand that we will be training our nodes with user variations which will not be possible if we have a very verbose or lengthy question.

> Question Character limit: is set to 100 characters to make sure that the questions are not too long.

**4. User Says**: Once we have the questions in place we need to come up with actual user utterances for those queries which will help us in training for that particular node. You can learn more about this [**here**](https://docs.haptik.ai/bot-builder/basic/user-says).

**5. Answer**: The answer should be relevant to the question. Vague answers on a bot are not the best UX. The Conversation Designer will proofread and format these answers in a conversational manner.

> Answer character limit: Ideally, it should NOT exceed 300 characters.

**6. Modified Answer**: Haptik(Conversation Designers) will modify each answer to make it conversational and chat compatible.

**7. Links**: In case if the client wants to re-direct the user to a particular webpage or to perform a task that cannot be performed on the IVA now is the time for the client to provide us with that. 

**8. Images/Videos**: Images or videos can be used to enhance the answers or replace them altogether if and when needed for the best experience.

We have the template attached with a sample ready to use for you - [**FAQ Guidelines and Template**](https://github.com/avanikawa/docs_haptik/files/6707821/FAQ.Guidelines.and.Template.xlsx).

## Phase 2: Content Sanitisation

Once you have all your content in place in our given format you start revising the answers. The answers that clients provide are fetched from the website which means that they are transactional. Neutral formulations such as “Customers can register here” should be converted to second person singular ”You can register here”, longer messages since they sometimes cannot be avoided given the subject matter must be split up into smaller messages which fit into a chat bubble perfectly.

We also need to be mindful of longer answers that can be converted into a carousel, Image, or sometimes video-like format. Here you can consult with your client and agree upon the final approach for such conversion.

## Phase 3: Adding UI elements

When we talk about UI elements for an FAQ bot we mean that the links that will be shared by the client need to be converted into clickable buttons for a web or an In-app bot. In some cases, you will have to convert longer answers into carousels. 

## Phase 4: Building guided journeys

Guided flows help users reach and discover an intent easily. Guided flows should be built for all the FAQ bots. Ask your client for top intents their users ask on their website currently. Make those tops intents easy to discover and navigate on the bot by designing a guided flow. Each top intent becomes your unique use case. It’ll be similar to designing any other bot for Web, In-App, or WhatsApp.

Watch the video below for a detailed understanding of how to convert your FAQs into a guided journey

<iframe width="560" height="315" src="https://www.youtube.com/embed/9ZX4YGzD374" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Phase 5: Development
In this phase you handover your design to a bot builder to develop and train on our **Conversation Studio**.

## Other Important Considerations

✅ Always have follow-up QR options. Your user should have a way to move forward in the conversation.

✅ To upload a large number of FAQs at once, you may use the [**bulk upload feature**](https://docs.haptik.ai/bot-builder/basic/general-nodes). However, make sure that all good conversation designer practices like follow-ups are implemented within your content.

✅ Ensure that follow-up feedback doesn’t jump in too early and obscure your follow-up QRs. Remember: QRs aren’t persistent.

✅ Make sure that your answer is generic. Don’t have any ultra-specific introductions like “Yes that’s a lovely question” before your answer begins.

✅ Reuse: If your bot is a bot for logged-in users - Can you reuse information from the signed-in profile to avoid repetition?. If your user has previously mentioned their name, can you reuse it elsewhere?

✅ Give directional cues to the user: Does your user always have a backup option to come back to the menu if they get lost during the journey?

✅ Handle free form queries: Has your bot been trained to handle free form questions related to the main use cases? **Example**: For an Insurance Product recommendation bot, do you provide basic information about the product in freeform like “Will I get free training”.
