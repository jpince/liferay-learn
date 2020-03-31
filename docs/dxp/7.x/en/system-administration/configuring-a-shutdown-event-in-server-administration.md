# Configuring a Shutdown Event in Server Administration

In addition to a system-defined message, Liferay DXP displays the message you define at the top of users' pages once you save the configuration until the expiration happens. When time expires, all pages display a message saying the portal has been shut down. The server must then be restarted to restore access. 

## Adding a Shutdown Event

To add a shutdown event, first enable the Inactive Request Handler configuration in system Settings:

1. Navigate to Control Panel &rarr; Configuration &rarr; System Settings, and search for _Inactive Request Handler_.

1. Enable _Show Inactive Request Message_ and click _Save_.

This enables display of a message to Users that try to navigate somewhere in Liferay DXP after the shutdown happens. Without, they'll have the unfriendly experience of seeing a totally blank page.

Now configure the shutdown itself:

1. Navigate to Control Panel &rarr; Configuration &rarr; Server Administration, and click the _Shutdown_ tab.

1. Enter the time (in minutes) until the shutdown will occur.

1. Enter a special message. Whatever you enter will be appended to the system default message:

   ```bash
   Maintenance Alert 4:48 PM EST The portal will shutdown for maintenance in 5 minute(s). You will automatically be signed out at that time. Please finish any work in progress. After the maintenance has been completed, you will be able to successfully sign in. [YOUR MESSAGE DISPLAYS HERE]
   ```

   In addition, this message is what Users will see if they navigate to a portal page after the shutdown (because you enabled the _Show Inactive Request Message_ setting)..

1. Click _Save_. The countdown to the shutdown event begins immediately.

![The time until shutdown and the warning message are configurable in the Shutdown tab.](./using-the-server-administration-panel/images/01.png)

Right away, all logged in Users see the system message and your appended custom message at the top of the page.

![Users are showed a warning about the impending shutdown.](./using-the-server-administration-panel/images/03.png)

Once the time has expired, logged in Users trying to navigate to a page in Liferay DXP see this:

![Your custom message is displayed to Users after the shutdown.](./using-the-server-administration-panel/images/02.png)

## Canceling a Shutdown Event

At any time before the shutdown has occurred, you can cancel it.

1. Navigate to Control Panel &rarr; Configuration &rarr; Server Administration, and click the _Shutdown_ tab.

   If a shutdown event is scheduled, you can only do one thing: cancel it.

1. Click _Cancel Shutdown_.

Now the scheduled shutdown messages disappear and the portal functions as as usual.