---
title: 規劃建立 DaRT 7.0 復原映像
description: 規劃建立 DaRT 7.0 復原映像
author: dansimp
ms.assetid: e5d49bee-ae4e-467b-9976-c1203f6355f9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c370d2a69ec8ccea217696045e64e9a0ae724815
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808691"
---
# 規劃建立 DaRT 7.0 復原映像


當您規劃建立 Microsoft Diagnostics 與復原工具集（DaRT）7復原影像時，請使用本節中的資訊。

## 規劃以建立 DaRT 7 恢復影像


當您建立 DaRT 復原影像時，必須決定要在影像中包含哪些工具。 當您作出決定時，請記住，最終使用者可能會偶爾存取各種 DaRT 工具。 如需有關 DaRT 工具的詳細資訊，請參閱[dart 7.0 中的工具概覽](overview-of-the-tools-in-dart-70-new-ia.md)。 如需如何協助建立安全的復原影像的詳細資訊，請參閱[DaRT 7.0 的安全性考慮](security-considerations-for-dart-70-dart-7.md)。

當您建立 DaRT 恢復影像時，您也會指定是否要包含其他驅動程式或檔案。 決定您想要包含在 DaRT 復原影像中的任何其他驅動程式或檔案的位置。

## 必要條件


建立 DaRT 復原影像時，必須使用下列專案：

-   Windows 7 來源檔案

    您必須提供 Windows 7 DVD 或 Windows 7 來源檔案的路徑。 Windows 7 來源檔案是建立 DaRT 復原影像所必需的。

-   適用于您平臺的 Windows 調試工具

    當您執行**系統崩潰分析**程式來判斷電腦當機的原因時，必須使用 Windows 調試工具。 我們建議您在建立 DaRT 恢復影像時，指定 Windows 調試工具的路徑。 如有需要，您可以在這裡下載 Windows 調試工具：[下載並安裝 windows 的調試工具](https://go.microsoft.com/fwlink/?LinkId=99934)。

-   選用：**獨立系統 Sweeper**定義

    當您執行此工具時，會需要**獨立系統 Sweeper**的最新定義。 雖然您可以在執行**獨立系統 Sweeper**時下載定義，但我們建議您在建立 DaRT 恢復影像時，下載最新的定義。 如此一來，即使有問題的電腦沒有網路連線，您仍然可以使用最新的定義來執行工具。

-   [選用]： Windows 符號檔案以用於**故障分析**程式

    通常，調試資訊會儲存在符號檔案中，與可執行檔不同。 調試已停止回應的應用程式時，您必須具備符號資訊的存取權（例如，如果它已損壞）。 如需詳細資訊，請參閱[使用故障分析程式診斷系統失敗](diagnosing-system-failures-with-crash-analyzer--dart-7.md)。

## 相關主題


[規劃部署 DaRT 7.0](planning-to-deploy-dart-70.md)

 

 





