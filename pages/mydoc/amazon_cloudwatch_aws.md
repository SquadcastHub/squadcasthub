---
title: Amazon Cloudwatch (AWS)
tags: [integration, amazon cloudwatch]
keywords: 
last_updated: 
summary: "Send events to Squadcast from AWS Cloudwatch (Amazon Web Services)"
sidebar: mydoc_sidebar
permalink: docs/amazon-cloudwatch-aws.html
folder: mydoc
---

Follow the steps below to configure a service so as to push related alert data from Honeybadger onto Squadcast.

Squadcast will then process this information to create incidents for this service as per your preferences.

## Using Amazon CloudWatch as an Alert Source

On the **Sidebar**, click on **Services**.

You can either choose to use existing service or [create a new service](adding-a-service.html)

Now, click on the corresponding **Alert Sources** button.

![](images/integration_1.png)

Select **Amazon CloudWatch** from  **Alert Source** drop down and copy the Webhook URL shown.

![](images/aws_1.png)

## Create a Squadcast Webhook in Amazon CloudWatch

Now log in to your AWS account and proceed to SNS.

Click on "**Create topic**" to get "Create new topic" dialog box. Fill in the details as per your requirements and then click on "Create topic"

![](images/aws_2.png)

Now inside the topic, click on "**Create subscription**" to get "Create subscription" dialog box. Select the protocol as "HTTPS" and in the endpoint enter the URL you obtained earlier. Finally, click on "Create subscription" to create the subscription.

![](images/aws_3.png)

The "**Subscription ID**" for the subscription should immediately change from "PendingConfirmation". Click on the refresh button to verify the same.

![](images/aws_4.png)

Now you can go to any of your AWS services for which you want to set the Alarm. We'll take the example of "EC2" in this case.

Right-click on your EC2 instance and go to "**CloudWatch Monitoring**". Click on "**Add/Edit Alarms**".

![](images/aws_5.png)

Click on "**Create Alarm**" and in the following dialog box for "Send a notification to" drop down, select the topic you created earlier. Configure the alarm as per your requirements and finally click on "**Create Alarm**". Now you will start receiving incidents on Squadcast whenever this Alarm moves to "**ALARM" state**.

![](images/aws_6.png)

Under "**Actions**", add a notification selecting "**Whenever this alarm: State is OK**" and "Send notification to:" as the topic you created earlier. Finally click on "**Save Changes**".

![](images/aws_7.png)

That's it your Amazon CloudWatch Integration is now good to go! Whenever an Alarm moves to OK state inside CloudWatch the corresponding incident will automatically be resolved in Squadcast.