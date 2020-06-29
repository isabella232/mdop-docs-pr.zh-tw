---
title: 關於 DaRT 7.0
description: 關於 DaRT 7.0
author: dansimp
ms.assetid: 217ffafc-6d73-4b80-88d9-71870460d4ab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cd647b2f596ce88ce38580f08422ff8f92b35c06
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809855"
---
# 關於 DaRT 7.0


Microsoft 診斷和修復工具組（DaRT）7可協助您疑難排解及修復 Windows 桌上型電腦。 這包含那些無法啟動的桌面。 DaRT 是一組可延伸 Windows 復原環境（WinRE）的強大工具。 您可以使用 DaRT 來分析問題，以判斷其原因，例如，檢查電腦的事件記錄或系統登錄。

DaRT 也提供工具，可協助您在判斷原因後立即修正問題。 例如，您可以使用 DaRT 中的工具來停用有問題的裝置驅動程式、移除修補程式、還原已刪除的檔案，以及在電腦上掃描惡意程式碼，即使您無法或不應該啟動已安裝的 Windows 作業系統時也一樣。

DaRT 可協助您快速復原執行32位或64位版本 Windows 7 的電腦，通常會比重新鏡像電腦所需的時間少。

## 關於 DaRT 7 恢復影像


DaRT 中的功能可讓您建立根據 WinRE 結合 DaRT 所提供之工具的 [恢復] 影像。 DaRT 復原影像會利用 WinRE，您可以在其中存取 [**診斷與修復工具**組] 視窗。

使用**Dart 復原映像嚮導**來建立 DaRT 復原影像。 根據預設，此嚮導會在桌面上建立名為 DaRT70 的國際組織結構檔案，不過您可以指定不同的位置和檔案名。 此嚮導也可讓您將影像燒制到 CD 或 DVD。 完成嚮導之後，您可以將復原影像儲存至 USB 快閃磁碟機，或將它儲存為您可以用來建立遠端分區或復原分區的格式。

當您必須使用 DaRT 啟動無法啟動的終端使用者電腦時，您可以按照指示[使用 Dart 復原影像來復原本機電腦](how-to-recover-local-computers-using-the-dart-recovery-image-dart-7.md)。

如需有關 DaRT 工具的詳細資訊，請參閱[dart 7.0 中的工具概覽](overview-of-the-tools-in-dart-70-new-ia.md)。

## <a href="" id="what-s-new-in-dart-7"></a>DaRT 7 的新功能


DaRT7 會繼續支援先前版本中包含的所有案例，而且除了三種新的部署選項之外，它還會新增新的遠端連線功能。

### DaRT 7 影像建立

您用來建立 DaRT ISO 映像的嚮導現在稱為 DaRT 復原**影像**，現在支援啟用或停用新的遠端連線功能的選項。 [遠端連線] 可讓支援人員代理程式從遠端位置執行 DaRT 工具。 在先前的版本中，服務台代理程式必須在最終使用者電腦上實際出現，才能執行 DaRT 工具。

此嚮導也可讓您自訂遠端連線功能的歡迎訊息（當使用者執行遠端連線工具時，就會顯示訊息）。 IT 管理員也可以設定遠端連線應使用哪個埠號。

如需**DaRT 復原映射嚮導**或遠端連線的詳細資訊，請參閱[建立 DaRT 7.0 復原影像](creating-the-dart-70-recovery-image-dart-7.md)。

### DaRT 7 部署

除了燒錄至 CD 或 DVD 之外，DaRT7 會在您部署包含 DaRT 復原影像的 ISO 時新增三個新選項：

-   USB 快閃記憶體磁片磁碟機部署

-   遠端分區部署

-   恢復分區部署

USB 快閃記憶體磁片磁碟機部署選項可讓公司在未提供 CD 或 DVD 光碟機的電腦上使用 DaRT。 [恢復] 和 [遠端分區] 選項可讓使用者輕鬆存取 DaRT 映射，並啟用遠端連線功能。

如需有關如何部署 DaRT 復原影像的詳細資訊，請參閱[部署 dart 7.0 復原映像](deploying-the-dart-70-recovery-image-dart-7.md)。

## 相關主題


[開始使用 DaRT 7.0](getting-started-with-dart-70-new-ia.md)

[DaRT 7.0 版本資訊](release-notes-for-dart-70-new-ia.md)

 

 





