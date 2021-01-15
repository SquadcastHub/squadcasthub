---
title: Sysdig Monitor
tags: [integration, sysdig monitor]
keywords: 
last_updated: 
summary: "Get alerts from Sysdig Monitor into Squadcast"
sidebar: mydoc_sidebar
permalink: docs/sysdig-monitor.html
folder: mydoc
---

Follow the steps below to configure a service so as to push related alert data from Sysdig Monitor onto Squadcast.

Squadcast will then process this information to create incidents for this service as per your preferences.

## Using Sysdig Monitor as an Alert Source

On the **Sidebar**, click on **Services**.

You can either choose to use existing service or [create a new service](adding-a-service.html)

Now, click on the corresponding **Alert Sources** button.

![](images/integration_1.png)

Select **Sysdig Monitor** from  **Alert Source** drop down and copy the Webhook URL shown.

![](images/sysdig_1.png)

## Add a Notification Channel

To add a new notification channel:

1.Log in to Sysdig Monitor as administrator and select **Settings**. 

![](images/sysdig_2.png)

2.Select Notification Channels. 

The Notifications main page is displayed:

![](images/sysdig_3.jpeg)

3.Add a notification channel with the **+** button and select Webhook.

![](images/sysdig_4.png)

4.Enter the Webhook channel configuration options: 

**URL:** Enter the Webhook URL you copied from Squadcast dashboard

**Channel Name:** Add a meaningful name, such as  “Squadcast”,  “Squadcast Notification” etc

**Enabled:** Toggle on

**Notify when Resolved:**  Toggle on 

**Notify when Acknowledged:**  **Toggle off **

**Test notification:** Toggle to be notified that the configured URL is working. 

![](images/sysdig_5.png)

5.Click **Save**.

Now whenever an event is triggered in Sysdig Monitor, an incident will be created automatically in Squadcast. And once the event that triggered the incident(s) is resolved in Sysdig Monitor, the relevant Squadcast incidents created would get resolved automatically.