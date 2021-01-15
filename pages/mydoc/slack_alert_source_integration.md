---
title: Slack Alert Source Integration
tags: [integration, slack]
keywords: 
last_updated: 
summary: "Slack Alert Source"
sidebar: mydoc_sidebar
permalink: docs/slack-as-an-alert-source.html
folder: mydoc
---

## Creating Incidents from Slack

Move over to the channel in which you want the incident to be created. 

Invoke the *Squadcast Bot* by calling out `@squadcast`. 

![](images/slack_1.png)

Once the bot is called in, you will be able to take some incident actions from Slack. 

### Using Slash Command in Slack

{{site.data.alerts.blue-note}}
<b>Help: </b>
<br/><br/><p>You can call out <code class="highlighter-rouge" style="color: #c7254e; background-color: #f9f2f4 !important;">/create_incident help</code> to walk you through the process on Slack as well</p>
{{site.data.alerts.end}}

![](images/slack_2.png)

`/create_incident <Incident Message Text>`

You can call the `/create_incident <Incident Message Text>` command to create an incident from Slack.

![](images/slack_3.png)

This will them prompt a UI pop-up where you can fill in additional information like the Impacted **Service**,**Incident Message** and **Incident Description**.

![](images/slack_4.png)

The created incident will now show up on the Slack channel and on Squadcast

![](images/slack_5.png)

### Using Message Actions in Slack

You can also choose to create an incident from an existing message on Slack.

![](images/slack_6.png)

Click on the **More Actions** icon for the chosen message. 

![](images/slack_7.png)

Choose **Create Incident** from the dropdown shown and then you will get a UI pop-up to fill in other relevant information needed to enrich the incident information.

![](images/slack_8.png)

The incident has now been created successfully

![](images/slack_9.png)

{{site.data.alerts.note}}
<br/><br/><p>The Squadcast Bot must be called into the channel where you will want to take any Bot Action</p>
{{site.data.alerts.end}}

### How to Video

<iframe width="560" height="315" src="https://www.youtube.com/embed/UmHk_jor_mg?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>