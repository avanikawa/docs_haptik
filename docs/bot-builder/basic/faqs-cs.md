---
title: FAQ
---

### 1. How to capture users location on bot?

There are two public entities present to capture user's location `origin_lat` and `origin_lng`. When the user's select a location on the map, bot captures the longitude and latitude of the user's location.

* Add a button HSL and select the **Button Type** as **Open Screen**. Then select the **Screen to open** as **Send Location**.
* Add `origin_lat` amd `origin_lng` entities in the Bot Says section.
* Mark them as non-mandatory.

![image](https://user-images.githubusercontent.com/75118325/121528224-e716f780-ca18-11eb-9402-d177c5eb29d9.png)
![image](https://user-images.githubusercontent.com/75118325/121528298-f72ed700-ca18-11eb-9622-b6f4855c6a19.png)

### 2. How many entities can we add on the bot?

You should not add more than **150** entities on the bot.

### 3. Does spell checker work on entity?

For Words and Phrases entity, entities follow pattern matching i.e., the bot tries to find the same variant added in the dictionary. Hence, the spell checker does not work entity.
