---
title: 設定 UE-V 2. x 的公司設定中心
description: 設定 UE-V 2. x 的公司設定中心
author: dansimp
ms.assetid: 48fadb0a-c0dc-4287-9474-f94ce1417003
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0226b3c156a6d6ca39b0214de8acf0c5990db349
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809867"
---
# 設定 UE-V 2. x 的公司設定中心


Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 和 2.1 SP1 包含新的應用程式，即 [公司設定中心]，可協助使用者管理同步處理的設定。 [公司設定中心] 是使用 UE-V Agent 來安裝的。 使用者存取 [控制台] 中的 [公司設定中心]、[**開始**] 功能表或 [**開始**] 畫面，以及透過 ue-v 通知區域圖示。 [公司設定中心] 會顯示已同步處理的設定，並可協助使用者查看 UE-V 的同步處理狀態。 使用者可以使用公司設定中心來選取哪些應用程式或 Windows 功能在電腦之間同步處理其設定。 他們也可以按一下 [**立即同步**處理] 按鈕，立即同步處理所有設定。 系統管理員也可以在 [公司設定中心] 中包含支援連結。

## 關於公司設定中心


[公司設定中心] 桌面應用程式會為使用者提供 UE-V 設定同步處理的相關資訊。 [公司設定中心] 有幾種不同的方式可供存取：

-   通知區域圖示：啟用**工作列圖示**群組原則設定或 Windows PowerShell 設定之後，就會在通知區域中出現 ue-v 圖示。 按一下 UE-V 圖示以開啟 [公司設定中心]。

    **記事** 您可以使用下列設定停用通知區域圖示：

    -   群組原則設定： `Policy Tray Icon`

    -   Windows PowerShell Cmdlet： `TrayIconEnabled`

    -   SystemCenter2012 ConfigurationManager 的 UE-V Configuration Pack 中的 [設定] 專案： `Tray icon enabled`

     

-   [控制台] 應用程式-在 [控制台] 中，流覽至 [**外觀及個人**化]，然後按一下 [**公司設定中心**]。

-   第一次使用通知–除非停用，否則 UE-V Agent 會提醒使用者，在電腦第一次執行 UE-V agent 時，這些設定會立即同步處理。 按一下 [通知] 對話方塊以開啟 [公司設定中心]。

-   [**開始**] 畫面或 [**開始**] 功能表包含 [公司設定中心] 的連結。 [在公司設定中心搜尋] 會找到應用程式。

## 在公司設定中心設定支援連結


[公司設定中心] 可以加入超連結，讓使用者按一下即可取得與 UE-V 設定同步處理問題的支援。 此連結可以開啟任何有效的 URL 通訊協定，例如網頁的 HTTP://或電子郵件的 mailto://。 支援連結可以使用 [群組原則]、[Windows PowerShell] 或 [System Center 2012 Configuration Manager UE-V Configuration Pack] 進行設定。

**如何設定公司設定中心支援連結**

1.  開啟您慣用的管理工具：

    -   **群組原則**-如果您尚未這麼做，請從[MDOP 管理範本](https://go.microsoft.com/fwlink/p/?LinkId=393941)下載 ue-v 2 的 ADMX 範本。

    -   **Windows powershell** -在已安裝 ue-v agent 的電腦上，開啟**Windows PowerShell**。 如需使用 Windows PowerShell 管理 UE-V 的詳細資訊，請參閱[使用 Windows powershell 和 WMI 管理 ue-v 2.](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

    -   **適用于 Microsoft 使用者體驗虛擬化（ue-v）的 System Center 2012 Configuration pack** -匯入 Ue-v 設定套件，然後遵循配置套件檔來建立設定項目。 如需 UE-V Configuration Pack 的詳細資訊，請參閱[使用 System Center Configuration Manager 2012 設定 ue-v 2. x](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md)。

2.  編輯下列原則的設定：

    -   **連絡人連結文字**-此設定會指定公司設定中心中的 [連絡人 IT URL] 超連結的文字。 如果您啟用這項設定，[公司設定中心] 會在連結中顯示特定的文字給連絡人的 URL。

        -   群組原則設定： `Contact IT Link Text`

        -   Windows PowerShell Cmdlet： `ContactITDescription`

        -   配置包設定專案： `IT contact descriptive text`

    -   [聯絡人] **url** -此設定會以有效的 URL 通訊協定（例如網頁的 HTTP://或電子郵件的 mailto://），指定 [公司設定] 中的 [連絡人] 連結的 URL。

        -   群組原則設定： `Contact IT URL`

        -   Windows PowerShell Cmdlet： `ContactITUrl`

        -   配置包設定專案： `IT contact URL`

3.  使用管理工具將設定部署至使用者的電腦。






 

 





