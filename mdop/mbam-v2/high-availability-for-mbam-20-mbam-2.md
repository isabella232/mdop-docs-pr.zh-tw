---
title: MBAM 2.0 的高可用性
description: MBAM 2.0 的高可用性
author: dansimp
ms.assetid: 244ee013-9e2a-48d2-b842-4e10594fd74f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6482a099d96aee731f81368b8b787325e592c453
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810730"
---
# MBAM 2.0 的高可用性


本主題提供有關高可用性的 Microsoft BitLocker 管理和監控（MBAM）安裝的基本資訊。 在這個版本的 MBAM 中並不完全支援高可用性案例，所以這裡並未說明它們。 建議您搜尋相關的博客和論壇，讓使用者描述他們在其環境中如何成功設定高可用性 MBAM。

## MBAM 的高可用性案例


Microsoft BitLocker 管理和監視是以容錯的設計。 如果伺服器無法使用，使用者就不應該受到負面影響。 例如，如果 MBAM 代理程式無法連線至 MBAM web 伺服器，則不應提示使用者執行動作。

規劃 MBAM 安裝時，請考慮下列專案，這可能會影響 MBAM 服務的可用性：

-   磁片磁碟機加密和復原密碼–如果無法 escrowed 復原密碼，就不會在用戶端電腦上啟動加密。

-   相容性狀態資料上傳–如果無法使用託管合規性狀態報表服務的伺服器，則合規性資料不會保持在最新狀態。

-   協助桌面復原金鑰存取-如果技術支援人員無法存取 MBAM 資料庫資訊，說明服務台無法提供復原金鑰給使用者。

-   報表的可用性–如果無法使用託管合規性和審核報告的伺服器，則無法使用報告。

## <a href="" id="how-the-mbam-backup-uses-the-volume-shadow-copy-service--vss--"></a>MBAM 備份如何使用卷影複製服務（VSS）


MBAM 2.0 提供了一個卷陰影複製服務（VSS）寫入程式，稱為 Microsoft BitLocker 管理與管理寫入程式，可協助您備份合規性和審核資料庫及恢復資料庫。

MBAM Server Windows 安裝程式會註冊 MBAM VSS 寫入程式。 在 VSS 寫入程式註冊期間發生任何失敗，都會導致 MBAM 伺服器安裝回滾。 在已將合規性與審計資料庫及復原資料庫安裝在不同伺服器的拓撲中，會在每個伺服器上登錄單獨的 MBAM VSS 書寫器實例。 MBAM VSS 書寫器依賴于 SQL Server VSS 寫入程式。 SQL Server VSS 書寫器已註冊為 Microsoft SQL Server 安裝的一部分。 任何使用 VSS 寫入程式來執行備份的備份技術，都可以探索 MBAM VSS 寫入程式。

## 相關主題


[維護 MBAM 2.0](maintaining-mbam-20-mbam-2.md)

 

 





