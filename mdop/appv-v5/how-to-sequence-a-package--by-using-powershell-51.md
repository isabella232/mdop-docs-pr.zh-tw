---
title: 如何使用 PowerShell 對套件進行排序
description: 如何使用 PowerShell 對套件進行排序
author: dansimp
ms.assetid: 6134c6be-937d-4609-a516-92d49154b290
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e1bc2933fdb64080dab3b514784e7f68b0236df9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800407"
---
# 如何使用 PowerShell 對套件進行排序


使用下列程式來建立使用 PowerShell 的新 App-v 5.1 套件。

**記事** 在您使用此程式之前，您必須先將相關聯的安裝程式檔案複製到執行排序器的電腦，並閱讀並瞭解[app-v 5.1 排序器和用戶端部署規劃](planning-for-the-app-v-51-sequencer-and-client-deployment.md)的排序器區段。

 

**使用 PowerShell 建立新的虛擬應用程式**

1.  安裝 App-v 5.1 排序器。 如需有關安裝排序器的詳細資訊，請參閱[如何安裝排序](how-to-install-the-sequencer-51beta-gb18030.md)器。

2.  若要開啟 PowerShell 主控台，請按一下 [**開始**]，然後輸入**powershell**。 以滑鼠右鍵按一下 **Windows PowerShell**，並選取 **\[以系統管理員身分執行\]**。

3.  使用 PowerShell 主控台，輸入下列內容：匯**入-模組 appvsequencer**。

4.  若要建立套件，請使用**AppvSequencerPackage** Cmdlet。 建立套件需要下列參數：

    -   **Name （名稱**）-指定套件的名稱。

    -   **PrimaryVirtualApplicationDirectory** -指定將用來安裝應用程式的目錄路徑。 這個路徑必須存在。

    -   **安裝**程式-指定關聯應用程式安裝程式的路徑。

    -   **Path** -指定套件的輸出目錄。

    例如：

    **新-AppvSequencerPackage- &lt; package &gt; -PrimaryVirtualApplicationDirectory 路徑的名稱， &lt; 這些路徑指向 &gt; &lt; 安裝程式可執行檔的安裝程式可執行檔 &gt; -OutputPath &lt; 目錄&gt;**

    等待排序器建立套件。 使用 PowerShell 建立套件可能需要一些時間。 如果未成功建立套件，則會傳回錯誤。

    下列清單顯示可搭配使用**AppvSequencerPackage** Cmdlet 使用的其他可選參數：

    -   AcceleratorFilePath –指定要產生套件的加速器 .cab 檔案路徑。

    -   InstalledFilesPath-指定應用程式的本機已安裝檔案的儲存路徑。

    -   InstallMediaPath-指定安裝媒體位置的路徑

    -   TemplateFilePath-如果您想要自訂先後順序程式，請指定範本檔案的路徑。

    -   FullLoad-指定套件必須完全下載到執行 App-v 5.1 的電腦，才能開啟 App。

    您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[使用 PowerShell 管理 App-V 5.1](administering-app-v-51-by-using-powershell.md)

 

 





