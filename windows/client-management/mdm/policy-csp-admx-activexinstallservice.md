---
title: Policy CSP - ADMX_ActiveXInstallService
description: Policy CSP - ADMX_ActiveXInstallService
ms.author: dansimp
ms.localizationpriority: medium
ms.topic: article
ms.prod: w10
ms.technology: windows
author: manikadhiman
ms.date: 11/09/2020
ms.reviewer: 
manager: dansimp
---

# Policy CSP - ADMX_ActiveXInstallService

> [!TIP]
> This is an ADMX-backed policy and requires a special SyncML format to enable or disable. For details, see [Understanding ADMX-backed policies](./understanding-admx-backed-policies.md).
> 
> You must specify the data type in the SyncML as &lt;Format&gt;chr&lt;/Format&gt;. For an example SyncML, refer to [Enabling a policy](./understanding-admx-backed-policies.md#enabling-a-policy).
> 
> The payload of the SyncML must be XML-encoded; for this XML encoding, there are a variety of online encoders that you can use. To avoid encoding the payload, you can use CDATA if your MDM supports it. For more information, see [CDATA Sections](http://www.w3.org/TR/REC-xml/#sec-cdata-sect).


<hr/>

<!--Policies-->
## ADMX_ActiveXInstallService policies  

<dl>
  <dd>
    <a href="#admx-activexinstallservice-axisurlzonepolicies">ADMX_ActiveXInstallService/AxISURLZonePolicies</a>
  </dd>
</dl>


<hr/>

<!--Policy-->
<a href="" id="admx-activexinstallservice-axisurlzonepolicies"></a>**ADMX_ActiveXInstallService/AxISURLZonePolicies**  

<!--SupportedSKUs-->
<table>
<tr>
    <th>Edition</th>
    <th>Windows 10</th>
    <th>Windows 11</th>
<tr>
    <td>Home</td>
    <td>No</td>
    <td>No</td>
</tr>
<tr>
    <td>Pro</td>
    <td>Yes</td>
    <td>Yes</td>
</tr>
<tr>
    <td>Enterprise</td>
    <td>Yes</td>
    <td>Yes</td>
</tr>
<tr>
    <td>Education</td>
    <td>Yes</td>
    <td>Yes</td>
</table>

<!--/SupportedSKUs-->
<hr/>

<!--Scope-->
[Scope](./policy-configuration-service-provider.md#policy-scope):

> [!div class = "checklist"]
> * Device

<hr/>

<!--/Scope-->
<!--Description-->
This policy setting controls the installation of ActiveX controls for sites in Trusted zone.

If you enable this policy setting, ActiveX controls are installed according to the settings defined by this policy setting.

If you disable or do not configure this policy setting, ActiveX controls prompt the user before installation. 

If the trusted site uses the HTTPS protocol, this policy setting can also control how ActiveX Installer Service responds to certificate errors. By default all HTTPS connections must supply a server certificate that passes all validation criteria. If you are aware that a trusted site has a certificate error but you want to trust it anyway you can select the certificate errors that you want to ignore.

> [!NOTE]
> This policy setting applies to all sites in Trusted zones.

<!--/Description-->

<!--ADMXBacked-->
ADMX Info:  
-   GP Friendly name: *Establish ActiveX installation policy for sites in Trusted zones*
-   GP name: *AxISURLZonePolicies*
-   GP path: *Windows Components\ActiveX Installer Service*
-   GP ADMX file name: *ActiveXInstallService.admx*

<!--/ADMXBacked-->
<!--/Policy-->
<hr/>


<!--/Policies-->

