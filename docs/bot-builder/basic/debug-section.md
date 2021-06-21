---
title: Debug Logs
---
 
When you are building the user journeys on an IVA, you can test the flows simultaneously using the **Test bot** section.
 
![image](https://user-images.githubusercontent.com/75118325/122736318-86e84700-d29d-11eb-8419-1b58aa337740.png)
 
Every user message has a **log** icon, as shown below
 
![image](https://user-images.githubusercontent.com/75118325/122736955-2f96a680-d29e-11eb-8240-5d34ce0a4fb8.png)
 
The **Debug** section aids in understanding how the users are proceeding ahead in the flow. You can also check what details the bot is capturing and whether these users are going in the right direction.
 
There are 2 sections in the **Debug** logs - 
1. Basic Info
2. Detailed Info
 
## I. Basic Info
 
There are 3 parts under this **Basic Info** tab.
 
![image](https://user-images.githubusercontent.com/75118325/122738407-94063580-d29f-11eb-925d-d2e0801fe509.png)

1. Basic Details
2. Node Details
3. Detected Entities
 
### 1. Basic Details
 
Basic Details section provides basic information about the bot like Business Name, Bot Name, etc.
 
![image](https://user-images.githubusercontent.com/75118325/122740004-2f4bda80-d2a1-11eb-9195-3fac924c02a1.png)
 
### 2. Node Details
 
Node Details section tells you which Static node was triggered when the user sent the message. If there is a code node and output node connection, the Node Details section mention which Code & Output nodes were executed.
 
![image](https://user-images.githubusercontent.com/75118325/122740417-910c4480-d2a1-11eb-9b4b-9db5a15a6017.png)

Important points to note -

1. If there is an error in the code node execution, the log section will only show the code node which was triggered but not mention the output node.
 
![image](https://user-images.githubusercontent.com/75118325/122740908-1132aa00-d2a2-11eb-85c2-1c0116c1e9a2.png)
 
2. When the bot is confused and disambiguating between different start nodes, you will be able to check the nodes which are causing the bot to confuse.
 
![image](https://user-images.githubusercontent.com/75118325/122741199-5951cc80-d2a2-11eb-9c03-dcd285bc8462.png)
 
### 3. Detected Entities
 
The Detected Entities section shows a list of all the entities which were detected on the bot. You will be able to see the total number of entities that were detected so far in the journey. A list of all the detected entities will help you debug if the right entity has captured the right value from the user.
 
![image](https://user-images.githubusercontent.com/75118325/122741550-b188ce80-d2a2-11eb-8c8c-9d7ded31b778.png)
 
## II. Detailed Info
 
In the Basic Info tab, you will be able to see a information about the bot with respect to the nodes which are getting triggered and the entities that are getting captured. In the **Detailed Info** tab, you can check all the attributes that led the user message to trigger a specific node.
 
![image](https://user-images.githubusercontent.com/75118325/122742231-5c00f180-d2a3-11eb-8f63-f68436e83626.png)
 
### `entities`
 
The `entities` section will show you the list of all entities with their values captured so far in the journey. This section will help you see the structure in which the entity is stored on the bot. You can expand the section to check the structure. This structure is useful while using the entity value in [code node](https://docs.haptik.ai/bot-builder/integrations/integrating-custom-code#using-entities-on-code-editor).
 
![image](https://user-images.githubusercontent.com/75118325/122742849-024cf700-d2a4-11eb-94a1-92a9f14432fb.png)
 
### `node_list`
 
The `node_list` section provides information about how the node was triggered i.e. whether the node was triggered on the basis of user says or entity value.
 
![image](https://user-images.githubusercontent.com/75118325/122743034-388a7680-d2a4-11eb-99f8-0d45bd8fcc7c.png)

`connecting_node_name` represents the node from which the transition was made. If it is NULL then the node was detected directly instead of some connection.

- When `transition_entity_name` is NULL and `transition_entity_value` is NULL, then node was detected using **user says**
- When `transition_entity_name` is not NULL and `transition_entity_value` is NULL, then node was detected using **entity presence** connection type
- When `transition_entity_name` is not NULL and not `transition_entity_value` is NULL, then node was detected using **entity value** connection type
 
### `response_list`
 
The `response_list` section mentions the response details which was sent to the user.
 
![image](https://user-images.githubusercontent.com/75118325/122743752-e9911100-d2a4-11eb-9786-4471d6b9229e.png)

### `response_components`
 
This section will help you understand which component is the bot replying from i.e. is the bot responding from the small talk module or the graph nodes created on the bot.
 
![image](https://user-images.githubusercontent.com/75118325/122749097-8efab380-d2aa-11eb-804d-460bc36aaa27.png)
 
### `smalltalk_intents`
 
This section will mention the Small Talk intent and the node name in the small talk section which is clashing with the user message.

![image](https://user-images.githubusercontent.com/75118325/122749013-77232f80-d2aa-11eb-95a5-2ef82580088f.png)
 
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
