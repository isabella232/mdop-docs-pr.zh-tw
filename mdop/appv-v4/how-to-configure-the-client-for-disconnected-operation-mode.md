---
title: 如何設定中斷連線的操作模式的用戶端
description: 如何設定中斷連線的操作模式的用戶端
author: dansimp
ms.assetid: 3b48464a-b8b4-494b-93e3-9a6d9bd74652
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1c917d87996a26b330551deb04b1828c31fd3c73
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801569"
---
# 如何設定中斷連線的操作模式的用戶端


[已中斷式作業] 模式可讓應用程式虛擬化（App-v）桌面用戶端或應用程式虛擬化（舊稱終端服務）用戶端在用戶端無法連線到 App V 管理伺服器時，執行儲存在用戶端檔案系統快取中的應用程式。

**重要** 在大型組織中，在多個遠端桌面工作階段主機（RD 度工作階段主機）伺服器（先前的終端伺服器）都連結在伺服器陣列中，以支援許多使用者，使用單一 App-v 管理伺服器來支援多個使用者，就能代表單一故障點。 若要提供高可用性以支援 RDSession 主機場，請考慮連結兩個以上的 App-v 管理伺服器來使用相同的資料庫。

 

**啟用中斷線上作業模式**

-   將下列登錄機碼值設定為1，以啟用中斷操作模式：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\AllowDisconnectedOperation

**若要設定中斷式作業模式使用的時間限制**

1.  將下列登錄機碼值設定為1：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\LimitDisconnectedOperation

2.  將下列登錄機碼的值設定為您要限制斷開連接操作模式的分鐘數。 有效的值範圍為1到999999。 預設值為90天或129600分鐘。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\DOTimeoutMinutes

**針對中斷線上作業模式設定遠端桌面服務的用戶端**

1.  將下列登錄機碼值設定為1，以啟用中斷式操作模式：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\AllowDisconnectedOperation

2.  將下列登錄機碼的值設定為0（零），以允許不限制中斷式操作模式的使用：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\LimitDisconnectedOperation

3.  確定所有套件都預先載入到快取中，以提升效能。

## 相關主題


[中斷連線的操作模式](disconnected-operation-mode.md)

[如何使用命令列設定 App-V 用戶端登錄設定](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





