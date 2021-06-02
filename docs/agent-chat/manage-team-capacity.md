---
title: Manage Team Capacity
---

## How to understand Team capacity?

In real-time, **Manage Agents** allows TLs to analyze the team capacity. This section helps you to gauge the incoming traffic and if the available agents would be able to handle all the incoming chats. You will also be able to check if the team needs more agents to be online to handle the incoming chats.

### Chat handling Capacity and Online Agent slots

![Queue capacity 1](assets/case_1.png)

The Chat handling capacity for a Team here helps figure the required number for agents at any given instant i.e. for under capacity scenario, the TLs can let some agents go offline. And in case a Team goes over capacity, TLs can call upon agents to be online.

Check the image above. Here, you get 2 values in the Capacity card - 

1. **Chat handling capacity:** This is a %age value that signifies if your team capacity is ideal or your team cannot handle the current incoming chat volume. For example, if the number value is in red and the copy states `over capacity`, it means the chat volume supercedes the available online agents' capacity 

2. **Chats waiting to be taken:** Total number of chats in queue + chats in waiting i.e. all users who might need an agent at any given instant

3. **Total Slots:** Total concurrency of each online agent in the team. Say, if a team had 4 agents with each having a concurrency of 3. The total available slots for the team would be 12. 

> Note: The Online agents' ratio tells you the number of agents online by total number of agents in a given team. 

### How is Team capacity calculated?

![Queue capacity 2](assets/case_2.png)

Let's understand the formula to get Chat handling capacity by a example -

i. Total concurrency for online agents in the team = A

ii. Queued + Assigned Chats total for all agents in the shown team = B

iii. Availability is calculated as = (A-B) / A x 100

The point `iii` above gives the availability %age value. This value in green means the team can handle the incoming chat volume. 
