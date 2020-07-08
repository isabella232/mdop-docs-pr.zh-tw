---
title: 使用 DaRT 7.0 復原電腦
description: 使用 DaRT 7.0 復原電腦
author: dansimp
ms.assetid: bcded7ca-237b-4971-ac34-4394b05cbc50
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 44dd48146155294bd8013b4b5a9bf23ffb3e8316
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809554"
---
# 使用 DaRT 7.0 復原電腦


使用 Microsoft Diagnostics 和復原工具集（DaRT）7來復原電腦有兩種方法可用。 您可以在本機執行 DaRT7 修復映射，或使用 DaRT7 中提供的遠端連線功能來復原遠端電腦。 本節將更詳細地說明這兩種方法。

## 使用 DaRT 恢復影像復原本機電腦


若要使用 DaRT7 來復原本機電腦，您必須在遇到需要 DaRT 之問題的最終使用者電腦上實際出現。

根據您部署 DaRT 復原影像的方式，您有數種不同的方法可供您選擇來引導至 DaRT。

-   在有問題的電腦中插入 DaRT 復原影像 CD、DVD 或 USB 快閃磁碟機，並使用它來引導至電腦。

-   從問題電腦上的 [恢復] 分區引導至 DaRT。

-   從網路上的遠端分區引導至 DaRT。

如需每個方法的優點與缺點的詳細資訊，請參閱[規劃如何儲存和部署 DaRT 7.0 恢復影像](planning-how-to-save-and-deploy-the-dart-70-recovery-image.md)。

無論您使用何種方法引導至 DaRT，您都必須在 BIOS 中啟用啟動裝置，以找到您要讓使用者使用的引導選項或選項。

**記事** 根據您組織中使用的硬碟、網路介面卡及其他硬體的類型，設定 BIOS 是唯一的。

 

[如何使用 DaRT 復原映像來復原本機電腦](how-to-recover-local-computers-using-the-dart-recovery-image-dart-7.md)

## 使用 DaRT 恢復影像復原遠端電腦


DaRT 中的遠端連線功能可讓 IT 系統管理員在最終使用者電腦上遠端執行 DaRT 工具。 當使用者（或由支援使用者電腦的技術人員）提供特定資訊之後，IT 系統管理員或技術支援人員就可以控制最終使用者的電腦，並以遠端方式執行必要的 DaRT 工具。

**重要** 建立遠端連線的兩台電腦必須是相同網路的一部分。

 

[**診斷與修復工具集**] 視窗包含在使用者從系統管理員電腦遠端執行 DaRT 的選項。 使用者會在有問題的電腦上開啟 DaRT 工具，然後按一下 [**遠端**連線] 以啟動遠端會話。

最終使用者電腦上的 [遠端連線] 功能會建立下列連線資訊：票證號碼、埠，以及所有可用 IP 位址的清單。 票據編號與埠會隨機產生。

IT 系統管理員或支援人員代理程式會將此資訊輸入到**DaRT 遠端連線檢視器**，以與使用者電腦建立終端服務連線。 建立的終端服務連線可讓 IT 系統管理員與端使用者電腦上的 DaRT 工具進行遠端互動。 最終使用者電腦接著會處理連線資訊、共用其螢幕，並回應來自 IT 系統管理員電腦的指示。

[如何使用 DaRT 復原映像來復原遠端電腦](how-to-recover-remote-computers-using-the-dart-recovery-image-dart-7.md)

## 使用 DaRT7 來復原電腦的其他資源


[適用於 DaRT 7.0 的操作](operations-for-dart-70-new-ia.md)

 

 





