---
title: Graylog
tags: [integration, graylog]
keywords: 
last_updated: 
summary: "Get alerts to Squadcast from Graylog"
sidebar: mydoc_sidebar
permalink: docs/graylog.html
folder: mydoc
---

Follow the steps below to configure a service so as to extract its related alert data from Graylog.

Squadcast will then process this information to create incidents for this service as per your preferences.

## Using Graylog as an Alert Source

You can either choose to use existing service or [create a new service](adding-a-service.html)

Now, click on the corresponding **Alert Sources** button.

![](images/integration_1.png)

Select **Graylog** from  **Alert Source** drop down and copy the Webhook URL shown.

![](images/graylog_1.png)

## Create a Squadcast Webhook in Graylog

1. Login to your graylog web console and go to **Alert** tab on the top.
2. Click on **Notifications**.
3. Click on **Add new notification**.
4. Select **All messages** on **Notify on Stream**
5. Select **HTTP Alarm Callback** on **Notification type** and click on **Add alert notification**.
6. Give a title to the notification and put the Squadcast web hook url from the previous step on the url field and click on **Save**.

![](images/graylog_2.png)

Now whenever an alert is triggered by Graylog, an incident will be created automatically in Squadcast.