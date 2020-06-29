---
title: 如何使用效能計數器管理 App-V 用戶端快取
description: 如何使用效能計數器管理 App-V 用戶端快取
author: dansimp
ms.assetid: 49d6c3f2-68b8-4c69-befa-7598a8737d05
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 396cceaf9a3bde661200be2771a85596a512732f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801294"
---
# 如何使用效能計數器管理 App-V 用戶端快取


您可以在應用程式虛擬化（App-v）用戶端快取中使用 [效能監視器] 以圖形顯示資訊來判斷有多少可用空間。 此資訊是在用戶端電腦上透過一個名為「應用程式 Virt 用戶端快取」的效能計數器來捕獲，且包含下列計數器：「快取大小（MB）」、「快取磁碟空間（MB）」和「% 可用空間」。

**判斷用戶端的快取空間使用量**

1.  以系統管理員身分開啟命令提示字元，或按一下 [**開始**]、[**執行**]，輸入**perfmon.exe**，然後按一下 **[確定]**。

2.  根據所使用的 Windows 作業系統，在 MMC 視窗開啟後，按一下 [效能監視器] 或 [系統監視器] 工具。

3.  若要新增計數器，請以滑鼠右鍵按一下繪圖區域，然後選取 [**新增計數器**]。

4.  按一下下拉式清單以顯示可用計數器的清單、滾動至 [尋找**應用程式 Virt 用戶端**快取]，然後新增三個計數器。

    **重要** App V 效能計數器是在32位 DLL 中實現，因此若要查看它們，您必須使用下列命令來啟動32位版本的效能監視器： **mmc/32 perfmon**。 這個命令必須直接在受監視的電腦上執行，而且無法用來監視執行64位作業系統的遠端電腦。

     

## 相關主題


[如何使用命令列管理虛擬應用程式](how-to-manage-virtual-applications-by-using-the-command-line.md)

 

 





