---
title: Azure Monitor
tags: [integration, azure monitor]
last_updated:
keywords: 
summary: "Get alerts from Azure Monitor into Squadcast"
sidebar: mydoc_sidebar
permalink: docs/azure-monitor.html
folder: mydoc
---

Follow the steps below to configure a service so as to extract its related alert data from Azure monitor. Squadcast will then process this information to create incidents for this service as per your preferences.

## Using Azure Monitor as an Alert Source

On the **Sidebar**, click on **Services**.

You can either choose to use existing service or [create a new service](adding-a-service.html)

Now, click on the corresponding **Alert Sources** button.

![](images/integration_1.png)

Select **Azure Monitor** from  **Alert Source** drop down and copy the Webhook URL shown.

![](images/azure_1.png)

## Create Squadcast Webhook in Azure

Login to your Azure account select your virtual machine. Under **Monitoring**, go to **Alerts**.

Then go to **Manage Actions** → **Add Action groups** → **Creatre action group** (Test grp or Squadcast webhook alerts) by selecting **Action type** as **Webhook**. Paste the squadcast webhook url from the previous step and make sure **Enable the common alert schema** toggle switch is turned on.

![](images/azure_2.png)

Go back to **Alerts** window and click **New Alert**. Specify Resource, Condition and under **Actions** select the action group (Test grp or Squadcast webhook alerts) you just made. Provide alert rule Name, Description and **Create Alert**.

![](images/azure_3.png)

Now whenever an alert is triggered by Azure Monitor, an incident will be created automatically in Squadcast. 

The Azure Monitor integration comes with an **Auto-Resolve** feature, meaning that whenever the alerts gets resolved in Azure, the incident will automatically get resolved in Squadcast as well.