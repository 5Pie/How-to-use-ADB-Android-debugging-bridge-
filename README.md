# **How to use ADB (Android debugging bridge)**

## **Initiation phase:**

1. Connect phone with *USB debugging* ON
2. Select *File Transfer Option* for the USB (it can work without this option, but it’s recommended for more stability.)
3. Go to the location:
 `C:\Users\Name\AppData\Local\Android\Sdk\platform-tools` **or similar** as per your system 
4. Left click on the empty space and click on *OPEN IN TERMINAL*
.<img width="1674" height="821" alt="image" src="https://github.com/user-attachments/assets/db80532c-ef39-4654-bac8-922b38e649fd" />

The terminal should now be open.
<img width="1687" height="813" alt="Screenshot 2026-03-20 122348" src="https://github.com/user-attachments/assets/b6e0c6e2-15cf-49c6-9b18-8e56f6055587" />



## **Using the ADB (Uninstalling):**

First, check if the device is actually connected by typing: `./adb devices` .You will get the list of devices connected and their respective ID.

**NOT REQUIRED:** you can access all commands by typing: `./adb` 

Uninstalling a file is not just as simple as writing the apk name. You will have to mention the **Package name**

## *How to get Package name:*

### For System package: 

• Write the code: `./adb shell pm list packages -s`

• This will give you the list of all system packages, if you want to ***search*** for a particular package use the code: `./adb shell pm list packages -s | findstr <name>`

• **Example:** `./adb shell pm list packages -s | findstr camera`


### For Third Party packages:

• Write the code: `./adb shell pm list packages -3`

• To ***search*** for a particular package: `./adb shell pm list packages -3 | findstr <name>`

• **Example:** `./adb shell pm list packages -3 | findstr What` (it will give result for whatsapp and any app with “what” in its name)

### For all/any packages:

• Write the code: `./adb shell pm list packages`

• To ***search*** for a particular package: `./adb shell pm list packages | findstr <name>`


Now you should have the required package name.

If you are not able to find the package name after searching for it. Then you probably are using the full name of an application to find its package. You should try to shorten it as much as you can.

Sometimes an application's name might not even match its package name. You can search the ***package name on the net*** to check what application it belongs to. Since all applications have a package name attached to them you will find the respective package name directly from the net.


## *How to uninstall a package:*

• Write the code: `./adb shell pm uninstall --user 0 <package name>`


• **Example:** `./adb shell pm uninstall --user 0 com.instagram.android`


and it's **DONE.**


# Correcting accidental mistakes:

• If you have accidentally deleted a package, you can recover the said package by using: `./adb shell pm install-existing <package name>`

If the above code doesn't work you can use: `./adb shell cmd install-existing <package name>`

• Make sure that you are not omitting any `./` from the code. Or have copied any ***formatting spaces (blank spaces)***

• Forgetting to turn on USB Debugging
