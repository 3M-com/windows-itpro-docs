---
title: TenantRestrictions Policy CSP
description: Learn more about the TenantRestrictions Area in Policy CSP
author: vinaypamnani-msft
manager: aaroncz
ms.author: vinpa
ms.date: 11/02/2022
ms.localizationpriority: medium
ms.prod: windows-client
ms.technology: itpro-manage
ms.topic: reference
---

<!-- Auto-Generated CSP Document -->

<!-- TenantRestrictions-Begin -->
# Policy CSP - TenantRestrictions

<!-- TenantRestrictions-Editable-Begin -->
<!-- Add any additional information about this policy here. Anything outside this section will get overwritten. -->
<!-- TenantRestrictions-Editable-End -->

<!-- ConfigureTenantRestrictions-Begin -->
## ConfigureTenantRestrictions

<!-- ConfigureTenantRestrictions-Applicability-Begin -->
| Scope | Editions | Applicable OS |
|:--|:--|:--|
| :heavy_check_mark: Device <br> :x: User | :x: Home <br> :heavy_check_mark: Pro <br> :heavy_check_mark: Enterprise <br> :heavy_check_mark: Education <br> :heavy_check_mark: Windows SE | :heavy_check_mark: Unknown [10.0.20348.320] and later <br> :heavy_check_mark: Windows 10, version 2004 [10.0.19041.1320] and later <br> :heavy_check_mark: Windows 10, version 2009 [10.0.19042.1320] and later <br> :heavy_check_mark: Windows 10, version 21H1 [10.0.19043.1320] and later <br> :heavy_check_mark: Windows 10, version 21H2 [10.0.19044] and later <br> :heavy_check_mark: Windows 11, version 21H2 [10.0.22000] and later |
<!-- ConfigureTenantRestrictions-Applicability-End -->

<!-- ConfigureTenantRestrictions-OmaUri-Begin -->
```Device
./Device/Vendor/MSFT/Policy/Config/TenantRestrictions/ConfigureTenantRestrictions
```
<!-- ConfigureTenantRestrictions-OmaUri-End -->

<!-- ConfigureTenantRestrictions-Description-Begin -->
This setting enables and configures the device-based tenant restrictions feature for Azure Active Directory.

When you enable this setting, compliant applications will be prevented from accessing disallowed tenants, according to a policy set in your Azure AD tenant.

Note: Creation of a policy in your home tenant is required, and additional security measures for managed devices are recommended for best protection. Refer to Azure AD Tenant Restrictions for more details.

https://go.microsoft.com/fwlink/?linkid=2148762

Before enabling firewall protection, ensure that a Windows Defender Application Control (WDAC) policy that correctly tags applications has been applied to the target devices. Enabling firewall protection without a corresponding WDAC policy will prevent all applications from reaching Microsoft endpoints. This firewall setting is not supported on all versions of Windows - see the following link for more information.
For details about setting up WDAC with tenant restrictions, see https://go.microsoft.com/fwlink/?linkid=2155230
<!-- ConfigureTenantRestrictions-Description-End -->

<!-- ConfigureTenantRestrictions-Editable-Begin -->
<!-- Add any additional information about this policy here. Anything outside this section will get overwritten. -->
<!-- ConfigureTenantRestrictions-Editable-End -->

<!-- ConfigureTenantRestrictions-DFProperties-Begin -->
**Description framework properties**:

| Property name | Property value |
|:--|:--|
| Format | chr (string) |
| Access Type | Add, Delete, Get, Replace |
<!-- ConfigureTenantRestrictions-DFProperties-End -->

<!-- ConfigureTenantRestrictions-AdmxBacked-Begin -->
**ADMX mapping**:

| Name | Value |
|:--|:--|
| Name | trv2_payload |
| Friendly Name | Cloud Policy Details |
| Location | Computer Configuration |
| Path | Windows Components > Tenant Restrictions |
| Registry Key Name | SOFTWARE\Policies\Microsoft\Windows\TenantRestrictions\Payload |
| ADMX File Name | TenantRestrictions.admx |
<!-- ConfigureTenantRestrictions-AdmxBacked-End -->

<!-- ConfigureTenantRestrictions-Examples-Begin -->
<!-- Add any examples for this policy here. Examples outside this section will get overwritten. -->
<!-- ConfigureTenantRestrictions-Examples-End -->

<!-- ConfigureTenantRestrictions-End -->

<!-- TenantRestrictions-CspMoreInfo-Begin -->
<!-- Add any additional information about this CSP here. Anything outside this section will get overwritten. -->
<!-- TenantRestrictions-CspMoreInfo-End -->

<!-- TenantRestrictions-End -->

## Related articles

[Policy configuration service provider](policy-configuration-service-provider.md)
