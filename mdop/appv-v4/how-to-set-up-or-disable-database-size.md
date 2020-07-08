---
title: 如何設定或停用資料庫大小
description: 如何設定或停用資料庫大小
author: dansimp
ms.assetid: 4abaf349-132d-4186-8873-a0e515593b93
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cbb041920e2680d51b01926f144eba595fe28d05
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801066"
---
# 如何設定或停用資料庫大小


您可以在應用程式虛擬化伺服器管理主控台中使用下列程式，以指定您想要儲存在資料庫中的應用程式虛擬化系統使用量大小（以 MB 為單位）。

當所儲存資料的大小達到指定限制的95% （高水位線）時，系統會刪除10% 的使用量資料，並將85% 的資料留在一起。 隨即會刪除套件和應用程式的使用資料。 當資料庫增長足夠大且接近高水位線時，系統會傳送一則警告訊息給 SQL Server 記錄，通知您已達到此限制。 此警告是必要的，因為清除動作可能會影響報表的輸出。 它也可協助您決定是否要增加最大資料庫大小、減少要保留的使用資料月份數，或關閉記錄層級。

**記事** [**無大小限制**] 和 [**保留所有使用方式**] 選項，因此您可以停用使用方式報告和資料庫清理。 選取這些專案將會同時清除資料庫事務記錄記錄。 （所有已提交的 Microsoft SQL Server 事務將會從資料庫記錄中移除）。

 

**設定資料庫大小**

1.  以滑鼠右鍵按一下左窗格中的 [應用程式虛擬化系統] 節點，然後選取 [**系統選項**]。

2.  選取 [**資料庫**] 索引標籤。

3.  選取 [**資料庫大小上限（MB）** ] 或 [**無大小限制**] 選項按鈕。

4.  如果您選擇指定資料庫大小，最佳做法建議您輸入介於512和 4096 MB 之間的數位。 預設大小為 1024 MB，如果您需要增加資料庫大小，您可以輸入的最大值為2147483647。 如果您選取 [**無大小限制**]，資料庫將會增長，直到達到磁片大小限制為止。

5.  按一下**Apply** [套用 **] 或 [確定]**。

**若要停用資料庫大小限制**

1.  以滑鼠右鍵按一下 [**範圍**] 窗格中的 [應用程式虛擬化系統] 節點，然後選取 [**系統選項**]。

2.  選取 [**資料庫**] 索引標籤。

3.  選取 [**無大小限制**]，然後**保留 [所有使用方式**] 選項按鈕。

4.  按一下**Apply** [套用 **] 或 [確定]**。

## 相關主題


[如何在伺服器管理主控台中自訂 Application Virtualization 系統](how-to-customize-an-application-virtualization-system-in-the-server-management-console.md)

[如何設定或停用使用量報告](how-to-set-up-or-disable-usage-reporting.md)

 

 





