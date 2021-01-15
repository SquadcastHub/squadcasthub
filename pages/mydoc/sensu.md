---
title: Sensu
tags: [integration, sensu]
keywords: 
last_updated: 
summary: "Send events to Squadcast from Sensu"
sidebar: mydoc_sidebar
permalink: docs/sensu.html
folder: mydoc
---

Follow the steps below to configure a service so as to extract its related alert data from Sensu.

Squadcast will then process this information to create incidents for this service as per your preferences.

## Using Sensu as an Alert Source

On the **Sidebar**, click on **Services**.

You can either choose to use existing service or [create a new service](adding-a-service.html)

Now, click on the corresponding **Alert Sources** button.

![](images/integration_1.png)

Select **Sensu** from  **Alert Source** drop down and copy the API Key shown.

![](images/sensu_1.png)

## On Your Sensu Server

**Note**: This guide was written and tested on Ubuntu 16.04 and Amazon Linux 2016.09, with Sensu 0.20.2-1 and 0.26.5-2. Paths may be different for other operating systems or Sensu versions. Note that all commands provided are intended to be run as the "root" user.

Save the Squadcast Sensu handler in your Sensu installation's plugins directory.

```
sudo wget -O /etc/sensu/plugins/squadcast-handler.rb https://raw.githubusercontent.com/squadcastHub/sensu_handler/master/squadcast-handler.rb
```

Make sure that the downloaded file has execute permission if not then provide the same using:

```
sudo chmod +x /etc/sensu/plugins/squadcast-handler.rb
```

Using the above file create a Sensu handler in the directory `/etc/sensu/conf.d` 
`/etc/sensu/conf.d/squadcast-handler.json`

```json
{            
    "handlers": {
        "squadcast": {
            "type": "pipe",
            "command":  "/etc/sensu/plugins/squadcast-handler.rb YOUR-INTEGRATION-KEY-HERE-FROM-STEP-2"                      
        }
    }
}
```

If you want, you can also make it the default handler as follows
`/etc/sensu/conf.d/default_handler.json`

```json
{
    "handlers": {
        "default": {
            "type": "set",
            "handlers": [
                "squadcast"
            ]
        }
    }
}
```

Now you can assign this handler to any of your checks, for example:
`/etc/sensu/conf.d/YOUR-CHECK.json`

```json
{
    "checks": {
        "YOUR-CHECK-NAME": {
            "command": "YOUR-CHECK-COMMAND",
            "subscribers": [
                "YOUR-SUBSCRIBERS"
            ],
            "interval": YOUR-INTERVAL,
            "handlers": ["default", "squadcast"]
        }
    }
}
```

Restart Sensu for the changes to take effect.

That's it!! Your Sensu integration is now good to go.

Once an event is resolved from Sensu, it will automatically be resolved in Squadcast.