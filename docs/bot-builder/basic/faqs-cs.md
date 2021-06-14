---
title: FAQs
---

### 1. How to capture user's location on bot?

There are two public entities present to capture user's location `origin_lat` and `origin_lng`. When the user's select a location on the map, bot captures the longitude and latitude of the user's location.

* Add a button HSL and select the **Button Type** as **Open Screen**. Then select the **Screen to open** as **Send Location**.
* Add `origin_lat` amd `origin_lng` entities in the Bot Says section.
* Mark them as non-mandatory.

![image](https://user-images.githubusercontent.com/75118325/121528224-e716f780-ca18-11eb-9402-d177c5eb29d9.png)

![image](https://user-images.githubusercontent.com/75118325/121528298-f72ed700-ca18-11eb-9622-b6f4855c6a19.png)

### 2. What is the maximum number of entities that could be added on the bot?

Not more than **150** entities can be added on the bot.

### 3. Does spell checker work on entities?

For Words and Phrases entity, entities follow pattern matching i.e., the bot tries to find the same variant added in the dictionary. Hence, the spell checker does not work on entities.

### 4. What are the dimensions for the custom icons to be followed so that they fit perfectly in the chat icon?

These are the dimensions for the custom icons to be followed so that they fit perfectly in the chat icon.

For an image of 100 px X 100 px, the `circular section of the chat icon` is a circle of diameter 75px, which is 11px from the X axis and 10 px on the Y axis.

![image](https://user-images.githubusercontent.com/75118325/121814030-85f75a00-cc8c-11eb-869e-1262e6d2f277.png)
