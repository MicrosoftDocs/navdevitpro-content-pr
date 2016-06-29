<properties
                pageTitle="Understanding Session Timeouts | Dynamics NAV"
                description="Describes use finsql.exe,"
                services=""
                documentationCenter="Madeira"
                authors="jswymer"/>
<tags
    ms.service="dynamics-nav"
    ms.topic="article"
    ms.devlang="na"
    ms.tgt_pltfrm="na"
    ms.workload="NAV"
    ms.date="06/16/2016"
    ms.author="jswymer" />

# Understanding Session Timeouts
When you start the Dynamics NAV Windows client or Dynamics NAV Web client, a connection is established with the Dynamics NAV Server instance, and a corresponding session is added on Dynamics NAV Server.

Dynamics NAV Server includes several timeout settings that determine when a session closes as a result of inactivity over the client connection, lost client connection, or closing of the client. To help you configure the timeout settings, this article provides an overview of how the session timeouts work and answers some basic questions about session behavior.

## Session Timeout Settings Overview
This section provides an overview of the settings that are available in Dynamics NAV to control when a Dynamics NAV Server session for a Dynamics NAV client connection times out and closes. Some of the settings are set on Dynamics NAV Server and others are set for the Dynamics NAV Windows client or for the Dynamics NAV Web client. For more details about using these settings, see the other sections in this article.

## Dynamics NAV Server timeout settings
The following table describes the session timeout settings that are used by Dynamics NAV Server.

|  Setting  |  Description  |  Remarks  |
|-----------|---------------|-----------|  
|  ClientServicesReconnectPeriod | The amount of time during which a client can reconnect to an existing session on Dynamics NAV Server before a session closes.|For more information, see [Configuring how long a session remains open after the Client connection is lost](#configuring-how-long-a-session-remains-open-after-the-client-connection-is-lost.md)|
|  ClientServicesIdleClientTimeout | The interval of time that a Dynamics NAV client connection can remain inactive before the session is closed.  |For more information, see [Configuring how long a session remains open when the client connection is inactive](#configuring-how-long-a-session-remains-open-when-the-client-connection-is-inactive.md)|
|  ClientServicesKeepAliveInterval | Specifies the interval (in seconds) between keep-alive messages that are sent from the  Dynamics NAV Windows client to Dynamics NAV Server. |This setting is also used, in part, to define the reconnect period when a connection is lost. For more information, see [Keeping inactive sessions alive](#keeping-inactive-sessions-alive.md).|

These settings are available in the CustomSettings.config file of Microsoft Dynamics NAV Server. For more information about this file, see [Configuring Microsoft Dynamics NAV](navserver_configuring.md).


## Dynamics NAV Web client timeout settings
The following table describes the session timeout settings that are used by the Microsoft Dynamics NAV Web client.

|  Setting  |  Description  |  Remarks  |
|-----------|---------------|-----------|  
|  SessionTimeout | Specifies the amount of time that session remains open when there is no activity over the connection from the Dynamics NAV Web client to Dynamics NAV Server.|For more information, see [Configuring how long a session remains open when the Client connection is inactive](#configuring-how-long-a-session-remains-open-when-the-client-connection-is-inactive.md).|

This setting is available in the web.config file of Dynamics Web Server for the client. For more information about this file, see [Configuring the Dynamics NAV Web Server and Client](navwebserver_configuring.md).

## Configuring how long a session remains open when the client connection is inactive
Inactivity on a connection is when the Dynamics NAV client is not sending messages to Dynamics NAV Server. Controlling when a session will timeout and close because of inactivity is different for the Dynamics NAV Windows client and the Dynamics NAV Web client.

## Configuring the inactive session timeout for the Dynamics NAV Windows client
When the Dynamics NAV Windows client is inactive, the session will remain open until the time period that is specified by the ClientServicesIdleClientTimeout setting has passed, provided that the client has not been stopped or the connection to Dynamics NAV Server has not been lost. The default value of the ClientServicesIdleClientTimeout setting is MaxValue, which means that there is no time limit so the session will remain active indefinitely.

## Configuring the inactive session timeout for the Microsoft Dynamics NAV Web client
There are two settings that control when a Web client session closes because of inactivity on a connection:
-   ClientServicesIdleClientTimeout setting on Dynamics NAV Server.
-   SessionTimeout setting on the Dynamics NAV Web Server.

The session closes according to the setting that has the shortest time period. By default, the ClientServicesIdleClientTimeout setting is set to MaxValue, which means no time limit, and the SessionTimout setting is 00:20:00 (20 minutes). This means that when client connection is inactive, a session will close after 20 minutes. The following figure illustrates the timeout behavior:

![Descriptive name](http://../images/NAV_timeout_behavior.md)

The SessionTimeout setting enables you to set the Dynamics NAV Web client inactive session timeout different than for the Dynamics NAV Windows client, which is only controlled by the ClientServicesIdleClientTimeout setting. Typically, you will set the inactive session timeout period on Dynamics NAV Web client connections shorter than for the Dynamics NAV Windows client.

## Keeping inactive sessions alive
To keep an inactive Dynamics NAV Windows client session alive, Dynamics NAV uses the Windows Communication Framework (WCF) reliable sessions feature. When the Dynamics NAV Windows client is inactive, reliable sessions automatically sends messages from the Dynamics NAV Windows client to Dynamics NAV Server. You control the interval of the keep-alive messages by setting the ClientServicesKeepAliveInterval setting on the Dynamics NAV Server instance. The default value of the ClientServicesKeepAliveInterval setting is 120 seconds (2 minutes).

For most installations, the ClientServicesKeepAliveInterval setting default value sufficient for keeping sessions open until the ClientServicesIdleClientTimeout setting period elapses. However, when Dynamics NAV Server is installed behind a load balancer, which is the case on Microsoft Azure, you might have to adjust the value the ClientServicesKeepAliveInterval setting to prevent sessions from closing before the expected session timeout. A load balancer typically has an idle timeout setting that it uses to determine whether to redirect connections. However, you want a stable connection between the Dynamics NAV Windows client and Dynamics NAV Server. If there is no activity on the client connection for duration of the load balancer's idle timeout setting, then the load balancer might redirect the client connection to another server. To avoid this condition, we recommend that you set the ClientServicesKeepAliveInterval to half the value of the load balancer’s idle timeout setting.

**Note:** The idle timeout on Azure is around 4 minutes, so the default setting of ClientServicesKeepAliveInterval (2 minutes) should be sufficient.

## Configuring how long a session remains open after the client connection is lost
Occasionally, a Dynamics NAV client can lose the network connection to Dynamics NAV Server. You can use ClientServicesReconnectPeriod setting on Dynamics NAV Server to control how long a session remains open after the connection is lost to allow time for the client to reconnect to the session.

The time a session remains open actually depends two settings: ClientServiceKeepAliveInterval and ClientServicesReconnectPeriod. The ClientServiceKeepAliveInterval setting is used to specify an initial inactivity period. The initial inactivity period is equal to two times the ClientServiceKeepAliveInterval setting value. After this initial inactivity period, the session remains open for the time period that is specified ClientServicesReconnectPeriod setting. By default, the ClientServiceKeepAliveInterval setting is 120 seconds (2 minutes) and the ClientServicesReconnectPeriod setting is 10 minutes. This means that Dynamics NAV Server waits approximately 14 minutes for the client to reconnect before closing the session.

The following figure illustrates the reconnect session timeout behavior:

![Descriptive name](http://../images/NAV_reconnect_session_timeout_behavior.png)

The process that occurs when a client does not reconnect to the session is explained as follows:

The connection is lost and the initial inactivity period starts (default is 4 minutes).

After the initial inactivity period, the service channel enters a faulted state.
When the service channel is in the faulted state, Microsoft Dynamics NAV Server considers the session with the client as orphaned and waits for it to reconnect.

If the client does not reconnect within the time period that is specified by the ClientServicesReconnectPeriod setting (default is 10 minutes), then Microsoft Dynamics NAV Server closes the session.

The session is then removed from the Active Session table in the Microsoft Dynamics NAV.

## FAQ
This section answers some typical questions about session timeout.

### How long does Microsoft Dynamics NAV Server wait when the Microsoft Dynamics NAV Windows client is inactive before closing a session?
With Microsoft Dynamics NAV Windows client, by default, Microsoft Dynamics NAV Server will wait indefinitely as long as the client has not been stopped or the connection to Microsoft Dynamics NAV Server has not been lost. With the Microsoft Dynamics NAV Web client, the session will remain active for 20 minutes. The Microsoft Dynamics NAV Windows client and Microsoft Dynamics NAV Web client include configuration settings that you can use to change the inactivity timeout period. For more information, see [Configuring How Long a Session Remains Open When the Client Connection is Inactive](#configuring-how-long-a-session-remains-open-when-the-client-connection-is-inactive.md).

### What happens to the session if I end the Dynamics NAV Windows client by using Task Manager?
If the Dynamics NAV Windows client is waiting for a response from Dynamics NAV Server, as is the case with a modal dialog, then the session remains open until the time period that is specified by the ClientServicesReconnectPeriod setting expires. When the Window Client process is ended, the service channel will enter a faulted state. Dynamics NAV Server considers the session with the Dynamics NAV client as orphaned and waits for it to reconnect.

### What happens to the session if the client loses the connection to Dynamics NAV Server?
By default, it will take approximately 14 minutes for the Dynamics NAV Server to close the current session. The time it takes to close the session is in part determined by the ClientServicesReconnectPeriod setting on  Dynamics NAV Server plus an initial 10 minute inactivity period. For more information, see [Configuring How Long a Session Remains Open after the Client Connection is Lost](#configuring-how-long-a-session-remains-open-after-the-client-connection-is-lost.md).

### What happens if the session is still active when Dynamics NAV Server tries to close it?
1.  The server stops any executing threads when the next statement is to be executed and the current call stack is aborted so any uncommitted transactions will be rolled back.
2.  The server cancels any callbacks to the client (similar to waiting for the response to a Confirm dialog).
3.  The session is closed, and then removed from the Active Session table.

## See Also  
[Configuring Microsoft Dynamics NAV](navserver_configuring.md)  
