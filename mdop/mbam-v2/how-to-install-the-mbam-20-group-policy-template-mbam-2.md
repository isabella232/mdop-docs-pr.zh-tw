---
title: 如何安裝 MBAM 2.0 群組原則範本
description: 如何安裝 MBAM 2.0 群組原則範本
author: dansimp
ms.assetid: bc193232-d060-4285-842e-d194a74dd3c9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6420fc4d499de05ed740b038b40aff6a9cd8a05f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811643"
---
# 如何安裝 MBAM 2.0 群組原則範本


除了伺服器相關的 Microsoft BitLocker 管理與監控（MBAM）功能之外，伺服器安裝應用程式還包含 Microsoft BitLocker 管理和監視群組原則範本。 此範本可安裝在任何能夠執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）的電腦上。

下列步驟說明如何安裝 MBAM 群組原則範本。

**記事** 請務必在32位伺服器上使用32位設定，以及在64位伺服器上進行64位設定。

 

**若要安裝 MBAM 群組原則範本**

1.  在您要安裝 MBAM 的伺服器上，執行**MBAMSetup.exe** ，啟動 [MBAM 安裝] 嚮導。

2.  在 [**歡迎**] 頁面上，選擇性地選取 [**客戶經驗改進計畫**]，然後按一下 [**開始**]。

3.  閱讀並接受 Microsoft 軟體授權條款，然後按一下 **[下一步]** 繼續安裝。

4.  根據預設，系統會選取所有 Microsoft BitLocker 管理和監視功能來進行安裝。 清除 [**原則範本**] 以外的所有功能選項，然後按 **[下一步]** 繼續安裝。

    **記事** 安裝精靈會檢查安裝的先決條件，並顯示遺失的先決條件。 如果符合所有先決條件，安裝會繼續進行。 如果偵測到遺失的先決條件，您必須先解決遺失的先決條件，然後再次按一下 [**檢查必備元件**]。 一旦符合所有先決條件，就會繼續安裝。

     

5.  如需如何以及在哪裡安裝範本的相關步驟，請參閱[如何下載和部署 MDOP 組原則（admx）範本](https://technet.microsoft.com/library/dn659707.aspx)。

6.  在 Microsoft BitLocker 管理及監視安裝精靈顯示所選功能的安裝頁面之後，按一下 **[完成]** 以關閉 MBAM 安裝程式。

## 相關主題


[部署 MBAM 2.0 群組原則物件](deploying-mbam-20-group-policy-objects-mbam-2.md)

 

 





