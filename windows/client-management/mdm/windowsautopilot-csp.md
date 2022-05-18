---
title: WindowsAutoPilot CSP
description: Learn how without the ability to mark a device as remediation required, the device will remain in a broken state, which results in security and privacy concerns in Autopilot.
ms.reviewer: 
manager: dansimp
ms.author: v-nsatapathy
ms.topic: article
ms.prod: w10
ms.technology: windows
author: dansimp
ms.date: 02/07/2022
---

# WindowsAutoPilot CSP

> [!WARNING]
> Some information relates to prereleased product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.


The WindowsAutopilot CSP collects hardware information about a device and formats it into a BLOB. This BLOB is used as input for calling Windows Autopilot Service to mark a device as remediation required if the device underwent a hardware change that affects its ability to use Windows Autopilot.” with “The WindowsAutopilot CSP exposes Windows Autopilot related device information.” Because the CSP description should be more general/high level.

**./Vendor/MSFT/WindowsAutopilot**

Root node. Supported operation is Get.

**HardwareMismatchRemediationData**

Interior node. Supported operation is Get. Collects hardware information about a device and returns it as an encoded string. This string is used as input for calling Windows Autopilot Service to remediate a device if the device underwent a hardware change that affects its ability to use Windows Autopilot.
