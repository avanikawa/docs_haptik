---
title: User Search
---

This feature can be used to search users who have had conversations with your business. You can look for them by their name or email address, to search for their previous conversations or detailed information.

![image](https://user-images.githubusercontent.com/75118325/123368889-4557e480-d59a-11eb-9e85-94a0a218401a.png)

Select your **Partner name** from the dropdown as shown below - 

![image](https://user-images.githubusercontent.com/75118325/123370187-d8921980-d59c-11eb-9827-049a674a5a9f.png)

In the **Search Bar**, you can type the relevant information about the user, either their email address or phone number.

> Provide the exact text, for example if you want to search the user with an email _abc@test.com_ then type the exact email address in the **Search Bar**.
>
> Avoid using irregular search terms such as 'abc' and others.

Once you have provided the information, the table will be populated with the relevant information about the user.

![image](https://user-images.githubusercontent.com/75118325/123371311-23ad2c00-d59f-11eb-8abc-4e0083254f79.png)

The table contains following information - 

1. **User Name:** The name of the user.

2. **Email id:** The email address of the user.

3. **Phone number:** The phone number of the user.

4. **Last conversation:** The date and time when the user had the last conversation with the business.
 
5. **Platform:** The channel on which the user had the last conversation (iOS, Android, Web SDK, and others).

6. **Matched custom info:** This column mentions what information was used to fetch user details. In the above example, the value provided in the Search Bar is _Haptik_ which matched with **name**, as seen in the _user details section_, and hence the **Matched custom info** column has the value **name**. 

This information is collected as part of the user journey and displayed under _user details section_ on the left side of the [**chat links**](https://docs.haptik.ai/bot-analytics/chat-links).

> This following view of chat link requires appropriate permissions. Please read [**here**](https://docs.haptik.ai/bot-analytics/chat-links) to know more about persmissions required to view user's personal information.
> 
> ![image](https://user-images.githubusercontent.com/75118325/123371633-c665aa80-d59f-11eb-9cbb-975f00952253.png)
> 
7. **Conversation count:** The total number of conversations user had with the business.

    - Clicking on the row will open the [**chat link**](https://docs.haptik.ai/bot-analytics/chat-links).
    - When the number of **Conversation count** is greater than 0, you can click on the row to check the conversations. 
    - When the user has not completed any conversation, the count will be 0.

> If the user with same email and phone number are showing twice, this means the user is registered two times.
> 
> In case of a match of email, phone number, and user name which are collected as part of SDK the **Matched custom info** will be shown as empty.

When there is no relevant information found related to the information provided in the **Search Bar**, you will see a screen as shown below - 

![image](https://user-images.githubusercontent.com/75118325/123394468-ccb64f80-d5bc-11eb-80e3-32435121bf7f.png)
