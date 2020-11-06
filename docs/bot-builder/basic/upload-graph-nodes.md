---
title: Upload Graph Nodes
---

>Note: This only works for Static nodes.

Graph nodes are nothing but the basic static nodes that we use in the graph of the Conversation Studio tool and it follows the same principle of User Says, Bot Says and Start Nodes to detect nodes, reply back to the user, update the chat status and also support the API Integrations.

#### Why do we need Graph Node uploader tool
To handle the scenarios where we need to create large number of nodes in one go, we can use graph node uploader tool.

#### How to Access Graph Node Uploader Tool

1. Open any bot.
2. Select the sub-story under which you want to upload these nodes.
3. Click on More(top right corner) -> uploads nodes from file 
![](assets/access-graph-node-uploader-tool.gif)


#### CSV Format
![CSV Format](assets/faq_node_csv_format.png)

```
1. node_name: Name of the node, node name should be unique

2. question(User Says): Independent Responses under User Says to detect this FAQ nov

3. answer(bot says): A node can have single or multiple bot says, to pass multiple bot says use `<m>` tag as delimiter

4. api_integration_url(optional): API Integration URL for the bot. It can be of two types.

    4.1 Absoulte URL: Absolute URLs contain more information than relative urls, as they also include the protocol (e.g http://xyz.com/get-products/ or https://xyz.com/get-products/) and the domain name.

    4.2. Relative URL: Relative URLs are generally easier to work with as they are shorter and more portable, but can only link to pages on the same domain. For eg: /get-products/

5. api_key(optional): If API Integration URL requires secret/token key.
```

You can download a sample CSV file from [here](assets/FAQ_Uploader.csv).

>Note: If you pass Relative URL under api_integration_url column then Base URL must be present at Bot level.

#### How to set base url at Bot Level
![](assets/set_base_url_at_bot_level.gif)

#### Error Messages

1. `Invalid Integration URL Provided` error msg will occur if we pass:

    a. Base URL without `http/https`.  
    b. Relative URL when no base url is set at domain level.  
    c. Relative URL and it doesn't start with `/`

2. `Node name is already used for a different node` if duplicate node name provided in the sheet.

>Note: Once nodes get created from the CSV, it can be updated only from the UI of bot-builder.
