---
title: Policy CSP - ADMX_Radar
description: Policy CSP - ADMX_Radar
ms.author: dansimp
ms.localizationpriority: medium
ms.topic: article
ms.prod: w10
ms.technology: windows
author: dansimp
ms.date: 12/08/2020
ms.reviewer: 
manager: dansimp
---

# Policy CSP - ADMX_Radar

<hr/>

<!--Policies-->
## ADMX_Radar policies  

> [!TIP]
> This is an ADMX-backed policy and requires a special SyncML format to enable or disable. For details, see [Understanding ADMX-backed policies](./understanding-admx-backed-policies.md).
> 
> You must specify the data type in the SyncML as &lt;Format&gt;chr&lt;/Format&gt;. For an example SyncML, refer to [Enabling a policy](./understanding-admx-backed-policies.md#enabling-a-policy).
> 
> The payload of the SyncML must be XML-encoded; for this XML encoding, there are a variety of online encoders that you can use. To avoid encoding the payload, you can use CDATA if your MDM supports it. For more information, see [CDATA Sections](http://www.w3.org/TR/REC-xml/#sec-cdata-sect).

<dl>
  <dd>
    <a href="#admx-radar-wdiscenarioexecutionpolicy">ADMX_Radar/WdiScenarioExecutionPolicy</a>
  </dd>
</dl>


<hr/>

<!--Policy-->
<a href="" id="admx-radar-wdiscenarioexecutionpolicy"></a>**ADMX_Radar/WdiScenarioExecutionPolicy**  

<!--SupportedSKUs-->

|Edition|Windows 10|Windows 11|
|--- |--- |--- |
|Home|No|No|
|Pro|No|No|
|Windows SE|No|No|
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
This policy determines the execution level for Windows Resource Exhaustion Detection and Resolution.  

- If you enable this policy setting, you must select an execution level from the dropdown menu. If you select problem detection and troubleshooting only, the Diagnostic Policy Service (DPS) will detect Windows Resource Exhaustion problems and attempt to determine their root causes.

These root causes will be logged to the event log when detected, but no corrective action will be taken. If you select detection, troubleshooting and resolution, the DPS will detect Windows Resource Exhaustion problems and indicate to the user that assisted resolution is available.  

- If you disable this policy setting, Windows won't be able to detect, troubleshoot or resolve any Windows Resource Exhaustion problems that are handled by the DPS.

If you don't configure this policy setting, the DPS will enable Windows Resource Exhaustion for resolution by default.  
This policy setting takes effect only if the diagnostics-wide scenario execution policy isn't configured.  No system restart or service restart is required for this policy to take effect: changes take effect immediately. This policy setting will only take effect when the Diagnostic Policy Service is in the running state. When the service is stopped or disabled, diagnostic scenarios won't be executed. The DPS can be configured with the Services snap-in to the Microsoft Management Console.

<!--/Description-->

<!--ADMXBacked-->
ADMX Info:  
-   GP Friendly name: *Configure Scenario Execution Level*
-   GP name: *WdiScenarioExecutionPolicy*
-   GP path: *System\Troubleshooting and Diagnostics\Windows Resource Exhaustion Detection and Resolution*
-   GP ADMX file name: *Radar.admx*

<hr/>

<!--/ADMXBacked-->
<!--/Policy-->

<!--/Policies-->

