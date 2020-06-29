---
title: 規劃 Application Virtualization Sequencer 實作
description: 規劃 Application Virtualization Sequencer 實作
author: dansimp
ms.assetid: 052f32fe-ad13-4921-a8ce-4a657eb2b2bf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ac62991e290dcd2da1c42f025a19365bda239fb8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800910"
---
# 規劃 Application Virtualization Sequencer 實作


排序，應用程式虛擬化用來建立虛擬應用程式和應用程式套件的處理常式，需要使用已安裝 Application Virtualization Sequencer 軟體的電腦。

在先後順序程式期間，Sequencer 會放在 [監視器] 模式中，而要排序的應用程式會安裝在先後順序電腦上。 接著，將會啟動已排序的應用程式，並使用其最重要及常用的函數，讓監視程式可以設定主要功能區塊，其中包含應用程式執行所需的應用程式套件中的最小內容。 完成這些步驟後，系統就會停止監視模式，並儲存並測試已排序的應用程式，以驗證正確的操作。

決定要為排序次序選擇哪些應用程式時，請記住某些應用程式無法排序。 其中包括 Windows 作業系統的特定部分，例如 Internet Explorer、裝置驅動程式，以及在啟動時啟動服務的應用程式。

如需安裝排序器的逐步資訊，請參閱[如何安裝 Application Virtualization 排序](how-to-install-the-application-virtualization-sequencer.md)器。

**重要** 整個連續處理程式方案應該由您的公司安全小組審查並核准。 排序器作業通常會與實驗室中的生產環境保持分開。 根據您的業務需求，這可以根據您的需求簡單或完整。 先後順序電腦需要連線到公司網路，才能將完成的套件複製到生產伺服器。 不過，由於它們通常是在沒有防防毒保護的情況下運作，因此它們不能在未受保護的商業網路上（例如，您可能可以在防火牆之後或獨立的網路區段上運作）。 使用配置來共用隔離虛擬網路的虛擬機器也可能是可接受的方法。 依照您公司的安全性原則來安全地解決這種情況。

 

規劃先後順序程式的主要步驟包括下列各項：

-   考慮您預計每個月處理的應用程式數、這些應用程式的大小，以及新增排序後續更新的余量。 套件的大小最多可達 4 GB，且已壓縮或未壓縮。

-   在排序每個應用程式時，準備並記錄貴組織要追蹤的可重複程式。 這應該包括在每個執行中使用檢查清單，以及版本控制程式。 在調查套件可能的技術問題時，對每個已排序的應用程式使用追蹤記錄也很有説明。

-   針對應用程式排序，請使用最適合處理輸送量的高性能電腦，其中至少有 4 GB 的 RAM 與快速 CPU （3 GHz 或更快的速度）。 快速硬碟及個別磁片卷的使用也可以改善效能。 虛擬機器非常適合用來進行排序，因為它們很容易重設，或者您可以在本機分區上使用具有乾淨影像的物理電腦，在完成每個套件排序作業之後，進行快速重新影像。

    **重要** 在安全模式中執行 App-v 排序器不受支援。

     

-   確認您瞭解已排序的應用程式的操作環境（包括 Microsoft Office 或 JAVA 執行時間環境等整合元素），因為這通常會判斷在排序應用程式之前，是否必須在順序電腦上安裝任何專案。

-   確定每個新的順序作業都是以乾淨的基本影像開始。 在放棄所有變更之後，請確認已將已儲存的影像還原至物理電腦，或重新開機虛擬機器，以確保先後順序電腦已重設。 在儲存前，基本影像應該已從 Windows Update 套用最新的更新。

-   在順序電腦上關閉可能幹擾安裝監控程式（例如防病毒掃描程式和 Windows Update）的任何專案，因為在排序程式期間有一個穩定的平臺是必要的。 因為這個步驟會產生大量的安全性風險，所以請務必採取正確的預防措施來保護電腦和網路，以及已排序的應用程式套件。 我們建議您在將應用程式套件排序前，先進行防病毒掃描。

-   在排序之後包含測試每個應用程式的詳細程式。 在將虛擬化應用程式部署到最終使用者之前，測試已排序的應用程式將會判斷它是否正常運作，且是程式的基本部分。 在橫向部署到最終使用者之前先測試的最後一個步驟，您也應該規劃試驗式部署至測試群組。

-   測試順序式應用程式時，請選擇相同類型的電腦設備，並執行在公司生產環境中使用的相同作業系統。 只要正確設定，就可以使用虛擬電腦或物理電腦。

## 相關主題


[Application Virtualization Sequencer 硬體和軟體需求](application-virtualization-sequencer-hardware-and-software-requirements.md)

[如何安裝 Application Virtualization Sequencer](how-to-install-the-application-virtualization-sequencer.md)

[如何升級 Application Virtualization Sequencer](how-to-upgrade-the-application-virtualization-sequencer.md)

[安全性與保護概觀](security-and-protection-overview.md)

 

 





