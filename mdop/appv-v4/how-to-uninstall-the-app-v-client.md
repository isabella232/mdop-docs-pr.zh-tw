---
title: 如何解除安裝 App-V Client
description: 如何解除安裝 App-V Client
author: dansimp
ms.assetid: 07591270-9651-4bb5-a5b3-e0fc009bd9e2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: acb3f53b42027ff2c1b84fd2ab2bdde3c52f96de
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801050"
---
# 如何解除安裝 App-V Client


使用下列程式從電腦卸載應用程式虛擬化用戶端。

**卸載應用程式虛擬化桌面用戶端**

1.  在 [控制台] 中，按兩下 [**新增或移除程式**] （或在 Windows Vista 中，按一下 [**程式和功能**]），然後按兩下 [ **Microsoft Application Virtualization 桌面用戶端**]。

2.  在出現的對話方塊中，按一下 [**是**] 以繼續卸載程式。

    **重要** 無法取消或中斷卸載程式。

     

3.  如果出現指出 Microsoft Application Virtualization 用戶端工作列應用程式的訊息必須在 [繼續] 出現前關閉，請以滑鼠右鍵按一下通知區域中的 app-v 圖示，**然後選取 [** 結束] 來關閉應用程式。 然後按一下 [**重試**] 繼續卸載程式。

    **重要** 您可能會看到一則訊息，指出正在使用一或多個虛擬應用程式。 在繼續之前，請先關閉任何開啟的應用程式並儲存您的資料。 然後按一下 **[確定]** ，繼續進行卸載程式。

     

4.  進度列會顯示剩餘的時間。 完成這個步驟後，您必須重新開機電腦，才能停止所有相關聯的驅動程式來完成卸載程式。

    **記事** 卸載程式完成之後，下列登錄機碼仍會保留：

    -   HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid

    -   HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4。5

    -   HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard "用戶端" = dword：00000000

    -   HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\SecKey

     

## 相關主題


[如何使用命令列安裝用戶端](how-to-install-the-client-by-using-the-command-line-new.md)

[如何手動安裝 Application Virtualization Client](how-to-manually-install-the-application-virtualization-client.md)

[如何在用戶端上發佈虛擬應用程式](how-to-publish-a-virtual-application-on-the-client.md)

 

 





