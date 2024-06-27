# build beautiful email marketing in json 

https://learn.microsoft.com/zh-cn/training/modules/adaptive-cards-create-engaging-messages/5-exercise-outlook-actionable-messages



# build-website-in-json

website have multiple blocks and sections already.right now we can design in figma and translate to html,but when contents change you need manually edit html or client /server code like ts whenever you use vue react astro  nextjs or else.

if we can make further step ,integrate with this translated html  to adaptivecards, separate card template and card data,everytime I want to change ,edit the json backend.you can have different data json for diff user to run ab test



import  html and gen design modularly

https://github.com/microsoft/AdaptiveCards/issues/8944


## basics

### components

https://learn.microsoft.com/en-us/adaptive-cards/rendering-cards/implement-a-renderer

https://adaptivecards.io/schemas/1.2.0/adaptive-card.json


https://adaptivecards.io/explorer/TextBlock.html

use this as starting point


https://adaptivecards.io/samples/





## samples 


sample output html
```
<div class="adaptivecard" data-designer-url="/designer/index.html" data-card-url="/payloads/TextBlock.json" null="" style="display: block;"><div class="ac-container ac-adaptiveCard" style="display: flex; flex-direction: column; justify-content: flex-start; box-sizing: border-box; flex: 0 0 auto; padding: 10px; margin: 0px; background-color: rgb(255, 255, 255);"><div class="ac-textBlock" style="overflow: hidden; font-family: &quot;Segoe UI&quot;, &quot;Helvetica Neue&quot;, Helvetica, sans-serif; font-size: 21px; color: rgb(0, 0, 0); font-weight: 400; text-align: start; line-height: 27.93px; white-space: nowrap; text-overflow: ellipsis; box-sizing: border-box; flex: 0 0 auto;"><p style="margin-top: 0px; width: 100%; overflow: hidden; text-overflow: ellipsis; margin-bottom: 0px;">This is some text</p>
</div><div class="ac-horizontal-separator" aria-hidden="true" style="height: 8px; overflow: hidden; flex: 0 0 auto; margin-right: 0px; margin-left: 0px;"></div><div class="ac-textBlock" style="overflow: hidden; font-family: &quot;Segoe UI&quot;, &quot;Helvetica Neue&quot;, Helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 0); font-weight: 600; text-align: start; line-height: 18.62px; white-space: nowrap; text-overflow: ellipsis; box-sizing: border-box; flex: 0 0 auto;"><p style="margin-top: 0px; width: 100%; overflow: hidden; text-overflow: ellipsis; margin-bottom: 0px;">It doesn't wrap by default</p>
</div><div class="ac-horizontal-separator" aria-hidden="true" style="height: 8px; overflow: hidden; flex: 0 0 auto; margin-right: 0px; margin-left: 0px;"></div><div class="ac-textBlock" style="overflow: hidden; font-family: &quot;Segoe UI&quot;, &quot;Helvetica Neue&quot;, Helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 0); font-weight: 400; text-align: start; line-height: 18.62px; overflow-wrap: break-word; box-sizing: border-box; flex: 0 0 auto;"><p style="margin-top: 0px; width: 100%; margin-bottom: 0px;">So set <strong>wrap</strong> to true if you plan on showing a paragraph of text</p>
</div><div class="ac-horizontal-separator" aria-hidden="true" style="height: 8px; overflow: hidden; flex: 0 0 auto; display: -webkit-box; margin-right: 0px; margin-left: 0px;"></div><div class="ac-textBlock" style="overflow: hidden; font-family: &quot;Segoe UI&quot;, &quot;Helvetica Neue&quot;, Helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 0); font-weight: 400; text-align: start; overflow-wrap: break-word; display: -webkit-box; -webkit-box-orient: vertical; -webkit-line-clamp: 2; box-sizing: border-box; flex: 0 0 auto;"><p style="margin-top: 0px; width: 100%; margin-bottom: 0px;">You can also use <strong>maxLines</strong> to prevent it from getting out of hand</p>
</div><div class="ac-horizontal-separator" aria-hidden="true" style="height: 8px; overflow: hidden; flex: 0 0 auto; margin-right: 0px; margin-left: 0px;"></div><div class="ac-textBlock" style="overflow: hidden; font-family: &quot;Segoe UI&quot;, &quot;Helvetica Neue&quot;, Helvetica, sans-serif; font-size: 14px; color: rgb(236, 19, 14); font-weight: 400; text-align: start; line-height: 18.62px; overflow-wrap: break-word; box-sizing: border-box; flex: 0 0 auto;"><p style="margin-top: 0px; width: 100%; margin-bottom: 0px;">You can even draw attention to certain text with color</p>
</div></div></div>
```

sample schema  
```
{
  "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
  "type": "AdaptiveCard",
  "version": "1.0",
  "body": [
    {
      "type": "TextBlock",
      "text": "This is some text",
      "size": "large"
    },
    {
      "type": "TextBlock",
      "text": "It doesn't wrap by default",
      "weight": "bolder"
    },
    {
      "type": "TextBlock",
      "text": "So set **wrap** to true if you plan on showing a paragraph of text",
      "wrap": true
    },
    {
      "type": "TextBlock",
      "text": "You can also use **maxLines** to prevent it from getting out of hand",
      "wrap": true,
      "maxLines": 2
    },
    {
      "type": "TextBlock",
      "text": "You can even draw attention to certain text with color",
      "wrap": true,
      "color": "attention"
    }
  ]
}
```


sample data
```
{
    "title": "Publish Adaptive Card Schema",
    "description": "Now that we have defined the main rules and features of the format, we need to produce a schema and publish it to GitHub. The schema will be the starting point of our reference documentation.",
    "creator": {
        "name": "Matt Hidinger",
        "profileImage": "https://pbs.twimg.com/profile_images/3647943215/d7f12830b3c17a5a9e4afcc370e3a37e_400x400.jpeg"
    },
    "createdUtc": "2017-02-14T06:08:39Z",
    "viewUrl": "https://adaptivecards.io",
    "properties": [
        {
            "key": "Board",
            "value": "Adaptive Cards"
        },
        {
            "key": "List",
            "value": "Backlog"
        },
        {
            "key": "Assigned to",
            "value": "Matt Hidinger"
        },
        {
            "key": "Due date",
            "value": "Not set"
        }
    ]
}
```
