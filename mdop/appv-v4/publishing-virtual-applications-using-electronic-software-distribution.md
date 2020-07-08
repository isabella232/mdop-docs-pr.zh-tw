---
title: 使用電子軟體發佈來發佈虛擬應用程式
description: 使用電子軟體發佈來發佈虛擬應用程式
author: dansimp
ms.assetid: 295fbc1d-ed1c-43b4-aeee-0df384d4e630
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a0354fc1226aa78d947dd764a0ab6157b563a321
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800880"
---
# 使用電子軟體發佈來發佈虛擬應用程式


電子軟體發佈（ESD）系統的設計目的是將軟體高效地移動到許多不同的電腦，以進行緩慢或快速的網路連線。 使用 ESD 系統的應用程式虛擬化，您可以使用下列其中一種方法來散佈您的虛擬應用程式套件：

-   使用應用程式虛擬化排序器所產生的 Windows Installer 版本，將您的 ESD 系統設定為將套件直接發佈到每個用戶端電腦。 Windows 安裝程式檔案包含圖示、封裝定義資訊和內容，當您使用 Windows 安裝程式時，它會將圖示發佈到 Windows 桌面和 [開始] 功能表，並將套件內容載入到 Application Virtualization 用戶端快取中。 使用者無需任何進一步的設定需求，就能立即開始使用應用程式。 將套件升級至較新版本的做法是使用 Windows 安裝程式卸載 package.msi 檔案，然後再安裝新版本。

-   將套件內容放在可在具有良好頻寬的網路連線（例如局域網）上的網路連線中輕鬆存取的軟體發佈點或應用程式虛擬化資料流程伺服器。 例如，您可能會在每個分支辦公室中使用現有的 ESD 系統發佈點電腦。 使用命令列參數定義用戶端將處理虛擬應用程式套件的資料流程來源，ESD 系統會將套件的 Windows Installer 版本部署到每個用戶端。 ESD 系統也可以用來將包含套件內容的 SFT 檔案複製到所有流式處理伺服器上的檔案共用中。 將套件升級至較新版本的做法是使用 Windows 安裝程式卸載 package.msi 檔案，然後再安裝新版本。

-   若要在上述任何一種模式中使用獨立的 Windows 安裝程式檔案來部署套件，您可以使用應用程式虛擬化命令列語言 SFTMIME，以更詳細的方式來控制部署。 這提供許多命令來控制套件管理的各個方面。 雖然 SFTMIME 功能強大，還是相當複雜，所以系統管理員應該規劃將所有命令建立為腳本，並在生產使用前在測試環境中徹底測試。 如需可用 SFTMIME 命令的詳細資訊，請參閱[SFTMIME 命令參考](sftmime--command-reference.md)。

## 相關主題


[以電子軟體發佈為基礎的案例](electronic-software-distribution-based-scenario.md)

[規劃 Application Virtualization 系統部署](planning-for-application-virtualization-system-deployment.md)

[在電子軟體發佈實作中規劃您的串流解決方案](planning-your-streaming-solution-in-an-electronic-software-distribution-implementation.md)

[SFTMIME 命令參考](sftmime--command-reference.md)

 

 





