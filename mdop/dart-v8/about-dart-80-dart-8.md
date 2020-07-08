---
title: 關於 DaRT 8.0
description: 關於 DaRT 8.0
author: dansimp
ms.assetid: ce91efd6-7d78-44cb-bb8f-1f43f768ebaa
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e70816425dc4775b11596b91d7b5c0045830c6ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808661"
---
# 關於 DaRT 8.0


Microsoft Diagnostics 與修復工具組（DaRT）8.0 可協助您疑難排解及修復 Windows 電腦。 這包括那些無法啟動的電腦。 DaRT 8.0 是一組功能強大的工具，可延伸 Windows 修復環境（WinRE）。 您可以使用 DaRT 來分析問題，以判斷其原因，例如，檢查電腦的事件記錄或系統登錄。 DaRT 支援恢復包含分區的基本硬碟（例如，主要分區及邏輯磁片磁碟機），並支援恢復卷。

**記事** DaRT 不支援恢復動態磁碟。

 

DaRT 也提供工具，可協助您在判斷原因後立即修正問題。 例如，您可以使用 DaRT 中的工具來停用有問題的裝置驅動程式、移除修補程式、還原已刪除的檔案，以及在電腦上掃描惡意程式碼，即使您無法或不應該啟動已安裝的 Windows 作業系統時也一樣。

DaRT 可協助您快速復原執行32位或64位版本 Windows 8 的電腦，通常會比重新鏡像電腦所需的時間少。

DaRT 中的功能可讓您建立恢復影像。 復原影像會啟動 Windows 修復環境（Windows RE），您可以從這裡啟動 [**診斷及修復工具集**] 視窗並存取 DaRT 工具。

使用**Dart 復原映像嚮導**來建立 DaRT 復原影像。 根據預設，此嚮導會建立國際標準化組織（ISO）圖像檔案和 Windows Imaging 格式（WIM）檔案，並讓您將影像燒錄至 CD、DVD 或 USB。 您可以在使用者的電腦上本機部署映射，或者您可以從遠端網路分區或本機硬碟上的復原分區進行部署。

## <a href="" id="what-s-new-in-dart-8-0"></a>DaRT 8.0 的新功能


DaRT 8.0 可協助您快速復原執行32位或64位版本的 Windows 8 的電腦，通常會比重新鏡像電腦所需的時間少。 DaRT 8.0 具有下列新功能。

### 使用 Windows 8 或 Windows Server 2012 建立 DaRT 映射

DaRT 8.0 可讓您使用 Windows®8或 Windows Server®2012來建立 DaRT 影像。 針對 Windows 8 和 Windows Server 2012 之前版本的 Windows，客戶應繼續使用舊版的 DaRT。

### 從一部電腦產生32與64位的影像

DaRT 8.0 可讓您從執行 DaRT 的單一電腦（無論電腦是32或64電腦），同時產生32位和64位的影像。 在 DaRT7 中，建立的影像必須是與執行 DaRT 的電腦相同、比對。

### 建立一個支援具有 BIOS 或 UEFI 介面的電腦的影像

DaRT 8.0 支援整合的可延伸韌體介面（UEFI）和 BIOS 介面，可讓您只建立一個可搭配有任何介面的電腦使用的影像。

### 使用 GUID 分區表（GPT）進行分區

DaRT 8.0 工具現在支援 Windows 8 GPT 磁片，可提供比舊版主開機記錄（MBR）分區配置更具彈性的磁碟分割方案。 DaRT 8.0 工具繼續支援 MBR 分區。

### 在本機硬碟上安裝 Windows 8 和 Windows Server 2012

DaRT 8.0 工具只能在 Windows 8 和 Windows Server 2012 安裝在本機硬碟上時使用。 目前不支援 Windows 的功能。

### <a href="" id="-------------dart-8-0-release-notes"></a> DaRT 8.0 版本資訊

如需詳細資訊，以及未在檔中顯示的最新消息，請參閱[DaRT 8.0 的版本](release-notes-for-dart-80--dart-8.md)資訊。

## 如何取得 DaRT 8。0


這項技術是 Microsoft 桌面優化套件（MDOP）的一部分。 MDOP 是 Microsoft 軟體保證的一部分。 如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱[如何取得 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。

## 相關主題


[開始使用 DaRT 8.0](getting-started-with-dart-80-dart-8.md)

[DaRT 8.0 版本資訊](release-notes-for-dart-80--dart-8.md)

 

 





