---
title: DaRT 8.0 的安全性考量
description: DaRT 8.0 的安全性考量
author: dansimp
ms.assetid: 45ef8164-fee7-41a1-9a36-de4e3264e7a8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 02d32d926c0def7d33bebd399cd380eed4e8385e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800158"
---
# DaRT 8.0 的安全性考量


本主題包含帳戶和群組、記錄檔案，以及 Microsoft Diagnostics 與恢復工具組（DaRT）8.0 的其他安全相關注意事項的簡短概述。 如需詳細資訊，請參閱本文中的連結。

## 一般安全性考慮


**瞭解安全性風險**。 DaRT 8.0 包含的功能可讓系統管理員或技術支援人員遠端執行 DaRT 工具，以解決最終使用者電腦上的問題。 此外，您可以將國際標準組織（ISO）影像儲存至 USB 快閃記憶體磁片磁碟機，或將 ISO 影像放在網路上，將其內容納入電腦硬碟上的復原分區。 這些功能提供靈活性，但也會產生您在設定 DaRT 時應考慮的潛在安全風險。

**在物理上保護您的電腦**。 當系統管理員與技術支援人員在電腦上實際不在電腦上時，他們應該鎖定其電腦，並使用安全的螢幕保護裝置程式。

**將最新的安全性更新套用至所有電腦**。 訂閱安全性通知服務（），隨時掌握新的作業系統更新通知 <https://go.microsoft.com/fwlink/?LinkId=28819> 。

## 限制最終使用者存取 DaRT 工具


當您建立 DaRT 復原影像時，您可以選取要包含的工具。 出於安全性考慮，您可能會想要限制最終使用者存取更強大的 DaRT 工具，例如磁片擦除及 Locksmith。 在 DaRT 8.0 中，您可以在設定期間停用某些工具，並讓使用者在使用者啟動遠端連線功能時，仍能使用技術支援人員。

您甚至可以設定 DaRT 影像，讓 [啟動遠端連線會話] 選項成為最終使用者可以使用的唯一工具。

**重要** 在遠端連線建立之後，您在復原影像中所包含的所有工具，包括最終使用者無法使用的所有工具，都會提供給在最終使用者電腦上工作的任何技術支援人員。

 

如需在 DaRT 復原影像中加入工具的詳細資訊，請參閱[dart 8.0 中的工具概覽](overview-of-the-tools-in-dart-80-dart-8.md)。

## 保護 DaRT 恢復影像


如果您是將 DaRT 復原影像儲存至 USB 快閃記憶體磁片磁碟機，或建立遠端分區或復原分區，您可能會想要在 ISO 上加入貴公司的首選磁片磁碟機加密方法。 加密 ISO 可協助確保使用者無法使用 DaRT 功能取得對復原影像的存取權，並確保未經授權的使用者無法在屬於其他人的電腦上啟動到 DaRT。 如果您使用加密方法，請務必在所有電腦中部署並啟用該方法。

**記事** DaRT 8.0 本身支援 BitLocker。

 

若要納入磁片磁碟機加密，請在建立復原影像時新增加密方案檔案。 您的加密解決方案必須能夠在 WinPE 上執行。 從 ISO 啟動的最終使用者可以存取該加密解決方案並解除封鎖磁片磁碟機。

## 當您使用遠端連線時，在兩部電腦之間維持安全性


根據預設，已建立**遠端**連線會話的兩台電腦之間的通訊可能不會被加密。 因此，為了協助維護兩個電腦之間的安全性，我們建議兩個電腦都是相同網路的一部分。

## 相關主題


[DaRT 8.0 的安全性與隱私權](security-and-privacy-for-dart-80-dart-8.md)

 

 





