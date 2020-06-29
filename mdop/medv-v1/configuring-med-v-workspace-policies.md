---
title: 設定 MED-V 工作區原則
description: 設定 MED-V 工作區原則
author: dansimp
ms.assetid: 0eaed981-cbf3-4b16-a4b7-4705c5705dc7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 84bdae38b1c801e2c2be2a3dd1d12dd2ca7d932d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810808"
---
# 設定 MED-V 工作區原則


MED-V 工作區原則是一組可設定的設定，可定義虛擬化環境和應用程式在主機電腦上的執行方式。 本節中的主題描述 MED-V 工作區原則中所有可設定的設定，以及這些設定如何影響 MED-V 工作區。

提供下列 MED-V 工作區類型：

-   **Persistent**：在持久的 med-v 工作區中，使用者對 med-v 工作區所做的所有變更和新增，都儲存在 [會話] 之間的 med-v 工作區中。 此外，在網域環境中通常會使用持久的 MED-V 工作區。

-   **Revertible**-在 REVERTIBLE 的 med-v 工作區中，在每個會話完成時（亦即，當 Med-v-v 工作區停止時），med-v 工作區會在部署期間還原為原始狀態。 使用者所做的任何變更或附加都不會儲存在 [會話] 之間的 MED-V 工作區。 在網域環境中不能使用 revertible MED-V 工作區。

在部署 MED-V 工作區之前，請務必決定您要建立的 MED-V 工作區類型，因為建議您在策略部署給使用者之後，再重新設定 MED-V 工作區類型。

**記事** 設定原則時，[強制] 欄位旁會出現一個警告符號，且未填入。 如果未填入強制性欄位，該符號也會出現在索引標籤上。

 

## 本節內容


<a href="" id="how-to-apply-general-settings-to-a-med-v-workspace"></a>[如何套用一般設定到 MED-V 工作區](how-to-apply-general-settings-to-a-med-v-workspace.md)  
描述 MED-V 工作區的一般設定，以及如何將其套用至原則。

<a href="" id="how-to-apply-virtual-machine-settings-to-a-med-v-workspace"></a>[如何套用虛擬機器設定到 MED-V 工作區](how-to-apply-virtual-machine-settings-to-a-med-v-workspace.md)  
描述 MED-V 工作區的虛擬機器設定，以及如何將其套用至原則。

<a href="" id="how-to-configure-a-domain-user-or-group"></a>[如何設定網域使用者或群組](how-to-configure-a-domain-user-or-groupmedvv2.md)  
說明如何設定網域使用者和群組。

<a href="" id="how-to-configure-published-applications"></a>[如何設定已發佈的應用程式](how-to-configure-published-applicationsmedvv2.md)  
說明已發佈的應用程式和功能表，以及如何將它們套用至原則。

<a href="" id="how-to-configure-web-settings-for-a-med-v-workspace"></a>[如何設定 MED-V 工作區的網頁設定](how-to-configure-web-settings-for-a-med-v-workspace.md)  
說明 MED-V 工作區可用的網路設定，以及如何將其套用至原則。

<a href="" id="how-to-configure-the-virtual-machine-setup-for-a-med-v-workspace"></a>[如何設定 MED-V 工作區的虛擬機器設定](how-to-configure-the-virtual-machine-setup-for-a-med-v-workspace.md)  
說明 MED-V 工作區的虛擬機器設定，以及如何將其套用至原則。

<a href="" id="how-to-apply-network-settings-to-a-med-v-workspace"></a>[如何套用網路設定到 MED-V 工作區](how-to-apply-network-settings-to-a-med-v-workspace.md)  
描述 MED-V 工作區的網路設定，以及如何將其套用至原則。

<a href="" id="how-to-apply-performance-settings-to-a-med-v-workspace"></a>[如何套用效能設定到 MED-V 工作區](how-to-apply-performance-settings-to-a-med-v-workspace.md)  
描述 MED-V 工作區的效能設定，以及如何將其套用至原則。

<a href="" id="how-to-import-and-export-a-policy"></a>[如何匯入和匯出原則](how-to-import-and-export-a-policy.md)  
說明如何匯入及匯出原則。

 

 





