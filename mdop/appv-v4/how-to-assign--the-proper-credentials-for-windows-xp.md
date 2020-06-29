---
title: 如何為 Windows XP 指派適當的認證
description: 如何為 Windows XP 指派適當的認證
author: dansimp
ms.assetid: cddbd556-d8f9-4981-a947-6e8e3f552b70
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 81581b75a9b7d5ce35e1c50fd01e0b7bbd3f7ef5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802170"
---
# 如何為 Windows XP 指派適當的認證


使用下列程式設定 App-V 桌面用戶端以取得適當的 WindowsXP 認證。

**記事** 完成這個程式後，非網域加入的用戶端可以在不加入網域的情況下執行發佈重新整理。

 

**為執行 WindowsXP 的 App-v 用戶端指派適當的認證**

1.  在執行 WindowsXP 的 App-V 用戶端上使用系統管理員許可權，開啟 [**使用者帳戶**] 控制台（傳統的 [控制台]）。

2.  按一下 [**高級]** 索引標籤，然後選取 [**管理密碼**]。

3.  在 [已**儲存的使用者名稱和密碼**] 畫面上，按一下 [**新增**]。

4.  在 [**登入資訊屬性**] 畫面上，使用 app-v 基礎結構中的資訊填寫下欄欄位：

    1.  **伺服器：** 發佈伺服器外部名稱的名稱。

    2.  **使用者名稱：**[表單 Domain\\username.] 中的外部使用者使用者名稱

    3.  **密碼：** 在 [**使用者名稱**] 欄位中輸入之使用者帳戶的密碼。

5.  按一下 \[確定\] ****。 認證將會儲存在用戶端上。

## 相關主題


[加入網域及未加入網域的用戶端](domain-joined-and-non-domain-joined-clients.md)

[如何為 Windows Vista 指派適當的認證](how-to-assign--the-proper-credentials-for-windows-vista.md)

 

 





