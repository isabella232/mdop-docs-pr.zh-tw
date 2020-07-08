---
title: 如何設定或停用使用量報告
description: 如何設定或停用使用量報告
author: dansimp
ms.assetid: 8587003a-128d-4b5d-ac70-5b9eddddd3dc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3f8f6c44d4060581f1ebe435875bc2f105cb93d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801061"
---
# 如何設定或停用使用量報告


您可以在應用程式虛擬化伺服器管理主控台中使用下列程式，以指定您想要儲存在資料庫中之應用程式虛擬化系統使用量資訊的持續時間（以月為單位）。

**記事** 若要儲存使用資訊，您必須在 [**提供者管道**] 索引標籤上選取 [**記錄使用量資訊**] 核取方塊。若要顯示此索引標籤，請以滑鼠右鍵按一下 [**提供者原則結果**] 窗格中的提供者原則，然後選取 [**屬性**]

 

**設定使用狀況報告**

1.  以滑鼠右鍵按一下左窗格中的 [應用程式虛擬化系統] 節點，然後選取 [**系統選項**]。

2.  選取 [**資料庫**] 索引標籤。

3.  選取 [**保留使用時間（月）** ] 或 [**保留所有使用方式**] 選項按鈕。

4.  如果您選擇指定使用時間（以月為單位），請輸入1到120之間的數位（預設值是6個月）。 如果您選取 [**保留所有使用方式**]，資料庫將會持續增長，直到達到指定的大小限制為止。

5.  按一下**Apply** [套用 **] 或 [確定]**。

**停用使用方式報告**

1.  按一下 [**提供者原則**] 節點。

2.  以滑鼠右鍵按一下 [**提供者原則**]，然後選取 [**屬性**]。

3.  選取 [**提供者管線**] 索引標籤。

4.  清除 [**記錄使用量資訊**] 核取方塊。

5.  按一下**Apply** [套用 **] 或 [確定]**。

## 相關主題


[如何在伺服器管理主控台中自訂 Application Virtualization 系統](how-to-customize-an-application-virtualization-system-in-the-server-management-console.md)

[如何設定或停用資料庫大小](how-to-set-up-or-disable-database-size.md)

 

 





