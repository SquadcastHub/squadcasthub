---
title: OverOps
tags: [integration, overops]
keywords: 
last_updated: 
summary: "Get alerts from OverOps into Squadcast"
sidebar: mydoc_sidebar
permalink: docs/overops.html
folder: mydoc
---

Follow the steps below to configure a service so as to extract its related alert data from Splunk. Squadcast will then process this information to create incidents for this service as per your preferences.

## Using OverOps as an Alert Source in Squadcast

On the **Sidebar**, click on **Services**.

You can either choose to use existing service or [create a new service](adding-a-service.html)

Now, click on the corresponding **Alert Sources** button.

![](images/integration_1.png)

Select **OverOps** from  **Alert Source** drop down and copy the Webhook URL shown.

![](images/overops_1.png)

## Create a Squadcast Webhook alert in OverOps

In your OverOps dashboard, click on the **Settings** icon, select **Alerts** and then select the **Webhooks** tab.

![](images/overops_2.png)

Paste the OverOps webhook URL that you have got from the previous step in the URL box and click **Apply** button.

![](images/overops_3.png)

That's it! Now your integration is good to go. Then you can configure alerts the usual way and it will be automatically created in Squadcast.