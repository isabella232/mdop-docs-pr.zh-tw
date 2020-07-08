---
title: 設定 MED-V 的 Windows 虛擬電腦映像
description: 設定 MED-V 的 Windows 虛擬電腦映像
author: dansimp
ms.assetid: d87a0df8-9e08-4d1e-bfb0-9dc3cebf0d28
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 340754b33576651c8ba89c85f369c48c0a0ab957
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811984"
---
# 設定 MED-V 的 Windows 虛擬電腦映像


在您已安裝想要包含在 MED-V 影像中的所有內容之後，您可以設定在 Microsoft 企業桌面虛擬化（MED-V）2.0 中使用的影像。 本節中的主題提供在建立 MED-V 工作區套件之前，先設定您的 MED-V 影像以執行第一次安裝程式的指導方針。

第一次設定為最終使用者準備 MED-V 工作區。 此程式會從在 MED-V 工作區封裝的影像建立虛擬機器，然後在虛擬機器上執行 Windows 迷你設定。 這包括執行自訂安裝程式腳本和第一次安裝完成應用程式時，FtsCompletion.exe。

請依照下列步驟來設定您的 MED-V 影像，以便在第一次執行安裝：

1. 作為選項，您可以壓縮虛擬硬碟（VHD）來回收空白磁碟空間，並減少 VHD 大小，然後再繼續設定 Windows 虛擬電腦影像。 如需詳細資訊，請參閱[壓縮 Med-v 虛擬硬碟](compacting-the-med-v-virtual-hard-disk.md)。

2. 自訂虛擬機器設定處理常式。

3. 使用 Sysprep 來密封 MED-V 影像。

   **自訂虛擬機器設定處理常式**

4. 在使用 MED-V 準備您的影像時，您可以設定虛擬機器上的各種設定，例如指定執行 Windows Update 的設定。 在建立 MED-V 工作區套件之前，請先指定所有必要的虛擬機器設定。

5. 在您建立 MED-V 工作區套件之前，我們建議您停用虛擬機器上的還原點，以避免差異磁片無限增加。 如需詳細資訊，請參閱[如何在 WINDOWS XP 中關閉及開啟系統還原](https://go.microsoft.com/fwlink/?LinkId=195927)（ https://go.microsoft.com/fwlink/?LinkId=195927) 。

   **注意**  
   您可以設定您的 Sysprep.inf 檔案，以便在第一次執行設定時停用還原點。 如需設定此 GuiRunOnce 金鑰的範例，請參閱本節稍後的範例 Sysprep.inf 檔案範例。



6. 將安裝程式設定為執行 [最小化安裝]，而不是預設的 [Windows 歡迎畫面]。 您必須使用 **-迷你**開關執行 Sysprep 工具，或選取圖形使用者介面中的 [ **MiniSetup** ] 核取方塊。 如需詳細資訊，請參閱[如何使用 Sysprep 來密封影像](#bkmk-seal)。

   **第一次設定完成檔案時呼叫**

   1.  在安裝 MED-V 來賓代理程式的過程中，會包含稱為 FtsCompletion.exe 的可執行檔。 根據預設，它位於 [程式檔] 下的 MED-V 影像系統磁碟機中 **-Microsoft 企業桌面虛擬化**。

       **重要**  
       當您第一次設定處理常式中的最後一個步驟，您必須執行這個可執行程式。 要呼叫的可執行程式的使用者必須是來賓的本機系統管理員群組的成員。



   2.  您可以決定您要如何呼叫此可執行程式，例如，透過使用 MED-V 工作區部署的腳本進行。 您可以呼叫此可執行檔做為 Sysprep.inf 檔案的最後一行。 如需如何在您的 Sysprep.inf 檔案中呼叫此可執行程式的範例，請參閱本節稍後的範例檔案。

在您完成 MED-V 影像的自訂之後，您就可以使用 Sysprep 來密封影像。

<a href="" id="bkmk-seal"></a>**使用 Sysprep 來密封 MED-V 影像**

1.  系統準備工具（Sysprep）是一種技術，您可以用來在整個網路中執行以影像為基礎的安裝，只要由管理員或 IT 專業人員來干預就能輕鬆。

2.  在 MED-V 環境中，您可以使用 Sysprep，在第一次啟動時，將唯一的安全識別碼（SID）及其他設定指派給每個 MED-V 工作區。

    **注意**  
    如需如何使用 Sysprep 的詳細資訊，請參閱[Sysprep 技術參考](https://go.microsoft.com/fwlink/?LinkId=195930)（ https://go.microsoft.com/fwlink/?LinkId=195930) 。



~~~
**Caution**  
When you use non-ASCII characters in the Sysprep.inf file, you must save the file by using the encoding appropriate for the characters entered. Windows XP expects the Sysprep.inf file to be encoded by using the code page for the language that you are targeting.

You must also make sure that the System Locale of the computers to which the MED-V workspace is deployed is set to handle the language specific characters that might be present in the Sysprep.inf file. To change the settings for the System Locale, follow these steps:

1.  To open Region and Language, click **Start**, click **Control Panel**, and then click **Region and Language**.

2.  Click the **Administrative** tab, and then click **Change System Locale** under **Language for non-Unicode programs**.

    If you are prompted for an administrator password or confirmation, type the administrator password or provide confirmation.

3.  Select your preferred language and then click **OK**.



**To configure Sysprep on the MED-V Guest Computer**

1.  Create a folder named *Sysprep* in the root of the MED-V image system drive.

2.  Download the deploy.cab file. For more information, see [Windows XP Service Pack 3 Deployment Tools](https://go.microsoft.com/fwlink/?LinkId=195928) From the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=195928).

3.  From the deploy.cab file, copy or extract the Setupmgr.exe, Sysprep.exe, and Setupcl.exe files to the Sysprep folder.

4.  In the Sysprep folder, run **Setup Manager** (Setupmgr.exe) to create a Sysprep.inf answer file.

    Or, you can create this file manually or use your company’s existing file. For more information, see [How to use the Sysprep tool to automate successful deployment of Windows XP](https://go.microsoft.com/fwlink/?LinkId=195929) (https://go.microsoft.com/fwlink/?LinkId=195929).

5.  Follow the **Setup Manager** wizard.

    **Important**  
    You must configure the MED-V guest to join a domain that lets users log on by using the credentials that they use to log on to the MED-V host.



    **Caution**  
    When you configure a proxy account for joining virtual machines to the domain, know that it is possible for an end user to obtain the proxy account credentials. Take all the necessary security precautions to minimize risk, such as limiting account user rights. For more information about security concerns when you configure a Windows Virtual PC image for MED-V, see [Security Best Practices for MED-V Operations](security-best-practices-for-med-v-operations.md).



    If end users must provide information during the first time setup process based on the parameters specified in the Sysprep.inf file, you must also specify that first time setup is run in **Attended** mode when you are creating your MED-V workspace package. If no information will be required from the end user, you can specify that first time setup is run in **Unattended** mode when you are creating your MED-V workspace package. For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).

    Although you can specify any settings that you prefer, a MED-V best practice is that you create the Sysprep.inf file so that first time setup can be run in **Unattended** mode. This requires that you provide all of the required settings information as you continue through the **Setup Manager** wizard.

    **Caution**  
    If you have set a local policy or registry entry to include a service level agreement (SLA) in your image (VHD), you must specify that first time setup is run in **Attended** mode or first time setup will fail. Or, a MED-V best practice is to enforce the SLA through Group Policy later so that the SLA is displayed to the end user after first time setup is finished.



    **Note**  
    You can configure the MED-V workspace to set certain Sysprep.inf settings based on the configuration of the host and the identity of the end user. For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).



6.  Seal the MED-V image.

    **Important**  
    We recommend that you make a backup copy of the MED-V image before sealing it.



    After you have completed all the steps in the **Setup Manager** wizard, you are ready to run Sysprep to seal the MED-V image.

**To run Sysprep**

1.  Run the System Preparation Tool (Sysprep.exe) from the *Sysprep* folder that you created when you configured Sysprep in the MED-V virtual machine.

2.  In the warning message box that appears, click **OK**.

3.  In the **Options** dialog box, select the **Don't reset grace period for activation** and **Use Mini-Setup** check boxes. Also, make sure that the **Shutdown mode** box is set to **Shut down**.

4.  Click **Reseal**. This removes identity information and clears event logs to prepare for first time setup.

5.  If you are not satisfied with the information listed in the confirmation message box that appears, click **Cancel** and then change the selections.

6.  Click **OK** to complete the system preparation process.

After you have run Sysprep on your MED-V image, the virtual machine shuts down and is ready for use in creating a MED-V workspace.
~~~

## 範例


以下是 Sysprep.inf 檔案的範例。

``` syntax
;SetupMgrTag
[GuiUnattended]
    EncryptedAdminPassword=NO
    TimeZone=10
    OEMDuplicatorstring="MED_V v2 Host"
    AdminPassword="administrator"
    AutoLogon=Yes
    AutoLogonCount=1
    OEMSkipRegional=1
    OemSkipWelcome=1

[UserData]
    ProductKey=
    FullName="MED-V User"
    OrgName="Contoso"
    ComputerName=*

[Identification]
    JoinDomain=domain.corp.contoso.com
    DomainAdmin=UserName
    DomainAdminPassword=Password

[Networking]
    InstallDefaultComponents=Yes

[Branding]
    BrandIEUsingUnattended=Yes

[Proxy]
    Proxy_Enable=0
    Use_Same_Proxy=0

[Unattended]
    InstallFilesPath=C:\sysprep\i386
    TargetPath=\WINDOWS
    UpdateServerProfileDirectory=1
    OemSkipEula=Yes

[RegionalSettings]
    LanguageGroup=1
    Language=00000409

[GuiRunOnce]
    Command0="wmic /namespace:\\root\default path SystemRestore call Disable %SystemDrive%\"
    Command1="c:\Program Files\Microsoft Enterprise Desktop Virtualization\FtsCompletion.exe"

[sysprepcleanup]
```

## 相關主題


[建立 MED-V 工作區套件](create-a-med-v-workspace-package.md)

[準備 MED-V 映像](prepare-a-med-v-image.md)









