---
title: 如何使用 Configuration Manager 驗證 MBAM 安裝
description: 如何使用 Configuration Manager 驗證 MBAM 安裝
author: dansimp
ms.assetid: 8e268539-91c3-4e8a-baae-faf3605da818
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 500c6f6ee5138b5677bf1fa20e2627a56981df1f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809476"
---
# 如何使用 Configuration Manager 驗證 MBAM 安裝


透過 Configuration Manager 安裝 Microsoft BitLocker 管理和監控（MBAM）之後，請完成下列步驟，以確認安裝已成功設定 MBAM 的所有必要功能。

**使用 Configuration Manager 驗證 MBAM Server 功能安裝**

1.  在部署 System Center Configuration Manager 的伺服器上，開啟 [**控制台**]。 選取用來卸載或變更程式的程式。 確認 [ **Microsoft BitLocker 管理及監視**] 出現在 [程式和功能] 清單中。

    **記事** 若要驗證安裝，您必須使用在每個伺服器上都有本機電腦管理認證的網域帳戶。

     

2.  使用 Configuration Manager 主控台確認顯示名為「MBAM 支援的電腦」的新集合。

    若要查看 Configuration Manager 2007 的集合：按一下 [**網站資料庫**（ &lt; **SiteCode** &gt;  -  &lt; **ServerName** &gt; 、 &lt; **SiteName** &gt; ）]、[**電腦管理**]。

    若要使用 SystemCenter2012 ConfigurationManager 來查看集合：按一下 [**資產] 和 [合規性**工作區]、[**裝置集合**]。

3.  使用 Configuration Manager 主控台確認下列報告已列在 [ **MBAM** ] 資料夾中：

    -   BitLocker 電腦合規性

    -   BitLocker Enterprise 合規性儀表板

    -   BitLocker 企業合規性詳細資料

    -   BitLocker Enterprise 合規性摘要

    若要查看 Configuration Manager 2007 的報表：按一下 [**報告**]、[**報表服務**]、[\\ &lt; **伺服器名稱**] &gt; 、[**報告資料夾**]

    若要使用 SystemCenter2012 ConfigurationManager 來查看報表：按一下 [**監視**] 工作區、[**報告**]、[**報告**]。

4.  使用 Configuration Manager 主控台確認已列出設定比較基準 "BitLocker 保護"。

    若要查看 Configuration Manager 2007 的配置基線：按一下 [想要的設定**管理**]、[**配置基線**]。

    若要使用 SystemCenter2012 ConfigurationManager 來查看配置基線：按一下 [**資產與合規性**工作區]、[**合規性設定**]、[**配置基準**]。

5.  使用 Configuration Manager 主控台確認顯示下列新的設定專案：

    -   BitLocker 固定資料磁碟機保護

    -   BitLocker 作業系統磁片磁碟機保護

    若要查看 configuration Manager 2007 的設定專案：按一下 [想要的設定**管理**]、[**設定項目**]。

    若要使用 SystemCenter2012 ConfigurationManager 來查看設定專案：按一下 [**資產與合規性**工作區]、[**合規性設定**]、[**設定項目**]。

## 相關主題


[使用設定管理員來部署 MBAM](deploying-mbam-with-configuration-manager-mbam2.md)

 

 





