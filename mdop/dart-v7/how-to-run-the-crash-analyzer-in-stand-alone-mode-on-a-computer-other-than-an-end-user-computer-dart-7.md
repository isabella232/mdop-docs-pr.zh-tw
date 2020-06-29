---
title: 如何在使用者電腦以外的電腦上，以獨立模式執行損毀分析器
description: 如何在使用者電腦以外的電腦上，以獨立模式執行損毀分析器
author: dansimp
ms.assetid: 881d573f-2f18-4c5f-838e-2f5320179f94
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6f398c56b7c631145388541b71229d69c16bf6f3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809566"
---
# 如何在使用者電腦以外的電腦上，以獨立模式執行損毀分析器


如果您無法存取 Windows 版 Microsoft 調試工具或終端使用者電腦上的符號檔案，您可以從問題電腦複製轉儲檔案，並在裝有獨立版本的崩潰分析程式的電腦（例如支援者管理員的電腦）上進行分析。

**在獨立模式下執行故障分析程式**

1.  在已安裝 DaRT7 的電腦上，按一下 [**開始**使用  /  **All Programs**  /  **Microsoft DaRT 7**] 中的 [所有程式]。

2.  提供下列所需的資訊：

    -   Windows 版 Microsoft 調試工具

    -   符號檔案

        如需有關符號檔案的詳細資訊，請參閱[如何確保系統崩潰分析程式可以存取符號](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md)檔案。

    -   損毀傾印檔案

        **記事** 使用 DaRT7 中的 [搜尋] 工具，找出複製的損毀盤案檔案。

         

3.  [**崩潰分析**程式] 會掃描損毀盤案檔案，並報告可能造成當機的問題。 您可以查看關於該損毀的詳細資訊，例如特定的故障訊息和描述、當機時載入的驅動程式，以及分析的完整輸出。

4.  根據適當的策略來判斷問題的解決方法。 這可能需要停用或更新使用 DaRT**電腦管理**工具之 [**服務與驅動程式**] 節點的裝置驅動程式。

## 相關主題


[使用損毀分析器來診斷系統失敗](diagnosing-system-failures-with-crash-analyzer--dart-7.md)

 

 





