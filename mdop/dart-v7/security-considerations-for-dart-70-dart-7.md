---
title: DaRT 7.0 的安全性考量
description: DaRT 7.0 的安全性考量
author: dansimp
ms.assetid: 52ad7e6c-c169-4ba4-aa76-56335a585eb8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 739c0319195aeb26e38d55ffe01d14b623de7f43
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809531"
---
# DaRT 7.0 的安全性考量


Microsoft Diagnostics 與修復工具組（DaRT）7包含可讓系統管理員以遠端方式執行 DaRT 工具，以解決最終使用者電腦上的問題的功能。 在舊版的 DaRT 中，技術支援人員或系統管理員必須在使用者電腦上實際使用，並使用包含 DaRT 復原影像的 CD 或 DVD 開機至 DaRT。 現在，技術支援人員或系統管理員可以遠端執行相同的程式。

此外，在 DaRT7 中，您現在可以將國際標準組織（ISO）影像儲存到 USB 快閃記憶體磁片磁碟機上。 您也可以將 ISO 影像放在網路上，或將其內容納入電腦硬碟上的復原分區。

DaRT7 中的**遠端**連線功能可讓使用者使用下列其中一種新的部署方法存取 DaRT。 因此，他們可以更輕鬆地啟動 DaRT 並存取 DaRT 工具。

DaRT7 中的新功能可在您的企業中使用 DaRT，提供更大的彈性。 不過，它們也會建立自己的一組安全問題，必須加以解決。 我們建議您在設定 DaRT 時，考慮下列安全性秘訣。

## 當您建立 DaRT 復原影像時，協助維護安全性


當您建立 DaRT 復原影像時，您可以選取要包含的工具。 出於安全性考慮，您可能會想要限制最終使用者存取更強大的 DaRT 工具，例如磁片擦除及 Locksmith。 在 DaRT7 中，您可以在設定期間停用某些工具，當使用者啟動遠端連線功能時，仍能讓支援人員使用。

您甚至可以設定 DaRT 影像，讓 [啟動遠端連線會話] 選項成為最終使用者可以使用的唯一工具。

**重要** 在遠端連線建立之後，您在復原影像中所包含的所有工具，包括最終使用者無法使用的所有工具，都會提供給支援人員在使用者電腦上工作的狀態。

 

如需在 DaRT 復原影像中加入工具的詳細資訊，請參閱[如何使用 dart 復原映射嚮導來建立恢復影像](how-to-use-the-dart-recovery-image-wizard-to-create-the-recovery-image-dart-7.md)。

## 使用加密 DaRT 恢復影像來協助維護安全性


如果您使用 DaRT7 中的新部署選項（例如，儲存至 USB 快閃記憶體磁片磁碟機或建立遠端分區或復原分區），您可以在 ISO 上加入貴公司的首選磁片磁碟機加密方法。 這將有助於確保使用者無法使用 DaRT 的功能，讓他們能夠存取恢復影像。 此外，也會確認未授權的使用者無法在屬於其他人的電腦上啟動到 DaRT。

您應該在所有電腦中部署並啟用您的加密方法。

**記事** DaRT7 支援 BitLocker 本身。

 

## 在遠端連線期間，協助維護兩台電腦之間的安全性


根據預設，已建立**遠端**連線會話的兩台電腦之間的通訊可能不會被加密。 因此，為了協助維護兩個電腦之間的安全性，我們建議兩個電腦都是相同網路的一部分。

## 相關主題


[適用於 DaRT 7.0 的操作](operations-for-dart-70-new-ia.md)

 

 





