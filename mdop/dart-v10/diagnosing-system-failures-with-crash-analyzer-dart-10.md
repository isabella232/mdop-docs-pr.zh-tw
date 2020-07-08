---
title: 使用損毀分析器來診斷系統失敗
description: 使用損毀分析器來診斷系統失敗
author: dansimp
ms.assetid: 7ebef49e-a294-4173-adb1-7e6994aa01ad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7d0f4b71bf267d65ec53dd1b3e23fd8a59190b0b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800261"
---
# 使用損毀分析器來診斷系統失敗


Microsoft Diagnostics 與修復工具組（DaRT）10中的 [**崩潰分析**程式] 可讓您在 Windows 電腦上調試記憶體傾印檔案，然後診斷任何相關的電腦錯誤。 [**崩潰分析**程式] 使用 Windows 版 Microsoft 調試工具，來檢查導致電腦失敗之驅動程式的記憶體傾印檔案。 您可以在使用者電腦以外的電腦（而非使用者電腦）上，在最終使用者電腦或獨立模式中執行當機。

## 在最終使用者電腦上執行 [崩潰分析程式]


通常，您會在遇到問題的最終使用者電腦上，從 [**診斷和修復工具**] 視窗中執行 [當機] 的 [**崩潰分析**程式]。 當**故障分析**程式在問題電腦上尋找 Windows 的調試工具。 如果 [目錄路徑] 對話方塊是空的，您必須輸入位置，或流覽至 Windows 調試工具的位置（您可以從 Microsoft 下載檔案）。 您也必須提供符號檔案所在位置的路徑。

如果您在建立 DaRT 10 復原影像時包含 Windows 版 Microsoft 調試工具和符號檔案，當您在有問題的**電腦上執行**[當機] 時，就應該能使用這些工具和符號檔案。 如果您未將其包含在 DaRT 復原影像中，或是磁片大小或網路連線問題無法取得它們，您也可以在非使用者電腦以外的電腦上以獨立模式執行該防故障分析程式，如下一節所述。

[如何在使用者電腦上執行損毀分析器](how-to-run-the-crash-analyzer-on-an-end-user-computer-dart-10.md)

## <a href="" id="run-the-crash-analyzer-in-stand-alone-mode-on-a-computer-other-than-an-end-user-s-computer"></a>在使用者電腦以外的電腦上，以獨立模式執行故障分析程式


雖然您通常會**在遇到**問題的最終使用者電腦上執行當機，但是您也可以在獨立模式（而非使用者電腦）上執行故障分析程式。 如果您沒有在 DaRT 復原影像中包含 Windows 調試工具，或是磁片大小或網路連線問題阻礙您取得調試工具，您就可以選擇這個選項。 在這種情況下，您可以從問題電腦複製轉儲檔案，並在裝有獨立版本的**故障分析**程式的電腦上進行分析，例如在服務台代理的電腦上。

[如何在使用者電腦以外的電腦上，以獨立模式執行損毀分析器](how-to-run-the-crash-analyzer-in-stand-alone-mode-on-a-computer-other-than-an-end-user-computer-dart-10.md)

## 如何確保 [損毀分析器] 可以存取符號檔案


若要調試已停止回應的應用程式，您需要存取符號檔案，該檔與程式不同。 雖然當您執行當機時，會自動下載符號檔案，但有時問題電腦無法存取網際網路。 有幾種方法可以確保您可以存取符號檔案。

[如何確保損毀分析器可以存取符號檔案](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-10.md)

## 使用故障分析程式診斷系統失敗的其他資源


[適用於 DaRT 10 的操作](operations-for-dart-10.md)

 

 





