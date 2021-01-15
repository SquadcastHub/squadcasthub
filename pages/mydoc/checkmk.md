---
title: Checkmk
tags: [integration, checkmk]
keywords:
last_updated:
summary: "Get Alerts from Checkmk into Squadcast"
sidebar: mydoc_sidebar
permalink: docs/checkmk.html
folder: mydoc
---

Follow the steps below to configure a service so as to extract its related alert data from Checkmk, which is built on top of Nagios. Squadcast will then process this information to create incidents for this service as per your preferences.

{{site.data.alerts.yellow-note-i}}
<b>Note: </b>
<br/><br/><p>Note that you must be logged in as <code class="highlighter-rouge" style="color: #c7254e; background-color: #f9f2f4 !important;">root</code> to complete the installation.</p>
{{site.data.alerts.end}}

These instructions might need to be altered based on your exact Linux distribution and your Checkmk version and configuration. 

Please drop our **[Support Team](mailto:support@squadcast.com)** a line if you have any trouble completing the integration

## Using Checkmk as an Alert Source

On the **Sidebar**, click on **Services**.

You can either choose to use existing service or [create a new service](adding-a-service.html)

Now, click on the corresponding **Alert Sources** button.

![](images/integration_1.png)

Select **Checkmk** from  **Alert Source** drop down and copy the Webhook URL shown.

![](images/checkmk_1.png)

## Steps for integrating Checkmk

+ Go to your Checkmk server.
+ Download the Squadcast notification script.

```
wget https://raw.githubusercontent.com/SquadcastHub/squadcast-checkmk-script/master/sq-script.py
```

+ Move the notification script into place.

For the standalone version of Checkmk, this is usually in the below path:

`/usr/share/check_mk/notifications`

```
mv sq-script.py /usr/share/check_mk/notifications
```

For the OMD version of Checkmk, this is usually located in
`/omd/sites/{site-name-here}/local/share/check_mk/ notifications`.

```
mv sq-script.py /omd/sites/{site-name-here}/local/share/check_mk/notifications
```

+ Then give the script execute permission.

```
chmod +x sq-script.py
```

+ Log in to the Checkmk web interface, go to **Users** (located in the WATO· Configuration box) and click **New User**

![](images/checkmk_2.png)

+ Enter a Username and, optionally, a Full name for the Squadcast user. 

{{site.data.alerts.green-note-check}}
<b>Pro Tip: </b>
<br/><br/><p>You will find it beneficial to set the full name to match the name of your Squadcast service if you will plan to configure Checkmk hosts and services to alert multiple Squadcast services and not just one.</p>
{{site.data.alerts.end}}

+ Do not enter a password for this user; instead **check** `disable the login to this account`. This step is done as this account exists solely to send notifications to the Squadcast script.

+ Set the user’s role to `Normal monitoring user`, or any custom role you’ve created with permissions to send notifications. 

+ Add the user to the Contact Groups which are a part of the hosts/services that you want to receive alerts for. Click **Save** when you are done.

![](images/checkmk_3.png)

+ Click the Notifications icon (bell icon) for the user created.

![](images/checkmk_4.png)

+ Enter a **Description** for the new notification method, then set **Notification Method** to **Squadcast**. 

+ Paste the Webhook URL you copied from Squadcast earlier in the text box that appears once you select **Squadcast**, and select any desired conditions to limit the alerts that get sent to Squadcast. Click **Save** when you are done.

![](images/checkmk_5.png)

+ Go back to the Users list and click  **Changes**, then click **Activate Changes**.

![](images/checkmk_6.png)

![](images/checkmk_7.png)

+ Congratulations! When you see **"Configuration successfully activated"** you are done! Checkmk will now be able send alerts into Squadcast. 

## Testing the Checkmk Integration

You can test the integration to make sure everything works as expected by going to a host or service in the Checkmk interface and clicking the Execute icon (hammer). 

+ In the Fake check results box, click **Critical** (if on a service) or **Down** (if on a host), then click `Yes!` to confirm that you want to send the fake alert. 

+ You should see a new incident created in Squadcast.

![](images/checkmk_8.png)

{{site.data.alerts.yellow-note-i}}
<b>Note: </b>
<br/><br/><p>This integration has been tested with Checkmk version 1.6. However, this integration should work with other existing versions as well, just with slight UI differences.</p>