---
title: 如何安裝 MBAM 搭配 Configuration Manager
description: 如何安裝 MBAM 搭配 Configuration Manager
author: dansimp
ms.assetid: fd0832e4-3b79-4e56-9550-d2f396be6d09
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a556ce961e6a423caecdd0766cf8623383897b58
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810970"
---
# 如何安裝 MBAM 搭配 Configuration Manager


本節說明使用 [開始] 中的 [[使用 MBAM 與 Configuration manager](getting-started---using-mbam-with-configuration-manager.md)] 來安裝 MBAM 與 configuration manager 的步驟。 這些步驟分為下列任務：

-   在 Configuration Manager 伺服器上安裝和設定 MBAM

-   在資料庫伺服器上安裝復原和審核資料庫

-   在管理和監控伺服器上安裝管理和監控伺服器功能

開始安裝之前，請先確定您已編輯或建立必要的 mof 檔案。 如需相關指示，請參閱[如何建立或編輯 mof](how-to-create-or-edit-the-mof-files.md)檔案。

**重要** 如果您使用的不是預設的 SQL Server Reporting Services （SSRS）實例，您必須使用下列命令列來啟動 MBAM 設定，以指定 SSRS 命名的實例：

`MbamSetup.exe CM_SSRS_INSTANCE_NAME=<NamedInstance>`

 

**在 Configuration Manager 伺服器上安裝 MBAM**

1.  在 Configuration Manager 伺服器上，執行**MBAMSetup.exe**以啟動 MBAM 安裝精靈。

    **記事** 若要取得安裝記錄檔，您必須使用 Msiexec 套件和 **/l** &lt; location &gt; 選項來安裝 Configuration Manager。 記錄檔案是在您指定的位置建立。

    在安裝 Configuration Manager 之使用者的電腦上，在 [% temp%] 資料夾中，會建立其他設定記錄檔。

     

2.  在 [**歡迎**] 頁面上，選擇性地選取 [**客戶經驗改進計畫**]，然後按一下 [**開始**]。

3.  閱讀並接受 Microsoft 軟體授權協定，然後按一下 **[下一步]** 繼續安裝。

4.  在 [**拓撲選取範圍**] 頁面上，選取 [ **System Center Configuration Manager 整合**]，然後按一下 **[下一步]**。

5.  在 [**選取要安裝的功能**] 頁面上，選取**System Center Configuration Manager 整合**。

    **記事** 在 [**檢查先決條件**] 頁面上，在 [安裝精靈] 檢查安裝的先決條件並確認沒有遺漏的情況下，按一下 **[下一步**]。 如果偵測到遺失的先決條件，您必須先解決遺失的先決條件，然後再次按一下 [**檢查必備元件]。**

     

6.  指定是否要使用 Microsoft 更新，協助保護您的電腦安全性，然後按 **[下一步]**。 使用 Microsoft 更新並不會開啟 Windows 中的自動更新。

7.  按 \[**下一步**\] 繼續。

8.  在 [**安裝摘要**] 頁面上，查看將要安裝的功能清單，然後按一下 [**安裝**] 以開始安裝 MBAM 功能。 如果您必須檢查或變更您的安裝設定，請按一下 [**返回**]，回到嚮導中，或按一下 [**取消**] 結束安裝程式。 安裝程式會安裝 MBAM 功能，並通知您安裝已完成。

9.  按一下 **[完成] 結束**嚮導。

**在資料庫伺服器上安裝復原和審核資料庫**

1.  在資料庫伺服器上，執行**MBAMSetup.exe**以啟動 MBAM 安裝精靈。

2.  在 [**歡迎**] 頁面上，選擇性地選取 [**客戶經驗改進計畫**]，然後按一下 [**開始**]。

3.  閱讀並接受 Microsoft 軟體授權協定，然後按一下 **[下一步]** 繼續安裝。

4.  在 [**拓撲選取專案**] 頁面上，選取 [ **System Center Configuration Manager 整合**拓撲]，然後按一下 **[下一步]**。

5.  從要安裝的功能清單中，選取 [**恢復資料庫**和**審核資料庫**]，然後清除其餘的功能。

    **記事** 安裝精靈會檢查安裝的先決條件，並顯示遺失的先決條件。 如果符合所有先決條件，安裝會繼續進行。 如果偵測到遺失的先決條件，您必須先解決遺失的先決條件，然後再次按一下 [**檢查必備元件**]。 如果此時間符合所有先決條件，安裝就會繼續。

     

6.  在 [**設定復原資料庫**] 頁面上，指定將執行 [管理及監視伺服器] 功能的電腦名稱稱。 部署管理和監視伺服器功能之後，它會使用其網域帳戶來連線至資料庫。

7.  按 \[**下一步**\] 繼續。

8.  指定要儲存恢復資料之資料庫的 SQL Server 實例名稱和名稱。 您也必須指定資料庫的位置和記錄資訊所在的位置。

9.  按一下 **[下一步]** ，繼續執行 MBAM 安裝程式安裝精靈。

10. 在 [**設定審核資料庫**] 頁面上，指定將用來存取報表資料庫的使用者帳戶。

11. 指定將執行管理和監視伺服器以及審核報告的電腦名稱稱。 在部署管理和監視及審核報告功能之後，就會使用其網域帳戶來連線至資料庫。

    **記事** 如果您在沒有 [審核報告] 功能的情況下安裝審核資料庫，您必須在審核資料庫電腦上新增例外狀況，才能在 Microsoft SQL Server 埠上啟用入站流量。 預設埠號碼是1433。

     

12. 指定要儲存審計資料之資料庫的 SQL Server 實例名稱與名稱。 您也必須指定資料庫和記錄資訊的存放位置。

13. 按一下 [**安裝**] 以開始安裝，然後按一下 **[完成]** 以完成安裝。

**若要在管理和監控伺服器上安裝管理和監控伺服器功能**

1.  在 [管理及監視伺服器] 上，執行**MBAMSetup.exe** ，啟動 [MBAM 安裝] 嚮導。

2.  在 [**歡迎**] 頁面上，選擇性地選取 [**客戶經驗改進計畫**]，然後按一下 [**開始**]。

3.  閱讀並接受 Microsoft 軟體授權協定，然後按一下 **[下一步]** 繼續安裝。

4.  在 [**拓撲選取專案**] 頁面上，選取 [ **System Center Configuration Manager 整合**拓撲]，然後按一下 **[下一步]**。

5.  從要安裝的功能清單中，選取 [**管理及監視伺服器**與**自助式入口網站**]，然後清除其餘的功能。

    **記事** 安裝精靈會檢查安裝的先決條件，並顯示遺失的先決條件。 如果符合所有先決條件，安裝會繼續進行。 如果偵測到遺失的先決條件，您必須先解決遺失的先決條件，然後再次按一下 [**檢查必備元件**]。 如果此時間符合所有先決條件，安裝就會繼續。

     

6.  若要安裝[和設定分散式伺服器上的 MBAM，](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md)請依照安裝**自助**入口網站一節中的步驟安裝自助式入口網站。

    **記事** 如果用戶端電腦將無法存取 Microsoft 內容傳遞網路（CDN），這會提供自助服務入口網站所需的特定 JavaScript 檔案存取權，完成在在分散式伺服器上**設定自助入口網站**以設定自助式入口網站，以將來自無障礙來源的 JavaScript 檔案的[安裝和設定 MBAM](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md)的步驟。

     

7.  [若要安裝和設定分散式伺服器上的 MBAM，請依照如何安裝及設定分散式伺服器上的](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md)，按照安裝**管理和監視伺服器功能**一節中的步驟安裝管理和監控伺服器功能一節。

8.  按一下 **[完成]** 以完成安裝。

## 相關主題


[如何使用 Configuration Manager 驗證 MBAM 安裝](how-to-validate-the-mbam-installation-with-configuration-manager.md)

[使用設定管理員來部署 MBAM](deploying-mbam-with-configuration-manager-mbam2.md)

 

 





