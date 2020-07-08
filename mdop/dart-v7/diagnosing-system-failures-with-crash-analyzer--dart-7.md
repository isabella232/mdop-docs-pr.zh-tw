---
title: 使用損毀分析器來診斷系統失敗
description: 使用損毀分析器來診斷系統失敗
author: dansimp
ms.assetid: 170d40ef-4edb-4a32-a349-c285c0ea5e56
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3c5f8b7e189de024d7ceb84f8cfc151dc82d56ed
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809974"
---
# 使用損毀分析器來診斷系統失敗


Microsoft Diagnostics 與修復工具組（DaRT）7中的 [崩潰分析程式] 可讓您在 Windows 電腦上調試損毀轉儲檔案，然後診斷任何相關的電腦錯誤。 [崩潰分析程式] 使用 Windows 版 Microsoft 調試工具，來檢查導致電腦失敗之驅動程式的損毀盤案檔案。

## 在最終使用者電腦上執行 [崩潰分析程式]


通常，您會在有問題的使用者電腦上，從 [診斷與修復工具] 視窗執行 [崩潰分析程式]。 當故障分析程式在問題電腦上尋找 Windows 的調試工具。 如果 [目錄路徑] 對話方塊是空的，您必須輸入位置或流覽至 Windows 調試工具的位置（您可以從 Microsoft 下載檔案）。 您也必須提供符號檔案所在位置的路徑。

如果您在建立 DaRT 復原影像時包含 Windows 版 Microsoft 調試工具和符號檔案，當您在有問題的電腦上執行 [當機] 時，就應該能使用這些檔案。

[如何在使用者電腦上執行損毀分析器](how-to-run-the-crash-analyzer-on-an-end-user-computer-dart-7.md)

## 在不是使用者電腦的電腦上，以獨立模式執行故障分析程式


當故障分析程式在問題電腦上尋找 Windows 的調試工具。 如果 [目錄路徑] 對話方塊是空的，您必須輸入位置或流覽至 Windows 調試工具的位置（您可以從 Microsoft 下載檔案）。 您也必須提供符號檔案所在位置的路徑。

如果您在建立 DaRT 復原影像時未包含 Windows 和符號檔案的 Microsoft 調試工具，或是磁片大小或網路連線問題無法取得它們，您可以從問題電腦複製轉儲檔案，並在已安裝獨立版本的故障分析程式的電腦上進行分析，例如 [支援者管理員的電腦]。

[如何在使用者電腦以外的電腦上，以獨立模式執行損毀分析器](how-to-run-the-crash-analyzer-in-stand-alone-mode-on-a-computer-other-than-an-end-user-computer-dart-7.md)

## 確定 [損毀分析器] 可以存取符號檔案


通常，調試資訊會儲存在符號檔案中，與可執行檔不同。 調試已停止回應的應用程式時，您必須具備符號資訊的存取權（例如，如果它已損壞）。

當您執行 [損毀分析程式] 時，會自動下載符號檔案。 如果電腦沒有網際網路連線，或網路需要電腦存取 HTTP proxy 伺服器，則無法下載符號檔案。

[如何確保損毀分析器可以存取符號檔案](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md)

## 使用故障分析程式診斷系統失敗的其他資源


[適用於 DaRT 7.0 的操作](operations-for-dart-70-new-ia.md)

 

 





