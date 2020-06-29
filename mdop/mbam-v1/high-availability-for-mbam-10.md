---
title: MBAM 1.0 的高可用性
description: MBAM 1.0 的高可用性
author: dansimp
ms.assetid: 5869ecf8-1056-4c32-aecb-838a37e05d39
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 1227967d647cbfbc16967b5936066fd73d2412e2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811109"
---
# MBAM 1.0 的高可用性


本主題說明如何設定高可用性的 Microsoft BitLocker 管理和監控安裝（MBAM）。

## MBAM 的高可用性案例


Microsoft BitLocker 管理和監控（MBAM）的設計是可容錯的。 如果伺服器無法使用，使用者就不應該受到負面影響。 例如，如果 MBAM 代理程式無法連線至 MBAM web 伺服器，則不應提示使用者執行動作。

規劃 MBAM 安裝時，請考慮下列可能會影響 MBAM 服務可用性的問題：

-   磁片磁碟機加密和復原密碼–如果無法 escrowed 復原密碼，則不會在用戶端電腦上啟動加密。

-   相容性狀態資料上傳–如果無法使用託管合規性狀態報表服務的伺服器，規範資料將不會保持在最新狀態。

-   協助桌面復原金鑰存取-如果技術支援人員無法存取 MBAM 資料庫資訊，他們將無法提供復原金鑰給使用者。

-   如果無法使用託管合規性和審核報告的伺服器，則無法使用報表的可用性。

MBAM 高可用性的主要考慮是 BitLocker 金鑰復原可用性。 如果技術支援人員無法提供復原金鑰，鎖定的使用者就無法解除鎖定電腦。 若要避免此問題，請考慮執行冗余的 web 伺服器和資料庫，以確保高可用性。

如需 MBAM 可伸縮性和高可用性的詳細資訊，請參閱[MBAM 可伸縮性白皮書](https://go.microsoft.com/fwlink/p/?LinkId=229025)（ https://go.microsoft.com/fwlink/p/?LinkId=229025) 。

如需 Microsoft SQL Server 高可用性的一般指導方針，請參閱[高可用性](https://go.microsoft.com/fwlink/p/?LinkId=221504)（ https://go.microsoft.com/fwlink/p/?LinkId=221504) 。

如需 web 伺服器可用性與伸縮性的一般指導方針，請參閱[可用性與伸縮性](https://go.microsoft.com/fwlink/p/?LinkId=221503)（ https://go.microsoft.com/fwlink/p/?LinkId=221503) 。

## 相關主題


[維護 MBAM 1.0](maintaining-mbam-10.md)

 

 





