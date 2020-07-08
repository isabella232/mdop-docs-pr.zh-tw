---
title: 如何在使用者電腦上執行損毀分析器
description: 如何在使用者電腦上執行損毀分析器
author: dansimp
ms.assetid: 40af4ead-6588-4a81-8eaa-3dc00c397e1d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 943e3956609ae7e24deaca4313036445802a8f7f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810196"
---
# 如何在使用者電腦上執行損毀分析器


通常，您會在有問題的最終使用者電腦上，從 [診斷與修復工具] 視窗中執行 Microsoft Diagnostics 和復原工具集（DaRT）7故障分析程式。 當故障分析程式在問題電腦上尋找 Windows 的調試工具。 如果 [目錄路徑] 對話方塊是空的，您必須輸入位置或流覽至 Windows 調試工具的位置（您可以從 Microsoft 下載檔案）。 您也必須提供符號檔案所在位置的路徑。

**在最終使用者電腦上開啟並執行 [損毀分析器]**

1.  在最終使用者電腦上的 [**診斷與修復工具**] 視窗中，按一下 [**崩潰分析**程式]。

2.  提供下列所需的資訊：

    -   Windows 版 Microsoft 調試工具

    -   符號檔案

        如需有關符號檔案的詳細資訊，請參閱[如何確保系統崩潰分析程式可以存取符號](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md)檔案。

    -   損毀傾印檔案

        請依照下列步驟來判斷損毀傾印檔案的位置：

        1.  開啟 [**系統屬性**] 視窗。

            按一下 [**開始**]，輸入 sysdm.cpl，然後按 enter。

        2.  按一下 **\[進階\]** 索引標籤。

        3.  在 [**啟動及修復**] 區域中，按一下 [**設定**]。

        **記事** 如果您無法存取 [**系統屬性**] 視窗，您可以使用 DaRT 中的 [**搜尋**] 工具，在最終使用者電腦上搜尋轉儲檔案。

         

3.  [**崩潰分析**程式] 會掃描損毀盤案檔案，並報告可能造成當機的問題。 您可以查看關於該損毀的詳細資訊，例如特定的故障訊息和描述、當機時載入的驅動程式，以及分析的完整輸出。

4.  根據適當的策略來判斷問題的解決方法。 這可能需要停用或更新使用 DaRT**電腦管理**工具之 [**服務與驅動程式**] 節點的裝置驅動程式。

## 相關主題


[使用損毀分析器來診斷系統失敗](diagnosing-system-failures-with-crash-analyzer--dart-7.md)

 

 





