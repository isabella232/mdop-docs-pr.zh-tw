---
title: 維護 MBAM 1.0
description: 維護 MBAM 1.0
author: dansimp
ms.assetid: 02ffb093-c364-4837-bbe8-23d4c09fbd3d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7eecef4e82680b08fde1b1bef88487a6fc156fe4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811355"
---
# 維護 MBAM 1.0


完成所有必要的規劃，然後部署 Microsoft BitLocker 管理與監控（MBAM）之後，您就可以將 MBAM 設定為在使用它來管理企業 BitLocker 加密作業時，以高度可用的方式執行。 本節中的資訊說明 MBAM 的高可用性選項，以及如何在必要時移動 MBAM 伺服器功能。

## MBAM 管理套件


您可以從 Microsoft 下載中心下載 MBAM 的 MicrosoftSystemCenterOperationsManager 管理套件。

此管理套件會監視伺服器端基礎結構中的重要互動，例如 web 服務與資料庫之間的連線，以及網站與其可進行的 web 服務之間的運營通話。 它也會上傳桌面用戶端與其各自的接收 web 服務端點之間的要求。

[Microsoft BitLocker 管理和監視管理套件](https://go.microsoft.com/fwlink/p/?LinkId=258390)

## 確保 MBAM 1.0 的高可用性


MBAM 已設計成可容錯。 如果伺服器無法使用，使用者就不應該受到負面影響。 本節中的資訊可用來設定高可用性的 MBAM 安裝。

[MBAM 1.0 的高可用性](high-availability-for-mbam-10.md)

## 將 MBAM 1.0 功能移至另一個伺服器


當您需要將 MBAM 伺服器功能從一台伺服器電腦移到另一個伺服器時，必須遵循特定的順序及必要步驟，以免損失生產力或資料。 本節說明將一或多個 MBAM 伺服器功能移至不同電腦時應採取的步驟。

[如何將 MBAM 1.0 功能移到其他電腦](how-to-move-mbam-10-features-to-another-computer.md)

## 維護 MBAM 的其他資源


[適用於 MBAM 1.0 的操作](operations-for-mbam-10.md)

 

 





