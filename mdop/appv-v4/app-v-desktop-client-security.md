---
title: App-V Desktop Client 安全性
description: App-V Desktop Client 安全性
author: dansimp
ms.assetid: 216b9c16-7bb4-4f94-b9d8-810501285008
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 26add6f855780113613cf1591c41722643954477
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809284"
---
# App-V Desktop Client 安全性


App-v Desktop 用戶端提供了許多舊版產品無法使用的安全性增強功能。 這些變更預設會提供較高的安全性等級，以及設定用戶端設定的設定。

**記事** 當您在電腦上安裝 app-v Desktop 用戶端時，軟體會預設為最安全的設定。 不過，當您升級時，用戶端的先前設定就會繼續。

 

根據預設，App-v Desktop 用戶端只會設定為允許非系統管理使用者執行發佈更新與資料流程應用程式所需的許可權。 在 App-v Desktop 用戶端中提供的其他安全性增強功能包括下列各項：

-   根據預設，只允許發佈重新整理程式來更新 OSD 快取。

-   `sftlog.txt`只有對用戶端有本機管理存取權的帳戶才能存取記錄檔（）。

-   記錄檔現在有最大大小。

-   記錄檔案是透過 [封存設定] 進行管理。

-   現在已執行系統事件記錄。

## 權限


安裝桌面用戶端之後，您可以透過 MMC 或使用 Microsoft 所提供的 ADM 範本，在個別用戶端上設定其他安全性設定。 App-v Desktop 用戶端具有您可以設定的許可權，以限制非系統管理員使用者存取桌面用戶端的所有功能。 如需許可權的完整清單，請參閱 App-v 用戶端說明檔案或 App-v 操作指南。

**重要** 請謹慎考慮變更許可權的後果，特別是在多位使用者所共用的系統上（例如終端伺服器）。

 

**記事** 如果環境中的使用者擁有其電腦的本機系統管理員許可權，則會略過許可權。

 

### ADM 範本

Microsoft Application Virtualization （App-v）引入 ADM 範本，您可以用來透過群組原則設定最常見的用戶端設定。 此範本可讓系統管理員透過集中式管理模型來實施及變更許多用戶端設定。 ADM 範本中提供的部分設定為安全性設定。

**重要** 使用 ADM 範本時，請記住設定是群組原則喜好設定，而不是完全管理的群組原則。

 

如需 ADM 範本的完整描述、特定設定，以及在您的環境中成功部署用戶端的指導方針，請參閱 App V ADM 範本白皮書 [https://go.microsoft.com/fwlink/LinkId=122063](https://go.microsoft.com/fwlink/?LinkId=122063) 。

## 移除 OSD 檔案類型關聯


如果您的組織不需要使用者直接從 OSD 檔案開啟應用程式，您可以移除用戶端上的檔案類型關聯，以加強安全性。 `HKEY_CURRENT_USERS`使用 [登錄編輯程式] 移除 OSD 的按鍵 `Softgird.osd.file` 。 您可以將此程式置於登入腳本或安裝後腳本中，以自動化這些變更。

 

 





