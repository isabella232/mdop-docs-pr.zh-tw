---
title: 如何移動 MBAM 2.5 網站
description: 如何移動 MBAM 2.5 網站
author: dansimp
ms.assetid: 71af9a54-c27b-408f-9d75-37c0d02e730e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa5bd8156810b3dccc1588b4dfd4cadd96fd22fb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811342"
---
# 如何移動 MBAM 2.5 網站


您可以使用這些程式將下列 MBAM 網站從一部電腦移到另一部，也就是將下列功能從伺服器 A 移到伺服器 B：

-   管理和監控網站

-   自助服務入口網站

**重要** 在這兩個網站的設定期間，您必須提供相同的連線字串、報表 URL、群群組帳戶，以及 web 服務應用程式池網域帳戶作為您目前正在使用的專案。 如果您沒有使用相同的值，就無法存取某些伺服器。 若要取得目前的值，請使用**MbamWebApplication** Windows PowerShell Cmdlet。

 

**將管理和監控網站移至另一個伺服器**

1.  在伺服器 B 上，安裝 MBAM 2.5 Server 軟體。 如需相關指示，請參閱[安裝 MBAM 2.5 Server 軟體](installing-the-mbam-25-server-software.md)。

2.  在伺服器 B 上，啟動 [MBAM 伺服器設定向導]，按一下 [新增**功能**]，然後只選取 [**管理及監視網站**] 功能。

    或者，您也可以使用**Enable-MbamWebApplication** Windows PowerShell Cmdlet 來設定管理和監控網站。

    如需如何設定管理和監控網站的相關指示，請參閱[如何設定 MBAM 2.5 Web 應用程式](how-to-configure-the-mbam-25-web-applications.md)。

**將自助式入口網站移至另一個伺服器**

1.  在伺服器 B 上，安裝 MBAM 2.5 Server 軟體。 如需相關指示，請參閱[安裝 MBAM 2.5 Server 軟體](installing-the-mbam-25-server-software.md)。

2.  在伺服器 B 上，啟動 [MBAM 伺服器設定向導]，按一下 [新增**功能**]，然後只選取 [**自助入口網站**] 功能。

    或者，您也可以使用**Enable-MbamWebApplication** Windows PowerShell Cmdlet 來設定自助入口網站。

    如需如何設定管理和監控網站的相關指示，請參閱[如何設定 MBAM 2.5 Web 應用程式](how-to-configure-the-mbam-25-web-applications.md)。

3.  如果貴組織中的用戶端電腦沒有 Microsoft 內容傳遞網路的存取權，您也必須移動 JavaScript 檔案。 如需詳細資訊，請參閱[如何在用戶端電腦無法存取 Microsoft 內容傳遞網路時，設定自助服務入口網站](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)。

4.  自訂貴組織的自助入口網站。 使用[自訂貴組織的自助入口網站](customizing-the-self-service-portal-for-your-organization.md)中的指示來查看您目前的自訂專案，以及在伺服器 B 的自助伺服器入口網站上設定自訂設定。



## 相關主題


[如何設定 MBAM 2.5 Web 應用程式](how-to-configure-the-mbam-25-web-applications.md)

[使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)

[將 MBAM 2.5 功能移到其他伺服器](moving-mbam-25-features-to-another-server.md)

 

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





