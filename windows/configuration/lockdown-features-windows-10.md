---
title: Lockdown features from Windows Embedded 8.1 Industry (Windows 10)
description: Many of the lockdown features available in Windows Embedded 8.1 Industry have been modified in some form for Windows 10. 
ms.assetid: 3C006B00-535C-4BA4-9421-B8F952D47A14
ms.reviewer: 
manager: dansimp
keywords: lockdown, embedded
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
---

# Lockdown features from Windows Embedded 8.1 Industry

**Applies to**

- Windows 10

Many of the lockdown features available in Windows Embedded 8.1 Industry have been modified in some form for Windows 10. This table maps Windows Embedded Industry 8.1 features to Windows 10 Enterprise features, along with links to documentation.

|Windows Embedded 8.1 Industry lockdown feature|Windows 10 feature|Changes|
|--- |--- |--- |
|[Hibernate Once/Resume Many (HORM)](/previous-versions/windows/embedded/dn449302(v=winembedded.82)): Quick boot to device|[HORM](/windows-hardware/customize/enterprise/hibernate-once-resume-many-horm-)|HORM is supported in Windows 10, version 1607 and later.|
|[Unified Write Filter](/previous-versions/windows/embedded/dn449332(v=winembedded.82)): protect a device's physical storage media|[Unified Write Filter](/windows-hardware/customize/enterprise/unified-write-filter)|The Unified Write Filter is continued in Windows 10.|
|[Keyboard Filter](/previous-versions/windows/embedded/dn449298(v=winembedded.82)): block hotkeys and other key combinations|[Keyboard Filter](/windows-hardware/customize/enterprise/keyboardfilter)|Keyboard filter is added in Windows 10, version 1511. As in Windows Embedded Industry 8.1, Keyboard Filter is an optional component that can be turned on via **Turn Windows Features On/Off**. Keyboard Filter (in addition to the WMI configuration previously available) will be configurable through Windows Imaging and Configuration Designer (ICD) in the SMISettings path.|
|[Shell Launcher](/previous-versions/windows/embedded/dn449423(v=winembedded.82)): launch a Windows desktop application on sign-on|[Shell Launcher](/windows-hardware/customize/enterprise/shell-launcher)|Shell Launcher continues in Windows 10. It is now configurable in Windows ICD under the **SMISettings** category.<br>Learn [how to use Shell Launcher to create a kiosk device](/windows/configuration/kiosk-single-app) that runs a Windows desktop application.|
|[Application Launcher](/previous-versions/windows/embedded/dn449251(v=winembedded.82)): launch a Universal Windows Platform (UWP) app on sign-on|[Assigned Access](/windows/client-management/mdm/assignedaccess-csp)|The Windows 8 Application Launcher has been consolidated into Assigned Access. Application Launcher enabled launching a Windows 8 app and holding focus on that app. Assigned Access offers a more robust solution for ensuring that apps retain focus.|
|[Dialog Filter](/previous-versions/windows/embedded/dn449395(v=winembedded.82)): suppress system dialogs and control which processes can run|[AppLocker](/windows/device-security/applocker/applocker-overview)|Dialog Filter has been deprecated for Windows 10. Dialog Filter provided two capabilities; the ability to control which processes were able to run, and the ability to prevent dialogs (in practice, system dialogs) from appearing.<li>Control over which processes are able to run will now be provided by AppLocker.<li>System dialogs in Windows 10 have been replaced with system toasts. To see more on blocking system toasts, see Toast Notification Filter below.|
|[Toast Notification Filter](/previous-versions/windows/embedded/dn449360(v=winembedded.82)): suppress toast notifications|Mobile device management (MDM) and Group Policy|Toast Notification Filter has been replaced by MDM and Group Policy settings for blocking the individual components of non-critical system toasts that may appear. For example, to prevent a toast from appearing when a USB drive is connected, ensure that USB connections have been blocked using the USB-related policies, and turn off notifications from apps.<br>Group Policy: **User Configuration** > **Administrative Templates** > **Start Menu and Taskbar** > **Notifications**<br>MDM policy name may vary depending on your MDM service. In Microsoft Intune, use **Allow action center notifications** and a [custom OMA-URI setting](https://go.microsoft.com/fwlink/p/?LinkID=616317) for **AboveLock/AllowActionCenterNotifications**.|
|[Embedded Lockdown Manager](/previous-versions/windows/embedded/dn449279(v=winembedded.82)): configure lockdown features|[Windows Imaging and Configuration Designer (ICD)](/windows/configuration/provisioning-packages/provisioning-install-icd)|The Embedded Lockdown Manager has been deprecated for Windows 10 and replaced by the Windows ICD. Windows ICD is the consolidated tool for Windows imaging and provisioning scenarios and enables configuration of all Windows settings, including the lockdown features previously configurable through Embedded Lockdown Manager.|
|[USB Filter](/previous-versions/windows/embedded/dn449350(v=winembedded.82)): restrict USB devices and peripherals on system|MDM and Group Policy|The USB Filter driver has been replaced by MDM and Group Policy settings for blocking the connection of USB devices.<br> <br> Group Policy: **Computer Configuration** > **Administrative Templates** > **System** > **Device Installation** > **Device Installation Restrictions**<br>MDM policy name may vary depending on your MDM service. In Microsoft Intune, use **Removable storage**.|
|[Assigned Access](/previous-versions/windows/embedded/dn449303(v=winembedded.82)): launch a UWP app on sign-in and lock access to system|[Assigned Access](/windows/client-management/mdm/assignedaccess-csp)|Assigned Access has undergone significant improvement for Windows 10. In Windows 8.1, Assigned Access blocked system hotkeys and edge gestures, and non-critical system notifications, but it also applied some of these limitations to other accounts on the device.<br>In Windows 10, Assigned Access no longer affects accounts other than the one being locked down. Assigned Access now restricts access to other apps or system components by locking the device when the selected user account logs in and launching the designated app above the lock screen, ensuring that no unintended functionality can be accessed.<br><br>Learn [how to use Assigned Access to create a kiosk device](/windows/configuration/kiosk-single-app) that runs a Universal Windows app.|
|[Gesture Filter](/previous-versions/windows/embedded/dn449374(v=winembedded.82)): block swipes from top, left, and right edges of screen|MDM and Group Policy|In Windows 8.1, gestures provided the ability to close an app, to switch apps, and to reach the Charms. In Windows 10, Charms have been removed. In Windows 10, version 1607, you can block swipes using the [Allow edge swipe](/windows/client-management/mdm/policy-configuration-service-provider#LockDown_AllowEdgeSwipe) policy.|
|[Custom Logon](/previous-versions/windows/embedded/dn449309(v=winembedded.82)): suppress Windows UI elements during Windows sign-on, sign-off, and shutdown|[Embedded Logon](/windows-hardware/customize/desktop/unattend/microsoft-windows-embedded-embeddedlogon)|No changes. Applies only to Windows 10 Enterprise and Windows 10 Education.|
|[Unbranded Boot](/previous-versions/windows/embedded/dn449249(v=winembedded.82)): custom brand a device by removing or replacing Windows boot UI elements|[Unbranded Boot](/windows-hardware/customize/enterprise/unbranded-boot)|No changes. Applies only to Windows 10 Enterprise and Windows 10 Education.|
