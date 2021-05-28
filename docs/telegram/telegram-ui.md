---
title: Telegram UI Comparison
---

Conversation Studio tool has various rich chat elements to show different types of messages to the users. The following table depicts how these chat elements are rendered on the Telegram bot.

<table>
  
  <th>Element</th>
  <th>On Conversation Studio</th>
  <th>On Telegram bot</th>
  
  <tr>
    <td><b>Buttons text and link buttons</b></td>
    <td align="center"><img src="https://user-images.githubusercontent.com/75118325/119966519-02214a80-bfc9-11eb-99b4-2080f56d248b.png" height=150 width=300/></td>
    <td align="center"><img src="https://user-images.githubusercontent.com/75118325/119966613-1d8c5580-bfc9-11eb-8f5b-5d0a28d36b17.png" height=150 width=300></img></td>
  </tr>
  
  <tr>
    <td><b>Text with Quick Replies</b></td>
    <td align="center"><img src="https://user-images.githubusercontent.com/75118325/119967698-46611a80-bfca-11eb-8dc4-28b9b04debda.png"/></td>
    <td align="center"><img src="https://user-images.githubusercontent.com/75118325/119967791-5b3dae00-bfca-11eb-91e9-9a67024843ff.png"/></td>
  </tr>
  
  <tr>
    <td><b>Carousels</b></td>
  <td colspan=2 align="center">Carousels are not supported on Telegram</td>
  </tr>
  
  <tr>
  <td><b>Sending Audio Files to the user</b></td>
  <td align="center">Refer the JSON provided below the table</td>
  <td align="center"><img src="https://user-images.githubusercontent.com/75118325/119971709-f0db3c80-bfce-11eb-8701-3e089d38f7c4.png"/></td>
  </tr>
  
  <tr>
  <td><b>Documents (for users to download)</b></td>
  <td align="center">Refer the JSON provided below the table</td>
  <td align="center"><img src="https://user-images.githubusercontent.com/75118325/119968981-a5735f00-bfcb-11eb-93e1-d688459a6602.png"/></td>
  </tr>
  
  <tr>
  <td colspan=3 align="center"> <h4> How Haptik receives information provided by the User </h4></td>
  </tr>
  
  <tr>
  <td><b>Images</b></td>
  <td align="center"><img src="https://user-images.githubusercontent.com/75118325/119968489-2aaa4400-bfcb-11eb-92ed-5e4aa87c3134.png"/></td>
  <td align="center"><img src="https://user-images.githubusercontent.com/75118325/119968552-43b2f500-bfcb-11eb-8613-f5325af1c01c.png"/></td>
  </tr>
    
  <tr>
  <td><b>Documents (uploaded by user)</b></td>
  <td align="center"><img src="https://user-images.githubusercontent.com/75118325/119969046-b45a1180-bfcb-11eb-9d89-b4cd8cdd6f94.png"/></td>
  <td align="center"><img src="https://user-images.githubusercontent.com/75118325/119968981-a5735f00-bfcb-11eb-93e1-d688459a6602.png"/></td>
  </tr>
  
  <tr>
  <td><b>Location (provided by user)</b></td>
  <td align="center"><img src="https://user-images.githubusercontent.com/75118325/119971975-46174e00-bfcf-11eb-9c0f-4325c59238fe.png"/></td>
  <td align="center"><img src="https://user-images.githubusercontent.com/75118325/119971931-37c93200-bfcf-11eb-8bce-f19a52472c09.png"/></td>
  </tr>
  
     
  </table>
  
  
  ### JSON to send Audio files to the user
  
  ```JSON
  {
  "text": "Here is audio file",
  "type": "BUTTON",
  "data": {
    "items": [
      {
        "actionable_text": "Download Audio",
        "location_required": false,
        "is_default": 0,
        "uri": "LINK",
        "type": "APP_ACTION",
        "payload": {
          "gogo_message": "",
          "url": "<LINK TO AUDIO FILE>"
        }
      }
    ]
  },
  "isNew": false
}
  ```
  
  ### JSON to display PDFs to the user
  
  ```JSON
  {
   "type":"BUTTON",
   "data":{
      "items":[
         {
            "actionable_text":"SID",
            "location_required":false,
            "is_default":0,
            "uri":"LINK",
            "type":"APP_ACTION",
            "payload":{
               "gogo_message":"",
               "url":"<LINK TO PDF>"
            }
         }
      ]
   },
   "isNew":false
}
  ```
  
 
