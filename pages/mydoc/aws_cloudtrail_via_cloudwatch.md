---
title: AWS CloudTrail via CloudWatch
tags: [integration, aws cloudtrail via cloudwatch]
keywords: 
last_updated: 
summary: "Get CloudTrail alerts into Squadcast using CloudWatch and SNS endpoints"
sidebar: mydoc_sidebar
permalink: docs/aws-cloudtrail-via-cloudwatch.html
folder: mydoc
---

Please use this integration guide to configure CloudTrail alerts so they can be received in Squadcast. This integration should be used only for getting CloudTrail alerts via CloudWatch and a SNS endpoint. 

For CloudTrail log alerts, use the [AWS CloudTrail Logs integration](aws-cloudtrail-logs.html). 

For regular AWS CloudWatch alarms (like EC2 alerts), use the [AWS CloudWatch Integration](amazon-cloudwatch-aws.html).

## Using AWS CloudTrail via CloudWatch as an Alert Source

On the **Sidebar**, click on **Services**.

You can either choose to use existing service or [create a new service](adding-a-service.html)

Now, click on the corresponding **Alert Sources** button.

![](images/integration_1.png)

Select **AWS CloudTrail via CloudWatch** from  **Alert Source** drop down and copy the Webhook URL shown.

![](images/cloudwatch_1.png)

## Create CloudTrail Alarm Endpoint in AWS SNS

Now log in to your AWS account and proceed to SNS.

Click on "**Create topic**" to get "Create new topic" dialog box. Fill in the details as per your requirements and then click on "**Create topic**"

![](images/cloudwatch_2.png)

Now inside the topic, click on "**Create subscription**" to get "Create subscription" dialog box. Select the protocol as "**HTTPS**" and in the endpoint enter the URL you obtained from previous step. Finally, click on "**Create subscription**" to create the subscription.

![](images/cloudwatch_3.png)

![](images/cloudwatch_4.png)

The "**Subscription ID**" for the subscription should immediately change to "**Confirmed**" from "**PendingConfirmation**". Click on the refresh button to verify the same.

![](images/cloudwatch_5.png)

Then you can [configure your CloudTrail alerts](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudwatch-alarms-for-cloudtrail.html#cloudwatch-alarms-for-cloudtrail-security-group) and assign this topic as the notification option and you are good to go.