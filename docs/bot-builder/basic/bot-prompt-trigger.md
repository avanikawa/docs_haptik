---
title: Bot Prompts
---

Bot Prompts provide a way to allow the bot to initiate a conversation with the user. Well designed and well written bot prompts can drastically improve your message sending rate from users and help drive key objectives for customers.

Bot Prompts are currently available on the JS SDK only.

The Bot Prompt visual consists of the following components:

-   _Bot prompt title_ -<br/>
    This is the main bot prompt text which shows up and is directed at the user. For example, "Need help picking a bot? I can guide you!".

-   _Quick Replies (QRs)_ -<br/>
    A bot prompt _can_ have quick replies. These _Quick Replies (QRs)_ serve as options the user can select right outside the XDK to get the conversation started.

-   _User Message_ - <br/>
    This is the actual text which is sent when a _Bot prompt title_ or a _QR_ is clicked. <br/>
    Each element, i.e, the _Bot prompt title_ as well as each of the _QRs_ have a corresponding _User Message_ configured for each of them.

![sample_bot_prompt](assets/new_bot_prompts/new-prompt.png)

<br/>

## Static Bot Prompt Triggers
- For a bot prompt to be triggered appropriately, we need to setup corresponding Bot Prompt Triggers.

- Bot Prompt Triggers, as their name implies are a bunch of triggers each containing the information that specifies:
    - When a bot prompt should be shown _(Bot Prompt Trigger Rules)_.
    - What information should it display _(Prompt Variations)_.


- To add a Bot Prompt Trigger, navigate to `Conversation Studio > Business Manager > (Select Business) > Bot Prompt Triggers > Create a Trigger`

- On clicking of `Create a Trigger` button, you get a popup Window titled `New Trigger`. In this window you can configure the _Bot Prompt Trigger Rules_ and _Prompt Variations_

<br/>

#### 1. Bot Prompt Trigger Rules

- Bot Prompts are triggered based on a set of defined rules evaluated either on a `AND` clause or a `OR` clause.
  >A combination of the `AND` and `OR` clauses cannot be used.

- Rules are set on the following parameters
  -   Page URL
  -   No. of Visits
  -   Query Params
  -   Time on Page (seconds)
  -   Form Field (id of the element)

- Different types of comparisons can be done based on the type of Parameter and by using a key value pair. Here are some examples:

    - A trigger rule could be set like <br/>
  If `[Page Url] [is equal to] [https://www.haptik.ai/technology`] we show our prompt.<br/>
  Needless to say, the _Prompt Variations_ for this trigger will be closely aligned to that of the `Technology` page.

    - if `[Query Param (utm_campaign)] [is equal to] [facebook]` we can welcome the users with a bot prompt that is catered to users who have navigated to this page from facebook.

    - if `[Time on Page] [is greater than] [100]` we can show a prompt which asks the user if they are stuck on anything.

    - If `[No. of Visits] [is greater than] [1]` we can use the greeting _Welcome Back_ instead of _Welcome_.

    - Remember that multiple such conditions can be combined using the `AND` or `OR` clauses to create a whole
    host of creative options to engage the user in an intelligent manner!

      For example:<br/>
      If `{[Form Field - PAN No] [is empty]} AND {[Time on Page] [is greater than] [30 seconds]}` we can ask the users if they need help finding their PAN No.

- Adding _Trigger Rules_ <br/>
  - Click on `Add New Rule`
  - In the `Trigger Based on` section you can select the appropriate trigger viz. Page URL, Query Params, Time on Page, Form Field.
  - Then in the `Condition` section, you can select one of the conditions that would match the requirement. Is Equal to, Is Greater than, etc.
  - And finally in the `Value` section, you can add the appropriate value that fits the case as mentioned in the examples above.
  - The `Prompt Rules Type` controls whether all the multiple rules would either be `AND` or `OR`.
  - ![sample_bot_prompt](assets/new_bot_prompts/prompt-rules.png "Adding rules to Bot Prompt Trigger")


- What if there are two _Bot Prompt Triggers_ with the same _Rules_? <br/>
  - When multiple bot prompts are present they are evaluated in the order of their priority. The prompt with the highest priority is evaluated first, and if the trigger conditions are met only then the prompt will be shown.
  - Priority of the _Bot Prompt Tirggers_ can be adjusted by drag and drop.

#### 2. Bot Prompt Variations:

- Bot Prompt Variations as their name implies, are a collection of different variants, where each variant specifies the _Bot Prompt Title_ and it's associated _QRs_ (if any).

- When the _Rules_ of a _Bot Prompt Trigger_ are met, it is selected to be displayed. Each _Bot Prompt Trigger_ has one or more _variants_ and one of these _variants_ is picked randomly to be displayed.

- Each variant contains:
  - Bot prompt title:
    - One variant can have only one Bot Prompt Title.
  - Quick Replies:
    - One variant can have 0, 2, 3 or 4 _QRs_. A variant cannot have just 1 single _QR_.

- Adding _Variations_ <br/>
  - Click on `Add New variant`
  - In the `Title` section, you enter the _Bot Prompt Title_
  - In the `User Message` section, you enter the _User Message_ that would be sent.
  - Adding _QRs_:
    - Click on the + icon to the right of the Bot prompt title.
    - A _QR_ _title_ and _User Message_ fields appear nested under the _Bot Prompt Title_.
    - Enter the values in the respective fields.
    - Click + to add more _QRs_.
    - To add another variant, click again on `Add New Variant` and repeat the above steps.
      > Limitations: <br/>
      > - _Prompt Title_: <br/>
      Cannot be more than 108 Characters <br/>
      > - _QR Title_: <br/>
      Cannot be more than 30 Characters
      > - _No. of QRs_: <br/>
      0, 2, 3 or 4. You cannot have 1 QR
    - ![sample_bot_prompt](assets/new_bot_prompts/prompt-variations.png "Adding Variants")

> - If a Bot prompt is displayed (with or without QRs) and the user clicks on the `Let's Chat` button, the SDK will behave as if the user had clicked the _Bot Prompt Title_.
> - After making changes for the Bot Prompt, **wait upto 6 hours** for them to reflect.

<hr>

## Bot Prompt using _prompt()_

Bot Prompts can also be added using the `prompt()` function while integrating the Haptik SDK. You can add the method in the `HTML` page as shown below in the example. 

`prompt(title, userMessage)`

The method will allow you to trigger the Bot Prompt on various custom events.

**Params:**

- `title <String>`
*The text that's displayed on the bot prompt.*
- `userMessage <String>`
*The message that's sent if the user taps on the bot prompt.*

Try out the following example to add a Bot prompt using prompt() - 

```
<!DOCTYPE html>
<html>
<head>
    <title>Haptik JS SDK Custom Sign Up Demo</title>
    <meta charset="UTF-8">
    <meta content="width=device-width; initial-scale=1.0;" name="viewport">
</head>
<body>
    <div style="width: 100%; padding-top: 100px;">
        <div style="max-width: 7000px; margin: 0 auto; padding: 0 40px; text-align: left; font-family: Calibri;">
            <h3>Bot Prompt using <i>prompt()</i></h3>
        </div>
    </div>
</body>
<script type="text/javascript">
    window.haptikInitSettings = {
        "business-id": "<BUSINESS_ID>", # Refer the document below to know more
        "client-id": "<CLIENT_ID>",     # Refer the document below to know more
        "base-url": "https://staging.hellohaptik.com/"
    };
</script>
<script type="text/javascript" charset="UTF-8"
    src="https://toolassets.haptikapi.com/platform/javascript-xdk/production/loader.js"></script>
<script> 
    document.addEventListener('haptik_sdk', function () {
        HaptikSDK.prompt("How can I help you with? 👇", "", [{"title": "Track my order", "userMessage": "Track my order"}, 
        {"title": "Refund and replacement", "userMessage": "Refund and Replacement"}])
    });
</script>
</html>
```

> Replace `<BUSINESS_ID>` and `<CLIENT_ID>` in the sample. Click [**here**](https://docs.haptik.ai/bot-builder/basic/sharebot#how-can-we-share-our-iva) to know more about bot credentials.

![image](https://user-images.githubusercontent.com/75118325/121005121-16c1c780-c7ad-11eb-818e-b2ec8839bd79.png)

<hr>

## Dynamic Bot Prompt Triggers

![dynamic bot prompt](https://user-images.githubusercontent.com/75118325/117744190-d3b01b00-b225-11eb-819f-52615df64ecc.gif)

Dynamic Bot Prompt Triggers change based on user's activity on the webpage. 

### How to create Dynamic Bot Prompt Triggers?

#### Step 1: Add it in your HTML code

To set up the Bot Prompt when user hovers on a specific field or area of the webpage, you will have to set which Bot Prompt needs to get triggered.

When user hovers on the **"i"** symbol besides **Year Built**, a Bot Prompt is triggered.

![image](https://user-images.githubusercontent.com/75118325/117745789-cfd1c800-b228-11eb-85b6-4c6f5e0638a9.png)

The following is the sample code of how the bot prompt is set on the hover of the **"i"** symbol and what messages will be sent.


```html
            <div class="form-group row">
              <div class="col-sm-5">
                <label for="staticEmail"
                class="col-sm-2 col-form-label set_inline bot_message"
                data-bot_says="Will the year affect my quote?"
                data-bot_prompt=" Why is year required?/-/-/Don't remember the year">
                  <i class="fa fa-info-circle bot_message"
                  data-bot_says="Will the year affect my quote?"
                  data-bot_prompt=" Why is year required?/-/-/Don't remember the year"></i>
                  Year Built
                </label>
              </div>
              <div class="col-sm-7">
                <input type="date" class="form-control" placeholder="1234567890">
              </div>
            </div>
```

#### Step 2: Create a JavaScript function

Bot Prompt Triggers can be initiated at different instances i.e. when user _clicks_ on some button or textarea, or when user _hovers_ overs some text or button on the page.

The following is the sample code for triggering the bot prompt on hovering over the **i** symbol.


```JavaScript
var tOut;
    $('.bot_message').hover(function() {
        let message = $(this).data('bot_prompt')
        message = message.split("/-/-/");
        console.log("hover timer started ----");
        tOut = setTimeout(function() {
            console.log("5 sec up")
            if (message.length > 1) {
                let prompt_msg = []
                message.map((item, i) = > {
                    prompt_msg.push({
                        "title": item,
                        "userMessage": item
                    })
                })
                HaptikSDK.prompt("Ask me if you have any such questions ðŸ‘‡", "", prompt_msg)
            } else {
                HaptikSDK.prompt(message[0], message[0])
            }
        }, 2000);
    }, function() {
        clearTimeout(tOut);
        console.log("timer reset")
    });
```
