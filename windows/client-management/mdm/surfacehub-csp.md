---
title: SurfaceHub CSP
description: The SurfaceHub configuration service provider (CSP) is used to configure Microsoft Surface Hub settings. This CSP was added in Windows 10, version 1511.
ms.assetid: 36FBBC32-AD6A-41F1-86BF-B384891AA693
ms.reviewer: 
manager: dansimp
ms.author: dansimp
ms.topic: article
ms.prod: w10
ms.technology: windows
author: dansimp
ms.date: 07/28/2017
---

# SurfaceHub CSP

The SurfaceHub configuration service provider (CSP) is used to configure Microsoft Surface Hub settings. This CSP was added in Windows 10, version 1511, and later.

The following shows the SurfaceHub CSP management objects in tree format.
```
./Vendor/MSFT
SurfaceHub
----DeviceAccount
--------DomainName
--------UserName
--------UserPrincipalName
--------Password
--------ValidateAndCommit
--------ExchangeServer
--------SipAddress
--------Email
--------CalendarSyncEnabled
--------ErrorContext
--------PasswordRotationPeriod
----MaintenanceHoursSimple
--------Hours
------------StartTime
------------Duration
----InBoxApps
--------SkypeForBusiness
------------DomainName
--------Welcome
------------AutoWakeScreen
------------CurrentBackgroundPath
------------MeetingInfoOption
--------Whiteboard
------------SharingDisabled
------------SigninDisabled
------------TelemeteryDisabled
--------WirelessProjection
------------PINRequired
------------Enabled
------------Channel
--------Connect
------------AutoLaunch
----Properties
--------FriendlyName
--------DefaultVolume
--------ScreenTimeout
--------SessionTimeout
--------SleepTimeout
--------AllowSessionResume
--------AllowAutoProxyAuth
--------ProxyServers
--------DisableSigninSuggestions
--------DoNotShowMyMeetingsAndFiles
----Management
--------GroupName
--------GroupSid
----MOMAgent
--------WorkspaceID
--------WorkspaceKey
```
<a href="" id="--vendor-msft-surfacehub"></a>**./Vendor/MSFT/SurfaceHub**  
<p>The root node for the Surface Hub configuration service provider.

<a href="" id="deviceaccount"></a>**DeviceAccount**
<p>Node for setting device account information. A device account is a Microsoft Exchange account that is connected with Skype for Business, which allows people to join scheduled meetings, make Skype for Business calls, and share content from the device. See the Surface Hub administrator guide for more information about setting up a device account.

<p>To use a device account from Azure Active Directory

1. Set the UserPrincipalName (for Azure AD).
2. Set a valid Password.
3. Execute ValidateAndCommit to validate the specified username and password combination against Azure AD.
4. Get the ErrorContext in case something goes wrong during validation.

> [!NOTE]
> If the device cannot auto-discover the Exchange server and Session Initiation Protocol (SIP) address from this information, you should specify the ExchangeServer and SipAddress.


<p>Here&#39;s a SyncML example.

```xml
<SyncML xmlns="SYNCML:SYNCML1.2">
    <SyncBody>
        <Replace>
            <CmdID>1</CmdID>
            <Item>
                <Target>
                    <LocURI>./Vendor/MSFT/SurfaceHub/DeviceAccount/UserPrincipalName</LocURI>
                </Target>
                <Meta>
                    <Format xmlns="syncml:metinf">chr</Format>
                </Meta>
                <Data>user@contoso.com</Data>
            </Item>
        </Replace>
        <Replace>
            <CmdID>2</CmdID>
            <Item>
                <Target>
                    <LocURI>./Vendor/MSFT/SurfaceHub/DeviceAccount/Password</LocURI>
                </Target>
                <Meta>
                    <Format xmlns="syncml:metinf">chr</Format>
                </Meta>
                <Data>password</Data>
            </Item>
        </Replace>
        <Exec>
            <CmdID>3</CmdID>
            <Item>
                <Target>
                    <LocURI>./Vendor/MSFT/SurfaceHub/DeviceAccount/ValidateAndCommit</LocURI>
                </Target>
            </Item>
        </Exec>
        <Get>
            <CmdID>4</CmdID>
            <Item>
                <Target>
                    <LocURI>./Vendor/MSFT/SurfaceHub/DeviceAccount/ErrorContext</LocURI>
                </Target>
            </Item>
        </Get>
        <Final/>
    </SyncBody>
</SyncML>
```

<p>To use a device account from Active Directory

1. Set the DomainName.
2. Set the UserName.
3. Set a valid Password.
4. Execute the ValidateAndCommit node.

<a href="" id="deviceaccount-domainname"></a>**DeviceAccount/DomainName**
<p>Domain of the device account when you are using Active Directory. To use a device account from Active Directory, you should specify both DomainName and UserName for the device account.

<p>The data type is string. Supported operation is Get and Replace.

<a href="" id="deviceaccount-username"></a>**DeviceAccount/UserName**
<p>Username of the device account when you are using Active Directory. To use a device account from Active Directory, you should specify both DomainName and UserName for the device account.

<p>The data type is string. Supported operation is Get and Replace.

<a href="" id="deviceaccount-userprincipalname"></a>**DeviceAccount/UserPrincipalName**
<p>User principal name (UPN) of the device account. To use a device account from Azure Active Directory or a hybrid deployment, you should specify the UPN of the device account.

<p>The data type is string. Supported operation is Get and Replace.

<a href="" id="deviceaccount-sipaddress"></a>**DeviceAccount/SipAddress**
<p>Session Initiation Protocol (SIP) address of the device account. Normally, the device will try to auto-discover the SIP. This field is only required if auto-discovery fails.

<p>The data type is string. Supported operation is Get and Replace.

<a href="" id="deviceaccount-password"></a>**DeviceAccount/Password**
<p>Password for the device account.

<p>The data type is string. Supported operation is Get and Replace. The operation Get is allowed, but it will always return a blank.

<a href="" id="deviceaccount-validateandcommit"></a>**DeviceAccount/ValidateAndCommit**
<p>This method validates the data provided and then commits the changes.

<p>The data type is string. Supported operation is Execute.

<a href="" id="deviceaccount-email"></a>**DeviceAccount/Email**
<p>Email address of the device account.

<p>The data type is string.

<a href="" id="deviceaccount-passwordrotationenabled"></a>**DeviceAccount/PasswordRotationEnabled**
<p>Specifies whether automatic password rotation is enabled. If you enforce a password expiration policy on the device account, use this setting to allow the device to manage its own password by changing it frequently, without requiring you to manually update the account information when the password expires. You can reset the password at any time using Active Directory (or Azure AD).

<p>Valid values:

- 0 - password rotation enabled
- 1 - disabled

<p>The data type is integer. Supported operation is Get and Replace.

<a href="" id="deviceaccount-exchangeserver"></a>**DeviceAccount/ExchangeServer**
<p>Exchange server of the device account. Normally, the device will try to auto-discover the Exchange server. This field is only required if auto-discovery fails.

<p>The data type is string. Supported operation is Get and Replace.

<a href="" id="deviceaccount-exchangemodernauthenabled"></a>**DeviceAccount/ExchangeModernAuthEnabled**
<p>Added in <a href="https://support.microsoft.com/en-us/topic/february-2-2021-kb4598291-os-builds-19041-789-and-19042-789-preview-6a766199-a4f1-616e-1f5c-58bdc3ca5e3b" data-raw-source="[KB4598291](https://support.microsoft.com/en-us/topic/february-2-2021-kb4598291-os-builds-19041-789-and-19042-789-preview-6a766199-a4f1-616e-1f5c-58bdc3ca5e3b)">KB4598291</a> for Windows 10, version 20H2. Specifies whether Device Account calendar sync will attempt to use token-based Modern Authentication to connect to the Exchange Server. Default value is True.

<p>The data type is boolean. Supported operation is Get and Replace.

<a href="" id="deviceaccount-calendarsyncenabled"></a>**DeviceAccount/CalendarSyncEnabled**
<p>Specifies whether calendar sync and other Exchange server services is enabled.

<p>The data type is boolean. Supported operation is Get and Replace.

<a href="" id="deviceaccount-errorcontext"></a>**DeviceAccount/ErrorContext**

If there is an error calling ValidateAndCommit, there is additional context for that error in this node. Here are the possible error values:

| ErrorContext value | Stage where error occurred | Description and suggestions |
| --- | --- | --- |
| 1 | Unknown | |
| 2 | Populating account | Unable to retrieve account details using the username and password you provided.<br/><br/>-For Azure AD accounts, ensure that UserPrincipalName and Password are valid.<br/>-For AD accounts, ensure that DomainName, UserName, and Password are valid.<br/>-Ensure that the specified account has an Exchange server mailbox. |
| 3 | Populating Exchange server address | Unable to auto-discover your Exchange server address. Try to manually specify the Exchange server address using the ExchangeServer field. |
| 4 | Validating Exchange server address | Unable to validate the Exchange server address. Ensure that the ExchangeServer field is valid. |
| 5 | Saving account information | Unable to save account details to the system. |
| 6 | Validating EAS policies | The device account uses an unsupported EAS policy. Ensure the EAS policy is configured correctly according to the admin guide. |

The data type is integer. Supported operation is Get.

<a href="" id="maintenancehourssimple-hours"></a>**MaintenanceHoursSimple/Hours**

<p>Node for maintenance schedule.

<a href="" id="maintenancehourssimple-hours-starttime"></a>**MaintenanceHoursSimple/Hours/StartTime**
<p>Specifies the start time for maintenance hours in minutes from midnight. For example, to set a 2:00 am start time, set this value to 120.

<p>The data type is integer. Supported operation is Get and Replace.

<a href="" id="maintenancehourssimple-hours-duration"></a>**MaintenanceHoursSimple/Hours/Duration**
<p>Specifies the duration of maintenance window in minutes. For example, to set a 3-hour duration, set this value to 180.

<p>The data type is integer. Supported operation is Get and Replace.

<a href="" id="inboxapps"></a>**InBoxApps**
<p>Node for the in-box app settings.

<a href="" id="inboxapps-skypeforbusiness"></a>**InBoxApps/SkypeForBusiness**
<p>Added in Windows 10, version 1703. Node for the Skype for Business settings.

<a href="" id="inboxapps-skypeforbusiness-domainname"></a>**InBoxApps/SkypeForBusiness/DomainName**
<p>Added in Windows 10, version 1703. Specifies the domain of the Skype for Business account when you are using Active Directory. For more information, see <a href="/SkypeForBusiness/set-up-skype-for-business-online" data-raw-source="[Set up Skype for Business Online](/SkypeForBusiness/set-up-skype-for-business-online)">Set up Skype for Business Online</a>.

<p>The data type is string. Supported operation is Get and Replace.

<a href="" id="inboxapps-welcome"></a>**InBoxApps/Welcome**
<p>Node for the welcome screen.

<a href="" id="inboxapps-welcome-autowakescreen"></a>**InBoxApps/Welcome/AutoWakeScreen**
<p>Automatically turn on the screen using motion sensors.

<p>The data type is boolean. Supported operation is Get and Replace.

<a href="" id="inboxapps-welcome-currentbackgroundpath"></a>**InBoxApps/Welcome/CurrentBackgroundPath**
<p>Download location for image to be used as the background during user sessions and on the welcome screen. To set this, specify an https URL to a 32-bit PNG file (only PNGs are supported for security reasons). If any certificate authorities need to be trusted in order to access the URL, ensure they are valid and installed on the Hub, otherwise it may not be able to load the image.

<p>The data type is string. Supported operation is Get and Replace.

<a href="" id="inboxapps-welcome-meetinginfooption"></a>**InBoxApps/Welcome/MeetingInfoOption**
<p>Meeting information displayed on the welcome screen.

<p>Valid values:

- 0 - Organizer and time only
- 1 - Organizer, time, and subject. Subject is hidden in private meetings.

<p>The data type is integer. Supported operation is Get and Replace.

<a href="" id="inboxapps-whiteboard"></a>**InBoxApps/Whiteboard**
<p>Node for the Whiteboard app settings.

<a href="" id="inboxapps-whiteboard-sharingdisabled"></a>**InBoxApps/Whiteboard/SharingDisabled**
<p>Invitations to collaborate from the Whiteboard app are not allowed.

<p>The data type is boolean. Supported operation is Get and Replace.

<a href="" id="inboxapps-whiteboard-signindisabled"></a>**InBoxApps/Whiteboard/SigninDisabled**
<p>Sign-ins from the Whiteboard app are not allowed.

<p>The data type is boolean. Supported operation is Get and Replace.

<a href="" id="inboxapps-whiteboard-telemetrydisabled"></a>**InBoxApps/Whiteboard/TelemeteryDisabled**
<p>Telemetry collection from the Whiteboard app is not allowed.

<p>The data type is boolean. Supported operation is Get and Replace.

<a href="" id="inboxapps-wirelessprojection"></a>**InBoxApps/WirelessProjection**
<p>Node for the wireless projector app settings.

<a href="" id="inboxapps-wirelessprojection-pinrequired"></a>**InBoxApps/WirelessProjection/PINRequired**
<p>Users must enter a PIN to wirelessly project to the device.

<p>The data type is boolean. Supported operation is Get and Replace.

<a href="" id="inboxapps-wirelessprojection-enabled"></a>**InBoxApps/WirelessProjection/Enabled**
<p>Enables wireless projection to the device.

<p>The data type is boolean. Supported operation is Get and Replace.

<a href="" id="inboxapps-wirelessprojection-channel"></a>**InBoxApps/WirelessProjection/Channel**
<p>Wireless channel to use for Miracast operation. The supported channels are defined by the Wi-Fi Alliance Wi-Fi Direct specification.

|Compatibility|Values|
|--- |--- |
|Works with all Miracast senders in all regions|1, 3, 4, 5, 6, 7, 8, 9, 10, 11|
|Works with all 5ghz band Miracast senders in all regions|36, 40, 44, 48|
|Works with all 5ghz band Miracast senders in all regions except Japan|149, 153, 157, 161, 165|


<p>The default value is 255. Outside of regulatory concerns, if the channel is configured incorrectly the driver will either not boot, or will broadcast on the wrong channel (which senders won&#39;t be looking for).

<p>The data type is integer. Supported operation is Get and Replace.

<a href="" id="inboxapps-connect"></a>**InBoxApps/Connect**
<p>Added in Windows 10, version 1703. Node for the Connect app.

<a href="" id="inboxapps-welcome-autowakescreen"></a>**InBoxApps/Connect/AutoLaunch**
<p>Added in Windows 10, version 1703. Specifies whether to automatically launch the Connect app whenever a projection is initiated.

<p>If this setting is true, the Connect app will be automatically launched. If false, the user will need to launch the Connect app manually from the Hub’s settings.

<p>The data type is boolean. Supported operation is Get and Replace.

<a href="" id="properties"></a>**Properties**
<p>Node for the device properties.

<a href="" id="properties-friendlyname"></a>**Properties/FriendlyName**
<p>Friendly name of the device. Specifies the name that users see when they want to wirelessly project to the device.

<p>The data type is string. Supported operation is Get and Replace.

<a href="" id="properties-defaultvolume"></a>**Properties/DefaultVolume**
<p>Added in Windows 10, version 1703. Specifies the default volume value for a new session. Permitted values are 0-100. The default is 45.

<p>The data type is integer. Supported operation is Get and Replace.

<a href="" id="properties-screentimeout"></a>**Properties/ScreenTimeout**
<p>Added in Windows 10, version 1703. Specifies the number of minutes until the Hub screen turns off.

<p>The following table shows the permitted values.

|Value|Description|
|--- |--- |
|0|Never time out|
|1|1 minute|
|2|2 minutes|
|3|3 minutes|
|5|5 minutes (default)|
|10|10 minutes|
|15|15 minutes|
|30|30 minutes|
|60|1 hour|
|120|2 hours|
|240|4 hours|

<p>The data type is integer. Supported operation is Get and Replace.

<a href="" id="properties-sessiontimeout"></a>**Properties/SessionTimeout**
<p>Added in Windows 10, version 1703. Specifies the number of minutes until the session times out.

<p>The following table shows the permitted values.

|Value|Description|
|--- |--- |
|0|Never time out|
|1|1 minute (default)|
|2|2 minutes|
|3|3 minutes|
|5|5 minutes|
|10|10 minutes|
|15|15 minutes|
|30|30 minutes|
|60|1 hour|
|120|2 hours|
|240|4 hours|

<p>The data type is integer. Supported operation is Get and Replace.

<a href="" id="properties-sleeptimeout"></a>**Properties/SleepTimeout**
<p>Added in Windows 10, version 1703. Specifies the number of minutes until the Hub enters sleep mode.

<p>The following table shows the permitted values.

|Value|Description|
|--- |--- |
|0|Never time out|
|1|1 minute|
|2|2 minutes|
|3|3 minutes|
|5|5 minutes (default)|
|10|10 minutes|
|15|15 minutes|
|30|30 minutes|
|60|1 hour|
|120|2 hours|
|240|4 hours|

<p>The data type is integer. Supported operation is Get and Replace.

<a href="" id="properties-sleepmode"></a>**Properties/SleepMode**
<p>Added in Windows 10, version 20H2. Specifies the type of sleep mode for the Surface Hub.

<p>Valid values:

- 0 - Connected Standby (default)
- 1 - Hibernate

<p>The data type is integer. Supported operation is Get and Replace.

<a href="" id="properties-allowsessionresume"></a>**Properties/AllowSessionResume**
<p>Added in Windows 10, version 1703. Specifies whether to allow the ability to resume a session when the session times out.

<p>If this setting is true, the &quot;Resume Session&quot; feature will be available on the welcome screen when the screen is idle. If false, once the screen idles, the session will be automatically cleaned up as if the “End Session&quot; feature was initiated.

<p>The data type is boolean. Supported operation is Get and Replace.

<a href="" id="properties-allowautoproxyauth"></a>**Properties/AllowAutoProxyAuth**
<p>Added in Windows 10, version 1703. Specifies whether to use the device account for proxy authentication.

<p>If this setting is true, the device account will be used for proxy authentication. If false, a separate account will be used.

<p>The data type is boolean. Supported operation is Get and Replace.

<a href="" id="properties-proxyservers"></a>**Properties/ProxyServers**
<p>Added in <a href="https://support.microsoft.com/topic/may-28-2019-kb4499162-os-build-15063-1839-ed6780ab-38d6-f590-d789-5ba873b1e142" data-raw-source="[KB4499162](https://support.microsoft.com/topic/may-28-2019-kb4499162-os-build-15063-1839-ed6780ab-38d6-f590-d789-5ba873b1e142)">KB4499162</a> for Windows 10, version 1703. Specifies FQDNs of proxy servers to provide device account credentials to before any user interaction (if AllowAutoProxyAuth is enabled). This is a semi-colon separated list of server names, without any additional prefixes (e.g. https://).

<p>The data type is string. Supported operation is Get and Replace.

<a href="" id="properties-disablesigninsuggestions"></a>**Properties/DisableSigninSuggestions**
<p>Added in Windows 10, version 1703. Specifies whether to disable auto-populating of the sign-in dialog with invitees from scheduled meetings.

<p>If this setting is true, the sign-in dialog will not be populated. If false, the dialog will auto-populate.

<p>The data type is boolean. Supported operation is Get and Replace.

<a href="" id="properties-donotshowmymeetingsandfiles"></a>**Properties/DoNotShowMyMeetingsAndFiles**
<p>Added in Windows 10, version 1703. Specifies whether to disable the &quot;My meetings and files&quot; feature in the Start menu, which shows the signed-in user&#39;s meetings and files from Office 365.

<p>If this setting is true, the “My meetings and files” feature will not be shown. When false, the “My meetings and files” feature will be shown.

<p>The data type is boolean. Supported operation is Get and Replace.

<a href="" id="momagent"></a>**MOMAgent**
<p>Node for the Microsoft Operations Management Suite.

<a href="" id="momagent-workspaceid"></a>**MOMAgent/WorkspaceID**
<p>GUID identifying the Microsoft Operations Management Suite workspace ID to collect the data. Set this to an empty string to disable the MOM agent.

<p>The data type is string. Supported operation is Get and Replace.

<a href="" id="momagent-workspacekey"></a>**MOMAgent/WorkspaceKey**
<p>Primary key for authenticating with the workspace.

<p>The data type is string. Supported operation is Get and Replace. The Get operation is allowed, but it will always return an empty string.

