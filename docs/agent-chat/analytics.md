---
title: Analytics
---

## Time Stats

![Time_stats](assets/time_stats.png)

1. **Avg. First Response Time** (FRT)

    FRT is the average of first response times taken by the agent to send the first response to end users. Only the chats whose first response was sent during the selected time range will be taken into account. Chats may have been created anytime (inside and outside the selected time range). Queue time is included in this metric. As we check this from first user message timestamp to the first agent response timestamp.
    
2. **Avg. Response Time** (RT)

    RT calculation is the average time taken by the agent to respond in a chat to all messages and not just the first message. Only the chats whose responses were sent during the selected time range will be taken into account. Chats may have been created anytime (inside and outside the selected time range). For the user’s 2nd, 3rd and so on messages, the response time is simply the delta in the user message timestamp and the agent’s response timestamp. 
    
3. **Avg. Resolution Time**

    This metric 'Average resolution time' should be the average time taken by the agent till there are no messages sent in a chat session. Only the chats that were completed during the selected time range will be taken into account. Chats may have been created anytime (inside and outside the selected time range). Resolution time is simply calculated from the user’s first message sent timestamp till the last agent/user message timestamp in a chat.
    

## Chat Stats

![Chat_stats](assets/chat_stats.png)

1. **Total Chats Received** 
    
    All ongoing chats for a chosen Team view, that started in the selected time duration. This includes chats in waiting, queued chats and pinned chats for the Team in question. The total number of all chats received i.e. `first_message_time` in the selected time duration from the time-date picker.

2. **Completed by Agents** 
    
    Count all chats that were closed by a human agent that means count all instances of manual clicks for closing a chat. Simply, total count of chats which were completed by agents in a particular team will be shown here.
    
> Note that this completed metric count is available starting from 24 March 2020 only. 

3. **Abandoned by Users**
    
    This metric counts all conversations which transfer from a Haptik bot to a human agent and the user did not send any message after the human agent was assigned. That means all chats wherein user gets an agent assigned but the user drops-off before sending a message would be counted as an abandoned chat.
    
> Edge case scenario - Consider another scenario when in conversation A, user chats with agent 1 and this agent 1 logs out after replying back to user’s query. In the same conversation A, user comes back and sends a message, now say this chat goes to agent 2 and the user doesn’t return. Now, if the chat goes to the complete state, we consider this chat as abandoned for agent 2.

4. **Delayed**
    
    This metric gets us a count of all instances where the `First_agent_response_time` is greater than `Delay Time` value as setup from the Team settings section. 
    

## Overview

![Overview](assets/overview.png)

1. **Avg. User rating**

    Average rating of all chats where the end user submitted a feedback and an agent was involved. Since this is a Team level view, we consider all agents in this team only, that is all chats where the agents from the chosen team took part.

2. **Total Number of agents**

    The value here gives us the number of agents, who received atleast a single chat in the Team. Only those agents who received any chat(s) are counted. Also note that an agent could be part of multiple teams. 

3. **Time saved of agents**

    All chats where an Haptik bot (gogo) took part, we add up the individual resolution time for all such chats, that would be the total amount of time, Haptik bot (gogo) was responding to the end user, instead of an human agent. 
    
> This metric is calculated on the `business` level i.e. we show the "Time saved of agents" value totalled for all teams in a business (for the chosen Team). Since, most of our clients have one team per business, this apporach works. 


## Agent Statistics

![Agent_stats](assets/agent_stats_table.png)

1. **Agent Name**

   When the agent was created, the username field for agent is shown here in this name column. You can find the agent name by using the search feature available here.
   
2. **Avg. First Response Time** (FRT)

    FRT here in the agent table is same as defined above in `Time stats` section. However, this metric is for a single agent. And the metric above in `Time stats` section is on a Team level.
    
2. **Avg. Response Time** (RT)

    Response Time (RT) is same as defined above in `Time stats` section. Just the change being, this metric is for the single agent. And the metric above is on a Team level.
    
> Note that FRT and response time metrics shown here for agents and team both include the queue time i.e. the time when the chat was in queue (pending) state. This response time value thus gives us the total time taken to respond to the user. 
    
3. **Avg. Resolution Time**

    Resolution Time here is same as defined above in Time stats. Just the change being, this metric is for the single agent. And the metric above is on a Team level.
    
> Note that resolution time metrics shown here for agents and team both include the wait time i.e. the time when the chat was in waiting state. This resolution time value thus gives us the total time taken to handle a user chat end to end. 
    
4. **Chats received**

    Similar to the Total Chats received, this metric is calculated at an agent level. And the Total chats received metric in Chat stats section above is at a Team level that is the Total chats received for the Team. 

5. **Avg. User Rating**

    User rating here is same as defined above in Overview section. Just the change being, this metric is for the single agent. And the metric above is on a Team level.

> Note that the User rating is calculated basis the last agent who claimed the chat. There are scenarios wherein the chat completes and then user submits feedback. If the claim name had changed from the last agent to another agent, the feedback will get tagged to this new agent. Feedback metric is integral more at a conversation level. And for agents, feedback is a tertiary metric. The reason being the number of feedbacks submitted considered against the volume of daily chats is nominal. 

6. **Agent Online Time**

    When agents are receiving chats, we total this time i.e. to give you a sense of agent's online activity. This is a useful input to understand agent productivity. 
    
![Online agents with no metrics](assets/no_ecm_agent.png)
    
> When agents are in online state and they have pinned chats, they would not get new chats assigned, as they are capped at their concurrency limit. So, we could get scenarios wherein, we have agents online but they don't get new chats and other metrics such as FRT, Resolution Time etc. are absent. This happens because the agent is not closing chats and is capped at their concurrency. This concurrency cap is the maximum allowed chats count that an agent is allowed to take at any instant. 

    
