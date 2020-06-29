---
title: 如何設定安裝後續管理伺服器安全性
description: 如何設定安裝後續管理伺服器安全性
author: dansimp
ms.assetid: 71979fa6-3d0b-4a8b-994e-cb728d013090
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 521e72ead78055a7d3261664ccb75d454c22e622
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801617"
---
# 如何設定安裝後續管理伺服器安全性


使用 App-v 管理主控台來新增憑證，並設定 App-v Management Server 以增強安全性。 您可以使用下列程式來設定安裝後的安全性。

**設定管理伺服器安全性安裝後**

1.  開啟 App-v 管理主控台，然後使用 App-v 管理員許可權連線到**管理服務**。

2.  展開 [伺服器]，展開 [**伺服器群組**]，然後選取要用來註冊管理伺服器的適當伺服器群組。

3.  以滑鼠右鍵按一下管理伺服器物件，然後選取 [**屬性**]。

4.  在 [**埠**] 索引標籤上，按一下 [**伺服器憑證**] 並完成嚮導，以選取正確提供的憑證。

    **記事** 如果嚮導中沒有顯示任何憑證，則憑證尚未提供，或憑證符合 App-v 的需求。

     

5.  按一下 **[下一步**]，繼續至 [**歡迎使用憑證] 嚮導**頁面。

6.  在 [**可用的憑證**] 畫面中選取正確的憑證。

7.  按一下 **\[完成\]**。

8.  完成嚮導之後，清除 [ **RTSP** ] 做為可用的偵聽埠。 這可防止透過不安全的通訊通道進行連線。

9.  按一下 **[** 套用]，然後重新開機**Microsoft 虛擬應用程式伺服器**服務。 使用服務的 MMC 管理單元來完成這項工作。

## 相關主題


[如何設定安裝後續串流伺服器安全性](how-to-configure-streaming-server-security-post-installation.md)

[疑難排解憑證權限問題](troubleshooting-certificate-permission-issues.md)

 

 





