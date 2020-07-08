---
title: 如何套用一般設定到 MED-V 工作區
description: 如何套用一般設定到 MED-V 工作區
author: dansimp
ms.assetid: 6152dced-e301-4fa2-bfa0-aecf3c23f23a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 176564ae1d22b27a24625d988f46c9746b291748
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811816"
---
# 如何套用一般設定到 MED-V 工作區


[一般] 設定可讓您在使用 MED-V 工作區時，設定基本的使用者體驗，方法是定義 MED-V 工作區是否會顯示在 [順暢整合] 或 [完整桌面圖案]。 順暢整合包括主機桌上出版中的繼承應用程式，讓它們看起來就像是直接安裝于主機上。 全電腦在主機上的另一個視窗中呈現 MED-V 工作區作業系統的桌面。

[**一般**] 索引標籤上的 [**原則**] 模組中會設定所有一般設定。

**將一般設定套用至 MED-V 工作區**

1.  按一下要設定的 MED-V 工作區。

2.  按照下表所述設定一般屬性。

3.  在 [**原則**] 功能表上，選取 [**確認**]。

**一般工作區屬性**

[屬性描述]*工作區屬性*

名稱

MED-V 工作區的名稱。

**警告** 請勿在用戶端電腦上執行現有的 MED-V 工作區時將它重新命名。

 

描述

MED-V 工作區的描述，其中可以包含 MED-V 工作區的內容或狀態，以及任何其他有用的資訊。

**記事** 描述供管理員使用，而且對原則沒有任何影響。

 

支援連絡資訊

技術支援的連絡人資訊。 輸入的資訊會顯示在 [支援連絡人資訊] 畫面中，可透過 MED-V 用戶端的通知區域存取。

*工作區 UI*

順暢整合

針對 MED-V 工作區視窗、工作列和通知區域圖示選取此選項，以順暢地整合到主機桌面。

在每個工作區視窗周圍繪製框架

使用無縫整合時，請選取這個選項，在所有在 MED-V 工作區中執行的應用程式以及所有工作列按鈕圖示的彩色背景周圍建立彩色框線。 在 [**框架色彩**] 欄位中，選取色彩。

完整桌面

選取這個選項，即可將 MED-V 工作區顯示為整個桌面，而不與主機整合。

*主機驗證*

命令列

啟動 MED-V 工作區前，請輸入要在主機上執行的命令列。

如果驗證失敗，請勿啟動工作區（結束程式碼不是 "0"）

如果您使用的是命令列，且想要只在腳本成功完成時才啟動 MED-V 工作區，請選取此核取方塊。

 

在啟動 MED-V 工作區前，命令列可以在主機上執行。

**啟動 MED-V 工作區之前執行命令列**

1.  在**命令列**欄位中，輸入命令列。

2.  若要只在命令列成功時啟動 MED-V 工作區，請選取 [**如果驗證失敗，請勿啟動工作區**] 核取方塊。

## 相關主題


[使用 MED-V 管理主控台使用者介面](using-the-med-v-management-console-user-interface.md)

[建立 MED-V 工作區](creating-a-med-v-workspacemedv-10-sp1.md)

 

 





