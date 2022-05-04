---
title: DMSessionActions CSP
description: Learn how the DMSessionActions configuration service provider (CSP) is used to manage the number of sessions the client skips if the device is in a low-power state.
ms.author: dansimp
ms.topic: article
ms.prod: w10
ms.technology: windows
author: dansimp
ms.date: 06/26/2017
ms.reviewer: 
manager: dansimp
---

# DMSessionActions CSP


The DMSessionActions configuration service provider (CSP) is used to manage:  

- the number of sessions the client skips if the device is in a low-power state
- which CSP nodes should send an alert back to the server if there were any changes.

This CSP was added in Windows 10, version 1703.

The following example shows the DMSessionActions configuration service provider in tree format.
```
./User/Vendor/MSFT
DMSessionActions
----ProviderID
--------CheckinAlertConfiguration
------------Nodes
----------------NodeID
--------------------NodeURI
--------AlertData
--------PowerSettings
------------MaxSkippedSessionsInLowPowerState
------------MaxTimeSessionsSkippedInLowPowerState


./Device/Vendor/MSFT
DMSessionActions
----ProviderID
--------CheckinAlertConfiguration
------------Nodes
----------------NodeID
--------------------NodeURI
--------AlertData
--------PowerSettings
------------MaxSkippedSessionsInLowPowerState
------------MaxTimeSessionsSkippedInLowPowerState


./User/Vendor/MSFT
./Device/Vendor/MSFT
DMSessionActions
----ProviderID
--------CheckinAlertConfiguration
------------Nodes
----------------NodeID
--------------------NodeURI
--------AlertData
--------PowerSettings
------------MaxSkippedSessionsInLowPowerState
------------MaxTimeSessionsSkippedInLowPowerState
```
<a href="" id="vendor-msft-dmsessionactions"></a>**./Device/Vendor/MSFT/DMSessionActions or ./User/Vendor/MSFT/DMSessionActions**  
<p>Defines the root node for the DMSessionActions configuration service provider.</p>

<a href="" id="providerid"></a>***ProviderID***  
<p>Group settings per device management (DM) server. Each group of settings is distinguished by the Provider ID of the server. It must be the same DM server Provider ID value that was supplied through the w7 APPLICATION configuration service provider XML during the enrollment process. Only one enterprise management server is supported, which means there should be only one ProviderID node under NodeCache. </p>

<p>Scope is dynamic. Supported operations are Get, Add, and Delete.</p>

<a href="" id="checkinalertconfiguration"></a>***ProviderID*/CheckinAlertConfiguration**  
<p>Node for the custom configuration of alerts to be sent during MDM sync session.</p>

<a href="" id="nodes"></a>***ProviderID*/CheckinAlertConfiguration/Nodes**  
<p>Required. Root node for URIs to be queried. Scope is dynamic.</p>

<p>Supported operation is Get.</p>

<a href="" id="nodeid"></a>***ProviderID*/CheckinAlertConfiguration/Nodes/*NodeID***  
<p>Required. Information about each node is stored under NodeID as specified by the server. This value must not contain a comma. Scope is dynamic.</p>

<p>Supported operations are Get, Add, and Delete.</p>

<a href="" id="nodeuri"></a>***ProviderID*/CheckinAlertConfiguration/Nodes/*NodeID*/NodeURI**  
<p>Required. The value is a complete OMA DM node URI. It can specify either an interior node or a leaf node in the device management tree. Scope is dynamic.</p>
<p>Value type is string. Supported operations are Add, Get, Replace, and Delete.</p>

<a href="" id="alertdata"></a>**AlertData**  
<p>Node to query the custom alert per server configuration</p>
<p>Value type is string. Supported operation is Get.</p>

<a href="" id="powersettings"></a>**PowerSettings**  
<p>Node for power-related configurations</p>

<a href="" id="maxskippedsessionsinlowpowerstate"></a>**PowerSettings/MaxSkippedSessionsInLowPowerState**  
<p>Maximum number of continuous skipped sync sessions when the device is in low-power state.</p>
<p>Value type is integer. Supported operations are Add, Get, Replace, and Delete.</p>

<a href="" id="maxtimesessionsskippedinlowpowerstate"></a>**PowerSettings/MaxTimeSessionsSkippedInLowPowerState**  
<p>Maximum time in minutes when the device can skip the check-in with the server if the device is in low-power state. </p>
<p>Value type is integer. Supported operations are Add, Get, Replace, and Delete.</p>
