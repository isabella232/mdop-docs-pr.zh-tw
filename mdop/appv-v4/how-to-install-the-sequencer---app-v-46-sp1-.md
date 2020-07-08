---
title: 如何安裝排序器（App-v 4.6 SP1）
description: 如何安裝排序器（App-v 4.6 SP1）
author: dansimp
ms.assetid: fe8eb876-28fb-46ae-b592-da055107e639
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 611564e861d65dcd357c58732fb60dab21c05abe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801350"
---
# 如何安裝排序器（App-v 4.6 SP1）


Microsoft Application Virtualization （App-v） Sequencer 會監視並記錄應用程式的安裝與設定程式，讓應用程式可以作為虛擬應用程式執行。 您應該在只安裝作業系統的電腦上安裝 App-v 排序器。 或者，您也可以在虛擬環境中執行的電腦上安裝 Sequencer （例如虛擬電腦）。 這個方法很實用，因為您可以更輕鬆地維護乾淨的順序環境，讓您可以使用最低的額外設定重複使用。

您必須在所用的電腦上擁有系統管理認證，才能對應用程式進行排序，且電腦不得執行任何版本的 App-v 用戶端。 使用 App-v 排序器建立虛擬應用程式需要多個作業，所以請務必在符合或超過[應用程式虛擬化排序器硬體和軟體需求](application-virtualization-sequencer-hardware-and-software-requirements.md)的電腦上安裝 Sequencer。

**注意**  
在安全模式中執行 App-v 排序器不受支援。



**若要安裝 Microsoft Application Virtualization 排序器**

1.  將 Microsoft Application Virtualization Sequencer 安裝檔案複製到您要安裝它的電腦上。

2.  若要啟動 Microsoft Application Virtualization Sequencer 安裝精靈，請按兩下 [ **Setup.exe**]。 如果在安裝前沒有偵測到**Microsoft Visual c + + SP1 可再發行套件（x86）** ，請按一下 [**安裝**] 以安裝必要的先決條件。

3.  若要繼續安裝，請在 [**歡迎**] 頁面上，按一下 **[下一步]**。

4.  若要接受授權合約條款，請在 [**授權協定**] 頁面上，按一下 **[我接受授權合約中的條款**]，然後按一下 **[下一步]**。

5.  若要接受預設安裝資料夾，請在 [**目的地資料夾**] 頁面上，按一下 **[下一步]**。 若要指定不同的目的地資料夾，請按一下 [**變更**]，然後指定安裝所用的安裝資料夾。 按 **\[下一步\]**。

6.  在**虛擬磁片磁碟機**頁面上，若要將應用程式虛擬化預設磁片磁碟機**Q:\\** （預設）設定為所有順序應用程式將從哪個磁碟機執行，請按 **[下一步]**。 如果您想要指定不同的磁片磁碟機盤符，請使用清單並選取您要使用的磁片磁碟機盤符，方法是選取適當的磁片磁碟機盤符，然後按 **[下一步]**。

    **重要**  
    在這個步驟中指定的應用程式虛擬化磁片磁碟機盤符就是虛擬應用程式將從目的電腦上執行的磁片磁碟機字母。 指定的磁碟機盤符必須提供，且目前未在執行 App-v 用戶端的電腦上使用。 如果指定的磁碟機已在使用中，虛擬應用程式會在目的電腦上失敗。



7.  在 [**準備好安裝程式**] 頁面上，按一下 [**安裝**]。

8.  在 [ **InstallShield 嚮導已完成]** 頁面上，若要關閉安裝精靈並開啟 app-v 排序器，請按一下 **[完成**]。 若要關閉 [安裝精靈] 而不開啟排序器，請清除 [**啟動程式**]，然後按一下 **[完成]**。

    **注意**  
    如果您在執行虛擬環境的電腦（例如虛擬電腦）上安裝 App-v 排序器，您現在必須拍攝快照。 當您將應用程式排序之後，您可以還原到這個影像，因此您可以將下一個應用程式序列化。



~~~
When you uninstall the Sequencer, the following registry keys are not removed from the computer that the Sequencer was installed on. Additionally, you must restart the computer after you have uninstalled the Sequencer so that all associated drivers can be stopped and the operation can be completed.

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid**

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5**

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard**

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\SecKey**
~~~

## 相關主題


[設定 Application Virtualization Sequencer (App-V 4.6 SP1)](configuring-the-application-virtualization-sequencer--app-v-46-sp1-.md)









