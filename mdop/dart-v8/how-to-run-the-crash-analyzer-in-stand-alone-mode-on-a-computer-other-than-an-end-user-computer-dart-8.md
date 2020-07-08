---
title: 如何在使用者電腦以外的電腦上，以獨立模式執行損毀分析器
description: 如何在使用者電腦以外的電腦上，以獨立模式執行損毀分析器
author: dansimp
ms.assetid: b2f87144-6379-478a-802b-9cfef5242f34
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ebd3c50c373ba9687a3b7fcbbf34e86bd07c6207
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810515"
---
# 如何在使用者電腦以外的電腦上，以獨立模式執行損毀分析器


如果您無法存取 Windows 版 Microsoft 調試工具或終端使用者電腦上的符號檔案，您可以從問題電腦複製轉儲檔案，並在已安裝獨立版本的崩潰分析程式（例如包含 Microsoft Diagnostics 與修復工具集（DaRT）8.0 的支援中心電腦）的電腦上進行分析。

若要在獨立模式下執行故障分析程式，您可以從問題電腦複製記憶體傾印檔案，並在另一部電腦（例如服務台電腦）上進行分析，且該電腦已安裝 [**崩潰] 分析**程式。

**在獨立模式下執行故障分析程式**

1.  在已安裝 DaRT 8.0 的電腦上，按一下 [**開始**]，輸入 [**系統崩潰分析**程式]，然後按一下 [**崩潰分析**程式]。

2.  遵循嚮導中的步驟操作，如如何在[最終使用者電腦上執行 [崩潰分析程式](how-to-run-the-crash-analyzer-on-an-end-user-computer-dart-8.md)] 中所述。

## 相關主題


[適用於 DaRT 8.0 的操作](operations-for-dart-80-dart-8.md)

[使用損毀分析器來診斷系統失敗](diagnosing-system-failures-with-crash-analyzer--dart-8.md)

[如何確保損毀分析器可以存取符號檔案](how-to-ensure-that-crash-analyzer-can-access-symbol-files.md)

 

 





