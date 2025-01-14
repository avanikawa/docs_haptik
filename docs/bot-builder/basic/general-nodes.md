---
title: FAQ Nodes
---

## What are FAQ Nodes?

FAQ nodes are like graph nodes and follow the same principle of **User Says**, **Bot Says**, and **Context Clear Nodes** to detect nodes, reply back to the user and update the chat status.

However, there are certain differences between FAQ Nodes and graph nodes which make them ideal for certain use cases like FAQs to answer general queries that a bot is usually asked in the category of the bot. Ex: ‘Who made you’ or ‘Are you a bot or Human’ which help in giving a personality to the bot.

![Screenshot 2021-06-02 at 4 45 11 PM](https://user-images.githubusercontent.com/55389979/120471240-1b0f6e80-c3c2-11eb-9fa6-02bd5dbd16a9.png)

## Related Terms

1. **Node Name**: This is the unique identifier for a Node. This cannot be modified after creation and is similar to the System Name for graph nodes.
2. **User Says**: This is similar to User Says in graph nodes. Enter a few phrases which should redirect a user to this node.
3. **Bot Says**: Add messages which the Bot should reply back with, whenever this node is reached.
4. **Mark as Context Clear Node**: If this is ticked, the context will be cleared and the chat will be marked complete after answering the user’s query. If not, the bot will reply back and remain in the Bot State with the context of the previous graph node.
5. **Activate/Deactivate**: This button can be used to activate/deactivate certain FAQ nodes as needed.

   ![General Nodes](assets/general_node_terms.png 'How to Create/Edit a General Node?')
   
## Graph Nodes vs FAQ Nodes

In bots, Graph nodes (flows built in Stories) and FAQ nodes are at the same level. What this means is an FAQ node and a Graph node would together be considered while trying to find a match for user’s response.

## Why FAQ Nodes?

To explain how FAQ Nodes are useful, look at the following example of a Product Sale Bot:

![image](https://user-images.githubusercontent.com/75118325/113535142-3f341680-95f0-11eb-81ad-a7a3bc68205a.png)

Now a user could ask about **Cashback/Product Offers** (not a part of the above conversational flow) at any stage. To avoid breaking the flow, we would create a FAQ Node related to Cashbacks which would answer the cashback and offer related queries without breaking the chat flow.

To understand another example of how FAQ Nodes could be used to improve the User’s Experience, we can create multiple FAQ nodes that answer general questions about the Bot domain. 

## How to use FAQ Uploader?

Because FAQ Nodes are very simple in terms of features (no entities/API calls etc.) and the ability to maintain the context of the bot, they are ideal for quick Question/Answer type contents.

To simplify the process of creating these FAQ nodes, there is an option to upload a TSV file (Tab-separated file).

A FAQ node is created for every Question/Answer pair in the file.

- The **question** is treated as ‘User Says’
- The corresponding **answer** is stored as ‘Bot Says’.
- The nodes are prefixed with the uploaded file’s name

So to quickly create a Bot that can answer all your FAQs:

1. Create a TSV file
2. Upload it to our Bot Maker
3. Click on Save
4. Train the Bot

### Sample Uploader

You can download the sample uploader [**here**](/general_nodes_faq.tsv).

And you're done!
