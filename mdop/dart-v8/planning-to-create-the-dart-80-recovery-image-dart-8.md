---
title: 規劃建立 DaRT 8.0 復原映像
description: 規劃建立 DaRT 8.0 復原映像
author: dansimp
ms.assetid: cfd0e1e2-c379-4460-b545-3f7be9f33583
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 1d1dc7dc5b3776638523a282d9216b80d4ce9ce1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810778"
---
# 規劃建立 DaRT 8.0 復原映像


當您計畫建立 Microsoft Diagnostics 與復原工具庫（DaRT）8.0 復原影像時，請使用本節中的資訊。

## 規劃以建立 DaRT 8.0 恢復影像


當您建立 DaRT 復原影像時，必須決定要在影像中包含哪些工具。 若要作出決定，請考慮最終使用者可以存取這些工具。 如果支援工程師會將復原影像媒體移至最終使用者的電腦，以診斷問題，您可能會想要在恢復影像上安裝所有工具。 如果您打算遠端診斷使用者的電腦，您可能會想要停用一些工具，例如 [磁片擦除] 和 [登錄編輯程式]，然後啟用其他工具，包括 [遠端連線]。

當您建立 DaRT 恢復影像時，您也會指定是否要包含其他驅動程式或檔案。 決定您想要包含在 DaRT 復原影像中的任何其他驅動程式或檔案的位置。

如需有關 DaRT 工具的詳細資訊，請參閱[dart 8.0 中的工具概覽](overview-of-the-tools-in-dart-80-dart-8.md)。 如需如何協助建立安全的復原影像的詳細資訊，請參閱[DaRT 8.0 的安全性考慮](security-considerations-for-dart-80--dart-8.md)。

## 復原映像的先決條件


建立 DaRT 復原影像時，必須使用下列專案：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>必備</strong></p></td>
<td align="left"><p><strong>詳細資料</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8 來源檔案</p></td>
<td align="left"><p>建立 DaRT 復原影像所需。 提供 Windows 8 DVD 或 Windows 8 來源檔案的路徑。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>適用于您平臺的 Windows 調試工具</p></td>
<td align="left"><p>當您執行 [當 <strong> 機] 分析程式 </strong> 來判斷電腦發生故障的原因時，必須使用此程式。 我們建議您在建立 DaRT 恢復影像時，指定 Windows 調試工具的路徑。 您可以在這裡下載 Windows 調試工具： <a href="https://go.microsoft.com/fwlink/?LinkId=99934" data-raw-source="[Download and Install Debugging Tools for Windows](https://go.microsoft.com/fwlink/?LinkId=99934)"> 下載並安裝 windows 版調試工具 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>選用： <strong> Defender </strong> 定義</p></td>
<td align="left"><p><strong> </strong> 當您執行 defender 時，需要安裝最新的 defender 定義 <strong> </strong> 。 雖然您可以在執行 Defender 時下載定義 <strong> </strong> ，但我們建議您在建立 DaRT 復原影像時下載最新的定義，讓您仍可以使用最新的定義來執行工具，即使問題電腦沒有網路連線也一樣。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>[選用]： Windows 符號檔案以用於 <strong> 故障分析程式</strong></p></td>
<td align="left"><p>通常，調試資訊會儲存在與程式不同的符號檔案中。 當您調試的應用程式已停止回應（例如，如果它已停止運作），就必須具備符號資訊的存取權。 如需詳細資訊，請參閱 <a href="diagnosing-system-failures-with-crash-analyzer--dart-8.md" data-raw-source="[Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer--dart-8.md)"> 使用故障分析程式診斷系統失敗 </a> 。</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[規劃部署 DaRT 8.0](planning-to-deploy-dart-80-dart-8.md)

 

 





