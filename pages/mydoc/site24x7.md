---
title: Site24x7
tags: [integration, site24x7]
keywords: 
last_updated: 
summary: "Get alerts from Site24x7 (a service by Zoho Corp) into Squadcast"
sidebar: mydoc_sidebar
permalink: docs/site24x7.html
folder: mydoc
---

## Pre-requisites
1.  A valid Squadcast cloud subscription 
2. A user account in Zoho's Site24x7

Follow the steps below to configure a service so as to push related alert data from Site24x7 onto Squadcast.

Squadcast will then process this information to create incidents for this service as per your preferences.

## Using Site24x7 as an Alert Source

On the **Sidebar**, click on **Services**.

You can either choose to use existing service or [create a new service](adding-a-service.html)

Now, click on the corresponding **Alert Sources** button.

![](images/integration_1.png)

Select **Site24x7** from  **Alert Source** drop down and copy the Webhook URL shown.

![](images/site24x7_1.png)

Next, head over to your Site24x7 dashboard and set up a Webhook based integration.

![](images/site24x7_2.png)

You will next be greeted by the Webhooks Integration configuration page.
Paste the previously copied Webhook URL into the **Hook URL** field.

{{site.data.alerts.blue-note}}
<b>Custom Parameters: </b>
<br/><br/><p>If you wish to send Custom Parameters in your payload, kindly prefix (this is an ABSOLUTE NECESSITY) every parameter-key with <b>CUSTOM_</b>. That way, we can point them out in the <b>Incident Description</b> in <b>Squadcast</b>.</p>
{{site.data.alerts.end}}

![](images/site24x7_3.png)

Scroll down to configure all other necessary details.

![](images/site24x7_4.png)

Click on **Save** and you're pretty much done with the configuration. 

![](images/site24x7_5.png)

You can now start using this integration with Monitors that you might have set up in Site24x7.

Now, whenever any Site24x7 Monitor reports "STATUS" as **DOWN**, an incident will be triggered in Squadcast . Once this "STATUS" goes back to **UP**, it will automatically be resolved in Squadcast.