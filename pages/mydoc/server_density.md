---
title: Server Density
tags: [integration, server density]
keywords: 
last_updated: 
summary: "Send events to Squadcast from Server Density"
sidebar: mydoc_sidebar
permalink: docs/server-density.html
folder: mydoc
---

Follow the steps below to configure a service so as to extract its related alert data from Server Density. Squadcast will then process this information to create incidents for this service as per your preferences.

## Using Server Density as an Alert Source

On the **Sidebar**, click on **Services**.

You can either choose to use existing service or [create a new service](adding-a-service.html)

Now, click on the corresponding **Alert Sources** button.

![](images/integration_1.png)

Select **Server Density** from  **Alert Source** drop down and copy the Webhook URL shown.

![](images/server_density_1.png)

Now log in to your Server Density account and click on the gear icon on the top right and then click on notifications.

![](images/server_density_2.png)

In the notifications page select "**Webhook**" as the type of notification and enter the URL obtained earlier as the **webhook URL**. Give it an appropriate name and click on Add.

![](images/server_density_3.png)

Now you can use this "**Webhook**" for any alert as per your requirements.

![](images/server_density_4.png)

That's it your Server Density Integration is now good to go. Once an alert is fixed inside Server Density it will automatically be resolved inside Squadcast as well.