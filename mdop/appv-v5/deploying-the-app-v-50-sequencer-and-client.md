---
title: 部署 App-V 5.0 排序器和用戶端
description: 部署 App-V 5.0 排序器和用戶端
author: dansimp
ms.assetid: 84cc84bd-5bc0-41aa-9519-0ded2932c078
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 647ea12018bf966592b9e831d532c7c08093d367
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800633"
---
# 部署 App-V 5.0 排序器和用戶端


App-v 5.0 排序器和用戶端可讓系統管理員虛擬化並執行虛擬化的應用程式。

## 部署用戶端


App-V 5.0 用戶端是在目的電腦上執行虛擬化應用程式的元件。 用戶端可讓使用者與圖示互動，並按兩下檔案類型，讓他們可以啟動虛擬化的應用程式。 用戶端也可以從管理伺服器取得虛擬應用程式內容。

[如何部署 App-V 用戶端](how-to-deploy-the-app-v-client-gb18030.md)

[如何解除安裝 App-V 5.0 Client](how-to-uninstall-the-app-v-50-client.md)

[如何在同一部電腦上部署 app-v 4.6 和 App-v 5.0 用戶端](how-to-deploy-the-app-v-46-and-the-app-v--50-client-on-the-same-computer.md)

## 用戶端配置設定


App-v 5.0 用戶端將其設定儲存在註冊表中。 如果您瞭解註冊表中的資料格式，就可以收集一些有關用戶端的有用資訊。 您也可以透過變更登錄專案來設定多個用戶端動作。

[關於 Client 組態設定](about-client-configuration-settings.md)

## 使用 ADMX 範本和群組原則設定用戶端


您可以使用 Microsoft ADMX 範本來設定 App-V 5.0 用戶端和遠端桌面服務用戶端的用戶端設定。 ADMX 範本利用現有的群組原則基礎結構管理常見的用戶端設定，其中包含 App-v 5.0 用戶端設定的設定。

**重要** 您可以從 Microsoft 下載中心取得 App-v 5.0 ADMX 範本。

 

下載並安裝 ADMX 範本之後，請在您將用來管理群組原則的電腦上執行下列步驟。 這通常是網網域控制站。

1.  將**admx**檔案儲存到下列目錄： **Windows \\ PolicyDefinitions**

2.  將**adml**檔案儲存到下列目錄： **Windows \\ PolicyDefinitions \\ &lt; &gt; 語言目錄**

完成上述步驟之後，您可以使用**群組原則管理**主控台來管理 app-v 5.0 用戶端配置設定。

App-v 5.0 用戶端也會將其設定儲存在註冊表中。 如果您瞭解註冊表中的資料格式，就可以收集一些有關用戶端的有用資訊。 您也可以透過變更登錄專案來設定多個用戶端動作。

[如何使用 ADMX 範本和群組原則來修改 App-V 5.0 用戶端組態](how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md)

## 使用 [共用內容存放區模式] 部署用戶端


App-V 5.0 共用內容存儲區（SCS）模式可讓 SCS App-V 5.0 用戶端執行虛擬化的應用程式，而不會在本機儲存任何相關聯的套件資料。 所有必要的虛擬化套件資料都是透過網路傳輸;因此，您應該只在具有快速連接的環境中使用 SCS 模式。 [SCS] 模式支援遠端桌面服務（RDS）和標準版的 App-v 5.0 用戶端。

**重要** 如果 App-v 5.0 用戶端設定為在 SCS 模式中執行，則必須提供 App-v 5.0 套件從哪個位置進行流式處理，否則虛擬化套件將會失敗。 此外，我們不建議您將虛擬化的應用程式部署到透過網際網路的 SCS 模式中執行 App-V 5.0 用戶端的電腦上。

 

此外，SCS 不是包含虛擬化套件的實體位置。 它是一種允許 App-v 5.0 用戶端在網路上傳輸所需虛擬化套件資料的模式。

SCS 模式在下列案例中很有用：

-   虛擬桌面基礎結構（VDI）部署

-   遠端桌面服務（RDS）部署

若要在您的環境中使用 SCS，您必須啟用 App-v 5.0 用戶端，才能在 SCS 模式中執行。 安裝期間應指定此設定。 根據預設，用戶端未設定為使用 SCS 模式。 如果您打算使用 SCS，您應該使用建議的程式來安裝用戶端。 不過，您可以在執行 App-v 5.0 用戶端的電腦上輸入下列 PowerShell 命令，來設定現有的 App-v 5.0 用戶端在 SCS 模式中執行：

**AppvClientConfiguration-SharedContentStoreMode 1**

在 SCS 模式中，可能會有系統管理員預先載入一些在執行 App-v 5.0 用戶端的電腦上的虛擬應用程式。 您可以使用 PowerShell 命令來新增、發佈及裝載套件來完成此工作。 例如，如果您已在所有電腦上預載入套件，系統管理員可以使用 PowerShell 命令來新增、發佈及裝載套件。 套件不會在網路上傳輸，因為它會在本機儲存。

[如何安裝 App-V 5.0 用戶端以使用共用內容存放區模式](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md)

## 部署排序器


Sequencer 是一個工具，可用於將標準應用程式轉換成虛擬套件，以便部署到執行 App-v 5.0 用戶端的電腦。 排序器可提供簡單且可預測的轉換程式，並將對預先排序工作流程所做的變更降至最低。 此外，排序器還能讓使用者更輕鬆地設定應用程式，以啟用虛擬化應用程式的連線。

如需 App-v 5.0 排序器中的變更清單，請參閱[app-v 5.0 的新增功能](whats-new-in-app-v-50.md)。

[如何安裝 Sequencer](how-to-install-the-sequencer-beta-gb18030.md)

## <a href="" id="---------app-v-5-0-client-and-sequencer-logs"></a> App-v 5.0 用戶端和 Sequencer 記錄


您可以使用 App-v 5.0 Sequencer 記錄資訊，協助您使用 App-v 5.0 來疑難排解排序程式安裝和操作事件。 使用**事件檢視器**，可以檢查與 Sequencer 相關的記錄資訊。 下列行顯示與 Sequencer 相關事件的特定路徑：

**事件檢視器 \\ 應用程式和服務記錄 \\ Microsoft \\ App V**。使用**AppV \ _Sequencer**預置與 Sequencer 相關的事件。 用戶端相關事件會預先加上**AppV \ _Client**。

在 App-v 5.0 SP3 中，已合併了一些記錄。 請參閱[關於 App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)。

## 部署排序器和用戶端的其他資源


[部署 App-V 5.0](deploying-app-v-50.md)

[為 App-V 5.0 進行規劃](planning-for-app-v-50-rc.md)






 

 





