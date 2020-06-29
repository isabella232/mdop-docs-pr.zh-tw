---
title: 如何在使用者電腦上執行損毀分析器
description: 如何在使用者電腦上執行損毀分析器
author: dansimp
ms.assetid: 10334800-ff8e-43ac-a9c2-d28807473ec2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4abf1ba2ae1a0cb1dfb129c1f5a26e11f5045290
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809494"
---
# 如何在使用者電腦上執行損毀分析器


若要從遇到問題的最終使用者電腦上的 [**診斷及修復工具集**]**視窗執行當**機，您必須具備 Windows 版 Microsoft 調試工具及已安裝的符號檔案。 若要下載 Windows 調試工具，請參閱[windows 版調試工具](https://go.microsoft.com/fwlink/?LinkId=266248)。

**在最終使用者電腦上執行 [崩潰分析程式]**

1.  在最終使用者電腦上的 [**診斷與修復工具**] 視窗中，按一下 [**崩潰分析**程式]。

2.  針對 Windows 版 Microsoft 調試工具提供所需的資訊。

3.  提供符號檔案所需的資訊。 如需符號檔案的詳細資訊，請參閱[如何確保當機分析器可以存取符號](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-10.md)檔案。

4.  提供記憶體傾印檔案所需的資訊。 若要判斷記憶體傾印檔案的位置：

    1.  開啟 [**系統屬性**] 視窗。

    2.  按一下 [**開始**]，輸入**sysdm.cpl**，然後按**enter**。

    3.  按一下 **\[進階\]** 索引標籤。

    4.  在 [**啟動及修復**] 區域中，按一下 [**設定**]。

        如果您無法存取 [**系統屬性**] 視窗，您可以使用 Microsoft Diagnostics 和恢復工具組（DaRT）10中的 [**搜尋**] 工具，在最終使用者電腦上搜尋轉儲檔案。

    [**崩潰分析**程式] 會掃描記憶體傾印檔案，並報告問題的可能原因。 您可以查看關於失敗的詳細資訊，例如特定記憶體傾印訊息和描述、在失敗時載入的驅動程式，以及分析的完整輸出。

5.  找出適當的戰略來解決問題。 策略可能需要停用或更新導致失敗的裝置驅動程式，方法是使用 DaRT 10 中的 [**電腦管理**] 工具的 [**服務和驅動程式**] 節點。

## 相關主題


[使用損毀分析器來診斷系統失敗](diagnosing-system-failures-with-crash-analyzer-dart-10.md)

[適用於 DaRT 10 的操作](operations-for-dart-10.md)

 

 





