---
title: Carousel
---

#### Sample JSON for default Carousel

```json
{
  "text": "Here are the latest scorecards for the Delhi Daredevils vs. Kings XI Punjab match 🔢",
  "type": "CAROUSEL",
  "data": {
    "image_aspect_ratio": 1.69,
    "width": "THIN",
    "items": [
      {
        "thumbnail": {
          "image": "http://haptikappimg.haptikapi.com/Cricket_Images/Base_Template/Thumbnail_Innings_1.png"
        },
        "title": "DD: 166/7 (20.0 overs)",
        "sub_title": "KXIP: Bowling",
        "description": "",
        "actionables": [
          {
            "actionable_text": "View Scorecard",
            "location_required": false,
            "is_default": 0,
            "uri": "CAROUSEL_DETAIL",
            "type": "APP_ACTION",
            "payload": {
              "title": "DD vs. KXIP",
              "sub_title": "1st Innings",
              "description": "DD: 166/7 (20.0 overs)",
              "images": [
                "http://haptikappimg.s3.amazonaws.com/Cricket_Images/Match_Scorecard/Innings_Score_Batting_1_186013_1_1523189431.png",
                "http://haptikappimg.s3.amazonaws.com/Cricket_Images/Match_Scorecard/Innings_Score_Batting_2_186013_1_1523189432.png",
                "http://haptikappimg.s3.amazonaws.com/Cricket_Images/Match_Scorecard/Innings_Score_Bowling_186013_1_1523189431.png"
              ],
              "gogo_message": "",
              "link": ""
            },
            "emoji": ""
          }
        ]
      },
      {
        "thumbnail": {
          "image": "http://haptikappimg.haptikapi.com/Cricket_Images/Base_Template/Thumbnail_Innings_2.png"
        },
        "title": "KXIP: 167/4 (18.5 overs)",
        "sub_title": "DD: Bowling",
        "description": "",
        "actionables": [
          {
            "actionable_text": "View Scorecard",
            "location_required": false,
            "is_default": 0,
            "uri": "CAROUSEL_DETAIL",
            "type": "APP_ACTION",
            "payload": {
              "title": "DD vs. KXIP",
              "sub_title": "2nd Innings",
              "description": "KXIP: 167/4 (18.5 overs)",
              "images": [
                "http://haptikappimg.s3.amazonaws.com/Cricket_Images/Match_Scorecard/Innings_Score_Batting_1_186013_2_1523197798.png",
                "http://haptikappimg.s3.amazonaws.com/Cricket_Images/Match_Scorecard/Innings_Score_Batting_2_186013_2_1523197799.png",
                "http://haptikappimg.s3.amazonaws.com/Cricket_Images/Match_Scorecard/Innings_Score_Bowling_186013_2_1523197798.png"
              ],
              "gogo_message": "",
              "link": ""
            },
            "emoji": ""
          }
        ]
      }
    ]
  }
}
```

#### Sample Output

![hsl_sample_carousel](assets/hsl_sample_carousel.png)

#### Sample JSON for mini actionable

```json
{
  "text": "Here is a Saving Tip for you",
  "type": "CAROUSEL",
  "data": {
    "image_aspect_ratio": "1.67",
    "width": "FAT",
    "items": [
      {
        "thumbnail": {
          "image": "http://haptik-staging.s3.amazonaws.com/Image%20Generator/money_saving_tip/money_saving_tip_ad712a04-065d-409a-bcbe-94dfc9e3ef56.png?w=1068&amp;h=639"
        },
        "actionables": [],
        "mini_actionable": {
          "actionable_text": ":share: Share",
          "location_required": false,
          "is_default": 0,
          "type": "SHARE",
          "payload": {
            "show_share_option": true,
            "image": "http://haptik-staging.s3.amazonaws.com/Image%20Generator/money_saving_tip/money_saving_tip_ad712a04-065d-409a-bcbe-94dfc9e3ef56.png?w=1068&amp;h=639",
            "gogo_message": "",
            "message": "A great Saving Tip for you!"
          },
          "uri": ""
        }
      }
    ]
  }
}
```

#### Sample Output

![hsl_mini_actionable_carousel](assets/hsl_mini_actionable_carousel.png)

#### Sample JSON for Carousel without Image

```
{
  "type": "CAROUSEL",
  "data": {
    "image_aspect_ratio": "1000.1",
    "width": "THIN",
    "items": [
      {
        "thumbnail": {
          "image": "https://haptikappimg.haptikapi.com/uploads/8d6e31d6504350164b3cb89e4931219e.png?w=121&h=86"
        },
        "title": "carousel without image - 1",
        "sub_title": "",
        "description": "Add a white image",
        "actionables": [
          {
            "actionable_text": "Click here to know more",
            "location_required": false,
            "is_default": 0,
            "uri": "LINK",
            "type": "APP_ACTION",
            "payload": {
              "title": "Button  1",
              "url": "https://docs.haptik.ai/bot-builder/basic/chat-elements#carousel",
              "gogo_message": ""
            }
          }
        ]
      },
      {
        "thumbnail": {
          "image": "https://haptikappimg.haptikapi.com/uploads/89fc31bbf2e166ad74daa42dd70b5550.png?w=121&h=86"
        },
        "title": "carousel without image - 1",
        "description": "Set the aspect ratio as 1000.1",
        "actionables": [
          {
            "actionable_text": "Click here to know more",
            "location_required": false,
            "is_default": 0,
            "uri": "LINK",
            "type": "APP_ACTION",
            "payload": {
              "title": "Button  1",
              "url": "https://docs.haptik.ai/bot-builder/basic/chat-elements#carousel",
              "gogo_message": ""
            }
          }
        ]
      }
    ]
  },
  "isNew": false
}
```

#### Sample Output

![hsl_no_image_carousel](assets/no_image_carousel.png)

#### Sample JSON for Video embedded on carousel

```
{
  "type": "CAROUSEL",
  "data": {
    "image_aspect_ratio": "1.77",
    "width": "THIN",
    "items": [
      {
        "thumbnail": {
          "image": "https://www.youtube.com/embed/hNQFjqDvPhA"
        },
        "title": "test",
        "sub_title": "test",
        "description": "test",
        "actionables": [
          {
            "actionable_text": "Button 1",
            "location_required": false,
            "is_default": 0,
            "uri": "",
            "payload": {
              "gogo_message": ""
            }
          }
        ]
      },
      {
        "thumbnail": {
          "image": "https://www.youtube.com/embed/aJOTlE1K90k"
        },
        "title": "not playing",
        "sub_title": "issue on mac",
        "actionables": [
          {
            "actionable_text": "Button 1",
            "location_required": false,
            "is_default": 0,
            "uri": "",
            "payload": {
              "gogo_message": ""
            }
          }
        ]
      },
      {
        "thumbnail": {
          "image": "https://www.youtube.com/embed/xcJtL7QggTI"
        },
        "title": "",
        "actionables": [
          {
            "actionable_text": "Button 1",
            "location_required": false,
            "is_default": 0,
            "uri": "",
            "payload": {
              "gogo_message": ""
            }
          }
        ]
      }
    ]
  },
  "isNew": false
}
```

#### Sample Output

![hsl_video_carousel](assets/video_carousel.png)


#### Carousel

Carousel works mostly on actionables but some parts of it are very specific to Carousel design. Here are the keys:

<table border="1" class="docutils">
   <thead>
      <tr>
         <th>Values</th>
         <th>Description</th>
         <th>Required</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>text</td>
         <td>this will be the notification text</td>
         <td>Yes</td>
      </tr>
      <tr>
         <td>type</td>
         <td>has to be "CAROUSEL"</td>
         <td>Yes</td>
      </tr>
      <tr>
         <td>data.image_aspect_ratio</td>
         <td>defines the height of the carousel</td>
         <td>No</td>
      </tr>
      <tr>
         <td>data.width</td>
         <td>THIN, MEDIUM, FAT, BIG</td>
         <td>Yes</td>
      </tr>
      <tr>
         <td>data.items</td>
         <td>list of each carousel element</td>
         <td>Yes</td>
      </tr>
      <tr>
         <td>data.items.title</td>
         <td>title of carousel element</td>
         <td>No</td>
      </tr>
      <tr>
         <td>data.items.sub_title</td>
         <td>below title of carousel element</td>
         <td>No</td>
      </tr>
      <tr>
         <td>data.items.description</td>
         <td>appears below sub_title</td>
         <td>No</td>
      </tr>
      <tr>
         <td>data.items.actionable</td>
         <td>type list as per the actionables list specified in <a href='https://docs.haptik.ai/hsl/hsl-properties'>hsl-properties</a></td>
         <td>Yes</td>
      </tr>
</table>
