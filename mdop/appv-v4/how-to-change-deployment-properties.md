---
title: 如何變更部署內容
description: 如何變更部署內容
author: dansimp
ms.assetid: 0a214a7a-cc83-4d04-89f9-5727153be918
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dfb42962d41159479db61da9c3beb3771ef35502
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801666"
---
# 如何變更部署內容


您可以使用下列程式來變更您要排序之應用程式的 [**部署**] 索引標籤資訊，包括應用程式虛擬化伺服器 URL、虛擬化應用程式所需的作業系統，以及要安裝之虛擬應用程式的輸出選項。

**若要變更伺服器 URL**

1.  從下拉式清單方塊中選取 [串流] 通訊協定。

2.  輸入虛擬應用程式伺服器的主機名稱或伺服器群組的負載平衡器。 您可以使用 [實際主機名稱] 或 [IP 位址]。

3.  指定虛擬應用程式伺服器或負載平衡器針對流程式應用程式偵聽應用程式虛擬化桌面用戶端要求的埠號碼。

4.  指定儲存軟體套件之虛擬應用程式伺服器上的相對路徑。

**變更應用程式作業系統需求**

1.  若要新增所需的作業系統，請在 [**可用**] 清單中選取它，然後按一下指向**選取**的作業系統清單控制項的箭號按鈕。

2.  若要移除作業系統，請在**選取**的清單控制項中選取它，然後按一下指向 [**可用**的作業系統] 清單控制項的箭號按鈕。

**變更應用程式輸出選項**

1.  從 [**壓縮演算法]** 下拉式清單中，選取要在流式處理應用程式時使用的壓縮方式。

2.  選取 [**強制安全性描述項**] 核取方塊，以確保已部署封裝應用程式的安全性描述項。

3.  選取 [**產生差異**檔案]，以產生來自先前已排序版本之應用程式的差異檔案。

4.  選取 **[產生 Microsoft Windows Installer （MSI）套件**] 來建立安裝程式套件。

## 相關主題


[關於部署索引標籤](about-the-deployment-tab.md)

[排序器主控台](sequencer-console.md)

 

 





