---
title: Policy CSP - Messaging
description: Enable, and disable, text message back up and restore as well as Messaging Everywhere by using the Policy CSP for messaging.
ms.author: dansimp
ms.topic: article
ms.prod: w10
ms.technology: windows
author: manikadhiman
ms.localizationpriority: medium
ms.date: 09/27/2019
ms.reviewer: 
manager: dansimp
---

# Policy CSP - Messaging



<hr/>

<!--Policies-->
## Messaging policies  

<dl>
  <dd>
    <a href="#messaging-allowmessagesync">Messaging/AllowMessageSync</a>
  </dd>
</dl>


<hr/>

<!--Policy-->
<a href="" id="messaging-allowmessagesync"></a>**Messaging/AllowMessageSync**  

<!--SupportedSKUs-->

|Edition|Windows 10|Windows 11|
|--- |--- |--- |
|Home|No|No|
|Pro|Yes|Yes|
|Business|No|No|
|Enterprise|Yes|Yes|
|Education|Yes|Yes|

<!--/SupportedSKUs-->
<hr/>

<!--Scope-->
[Scope](./policy-configuration-service-provider.md#policy-scope):

> [!div class = "checklist"]
> * Device

<hr/>

<!--/Scope-->
<!--Description-->
Enables text message back up and restore and Messaging Everywhere. This policy allows an organization to disable these features to avoid information being stored on servers outside of their control.

<!--/Description-->
<!--ADMXMapped-->
ADMX Info:  
-   GP Friendly name: *Allow Message Service Cloud Sync*
-   GP name: *AllowMessageSync*
-   GP path: *Windows Components/Messaging*
-   GP ADMX file name: *messaging.admx*

<!--/ADMXMapped-->
<!--SupportedValues-->
The following list shows the supported values:

-   0 - message sync is not allowed and cannot be changed by the user.
-   1 - message sync is allowed. The user can change this setting.

<!--/SupportedValues-->
<!--/Policy-->

<hr/>

<!--/Policies-->

