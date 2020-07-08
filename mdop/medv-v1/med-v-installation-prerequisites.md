---
title: MED-V 安裝必要條件
description: MED-V 安裝必要條件
author: dansimp
ms.assetid: cf3c0906-23eb-4c4a-8951-a65741720f95
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2b432b8c2b06e171eb339aab6c7b15efb20d5919
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810874"
---
# MED-V 安裝必要條件


以下是安裝 MED-V 的先決條件：

[Active Directory 需求](#bkmk-activedirectoryrequirements)

[報表資料庫](#bkmk-howtoinstallthereportdatabase)

[防病毒/備份軟體設定](#bkmk-antivirusbackupsoftwareconfiguration)

[Microsoft Virtual PC 2007 SP1](#bkmk-howtoinstallandconfiguremicrosoftvirtualpc2007sp1)

## <a href="" id="bkmk-activedirectoryrequirements"></a>Active Directory 需求


在配置 MED-V 伺服器時，如果使用者不屬於伺服器所屬的網域，則必須在網域之間設定信任。

## <a href="" id="bkmk-howtoinstallthereportdatabase"></a>如何安裝報表資料庫


儲存所有 MED-V 工作區記錄需要報表資料庫。 然後，就會使用記錄資料庫來產生 MED-V 報告。 如需報告的相關資訊，請參閱[Med-v 報告](med-v-reporting.md)。

SQL Server 可以安裝在與 MED-V 伺服器相同的伺服器上，或安裝在遠端伺服器上。 如果是在遠端伺服器上安裝，請參閱[在遠端伺服器上安裝 SQL server](#bkmk-installingsqlserveronaremoteserver)。

### <a href="" id="bkmk-installingsqlserveronaremoteserver"></a>在遠端伺服器上安裝 SQL Server

**在遠端伺服器上安裝 SQL Server**

1.  在遠端伺服器上設定下列專案：

    -   實例名稱-預設實例

    -   驗證模式-混合模式

    -   使用者：建立的預設使用者為「sa」

    -   密碼-所需的密碼

    -   排序規則設定-預設

    -   使用方式報告設定中的錯誤-預設值

2.  在 MED-V 伺服器上安裝下列檔案：

    -   若要針對 Microsoft SQL Server2008 的管理套件物件集合安裝必備元件，請從 Microsoft 下載中心下載[MICROSOFT Sql Server2008 原生用戶端](https://go.microsoft.com/fwlink/?LinkId=164039)。

    -   若要針對 Microsoft SQL Server2005 的管理套件物件集合安裝必備元件，請從 Microsoft 下載中心下載[MICROSOFT Sql Server2005 原生用戶端](https://go.microsoft.com/fwlink/?LinkId=164038)。

    -   若要為 Microsoft SQL Server2008 安裝必要的 dll 檔案，請從 Microsoft 下載中心下載[MICROSOFT Sql Server 2008 管理物件集合](https://go.microsoft.com/fwlink/?LinkId=164041)。

    -   若要為 Microsoft SQL Server2005 安裝必要的 dll 檔案，請從 Microsoft 下載中心下載[MICROSOFT SQL Server2005 管理物件](https://go.microsoft.com/fwlink/?LinkId=164040)。

    -   若要安裝可提供其他 SQL Server2008 值的獨立安裝套件，請從 Microsoft 下載中心下載[MICROSOFT SQL Server2008 功能套件](https://go.microsoft.com/fwlink/?LinkId=163960)。

    -   若要安裝可提供其他 SQL Server2005 值的獨立安裝套件，請從 Microsoft 下載中心下載[MICROSOFT SQL Server2005 的功能套件]( https://go.microsoft.com/fwlink/?LinkId=163961)。

    如需這些檔案的詳細資訊，請參閱 microsoft 下載中心（或 microsoft 下載中心的功能套件）上的[MICROSOFT Sql Server2008 功能套件](https://go.microsoft.com/fwlink/?LinkId=163960)（ https://go.microsoft.com/fwlink/?LinkId=163960) 或 microsoft 下載中心的 [ [microsoft sql Server2005](https://go.microsoft.com/fwlink/?LinkId=163961) ] https://go.microsoft.com/fwlink/?LinkId=163961) 。

## <a href="" id="bkmk-antivirusbackupsoftwareconfiguration"></a>防病毒/備份軟體設定


若要防止防病毒活動影響虛擬桌面的效能，建議您盡可能從主機上執行的任何防毒軟體或備份處理常式中排除下列虛擬機器檔案類型：

-   \*.VMC

-   \*.VUD

-   \*.VSV

-   \*.CKM

-   \*.EVHD

## <a href="" id="bkmk-howtoinstallandconfiguremicrosoftvirtualpc2007sp1"></a>如何安裝和設定 Microsoft Virtual PC2007 SP1


**重要** 如果主機電腦上存在 Windows 版虛擬電腦，請在安裝 Virtual PC2007 SP1 之前先將它卸載。

 

**若要安裝 Microsoft Virtual PC2007 SP1**

1.  從 Microsoft 下載中心[VIRTUAL PC 2007 SP1](https://go.microsoft.com/fwlink/?LinkId=142994)下載 VIRTUAL PC2007 SP1。

2.  在主機電腦上執行安裝檔，然後依照嚮導進行。

3.  在主機電腦上以提升模式安裝 Virtual PC2007 SP1 更新。

    如需詳細資訊，請參閱適用于[VIRTUAL PC 2007 SP1 之修補程式套件的說明](https://go.microsoft.com/fwlink/?LinkId=150575)。

    **記事** 執行 Virtual PC2007 SP1 需要 Virtual PC2007 SP1 更新。

     

## 相關主題


[支援的設定](supported-configurationsmedv-orientation.md)

 

 





