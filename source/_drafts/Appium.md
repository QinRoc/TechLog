---
layout: draft
title: Appium使用
date: 2019-03-28
updated: 
thumbnail: 
comments: true
tags: Android
categories: 
permalink: true
toc: true
---

# 准备

## Appium
[官网](http://appium.io)
[GitHub主页](https://github.com/appium/appium)
[下载页](https://github.com/appium/appium-desktop/releases)

## ADB
http://adbshell.com
http://adbdriver.com/downloads/

ADB Driver Installer 提示已安装
但是cmd中提示无此命令无用
需要配置path
everything搜索adb未果

>Search:set adb path

[Using ADB and fastboot](https://wiki.lineageos.org/adb_fastboot_guide.html)

https://dl.google.com/android/repository/platform-tools-latest-windows.zip

```
C:\Users\Roc>adb devices -l
List of devices attached
* daemon not running; starting now at tcp:5037
* daemon started successfully
b8b4d9e3               unauthorized transport_id:1
```

>Search: Android SDK

[Command line tools only](https://developer.android.com/studio)

sdk-tools-windows-4333796.zip中没有adb

## 配置Appium Configurations
    ANDROID_HOME c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\

```
An unknown server-side error occurred while processing the command. Original error: Could not find adb.exe in c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\platform-tools\adb.exe,c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\emulator\adb.exe,c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\tools\adb.exe,c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\tools\bin\adb.exe. Do you have the Android SDK installed at 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\'?
```

    改为 ANDROID_HOME c:\Program\Dev\Android\platform-tools_r28.0.2-windows\

```
An unknown server-side error occurred while processing the command. Original error: Error getting device API level. Original error: Error executing adbExec. Original error: 'Command 'c\:\\Program\\Dev\\Android\\platform-tools_r28.0.2-windows\\platform-tools\\adb.exe -P 5037 -s b8b4d9e3 shell getprop ro.build.version.sdk' exited with code 1'; Stderr: 'error: device unauthorized.
 This adb server's $ADB_VENDOR_KEYS is not set
 Try 'adb kill-server' if that seems wrong.
 Otherwise check for a confirmation dialog on your device.'; Code: '1'
```

未授权调试
手机上操作授权
 "Because an app is obscuring a permission request..."
取消常用应用的无障碍设置

仍然报该错误

出现在其他应用上，取消FV悬浮球后OK

# 运行

```
[Appium] Welcome to Appium v1.12.1
[Appium] Appium REST http interface listener started on 0.0.0.0:4723
[HTTP] --> GET /wd/hub/sessions
[HTTP] {}
[GENERIC] Calling AppiumDriver.getSessions() with args: []
[GENERIC] Responding to client with driver.getSessions() result: []
[HTTP] <-- GET /wd/hub/sessions 200 6 ms - 40
[HTTP] 
[HTTP] --> POST /wd/hub/session
[HTTP] {"desiredCapabilities":{"appActivity":".ui.LauncherUI","appPackage":"com.tencent.mm","deviceName":"3T","platformName":"Android","newCommandTimeout":0,"connectHardwareKeyboard":true}}
[MJSONWP] Calling AppiumDriver.createSession() with args: [{"appActivity":".ui.LauncherUI","appPackage":"com.tencent.mm","deviceName":"3T","platformName":"Android","newCommandTimeout":0,"connectHardwareKeyboard":true},null,null]
[BaseDriver] Event 'newSessionRequested' logged at 1553740387810 (10:33:07 GMT+0800 (中国标准时间))
[Appium] DeprecationWarning: 'automationName' capability was not provided. Future versions of Appium will require 'automationName' capability to be set for Android sessions.
[Appium] Setting automation to 'UiAutomator1'. 
[Appium] Appium v1.12.1 creating new AndroidDriver (v4.11.0) session
[Appium] Capabilities:
[Appium]   appActivity: .ui.LauncherUI
[Appium]   appPackage: com.tencent.mm
[Appium]   deviceName: 3T
[Appium]   platformName: Android
[Appium]   newCommandTimeout: 0
[Appium]   connectHardwareKeyboard: true
[BaseDriver] Creating session with MJSONWP desired capabilities: {"appActivity":".ui.Launche...
[BaseDriver] The following capabilities were provided, but are not recognized by appium: connectHardwareKeyboard.
[BaseDriver] Session created with session id: 87a01401-530f-438e-a1a0-313428e1e53a
[ADB] Checking whether adb is present
[ADB] Found 0 'build-tools' folders under 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows' (newest first):
[ADB] Using adb.exe from c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe
[AndroidDriver] Retrieving device list
[ADB] Trying to find a connected android device
[ADB] Getting connected devices...
[ADB] 1 device(s) connected
[AndroidDriver] Using device: b8b4d9e3
[ADB] Setting device id to b8b4d9e3
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell getprop ro.build.version.sdk'
[AndroidDriver] Shutting down Android driver
[AndroidDriver] Called deleteSession but bootstrap wasn't active
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell am force-stop io.appium.unlock'
[BaseDriver] Event 'newSessionStarted' logged at 1553740388288 (10:33:08 GMT+0800 (中国标准时间))
[MJSONWP] Encountered internal error running command: Error: Error getting device API level. Original error: Error executing adbExec. Original error: 'Command 'c\:\\Program\\Dev\\Android\\platform-tools_r28.0.2-windows\\platform-tools\\adb.exe -P 5037 -s b8b4d9e3 shell getprop ro.build.version.sdk' exited with code 1'; Stderr: 'error: device unauthorized.
[MJSONWP] This adb server's $ADB_VENDOR_KEYS is not set
[MJSONWP] Try 'adb kill-server' if that seems wrong.
[MJSONWP] Otherwise check for a confirmation dialog on your device.'; Code: '1'
[MJSONWP]     at ADB.getApiLevel (C:\Users\Roc\AppData\Local\Programs\Appium\resources\app\node_modules\appium\node_modules\appium-adb\lib\tools\adb-commands.js:92:13)
[HTTP] <-- POST /wd/hub/session 500 490 ms - 614
[HTTP] 
[HTTP] --> DELETE /wd/hub/session
[HTTP] {}
[HTTP] No route found. Setting content type to 'text/plain'
[HTTP] <-- DELETE /wd/hub/session 404 3 ms - 57
[HTTP] 
[HTTP] --> POST /wd/hub/session
[HTTP] {"desiredCapabilities":{"appActivity":".ui.LauncherUI","appPackage":"com.tencent.mm","deviceName":"3T","platformName":"Android","newCommandTimeout":0,"connectHardwareKeyboard":true}}
[MJSONWP] Calling AppiumDriver.createSession() with args: [{"appActivity":".ui.LauncherUI","appPackage":"com.tencent.mm","deviceName":"3T","platformName":"Android","newCommandTimeout":0,"connectHardwareKeyboard":true},null,null]
[BaseDriver] Event 'newSessionRequested' logged at 1553740476436 (10:34:36 GMT+0800 (中国标准时间))
[Appium] DeprecationWarning: 'automationName' capability was not provided. Future versions of Appium will require 'automationName' capability to be set for Android sessions.
[Appium] Setting automation to 'UiAutomator1'. 
[Appium] Appium v1.12.1 creating new AndroidDriver (v4.11.0) session
[Appium] Capabilities:
[Appium]   appActivity: .ui.LauncherUI
[Appium]   appPackage: com.tencent.mm
[Appium]   deviceName: 3T
[Appium]   platformName: Android
[Appium]   newCommandTimeout: 0
[Appium]   connectHardwareKeyboard: true
[BaseDriver] Creating session with MJSONWP desired capabilities: {"appActivity":".ui.Launche...
[BaseDriver] The following capabilities were provided, but are not recognized by appium: connectHardwareKeyboard.
[BaseDriver] Session created with session id: efa77542-a0de-4ba5-abc7-54f3fb80b08d
[AndroidDriver] Retrieving device list
[ADB] Trying to find a connected android device
[ADB] Getting connected devices...
[ADB] 1 device(s) connected
[AndroidDriver] Using device: b8b4d9e3
[ADB] Setting device id to b8b4d9e3
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell getprop ro.build.version.sdk'
[AndroidDriver] Shutting down Android driver
[AndroidDriver] Called deleteSession but bootstrap wasn't active
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell am force-stop io.appium.unlock'
[BaseDriver] Event 'newSessionStarted' logged at 1553740476593 (10:34:36 GMT+0800 (中国标准时间))
[MJSONWP] Encountered internal error running command: Error: Error getting device API level. Original error: Error executing adbExec. Original error: 'Command 'c\:\\Program\\Dev\\Android\\platform-tools_r28.0.2-windows\\platform-tools\\adb.exe -P 5037 -s b8b4d9e3 shell getprop ro.build.version.sdk' exited with code 1'; Stderr: 'error: device unauthorized.
[MJSONWP] This adb server's $ADB_VENDOR_KEYS is not set
[MJSONWP] Try 'adb kill-server' if that seems wrong.
[MJSONWP] Otherwise check for a confirmation dialog on your device.'; Code: '1'
[MJSONWP]     at ADB.getApiLevel (C:\Users\Roc\AppData\Local\Programs\Appium\resources\app\node_modules\appium\node_modules\appium-adb\lib\tools\adb-commands.js:92:13)
[HTTP] <-- POST /wd/hub/session 500 158 ms - 614
[HTTP] 
[HTTP] --> DELETE /wd/hub/session
[HTTP] {}
[HTTP] No route found. Setting content type to 'text/plain'
[HTTP] <-- DELETE /wd/hub/session 404 1 ms - 57
[HTTP] 
[HTTP] --> POST /wd/hub/session
[HTTP] {"desiredCapabilities":{"appActivity":".ui.LauncherUI","appPackage":"com.tencent.mm","deviceName":"3T","platformName":"Android","newCommandTimeout":0,"connectHardwareKeyboard":true}}
[MJSONWP] Calling AppiumDriver.createSession() with args: [{"appActivity":".ui.LauncherUI","appPackage":"com.tencent.mm","deviceName":"3T","platformName":"Android","newCommandTimeout":0,"connectHardwareKeyboard":true},null,null]
[BaseDriver] Event 'newSessionRequested' logged at 1553740775202 (10:39:35 GMT+0800 (中国标准时间))
[Appium] DeprecationWarning: 'automationName' capability was not provided. Future versions of Appium will require 'automationName' capability to be set for Android sessions.
[Appium] Setting automation to 'UiAutomator1'. 
[Appium] Appium v1.12.1 creating new AndroidDriver (v4.11.0) session
[Appium] Capabilities:
[Appium]   appActivity: .ui.LauncherUI
[Appium]   appPackage: com.tencent.mm
[Appium]   deviceName: 3T
[Appium]   platformName: Android
[Appium]   newCommandTimeout: 0
[Appium]   connectHardwareKeyboard: true
[BaseDriver] Creating session with MJSONWP desired capabilities: {"appActivity":".ui.Launche...
[BaseDriver] The following capabilities were provided, but are not recognized by appium: connectHardwareKeyboard.
[BaseDriver] Session created with session id: 40cd6c8c-53b1-4019-99f7-d52e45a88fb5
[AndroidDriver] Retrieving device list
[ADB] Trying to find a connected android device
[ADB] Getting connected devices...
[ADB] 1 device(s) connected
[AndroidDriver] Using device: b8b4d9e3
[ADB] Setting device id to b8b4d9e3
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell getprop ro.build.version.sdk'
[ADB] Current device property 'ro.build.version.sdk': 26
[ADB] Device API level: 26
[AndroidDriver] Consider setting 'automationName' capability to 'uiautomator2' on Android >= 6, since UIAutomator framework is not maintained anymore by the OS vendor.
[AndroidDriver] App file was not listed, instead we're going to run com.tencent.mm directly on the device
[AndroidDriver] Checking whether package is present on the device
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell pm list packages com.tencent.mm'
[AndroidDriver] Starting Android session
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 wait-for-device'
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell echo ping'
[AndroidDriver] Pushing settings apk to device...
[ADB] Getting install status for io.appium.settings
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell dumpsys package io.appium.settings'
[ADB] 'io.appium.settings' is not installed
[ADB] App 'C:\Users\Roc\AppData\Local\Programs\Appium\resources\app\node_modules\appium\node_modules\io.appium.settings\apks\settings_apk-debug.apk' is not installed
[ADB] Installing 'C:\Users\Roc\AppData\Local\Programs\Appium\resources\app\node_modules\appium\node_modules\io.appium.settings\apks\settings_apk-debug.apk'
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell ls -t -1 /data/local/tmp/appium_cache'
[ADB] The count of applications in the cache: 0
[ADB] Caching the application at 'C:\Users\Roc\AppData\Local\Programs\Appium\resources\app\node_modules\appium\node_modules\io.appium.settings\apks\settings_apk-debug.apk' to '/data/local/tmp/appium_cache/728413456b86856a2003edeb524d6bd577ca6418.apk'
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 push C\:\\Users\\Roc\\AppData\\Local\\Programs\\Appium\\resources\\app\\node_modules\\appium\\node_modules\\io.appium.settings\\apks\\settings_apk-debug.apk /data/local/tmp/appium_cache/728413456b86856a2003edeb524d6bd577ca6418.apk'
[ADB] The upload of 'settings_apk-debug.apk' (1.16 MB) took 0.094s
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell pm install -g /data/local/tmp/appium_cache/728413456b86856a2003edeb524d6bd577ca6418.apk'
[ADB] The installation of 'settings_apk-debug.apk' took 3.124s
[ADB] Install command stdout: Success
[ADB] Getting IDs of all 'io.appium.settings' processes
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell 'pgrep --help; echo $?''
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell pgrep \^appium\\.settings\$'
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell am start -W -n io.appium.settings/.Settings -a android.intent.action.MAIN -c android.intent.category.LAUNCHER -f 0x10200000'
[AndroidDriver] Failed to launch settings app: Cannot start the 'io.appium.settings' application. Visit https://github.com/appium/appium/blob/master/docs/en/writing-running-appium/android/activity-startup.md for troubleshooting. Original error: Error executing adbExec. Original error: 'Command 'c\:\\Program\\Dev\\Android\\platform-tools_r28.0.2-windows\\platform-tools\\adb.exe -P 5037 -s b8b4d9e3 shell am start -W -n io.appium.settings/.Settings -a android.intent.action.MAIN -c android.intent.category.LAUNCHER -f 0x10200000' timed out after 20000ms'. Try to increase the 20000ms adb execution timeout represented by 'adbExecTimeout' capability
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell appops set io.appium.settings android\:mock_location allow'
[Logcat] Starting logcat capture
[ADB] Getting device platform version
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell getprop ro.build.version.release'
[ADB] Current device property 'ro.build.version.release': 8.0.0
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell wm size'
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell getprop ro.product.model'
[ADB] Current device property 'ro.product.model': ONEPLUS A3010
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell getprop ro.product.manufacturer'
[ADB] Current device property 'ro.product.manufacturer': OnePlus
[AndroidDriver] No app sent in, not parsing package/activity
[AndroidDriver] No app capability. Assuming it is already on the device
[ADB] Getting install status for com.tencent.mm
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell dumpsys package com.tencent.mm'
[ADB] 'com.tencent.mm' is installed
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell am force-stop com.tencent.mm'
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell pm clear com.tencent.mm'
[AndroidDriver] Performed fast reset on the installed 'com.tencent.mm' application (stop and clear)
[AndroidBootstrap] Watching for bootstrap disconnect
[ADB] Forwarding system: 4724 to device: 4724
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 forward tcp\:4724 tcp\:4724'
[UiAutomator] Starting UiAutomator
[UiAutomator] Moving to state 'starting'
[UiAutomator] Parsing uiautomator jar
[UiAutomator] Found jar name: 'AppiumBootstrap.jar'
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 push C\:\\Users\\Roc\\AppData\\Local\\Programs\\Appium\\resources\\app\\node_modules\\appium\\node_modules\\appium-android-driver\\bootstrap\\bin\\AppiumBootstrap.jar /data/local/tmp/'
[ADB] Attempting to kill all uiautomator processes
[ADB] Getting IDs of all 'uiautomator' processes
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell pgrep \^uiautomator\$'
[ADB] No 'uiautomator' process has been found
[UiAutomator] Starting UIAutomator
[ADB] Creating ADB subprocess with args: ["-P",5037,"-s","b8b4d9e3","shell","uiautomator","runtest","AppiumBootstrap.jar","-c","io.appium.android.bootstrap.Bootstrap","-e","pkg","com.tencent.mm","-e","disableAndroidWatchers",false,"-e","acceptSslCerts",false]
[UiAutomator] Moving to state 'online'
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Loading json...
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Registered crash watchers.
[AndroidBootstrap] Android bootstrap socket is now connected
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell dumpsys window'
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Client connected
[AndroidDriver] Screen already unlocked, doing nothing
[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell am start -W -n com.tencent.mm/.ui.LauncherUI -S'
[AndroidBootstrap] Emitting alert message...
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Emitting system alert message
[Appium] New AndroidDriver session created successfully, session 40cd6c8c-53b1-4019-99f7-d52e45a88fb5 added to master session list
[BaseDriver] Event 'newSessionStarted' logged at 1553740837217 (10:40:37 GMT+0800 (中国标准时间))
[MJSONWP (40cd6c8c)] Cached the protocol value 'MJSONWP' for the new session 40cd6c8c-53b1-4019-99f7-d52e45a88fb5
[MJSONWP (40cd6c8c)] Responding to client with driver.createSession() result: {"platform":"LINUX","webStorageEnabled":false,"takesScreenshot":true,"javascriptEnabled":true,"databaseEnabled":false,"networkConnectionEnabled":true,"locationContextEnabled":false,"warnings":{},"desired":{"appActivity":".ui.LauncherUI","appPackage":"com.tencent.mm","deviceName":"3T","platformName":"Android","newCommandTimeout":0,"connectHardwareKeyboard":true},"appActivity":".ui.LauncherUI","appPackage":"com.tencent.mm","deviceName":"b8b4d9e3","platformName":"Android","newCommandTimeout":0,"connectHardwareKeyboard":true,"deviceUDID":"b8b4d9e3","platformVersion":"8.0.0","deviceScreenSize":"1080x1920","deviceModel":"ONEPLUS A3010","deviceManufacturer":"OnePlus"}
[HTTP] <-- POST /wd/hub/session 200 62017 ms - 741
[HTTP] 
[HTTP] --> POST /wd/hub/session/40cd6c8c-53b1-4019-99f7-d52e45a88fb5/context
[HTTP] {"name":"NATIVE_APP"}
[MJSONWP (40cd6c8c)] Calling AppiumDriver.setContext() with args: ["NATIVE_APP","40cd6c8c-53b1-4019-99f7-d52e45a88fb5"]
[MJSONWP (40cd6c8c)] Responding to client with driver.setContext() result: null
[HTTP] <-- POST /wd/hub/session/40cd6c8c-53b1-4019-99f7-d52e45a88fb5/context 200 2 ms - 76
[HTTP] 
[HTTP] --> GET /wd/hub/session/40cd6c8c-53b1-4019-99f7-d52e45a88fb5/source
[HTTP] {}
[MJSONWP (40cd6c8c)] Calling AppiumDriver.getPageSource() with args: ["40cd6c8c-53b1-4019-99f7-d52e45a88fb5"]
[AndroidBootstrap] Sending command to android: {"cmd":"action","action":"source","params":{}}
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Got data from client: {"cmd":"action","action":"source","params":{}}
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Got command of type ACTION
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Got command action: source
[AndroidBootstrap] [UIAUTO STDOUT] [APPIUM-UIAUTO] [debug] Returning result: {"status":0,"value":"<\/android.widget.LinearLayout><\/android.widget.LinearLayout><\/android.widget.GridLayout>
[AndroidBootstrap] Received command result from bootstrap
[AndroidBootstrap] Stream still not complete, waiting up to 60000ms for the data to arrive
[AndroidBootstrap] [UIAUTO STDOUT] 07][816,662]\" resource-id=\"\" instance=\"6\"\/><\/android.widget.LinearLayout><\/android.widget.LinearLayout><\/android.widget.LinearLayout><\/android.widget.LinearLayout><\/android.widget.LinearLayout><\/android.widget.RelativeLayout><\/hierarchy>"}[/APPIUM-UIAUTO]
[AndroidBootstrap] Received command result from bootstrap
[MJSONWP (40cd6c8c)] Responding to client with driver.getPageSource() result: "
[HTTP] <-- GET /wd/hub/session/40cd6c8c-53b1-4019-99f7-d52e45a88fb5/source 200 852 ms - 11356
[HTTP] 
[HTTP] --> GET /wd/hub/session/40cd6c8c-53b1-4019-99f7-d52e45a88fb5/screenshot
[HTTP] {}
[MJSONWP (40cd6c8c)] Calling AppiumDriver.getScreenshot() with args: ["40cd6c8c-53b1-4019-99f7-d52e45a88fb5"]
[MJSONWP (40cd6c8c)] Responding to client with driver.getScreenshot() result: "iVBORw0KGgoAAAANSUhEUgAABDgAAAeACAYAAAArYecKAAAsR0lEQVR4AezBAQ0AMAwDoL7+Pe86mgAvyQUAAABgWAMAAAAwrgEAAAAY1wAAAACMawAAAADGNQAAAADjGgAAAIBxDQAAAMC4BgAAAGBcAwAAADCuAQAAABjXAAAAAIxrAAAAAMY1AAAAAOMaAAAAgHENAAAAwLgGAAAAYFwDAAAAMK4BAAAAGNcAAAAAjGsAAAAAxjUAAAAA4xoAAACAcQ0AAADAuAYAAABgXAMAAAAwrgEAAAAY1wAAAACMawAAAADGNQAAAADjGgAAAIBxDQAAAMC4BgAAAGBcAwAAADCuAQAAABjXAAAAAIxrAAAAAMY1AAAAAOMaAAAAgHENAAAAwLgGAAAAYFwDAAAAMK4BAAAAGNcAAAAAjGsAAAAAxjUAAAAA4xoAAACAcQ0AAADAuAYAAABgXAMAAAAwrgEAAAAY1wAAAACMawAAAADGNQAAAADjGgAAAIBxDQAAAMC4BgAAAGBcAwAAADCuAQAAABjXAAAAAIxrAAAAAMY1AAAAAOMaAAAAgHENAAAAwLgGAAAAYFwDAAAAMK4BAAAAGNcAAAAAjGsAAAAAxjUAAAAA4xoAAACAcQ0AAADAuAYAAABgXAMAAAAwrgEAAAAY1wAAAACMawAAAADGNQAAAADjGgAAAIBxDQAAAMC4BgAAAGBcAwAAADCuAQAAABjXAAAAAIxrAAAAAMY1AAAAAOMaAAAAgHENAAAAwLgGAAAAYFwDAAAAMK4BAAAAGNcAAAAAjGsAAAAAxjUAAAAA4xoAAACAcQ0AAADAuAYAAABgXAMAAAAwrgEAAAAY1wAAAACMawAAAADGNQAAAADjGgAAAIBxDQAAAMC4BgAAAGBcAwAAADCuAQAAABjXAAAAAIxrAAAAAMY1AAAAAOMaAAAAgHENAAAAwLgGAAAAYFwDAAAAMK4BAAAAGNcAAAAAjGsAAAAAxjUAAAAA4xoAAACAcQ0AAADA...
[HTTP] <-- GET /wd/hub/session/40cd6c8c-53b1-4019-99f7-d52e45a88fb5/screenshot 200 1061 ms - 15266
[HTTP] 
[HTTP] --> GET /wd/hub/session/40cd6c8c-53b1-4019-99f7-d52e45a88fb5/window/current/size
[HTTP] {}
[MJSONWP (40cd6c8c)] Calling AppiumDriver.getWindowSize() with args: ["current","40cd6c8c-53b1-4019-99f7-d52e45a88fb5"]
[AndroidBootstrap] Sending command to android: {"cmd":"action","action":"getDeviceSize","params":{}}
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Got data from client: {"cmd":"action","action":"getDeviceSize","params":{}}
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Got command of type ACTION
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Got command action: getDeviceSize
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Returning result: {"status":0,"value":{"height":1920,"width":1080}}
[AndroidBootstrap] Received command result from bootstrap
[MJSONWP (40cd6c8c)] Responding to client with driver.getWindowSize() result: {"height":1920,"width":1080}
[HTTP] <-- GET /wd/hub/session/40cd6c8c-53b1-4019-99f7-d52e45a88fb5/window/current/size 200 18 ms - 100
[HTTP] 
[HTTP] --> POST /wd/hub/session/40cd6c8c-53b1-4019-99f7-d52e45a88fb5/elements
[HTTP] {"using":"id","value":"com.oneplus.aod:id/battery_empty_view"}
[MJSONWP (40cd6c8c)] Calling AppiumDriver.findElements() with args: ["id","com.oneplus.aod:id/battery_empty_view","40cd6c8c-53b1-4019-99f7-d52e45a88fb5"]
[BaseDriver] Valid locator strategies for this request: xpath, id, class name, accessibility id, -android uiautomator
[BaseDriver] Waiting up to 0 ms for condition
[AndroidBootstrap] Sending command to android: {"cmd":"action","action":"find","params":{"strategy":"id","selector":"com.oneplus.aod:id/battery_empty_view","context":"","multiple":true}}
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Got data from client: {"cmd":"action","action":"find","params":{"strategy":"id","selector":"com.oneplus.aod:id/battery_empty_view","context":"","multiple":true}}
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Got command of type ACTION
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Got command action: find
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Finding 'com.oneplus.aod:id/battery_empty_view' using 'ID' with the contextId: '' multiple: true
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Using: UiSelector[RESOURCE_ID=com.oneplus.aod:id/battery_empty_view]
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] getElements selector:UiSelector[RESOURCE_ID=com.oneplus.aod:id/battery_empty_view]
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Element[] is null: (0)
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] getElements tmp selector:UiSelector[INSTANCE=0, RESOURCE_ID=com.oneplus.aod:id/battery_empty_view]
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Element[] is null: (1)
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] getElements tmp selector:UiSelector[INSTANCE=1, RESOURCE_ID=com.oneplus.aod:id/battery_empty_view]
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Returning result: {"status":0,"value":[{"ELEMENT":"1"}]}
[AndroidBootstrap] Received command result from bootstrap
[MJSONWP (40cd6c8c)] Responding to client with driver.findElements() result: [{"element-6066-11e4-a52e-4f735466cecf":"1","ELEMENT":"1"}]
[HTTP] <-- POST /wd/hub/session/40cd6c8c-53b1-4019-99f7-d52e45a88fb5/elements 200 50 ms - 131
[HTTP] 
[HTTP] --> POST /wd/hub/session/40cd6c8c-53b1-4019-99f7-d52e45a88fb5/elements
[HTTP] {"using":"id","value":"com.oneplus.aod:id/main_view"}
[MJSONWP (40cd6c8c)] Calling AppiumDriver.findElements() with args: ["id","com.oneplus.aod:id/main_view","40cd6c8c-53b1-4019-99f7-d52e45a88fb5"]
[BaseDriver] Valid locator strategies for this request: xpath, id, class name, accessibility id, -android uiautomator
[BaseDriver] Waiting up to 0 ms for condition
[AndroidBootstrap] Sending command to android: {"cmd":"action","action":"find","params":{"strategy":"id","selector":"com.oneplus.aod:id/main_view","context":"","multiple":true}}
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Got data from client: {"cmd":"action","action":"find","params":{"strategy":"id","selector":"com.oneplus.aod:id/main_view","context":"","multiple":true}}
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Got command of type ACTION
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Got command action: find
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Finding 'com.oneplus.aod:id/main_view' using 'ID' with the contextId: '' multiple: true
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Using: UiSelector[RESOURCE_ID=com.oneplus.aod:id/main_view]
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] getElements selector:UiSelector[RESOURCE_ID=com.oneplus.aod:id/main_view]
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Element[] is null: (0)
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] getElements tmp selector:UiSelector[INSTANCE=0, RESOURCE_ID=com.oneplus.aod:id/main_view]
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Failed to locate element. Clearing Accessibility cache and retrying.
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Finding 'com.oneplus.aod:id/main_view' using 'ID' with the contextId: '' multiple: true
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Using: UiSelector[RESOURCE_ID=com.oneplus.aod:id/main_view]
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] getElements selector:UiSelector[RESOURCE_ID=com.oneplus.aod:id/main_view]
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Element[] is null: (0)
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] getElements tmp selector:UiSelector[INSTANCE=0, RESOURCE_ID=com.oneplus.aod:id/main_view]
[AndroidBootstrap] Received command result from bootstrap
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Returning result: {"status":0,"value":[]}
[MJSONWP (40cd6c8c)] Responding to client with driver.findElements() result: []
[HTTP] <-- POST /wd/hub/session/40cd6c8c-53b1-4019-99f7-d52e45a88fb5/elements 200 128 ms - 74
[HTTP] 
[HTTP] --> POST /wd/hub/session/40cd6c8c-53b1-4019-99f7-d52e45a88fb5/elements
[HTTP] {"using":"xpath","value":"/hierarchy/android.widget.RelativeLayout/android.widget.LinearLayout"}
[MJSONWP (40cd6c8c)] Calling AppiumDriver.findElements() with args: ["xpath","/hierarchy/android.widget.RelativeLayout/android.widget.LinearLayout","40cd6c8c-53b1-4019-99f7-d52e45a88fb5"]
[BaseDriver] Valid locator strategies for this request: xpath, id, class name, accessibility id, -android uiautomator
[BaseDriver] Waiting up to 0 ms for condition
[AndroidBootstrap] Sending command to android: {"cmd":"action","action":"find","params":{"strategy":"xpath","selector":"/hierarchy/android.widget.RelativeLayout/android.widget.LinearLayout","context":"","multiple":true}}
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Got data from client: {"cmd":"action","action":"find","params":{"strategy":"xpath","selector":"/hierarchy/android.widget.RelativeLayout/android.widget.LinearLayout","context":"","multiple":true}}
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Got command of type ACTION
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Got command action: find
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Finding '/hierarchy/android.widget.RelativeLayout/android.widget.LinearLayout' using 'XPATH' with the contextId: '' multiple: true
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Failed to locate element. Clearing Accessibility cache and retrying.
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Finding '/hierarchy/android.widget.RelativeLayout/android.widget.LinearLayout' using 'XPATH' with the contextId: '' multiple: true
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Returning result: {"status":0,"value":[]}
[AndroidBootstrap] Received command result from bootstrap
[MJSONWP (40cd6c8c)] Responding to client with driver.findElements() result: []
[HTTP] <-- POST /wd/hub/session/40cd6c8c-53b1-4019-99f7-d52e45a88fb5/elements 200 442 ms - 74
[HTTP] 
[AndroidBootstrap] Emitting alert message...
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Emitting system alert message
[AndroidBootstrap] Emitting alert message...
[AndroidBootstrap] [BOOTSTRAP LOG] [debug] Emitting system alert message
```

看到clear命令心中一凉，清空数据？
```[ADB] Running 'c:\Program\Dev\Android\platform-tools_r28.0.2-windows\platform-tools\adb.exe -P 5037 -s b8b4d9e3 shell pm clear com.tencent.mm'```

启动后重新登录、载入数据

真的都被清空了

微痕迹里还能看到历史文件

[adb命令pm工具讲解](https://www.jianshu.com/p/9123cc89e9f3)
    clear ‘pkgname’ ：对指定的package删除所有数据；

钛备份恢复数据最新备份是2018.10.20
以后要养成备份数据的习惯

还是不要在日用手机上调试了。

权限也被清除了。

所有的设置也全部清空。