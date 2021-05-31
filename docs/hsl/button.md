---
title: Button
---

## Sample Button

```json
{
  "text": "Click on the below button to be redirected",
  "type": "BUTTON",
  "data": {
    "items": [
      {
        "actionable_text": "Google",
        "location_required": false,
        "is_default": 0,
        "uri": "LINK",
        "type": "APP_ACTION",
        "payload": {
          "message": "message that will be sent as a chat message on behalf of the user",
          "url": "https://google.com",
          "gogo_message": ""
        }
      }
    ]
  }
}
```

## Sample Output

![hsl_sample_button](assets/hsl_sample_button.png)


## HSL to upload PDF

```JSON
{
  "text": "Upload PDF",
  "type": "BUTTON",
  "data": {
    "items": [
      {
        "actionable_text": "PDF upload",
        "location_required": false,
        "is_default": 0,
        "uri": "DOCUMENT_PICKER",
        "type": "APP_ACTION",
        "payload": {
          "mime_types": [
            "application/pdf",
            "application/msword",
            "application/vnd.openxmlformats-officedocument.wordprocessingml.document",
            "application/vnd.ms-excel",
            "application/vnd.openxmlformats-officedocument.spreadsheetml.sheet",
            "text/csv",
            "comma-separated-values"
          ]
        }
      }
    ]
  },
  "isNew": false
}
```

## Output

![image](https://user-images.githubusercontent.com/75118325/117771789-17ba1480-b254-11eb-9b2f-f81ff4cc1bc6.png)


<table border="1" class="docutils">
   <thead>
      <tr>
         <th>Property Name</th>
         <th>Description</th>
         <th>Required</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>text</td>
         <td>The main text that is shown in the Button element</td>
         <td>Yes</td>
      </tr>
      <tr>
         <td>type</td>
         <td>To be set as BUTTON for a button HSL element</td>
         <td>Yes</td>
      </tr>
      <tr>
         <td>data.items.actionable_text</td>
         <td>The text that is displayed to the users</td>
         <td>Yes</td>
      </tr>
      <tr>
         <td>data.items.location_required</td>
         <td>DEPRECATED - true or false, if true, location information is sent to backend<</td>
         <td>Yes</td>
      </tr>
      <tr>
         <td>data.items.is_default</td>
         <td>If True, this is the default element that is invoked if the image/text part of the element is tapped</td>
         <td>Yes</td>
      </tr>
      <tr>
         <td>data.items.uri</td>
         <td>This can take multiple values that is defined in the <a href='https://docs.haptik.ai/hsl/hsl-properties'>hsl-properties</a></td>
         <td>Yes</td>
      </tr>
      <tr>
         <td>data.items.type</td>
         <td>This can take multiple values that is defined in the <a href='https://docs.haptik.ai/hsl/hsl-properties'>hsl-properties</a></td>
         <td>Yes</td>
      </tr>
      <tr>
         <td>data.items.payload</td>
         <td>This can take multiple values that is defined in the <a href='https://docs.haptik.ai/hsl/hsl-properties'>hsl-properties</a></td>
         <td>Yes</td>
      </tr>
   </tbody>
</table>
