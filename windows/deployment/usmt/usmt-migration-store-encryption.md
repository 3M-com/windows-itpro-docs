---
title: Migration Store Encryption (Windows 10)
description: Learn how the User State Migration Tool (USMT) enables support for stronger encryption algorithms, called Advanced Encryption Standard (AES).
ms.reviewer: 
manager: dougeby
ms.author: aaroncz
ms.prod: windows-client
author: aczechowski
ms.date: 04/19/2017
ms.topic: article
ms.technology: itpro-deploy
---

# Migration Store Encryption

This topic discusses User State Migration Tool (USMT) 10.0 options for migration store encryption to protect the integrity of user data during a migration.

## USMT Encryption Options

USMT enables support for stronger encryption algorithms, called Advanced Encryption Standard (AES), in several bit-level options. AES is a National Institute of Standards and Technology (NIST) specification for the encryption of electronic data.

The encryption algorithm you choose must be specified for both the **ScanState** and the **LoadState** commands, so that these commands can create or read the store during encryption and decryption. The new encryption algorithms can be specified on the **ScanState** and the **LoadState** command lines by using the **/encrypt**:*"encryptionstrength"* and the **/decrypt**:*"encryptionstrength"* command-line options. All of the encryption application programming interfaces (APIs) used by USMT are available in Windows 7, Windows 8, and Windows 10 operating systems. However, export restrictions might limit the set of algorithms that are available to computers in certain locales. You can use the Usmtutils.exe file to determine which encryption algorithms are available to the computers' locales before you begin the migration.

The following table describes the command-line encryption options in USMT.

|Component|Option|Description|
|--- |--- |--- |
|**ScanState**|**/encrypt**<*AES, AES_128, AES_192, AES_256, 3DES, 3DES_112*>|This option and argument specify that the migration store is encrypted and which algorithm to use. When the algorithm argument is not provided, the **ScanState** tool employs the 3DES algorithm.|
|**LoadState**|**/decrypt**<*AES, AES_128, AES_192, AES_256, 3DES, 3DES_112*>|This option and argument specify that the store must be decrypted and which algorithm to use. When the algorithm argument is not provided, the **LoadState** tool employs the 3DES algorithm.|

**Important**  
Some encryption algorithms may not be available on your systems. You can verify which algorithms are available by running the UsmtUtils command with the **/ec** option. For more information see [UsmtUtils Syntax](usmt-utilities.md)

## Related topics

[Plan Your Migration](usmt-plan-your-migration.md)
