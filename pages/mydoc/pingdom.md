---
title: Pingdom
tags: [integration, pingdom]
keywords: 
last_updated: 
summary: "Send events to Squadcast from Pingdom"
sidebar: mydoc_sidebar
permalink: docs/pingdom.html
folder: mydoc
---

Follow the steps below to configure a service so as to extract its related alert data from Pingdom. Squadcast will then process this information to create incidents for this service as per your preferences.

## Using Pingdom as an Alert Source

On the **Sidebar**, click on **Services**.

You can either choose to use existing service or [create a new service](adding-a-service.html)

Now, click on the corresponding **Alert Sources** button.

![](images/integration_1.png)

Select **Pingdomr** from  **Alert Source** drop down and copy the Webhook URL shown.

![](images/pingdom_1.png)

## Create a Squadcast Webhook in Pingdom

Now login to your Pingdom account.

Click on **Integrations** to go to the Integrations page.

![](images/pingdom_2.png){: style="max-width: 30%" }

Click on "**Add Integration**" and in the subsequent dialog box select type as "**Webhook**" and provide an appropriate name for the integration. Enter the URL obtained earlier and tick the "**Active Checkbox**". Finally click on "**Save Integration**" button. 

![](images/pingdom_3.png)

Now you can connect this integration to any of yours checks on Pingdom.

![](images/pingdom_4.png)

That's it! Your Pingdom integration is now good to go.

Once a check gets **UP** or **SUCCESS** from Pingdom it will automatically be resolved inside Squadcast.