---
title: Identify Operating System Settings (Windows 10)
description: Identify which system settings you want to migrate, then use the User State Migration Tool (USMT) to select settings and keep the default values for all others.
ms.reviewer: 
manager: dougeby
ms.author: aaroncz
ms.prod: windows-client
author: aczechowski
ms.date: 04/19/2017
ms.topic: article
ms.technology: itpro-deploy
---

# Identify Operating System Settings


When planning for your migration, you should identify which operating system settings you want to migrate and to what extent you want to create a new standard environment on each of the computers. User State Migration Tool (USMT) 10.0 enables you to migrate select settings and keep the default values for all others. The operating system settings include the following parameters:

-   **Appearance.**

    The appearance factor includes items such as wallpaper, colors, sounds, and the location of the taskbar.

-   **Action.**

    The action factor includes items such as the key-repeat rate, whether double-clicking a folder opens it in a new window or the same window, and whether you need to single-click or double-click an item to open it.

-   **Internet.**

    The Internet factor includes the settings that let you connect to the Internet and control how your browser operates. The settings include items such as your home page URL, favorites, bookmarks, cookies, security settings, dial-up connections, and proxy settings.

-   **Mail.**

    The mail factor includes the information that you need to connect to your mail server, your signature file, views, mail rules, local mail, and contacts.

To help you decide which settings to migrate, you should consider any previous migration experiences and the results of any surveys and tests that you have conducted. You should also consider the number of help-desk calls related to operating-system settings that you have had in the past, and are able to handle in the future. Also decide how much of the new operating-system functionality you want to take advantage of.

You should migrate any settings that users need to get their jobs done, those settings that make the work environment comfortable, and those settings that will reduce help-desk calls after the migration. Although it is easy to dismiss migrating user preferences, you should consider the factor of users spending a significant amount of time restoring items such as wallpaper, screen savers, and other customizable user-interface features. Most users do not remember how these settings were applied. Although these items are not critical to migration success, migrating these items increases user productivity and overall satisfaction of the migration process.

**Note**  
For more information about how to change the operating-system settings that are migrated, see [User State Migration Tool (USMT) How-to topics](usmt-how-to.md).

For information about the operating-system settings that USMT migrates, see [What Does USMT Migrate?](usmt-what-does-usmt-migrate.md)

 

## Related topics


[Determine What to Migrate](usmt-determine-what-to-migrate.md)

 

 





