---
title: Debug Logs
---
 
When you are building the user journeys you can test the flows simultaneously using the **Test bot** section.
 
![image](https://user-images.githubusercontent.com/75118325/122736318-86e84700-d29d-11eb-8419-1b58aa337740.png)
 
Every user message has a **log** icon, as shown below
 
![image](https://user-images.githubusercontent.com/75118325/122736955-2f96a680-d29e-11eb-8240-5d34ce0a4fb8.png)
 
The **Debug** section aids in understanding how the users are going ahead in the flow. You can also check what details the bot is capturing and whether the users are going in the right flow.
 
There are 2 sections in the **Debug** logs - 
1. Basic Info
2. Detailed Info
 
## Basic Info
 
There are 3 sections in the **Basic Info** tab.
 
![image](https://user-images.githubusercontent.com/75118325/122738407-94063580-d29f-11eb-925d-d2e0801fe509.png)
 
### Basic Details
 
Basic Details provides basic information about the bot.
 
![image](https://user-images.githubusercontent.com/75118325/122740004-2f4bda80-d2a1-11eb-9195-3fac924c02a1.png)
 
### Node Details
 
Node Details section tells you which static node was triggered when the user sent the message. If there is a code node and output node connection, the Node Details section mention which nodes were executed.
 
![image](https://user-images.githubusercontent.com/75118325/122740417-910c4480-d2a1-11eb-9b4b-9db5a15a6017.png)
 
If there is an error in the code node execution, the log section will only show the code node which was triggered but not mention the output node.
 
![image](https://user-images.githubusercontent.com/75118325/122740908-1132aa00-d2a2-11eb-85c2-1c0116c1e9a2.png)
 
When the bot is confused and disambiguating between different start nodes, you will be able to check the nodes which are causing the bot to confuse.
 
![image](https://user-images.githubusercontent.com/75118325/122741199-5951cc80-d2a2-11eb-9c03-dcd285bc8462.png)
 
 
### Detected Entities
 
The Detected Entities section shows a list of all the entities which were detected on the bot. 
 
You will be able to see the number of entities that were detected.
 
A list of all the detected entities will help you debug if the right entity has captured the right value from the user.
 
![image](https://user-images.githubusercontent.com/75118325/122741550-b188ce80-d2a2-11eb-8c8c-9d7ded31b778.png)
 
## Detailed Info
 
In the Basic Info tab, you will be able to see a lot of basic information about the bot with respect to the nodes which are getting triggered and the entities that are getting captured.
 
In the **Detailed Info** tab, you can check all the attributes that lead the user message to trigger a specific node. There are several flags in the **Detailed Info** tab.
 
![image](https://user-images.githubusercontent.com/75118325/122742231-5c00f180-d2a3-11eb-8f63-f68436e83626.png)
 
### `entities`
 
The `entities` section will help you see the structure in which the entity is stored on the bot. You can expand the section to check the structure. This structure is useful while using the entity value in [code node](https://docs.haptik.ai/bot-builder/integrations/integrating-custom-code#using-entities-on-code-editor).
 
![image](https://user-images.githubusercontent.com/75118325/122742849-024cf700-d2a4-11eb-94a1-92a9f14432fb.png)
 
### `node_list`
 
The `node_list` section provides information about how the node was triggered i.e. whether the node was triggered on the basis of user says or entity value, this is mentioned in the `node_detection_method` parameter.
 
![image](https://user-images.githubusercontent.com/75118325/122743034-388a7680-d2a4-11eb-99f8-0d45bd8fcc7c.png)
 
### `response_list`
 
The `response_list` section mentions the response details which was sent to the user.
 
![image](https://user-images.githubusercontent.com/75118325/122743752-e9911100-d2a4-11eb-9786-4471d6b9229e.png)
 
### `stop_logic`
 
The value in `stop_logic` will be true if the bot is not replying from the graph nodes created on the bot. It will help you to identify if the message is coming from the small talk module or giving a response from the entity reprompt section. 

![image](https://user-images.githubusercontent.com/75118325/122749162-9e79fc80-d2aa-11eb-8977-7fb31cebc75a.png)

 
### `response_component`
 
This section will you understand which component is the bot replying from i.e. is the bot responding from the small talk module or the graph nodes created on the bot.
 
![image](https://user-images.githubusercontent.com/75118325/122749097-8efab380-d2aa-11eb-804d-460bc36aaa27.png)
 

### `response_container_names`
 
This section will tell you where the bot has replied from.

![image](https://user-images.githubusercontent.com/75118325/122749054-830ef180-d2aa-11eb-859b-af338f65b431.png)

 
### `smalltalk_intents`
 
This section will mention the Small Talk intent and the node name in the small talk section which is clashing with the user message.

![image](https://user-images.githubusercontent.com/75118325/122749013-77232f80-d2aa-11eb-95a5-2ef82580088f.png)

 
### `execution_times`
 
In this section, you will be able to check the different execution times of all the modules present on the bot.

![image](https://user-images.githubusercontent.com/75118325/122748995-6ffc2180-d2aa-11eb-885b-149d594a96b6.png)

 
### `user_message_language_script` and `user_message_source_language`
 
These two flags mention the language in which the user has sent the original message and the detected language on the bot.

![image](https://user-images.githubusercontent.com/75118325/122748960-6672b980-d2aa-11eb-87e8-2ec54b55cca3.png)

 
### `nodes_below_threshold`
 
When the bot is getting confused between different start nodes, this section can help you understand the attributes that are causing confusion on the bot.

![image](https://user-images.githubusercontent.com/75118325/122748929-5ce95180-d2aa-11eb-8f89-e4f78df9b0ee.png)

 
### `code_nodes`
 
The `code_nodes` section will mention the code node which was executed.

![image](https://user-images.githubusercontent.com/75118325/122748898-54911680-d2aa-11eb-9dad-fbd0fa3aa0a1.png)

 
### `botbreak`
 
If the user message has caused the bot to break, the `botbreak` flag will be `true`.

![image](https://user-images.githubusercontent.com/75118325/122748854-493deb00-d2aa-11eb-99a7-334f55aaad37.png)
 
### `translated`
 
If the bot is translating the message sent by the user the `translated` flag will be `true`.

![image](https://user-images.githubusercontent.com/75118325/122748830-43e0a080-d2aa-11eb-89ca-9d3f911ac331.png)

 
### `end_of_context`
 
If the `end_of_context` flag is `true` that means the user has reached a Context Clear Node.

![image](https://user-images.githubusercontent.com/75118325/122748787-375c4800-d2aa-11eb-83e2-88e93b08ffa9.png)

 
### `handover`
 
If the handover flag is `true` that means there is a handover to a live agent. 

![image](https://user-images.githubusercontent.com/75118325/122748761-31666700-d2aa-11eb-92b2-f5521461711a.png)

 
### `processed`
 
This flag tells if the message was received by the bot.

![image](https://user-images.githubusercontent.com/75118325/122748732-2ad7ef80-d2aa-11eb-9b1c-f8103571409c.png)
 
### `business_via_name`
 
This is the business name of the bot.

![image](https://user-images.githubusercontent.com/75118325/122748701-24e20e80-d2aa-11eb-9807-063048a2b0d3.png)

 
### `detected_language`
 
The `detected_language` flag shows the language in which the user has sent the original message.

![image](https://user-images.githubusercontent.com/75118325/122748684-1eec2d80-d2aa-11eb-95dc-50abbbc4dec8.png)

 
### `detected_output_nodes`
 
The `detected_output_nodes` section mentions the detail about the output node that was triggered.

![image](https://user-images.githubusercontent.com/75118325/122748662-18f64c80-d2aa-11eb-8d4d-c6514c7b3145.png)


### `detected_code_nodes`
 
The `detected_code_nodes` section mentions the detail about the code node that was executed.

![image](https://user-images.githubusercontent.com/75118325/122748624-0bd95d80-d2aa-11eb-93d1-c832210ce44e.png)

 
### `processed_message_id`
 
Every message sent by the user has its own unique id.

![image](https://user-images.githubusercontent.com/75118325/122748563-f8c68d80-d2a9-11eb-84c6-5b971056c8ec.png)
