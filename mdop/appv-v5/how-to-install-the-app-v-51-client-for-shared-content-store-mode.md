---
title: 如何安裝 App-V 5.1 用戶端以使用共用內容存放區模式
description: 如何安裝 App-V 5.1 用戶端以使用共用內容存放區模式
author: dansimp
ms.assetid: 6f3ecb1b-b5b5-4ae0-8de9-b4ffdfd2c216
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a7ce8114a44762180bf9bb0240913dca50c55d31
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800497"
---
# 如何安裝 App-V 5.1 用戶端以使用共用內容存放區模式


使用下列程式來安裝 Microsoft Application Virtualization （App-v）5.1 用戶端，讓它使用 App-v 5.1 的共用內容儲存區（SCS）模式。 您應該確保您打算安裝的電腦上已安裝所有必要的先決條件。 使用下列連結，查看[App-V 5.1 先決條件](app-v-51-prerequisites.md)。

**記事** 在執行此程式之前，請先卸載任何現有的 App-v 5.1 用戶端版本。

 

如需 SCS 模式的詳細資訊，請參閱[Microsoft app-v 5.0 中的共用內容存放區](https://go.microsoft.com/fwlink/?LinkId=316879)（位於幕後） https://go.microsoft.com/fwlink/?LinkId=316879) 。

**安裝並設定適用于 SCS 模式的 App-v 5.1 用戶端**

1.  將 App-v 5.1 用戶端安裝檔案複製到安裝該檔案的電腦上。 開啟命令列，並從儲存安裝盤案的目錄中，輸入下列其中一個選項（視您要安裝的用戶端版本而定）：

    -   若要安裝 RDS 版的 App-v 5.1 用戶端類型： **appv\_client\_setup\_rds.exe/SHAREDCONTENTSTOREMODE = 1/q**

    -   若要安裝標準版的 App-v 5.1 用戶端類型： **appv\_client\_setup.exe/SHAREDCONTENTSTOREMODE = 1/q**

        **重要** 您必須執行緘默安裝，否則安裝將會失敗。

         

2.  完成安裝之後，您可以將套件部署到執行用戶端的電腦，所有套件內容都會在整個網路中流動。

    您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[部署 App-V 5.1 排序器和用戶端](deploying-the-app-v-51-sequencer-and-client.md)

 

 





