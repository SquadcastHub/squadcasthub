---
title: Sqreen
tags: [integration, sqreen]
keywords: 
last_updated: 
summary: "Get alerts from Sqreen into Squadcast"
sidebar: mydoc_sidebar
permalink: docs/sqreen.html
folder: mydoc
---

Follow the steps below to configure a service so as to push related alert data from Sqreen onto Squadcast.

Squadcast will then process this information to create incidents for this service as per your preferences.

## Using Sqreen as an Alert Source

On the **Sidebar**, click on **Services**.

You can either choose to use existing service or [create a new service](adding-a-service.html)

Now, click on the corresponding **Alert Sources** button.

![](images/integration_1.png)

Select **Sqreen** from  **Alert Source** drop down and copy the Webhook URL shown.

![](images/sqreen_1.png)

## Add webhook to your application

1.Log in to **Sqreen dashboard** and select the the application you want to add webhook from the dropdown.

2.And click the **settings** button 

![](images/sqreen_2.png)

3.Click on the **Integrations** tab.

Come to down to the Webhook page and paste the **Webhook URL** in the URL text box and click on 
the **Save Webhook** button.

![](images/sqreen_3.png)


Now you're all set & good to go.

4.[Optional] You can now test your configuration by clicking on the **Test your configuration** button.

Now whenever an event is triggered in Sqreen, an incident will be created automatically in Squadcast.
