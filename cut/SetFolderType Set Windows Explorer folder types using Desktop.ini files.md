# SetFolderType | Set Windows Explorer folder types using Desktop.ini files
[SetFolderType | Set Windows Explorer folder types using Desktop.ini files](https://lesferch.github.io/SetFolderType/) 

     SetFolderType | Set Windows Explorer folder types using Desktop.ini files                  

SetFolderType
=============

![](https://github.com/LesFerch/SetFolderType/assets/79026235/8462baf2-e131-436b-954e-ff7ee58b8c88)

Set Windows Explorer folder types using Desktop.ini files[](#set-windows-explorer-folder-types-using-desktopini-files)
----------------------------------------------------------------------------------------------------------------------

This program adds a right-click context menu to Windows Explorer that allows you to set the folder type for an entire folder tree by creating (or editing existing) **desktop.ini** files in each folder.

Why set folder types using Desktop.ini files?[](#why-set-folder-types-using-desktopini-files)
---------------------------------------------------------------------------------------------

### Background Information[](#background-information)

Windows supports setting the folder type to one of **General items**, **Documents**, **Pictures**, **Music**, or **Videos** with the appropriate entry in a **hidden**, **system** file named **desktop.ini**. This has the advantage of making the folder type setting permanent to the folder itself. You can reset your profile, create a new user, or reset Windows, and the folder types will be remembered and displayed with whatever view you have chosen for that folder type.

**Note**: To globallly set your preferred folder type views, please see [WinSetView](https://lesferch.github.io/WinSetView/)

However, there is a catch. Explorer only provides this functionality on drives that mount as **Local Disk** (aka “fixed disk”) and are formatted **NTFS**. Therefore, this tool will work on all internal drives that are formatted **NTFS**, but it will only work on some USB drives. For example, SanDisk USB SSD drives mount as type **Local Disk**, so they will work with this tool if the drive is formatted to **NTFS**.

**IMPORTANT**: This tool will have no effect if you have disabled _automatic folder type discovery_ (e.g. WinSetView option “Make all folders Generic”). Explorer’s automatic folder type discovery function checks the folder contents to determine and set the folder type. If it finds a `desktop.ini` file, the folder type setting in that file takes precedence.

### Partial Fix for Windows 11[](#partial-fix-for-windows-11)

For **Windows 11**, this tool provides a partial fix for some broken funtionality in the Windows 11 Explorer. Specifically, the feature **Also apply this template to all subfolders** is completely broken in Windows 11 (assuming you have not patched Windows 11 to run the Windows 10 Explorer). Here’s a [video](https://www.youtube.com/watch?v=U5eEFNZEWZg) demonstrating the issue.

The fix is partial because, as noted above, it only applies to drives of type **Local Disk** that are formatted **NTFS**. For such drives, SetFolderType will give you back the ability to set the folder type for an entire folder tree.

### Permanent folder type setting for both Windows 10 and Windows 11[](#permanent-folder-type-setting-for-both-windows-10-and-windows-11)

For **Windows 10** (or [Windows 10 Explorer on Windows 11](https://lesferch.github.io/SwitchExplorer/)), the feature **Also apply this template to all subfolders** works fine, but there is still a scenario where you may want this tool.

As noted in the **Background** section above, setting the folder type via **desktop.ini** files makes the folder type setting _permanent_ because it’s part of the folder, instead of just a registry setting.

How to Download and Install[](#how-to-download-and-install)
-----------------------------------------------------------

[![](https://github.com/LesFerch/WinSetView/assets/79026235/0188480f-ca53-45d5-b9ff-daafff32869e)
Download the zip file](https://github.com/LesFerch/SetFolderType/releases/download/1.0.4/SetFolderType.zip)

**Note**: Some antivirus software may falsely detect the download as a virus. This can happen any time you download a new executable and may require extra steps to whitelist the file.

1.  Download the zip file using the link above.
2.  Extract **SetFolderType.exe**.
3.  Right-click **SetFolderType.exe**, select Properties, check **Unblock**, and click **OK**.
4.  Move **SetFolderType.exe** to the folder of your choice (you need to keep this file). Keep the **Language.ini** file with the Exe if your language is not English.
5.  Double-click **SetFolderType.exe** to open the Install/Remove dialog and click **Yes** to install.
6.  If you skipped step 3, then, in the SmartScreen window, click **More info** and then **Run anyway**.
7.  Click **OK** when the **Done** message box appears.

![](https://github.com/LesFerch/SetFolderType/assets/79026235/76c1791b-12ff-4df1-a6ed-b5555389147f)

![](https://github.com/LesFerch/SetFolderType/assets/79026235/4176f8c5-78cc-41b8-ab63-0f53a918f891)

**Note**: Sometimes the **Done** message pops up behind another open window. If that happens, you should see the SetFolderType icon on the taskbar, where you can click to bring that dialog to the front. Alternatively, you can minimize the window(s) that are on top of the dialog.

**Note**: If you move **SetFolderType.exe** after installing, the context menu entries will do nothing because the exe path will be incorrect. To fix that issue, just run the install again (as descibed in Step 5 above).

### Command line Installation and Removal[](#command-line-installation-and-removal)

If you wish to install or remove the tool via the command line, usse these commands:

`SetFolderType /install`

`SetFolderType /remove`

### About the context menu[](#about-the-context-menu)

The context menu item is created with registry entries only and simply provides submenus entries for each folder type. When one of those items are selected, SetFolderType.exe is run with the appropriate arguments to set the selected folder type for the selected folder tree.

This program does NOT create a context menu handler. That is, there is no code that runs when you right-click a folder. Code only runs when you actually select an action (i.e. select a folder type that you want applied). SetFolderType will add no overhead to your context menu, other than the insignificant impact of one more context menu item.

How to Use[](#how-to-use)
-------------------------

Right-click any folder and you should see the SetFolderType context menu:

![](https://github.com/LesFerch/SetFolderType/assets/79026235/8462baf2-e131-436b-954e-ff7ee58b8c88)

Select the folder type you want applied to the folder. This will create (or edit any existing) **desktop.ini** file in the selected folder and ALL of its subfolders, all the way down the tree.

**Note**: Hold down the **Ctrl** key when selecting the folder type to apply the folder type to only the current folder and none of its subfolders.

### Patience![](#patience)

Although SetFolderType is very fast at populating all the subfolders with **desktop.ini** files, it’s up to Explorer to update the view. Explorer does that in the background as it notices the addition (or change) of the desktop.ini files. How long it will take is variable. It depends on the speed of the computer, what other processes are running, how many folders are affected, and so forth. But it can often take 30 seconds or so for all the folder views to update. So, before you jump onto GitHub and post an issue, relax, do something else for a minute and then go back and check your folders. You should see that Explorer did its thing and updated the view.

### The view won’t change if you’re looking at it![](#the-view-wont-change-if-youre-looking-at-it)

Explorer will not update the folder’s view until the folder is closed. However, having an open folder only stops the view update for that particular folder level. The subfolder’s views will update even if you have the parent folder open.

### The target folder must be on a Local Disk that’s formatted NTFS[](#the-target-folder-must-be-on-a-local-disk-thats-formatted-ntfs)

If the target folder is not both a **Local Disk** and **NTFS**, an error message, indicating which criteria are met (or not), will be displayed. Here’s all three error possibilities:

![](https://github.com/LesFerch/SetFolderType/assets/79026235/e5087ec9-1d2b-448a-b27a-f68cc6143828)
 ![](https://github.com/LesFerch/SetFolderType/assets/79026235/214496f2-05a8-4287-9c1a-63617758b3a8)
 ![](https://github.com/LesFerch/SetFolderType/assets/79026235/024cb983-49b6-4c0e-a6a8-28e5eab51d8f)

### Remove Desktop.ini Files[](#remove-desktopini-files)

If you select **(None)** from the context menu, SetFolderType will remove all desktop.ini files from the entire selected folder tree. This will work on all drive types and files systems. The check for Local Disk and NTFS is skipped for this action.

It’s Multilingual![](#its-multilingual)
---------------------------------------

Here’s an example of SetFolderType installed for German (de-DE):

![](https://github.com/LesFerch/SetFolderType/assets/79026235/a8bc53e2-80b8-4717-877c-1fcea1e8334d)

SetFolderType will detect your Windows language and use it, as long as it can find the **Shell32.dll.mui** file for your current language. If that file is missing, you will see this error:

![](https://github.com/LesFerch/SetFolderType/assets/79026235/ed823d95-607b-45c8-b97a-8d20bcfca42e)

This error often occurs if you just installed a new language. Windows sometimes takes a long time to populate the language folder with the MUI files. Sometimes you just have to wait a few minutes. Other times, the MUI files don’t show up until you run Windows Update. For some reason, just running Windows Update to check and/or get the latest updates forces the language installation to complete.

If you get that error but are OK with English, you may click **OK** and continue to install the tool with English context menu entries. If the missing MUI file is added later, you can simply double-click **SetFolderType.exe** again to install it in the correct language. The install always removes any of its previous context menu entries before creating new ones.

If the MUI file is found, the Install/Remove dialog will appear in the correct language:

![](https://github.com/LesFerch/SetFolderType/assets/79026235/4fa9adbd-3cf3-4e89-aff2-023f5d7472db)

**Note for Vietnamese**: On Windows 10, the file **C:\\Windows\\System32\\vi-VN\\Shell32.dll.mui** may be missing. Without this file, SetFolderType will not be able to provide a **Vietnamese** display. One way to fix this issue is to copy the missing file from a Windows 11 computer that has the Vietnamese language installed.

Help![](#help)
--------------

Selecting **Help** from the context menu opens this Readme file.  
  
[![](https://github.com/LesFerch/WinSetView/assets/79026235/63b7acbc-36ef-4578-b96a-d0b7ea0cba3a)
](https://github.com/LesFerch/SetFolderType)

This site is open source. [Improve this page](https://github.com/LesFerch/SetFolderType/edit/main/README.md).

↑↓⇔⇧⇩