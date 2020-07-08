---
title: 移除 MBAM 伺服器功能或軟體
description: 移除 MBAM 伺服器功能或軟體
author: dansimp
ms.assetid: 5212ba3f-124d-43c5-824a-608e9a192e86
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2e6e57c3d2a62a4e01242ade7a82a7bfa551da83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810880"
---
# 移除 MBAM 伺服器功能或軟體


這些指示說明如何從 Microsoft BitLocker 管理和監控（MBAM）移除軟體和功能。 如果您移除 MBAM 伺服器功能，則只會從伺服器移除已設定的功能，而不會從伺服器中移除 MBAM 伺服器軟體。 如果您移除 MBAM 伺服器軟體，您在該伺服器上設定的軟體及任何 MBAM 伺服器功能都會被移除。

**記事** 為了防止意外移除資料，MBAM 不提供移除資料庫的機制;您必須手動執行此動作。

 

## <a href="" id="bkmk-removeserverfeatures"></a>移除 MBAM 伺服器功能


您可以使用下列其中一種方法，移除您已設定的 MBAM 伺服器功能：

-   MBAM Server 設定精靈

-   Windows PowerShell Cmdlet

### 使用 MBAM 伺服器設定精靈來移除功能

請依照下列指示使用 MBAM 伺服器設定向導，以從伺服器中移除已設定的 MBAM 伺服器功能。

**使用嚮導來移除 MBAM 功能**

1.  在您要移除功能的伺服器上，選取 [ **MBAM 伺服器**設定] 以開啟 [設定] 嚮導。

2.  按一下 [**移除功能**]，選取要移除的功能，然後按 **[下一步]**。 [**摘要**] 頁面會顯示您選取要移除的功能。

3.  按一下 [**移除**] 以開始移除功能，然後按一下 [**關閉**]。

### 使用 Windows PowerShell 移除功能

使用下列步驟做為使用 Windows PowerShell Cmdlet 來移除 MBAM 伺服器功能的一般指南。

**使用 Windows PowerShell 來移除 MBAM 功能**

1.  在移除任何功能前，請參閱[使用 Windows powershell 設定 MBAM 2.5 Server 功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)，以查看使用 windows powershell 的先決條件。

2.  使用下列 Cmdlet 來移除 MBAM 伺服器功能：

    -   Disable-MbamReport

    -   Disable-MbamWebApplication

    -   Disable-MbamCMIntegration

    若要取得 Windows powershell Cmdlet 的說明，請輸入**get-help** &lt; *Cmdlet* ， &gt; 或參閱適用于 windows powershell Cmdlet 的[Microsoft 桌面優化套件 [使用 Windows powershell](https://go.microsoft.com/fwlink/?LinkId=393498) MBAM] 頁面。

## 移除 MBAM Server 軟體


使用下列步驟來移除 MBAM Server 軟體以及您在該伺服器上設定的任何 MBAM 伺服器功能。

**移除 MBAM 伺服器軟體**

1.  在您要卸載 MBAM Server 軟體的伺服器上，執行**MBAMserversetup.exe**以啟動 Microsoft BitLocker 管理及監視設定向導。

2.  選取 [**卸載**]，然後依照其餘的提示完成卸載 MBAM Server 軟體的程式。



## 相關主題


[部署 MBAM 2.5](deploying-mbam-25.md)

 

 

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。



