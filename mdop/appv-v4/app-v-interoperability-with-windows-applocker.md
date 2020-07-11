---
title: App-V 與 Windows AppLocker 的互通性
description: App-V 與 Windows AppLocker 的互通性
author: dansimp
ms.assetid: 9a488034-607d-411c-b495-ff184c726f49
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 6f67bb87c0a4474acee3c4982b65c930e86c4917
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809279"
---
# App-V 與 Windows AppLocker 的互通性


Microsoft Application Virtualization (的 4.5 SP1 版本，app-v) 用戶端支援 Windows 7 的 AppLocker 功能。 AppLocker 功能可讓 IT 系統管理員指定哪些應用程式受到限制，無法在電腦上執行。 本檔說明如何設定 AppLocker 規則，以搭配使用 App-v 虛擬環境和虛擬化應用程式。

**記事** 必須先啟用 Windows AppLocker，才能為虛擬應用程式設定 Windows AppLocker 規則。 如需啟用 Windows AppLocker 的詳細資訊，請參閱[Windows applocker](https://go.microsoft.com/fwlink/?LinkId=156732) (https://go.microsoft.com/fwlink/?LinkId=156732) 。

 

## 針對虛擬應用程式設定 Windows AppLocker 規則


本機管理員可以建立 Windows AppLocker 規則，限制執行程式的可執行檔 ( .exe 檔案) 、Windows Installer 檔案 ( .msi 與 .msp 檔案) ，以及腳本 ( .ps、.bat、.cmd、.vbs 和 .js 檔案) 。 系統管理員會使用已安裝 App-v 用戶端且已將所有相關虛擬應用程式流入用戶端快取的參考電腦來執行此動作。 然後，系統管理員會使用本機安全性原則的 Windows AppLocker 區段 Microsoft 管理主控台 (MMC) 在參考電腦上的管理單元來建立規則。

當您流覽以尋找您要為其建立規則的目錄路徑或特定檔案時，您可以使用隱藏共用的路徑來存取 app-v 磁片磁碟機。 例如，您可以流覽至 \\\\localhost\\Q $，其中 App-v 磁片磁碟機是磁碟機 Q。不過，若要建立規則，您必須編輯路徑，移除 \\\\localhost\\Q $ 的參照，然後改為使用 Q:\\。 您必須啟動參考電腦上的每個應用程式，才能存取應用程式的檔案，且需要系統管理許可權才能流覽至 \\\\localhost\\Q $。

 

 





