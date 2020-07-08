---
title: 如何為 Windows Vista 指派適當的認證
description: 如何為 Windows Vista 指派適當的認證
author: dansimp
ms.assetid: cc11d2af-a350-4d16-ba7b-f9c1d89e14b4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 111dafea505133f123cf8531a2891a452e725ac2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808714"
---
# 如何為 Windows Vista 指派適當的認證


使用下列程式設定 App-V 桌面用戶端以取得適當的 WindowsVista 認證。

**記事** 此程式必須在每個未加入網域的電腦上完成。 根據您的環境中未加入網域的電腦數目而定，這可能是相當乏味的操作。 您可以將腳本與命令列介面用於認證管理員，以協助管理員自動執行此程式。

 

**若要為執行 Windows Vista 的 App-v 用戶端指派適當的認證**

1.  在執行 Windows Vista 的 App-v Desktop 用戶端上使用系統管理員許可權，開啟 [**使用者帳戶**] 控制台（傳統的 [控制台]）。

2.  從 [左側工作] 窗格中的 [**使用者帳戶**] 選取 [**管理您的網路密碼**]。

3.  選取 [儲存的**使用者名稱和密碼**] 畫面上的 [**新增**]。

4.  在 [**儲存的認證屬性**] 畫面上，提供 app-v 基礎結構的資訊：

    1.  **登入：** 發佈伺服器的外部名稱。

    2.  **使用者名稱：**[表單 Domain\\Username.] 中的外部使用者使用者名稱

    3.  **密碼：** 在 [**使用者名稱**] 欄位中輸入之使用者帳戶的密碼。

    4.  保留已選取的**認證類型**，然後按一下 **[確定]**。

5.  按一下 **\[關閉\]**。 認證儲存在認證存放區中，以適當驗證 App V 基礎結構。

## 相關主題


[加入網域及未加入網域的用戶端](domain-joined-and-non-domain-joined-clients.md)

[如何為 Windows XP 指派適當的認證](how-to-assign--the-proper-credentials-for-windows-xp.md)

 

 





