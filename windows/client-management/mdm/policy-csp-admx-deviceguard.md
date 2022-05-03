---
title: Policy CSP - ADMX_DeviceGuard
description: Policy CSP - ADMX_DeviceGuard
ms.author: dansimp
ms.localizationpriority: medium
ms.topic: article
ms.prod: w10
ms.technology: windows
author: dansimp
ms.date: 09/08/2021
ms.reviewer: 
manager: dansimp
---

# Policy CSP - ADMX_DeviceGuard

> [!TIP]
> This is an ADMX-backed policy and requires a special SyncML format to enable or disable.  For details, see [Understanding ADMX-backed policies](./understanding-admx-backed-policies.md).
> 
> You must specify the data type in the SyncML as &lt;Format&gt;chr&lt;/Format&gt;. For an example SyncML, refer to [Enabling a policy](./understanding-admx-backed-policies.md#enabling-a-policy).
> 
> The payload of the SyncML must be XML-encoded; for this XML encoding, there are a variety of online encoders that you can use. To avoid encoding the payload, you can use CDATA if your MDM supports it.  For more information, see [CDATA Sections](http://www.w3.org/TR/REC-xml/#sec-cdata-sect).

<hr/>

<!--Policies-->
## ADMX_DeviceGuard policies  

<dl>
  <dd>
    <a href="#admx-deviceguard-configcipolicy">ADMX_DeviceGuard/ConfigCIPolicy</a>
  </dd>
</dl>


<hr/>

<!--Policy-->
<a href="" id="admx-deviceguard-configcipolicy"></a>**ADMX_DeviceGuard/ConfigCIPolicy**  

<!--SupportedSKUs-->

|Edition|Windows 10|Windows 11|
|--- |--- |--- |
|Home|No|No|
|Pro|No|No|
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
This policy setting lets you deploy a Code Integrity Policy to a machine to control what is allowed to run on that machine.  

If you deploy a Code Integrity Policy, Windows will restrict what can run in both kernel mode and on the Windows Desktop based on the policy. 

To enable this policy, the machine must be rebooted.  
The file path must be either a UNC path (for example, `\\ServerName\ShareName\SIPolicy.p7b`),
or a locally valid path (for example, `C:\FolderName\SIPolicy.p7b)`. 
 
The local machine account (LOCAL SYSTEM) must have access permission to the policy file.    
If using a signed and protected policy, then disabling this policy setting doesn't remove the feature from the computer. Instead, you must either:  
1. First update the policy to a non-protected policy and then disable the setting.  
2. Disable the setting and then remove the policy from each computer, with a physically present user.

<!--/Description-->

<!--ADMXBacked-->
ADMX Info:  
-   GP Friendly name: *Deploy Windows Defender Application Control*
-   GP name: *ConfigCIPolicy*
-   GP path: *Windows Components/DeviceGuard!DeployConfigCIPolicy*
-   GP ADMX file name: *DeviceGuard.admx*

<!--/ADMXBacked-->
<!--/Policy-->


<!--/Policies-->

