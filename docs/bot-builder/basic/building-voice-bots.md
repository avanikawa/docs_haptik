---
title: Building Voice bots
---

## What is a voice bot?

Voice bot works by using voice as an input. For example, we see voice input in Whatsapp to send voice messages and in Music/e-commerce apps for discovery.
In a voice-bot, the  primary mode of communication is voice. Users Listen to the command(s) given by the speaker and perform the required action. Voice bot is commonly integrated on voice assistants like Amazon Alexa and Google Assistant. You can also enable voice input in your **website (JS SDK) bot**. 

## How does it work?

To configure a Voice Bot on our Conversation Studio, go to any node and set voice-specific bot responses. On a node, you can tap on `+Add a chat element` in Bot says. Once you click on it, a slide bar opens on the right hand side. 

Click on preferred chat element. Here for your element, you can configure the voice bot via two fields
1. Bot Says: This is the text on UI as a bot message bubble i.e. Add bot says, which will be sent as text to the user.
2. Voice Says: This is what the bot says out loud i.e. the output from your device speaker. You tap on +Voice support and add message details. Once the message is added, tap on the Done button at the top.
 
It will look as depicted in the image below.

![Voice Says](assets/voice-says.png)

You can use any chat element and add voice says except for Raw Json. For this specific chat element, bot says and voice says will be the same. You will not get an option to separately feed in voice says.
Once the details are added, click on save on the top right to save the data.

## Enabling Auto Mic option

Enabling the auto open mic, allows the user to talk with the bot, and activate even if the mic button is not pressed on chat. This makes it user friendly depending on the bot personality.

Note - If changes are made in Bot says, you have to save the data to test the bot. If changes are made in User says, you will have to save, then train the bot and later you can test the bot. 

## SSML tags

You can use a bunch of tags to modify the Text to speech experience. This is crucial to control how and what the bot says out the bot response. 

For example, you can add pauses in the bot speech or emphasise on a certain part of the bot speech -

SSML tags are to be added in the Voice Says field box as shown in the image above. For understanding how SSML tags are to be added, check the syntax details below -

1. Adding a break

`<speak> Not sure. <break time="2s"/> Please reach out on our email-id. </speak>`

As per the SSML tags used above, after Bot says "Not sure." there will be a break time of 2 seconds and then bot speaks the rest. 

2. Adding emphasis

`<speak> You can contact us on <emphasis level="strong"> our landline </emphasis> on weekdays. </speak>`

As per the SSML tags used above, after Bot says "You can contact us on" there will be emphasis on "our landline" phrase and then bot speaks the rest of the text. 

## Using HSLs for voice

Voice input does not work to read out Quick replies and buttons. Using a lot of quick replies in voice bots will be a little difficult as the bot will not read out content of the quick replies.
We can use less of Quick replies & buttons or try directing the user with every message on what to do next to proceed ahead with the chat.

## Sending ASR break message

Sometimes, we get an incorrect response for the user’s voice input, if the user speaks in a low voice or in a noisy environment. We need to detect such scenarios and get the right user input.

If the ASR captures half-baked response ie the voice input is wrongly captured, the chances of getting a correct bot response match goes for a toss. When we are not able to capture user’s said speech due to background noise, training data scarcity, unclear user input or when users start speaking away from the phone mic; we ask user to rephrase their query one more time. 

![ASR break](assets/ASR_Break.png)

## Bot Testing

When testing a Bot on our platform, we generate a demo link to share and test it.

To test a Voice Bot, we will have to add `"&bot-type=VOICE"` in the demo QP link for testing. You can also add `&bot-type=VOICE&&voice-bot-initial-input=TEXT` at the end of the demo QP link to change the voice input method to secondary. You can also have voice input as primary i.e. mic placed at the center of the composer area.

## Do’s & Don'ts

1. Voice Bot may sometimes not pronounce the words properly. Misspelling the word in “Voice says” may help at times
2. Bot may also not pronounce Hindi words properly. Accordingly, edit the text in "Voice text" field
3. Bot tends to read out some special characters. Avoid using special characters which aren't SSML tags
4. Too much of content may lead to bore the users. Do not use long message copies for Voice support. To make the bot pause while reading out a sentence add respective punctuations like commas, full stops
5. Bot does not read two separate messages together, it takes a pause before reading the second message
6. Add spaces between numbers so that the Bot will read them individually. Example - you type “99” in voice support, bot will read it as “ninety nine”. Instead type “9 9” in voice support, and the bot will read it as “nine nine”
7. Keep different message copies for text support and Voice support.
 
 
