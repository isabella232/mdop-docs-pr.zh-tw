---
title: 部署 App-V 5.1 伺服器
description: 部署 App-V 5.1 伺服器
author: dansimp
ms.assetid: 987b61dc-00d6-49ba-8f1b-92d7b948e702
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2bcff2a3211ea3e2f666aff1d6f2ad919509aa3a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800625"
---
# 部署 App-V 5.1 伺服器

您可以使用本主題中所述的不同部署配置來安裝 Microsoft Application Virtualization （App-v）5.1 伺服器功能。 在您安裝伺服器功能前，請先參閱[app-v 5.1 安全性考慮](app-v-51-security-considerations.md)的伺服器區段。

如需有關部署 App-v Server 的資訊，請參閱[關於 app-v 5.1](about-app-v-51.md#bkmk-migrate-to-51)。

> [!IMPORTANT]
> 在您安裝並設定 App-v 5.1 伺服器之前，您必須指定將託管每個元件的埠。 您也必須新增相關聯的防火牆規則，以允許傳入要求存取指定的埠。 安裝程式不會修改防火牆設定。

## <a href="" id="---------app-v-5-1-server-overview"></a> App-V 5.1 伺服器概述

App-v 5.1 Server 是由五個元件所組成。 每個元件在 App-v 5.1 環境中都有不同的用途。 這裡簡要說明五個元件中的每一個：

- 管理伺服器-提供 App-V 5.1 基礎結構的整體管理功能。
- 管理資料庫–可協助 App-v 5.1 管理的資料庫 predeployments。
- 發佈伺服器-提供虛擬應用程式的託管與流式處理功能。
- 報表伺服器–提供 App-v 5.1 reporting services。
- 報告資料庫–協助 App-v 5.1 報告的資料庫 predeployments。

## <a href="" id="---------app-v-5-1-stand-alone-deployment"></a> App-v 5.1 獨立部署

App-v 5.1 獨立部署可為小型部署或測試環境提供良好的拓撲。 當您使用這種類型的實現時，所有伺服器元件都會部署到單台電腦上。 服務與相關聯的資料庫會爭用執行 App-v 5.1 元件之電腦上的資源。 因此，您不應該將這個拓朴用於較大型的部署。

[如何部署 App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md)

[如何使用指令碼來部署 App-V 5.1 伺服器](how-to-deploy-the-app-v-51-server-using-a-script.md)

## <a href="" id="---------app-v-5-1-server-distributed-deployment"></a> App-V 5.1 伺服器分散式部署

分散式部署拓撲可支援大型 App-v 5.1 用戶端基礎，並可讓您更輕鬆地管理和縮放您的環境。 當您使用這種類型的部署時，App-V 5.1 伺服器元件會根據組織的結構與需求，在多部電腦上部署。

[如何在與管理和報告服務不同的電腦上安裝管理和報告資料庫](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services51.md)

[如何在獨立電腦上安裝 Management Server 並將它連線到資料庫](how-to-install-the-management-server-on-a-standalone-computer-and-connect-it-to-the-database51.md)

[如何使用指令碼來部署 App-V 5.1 伺服器](how-to-deploy-the-app-v-51-server-using-a-script.md)

[如何在遠端電腦上安裝發佈伺服器](how-to-install-the-publishing-server-on-a-remote-computer51.md)

[如何在獨立電腦上安裝 Management Server 並將它連線到資料庫](how-to-install-the-management-server-on-a-standalone-computer-and-connect-it-to-the-database51.md)

## 使用企業軟體發佈（ESD）解決方案和 App-v 5。1

您也可以使用 ESD 來部署 app-v 5.1 用戶端和套件，而不需部署 App-v 5.1。 整合的完整功能會視您所使用的 ESD 而有所不同。

> [!NOTE]
> App-V 5.1 報表服務器與報告資料庫仍可在 ESD 中部署，以從 App-v 5.1 用戶端收集報告資料。 不過，不應該部署其他三個伺服器元件，因為它們會與 ESD 功能發生衝突。

[使用電子軟體發佈 (ESD) 來部署 App-V 5.1 封裝](deploying-app-v-51-packages-by-using-electronic-software-distribution--esd-.md)

## <a href="" id="---------app-v-5-1-server-logs"></a> App-v 5.1 Server 記錄

您可以使用 app-v 5.1 server 記錄資訊，協助您在使用 App-v 5.1 時，對伺服器安裝與操作事件進行疑難排解。 伺服器相關記錄資訊可以使用**事件檢視器**進行檢查。 下一行顯示與伺服器相關事件的特定路徑：

**事件檢視器 \\ 應用程式和服務記錄 \\ Microsoft \\ App V**

關聯的安裝記錄會儲存在下列目錄中：

**temp**

在 App-v 5.0 SP3 中，已整合並移動一些記錄。 請參閱[關於 App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)。

## <a href="" id="---------app-v-5-1-reporting"></a> App-V 5.1 報告

App-v 5.1 報告可讓 App-v 5.1 用戶端收集資料，然後再將資料傳送回儲存在中央儲存庫中。 您可以使用這項資訊，更清楚地瞭解貴組織內的虛擬應用程式使用量。 下列清單顯示 App-v 5.1 用戶端所收集的一些資訊類型：

- 有關執行 App-v 5.1 用戶端的電腦資訊。
- 在執行 App-v 5.1 用戶端之特定電腦上的虛擬化套件的相關資訊。
- 針對特定使用者開啟和關閉套件的相關資訊。

報告資訊將會保留，直到成功傳送到報表伺服器資料庫為止。 在資料庫中資料之後，您就可以使用 Microsoft SQL Server Reporting Services 來產生任何必要的報告。

如果您想要檢索報表資訊，您必須使用 Microsoft sql Server Reporting Services （SSRS），這可與 Microsoft SQL 搭配使用。 當您安裝應用程式 V 5.1 報表伺服器且必須單獨部署它才能產生相關聯的報表時，就不會安裝 SSRS。

如需[app-v 5.1 報告](about-app-v-51-reporting.md)的詳細資訊，請使用下列連結。

[如何使用 PowerShell 在 App-V 5.1 用戶端上啟用報表](how-to-enable-reporting-on-the-app-v-51-client-by-using-powershell.md)

## App-V 伺服器的其他資源

[部署 App-V 5.1](deploying-app-v-51.md)
