---
title: MBAM 2.5 搭配 Configuration Manager 整合拓撲的概要架構
description: MBAM 2.5 搭配 Configuration Manager 整合拓撲的概要架構
author: dansimp
ms.assetid: 075bafa1-792b-4c24-9d8e-5d3153e2112c
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/23/2018
ms.author: dansimp
ms.openlocfilehash: a0f9349391794100a670e382bb18d0713f4b5b60
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910718"
---
# <a name="high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology"></a>具有 Configuration Manager 整合拓撲的 LEVELM 2.5 架構

本主題說明使用 Configuration Manager 整合拓撲 (部署 Microsoft BitLocker 系統管理與監控) 架構。 此拓撲整合了 SYSTEM CENTER CONFIGURATION MANAGER。 若要使用獨立拓撲部署管理，請參閱使用獨立拓撲的[高層級架構的 2.5。](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)

有關本主題中提及的軟體支援版本清單，請參閱[適用于支援的組配置。](mbam-25-supported-configurations.md)

**重要**  
Windows當您使用 Configuration Manager 2007 時，Configuration Manager 整合拓撲安裝不支援前往。

 

## <a name="recommended-number-of-servers-and-supported-number-of-clients"></a>建議的伺服器數量和支援的用戶端數目


在生產環境中，建議的伺服器數目和支援的用戶端數目如下：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">建議的架構</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>伺服器和其他電腦數目</p></td>
<td align="left"><p>三個伺服器</p>
<p>一個工作站</p></td>
</tr>
<tr class="even">
<td align="left"><p>支援的用戶端電腦數目</p></td>
<td align="left"><p>500,000</p></td>
</tr>
</tbody>
</table>

 

## <a name="differences-between-configuration-manager-integration-and-stand-alone-topologies"></a>Configuration Manager 整合與獨立拓撲之間的差異


拓撲的主要差異為：

-   合規性與報告功能會從管理管理區中移除，並且從 Configuration Manager 存取。

-   報表會從 Configuration Manager 管理主控台進行查看，但復原稽核報告除外，您可以繼續從管理與監控網站查看。

## <a name="recommended-mbam-high-level-architecture-with-the-configuration-manager-integration-topology"></a>建議的具有 Configuration Manager 整合拓撲的高層級架構


下列圖表和表格說明建議使用 Configuration Manager 整合拓撲的適用于該架構的高層級架構。 需要單向或雙向信任的跨林部署。 單向信任要求伺服器網域信任用戶端網域。

![5。](images/mbam2-5-cmserver.png)

### <a name="database-server"></a>資料庫伺服器

#### <a name="recovery-database"></a>修復資料庫

這項功能是在執行伺服器Windows且受支援SQL Server實例上。

修復 **資料庫** 會儲存從 SQLM 用戶端電腦收集的修復資料。

#### <a name="audit-database"></a>稽核資料庫

這項功能是在執行伺服器Windows且受支援SQL Server實例上。

稽 **核資料庫** 會儲存從已存取復原資料的用戶端電腦收集的稽核活動資料。

#### <a name="reports"></a>報告

這項功能是在執行伺服器Windows且受支援SQL Server實例上。

報告 **會** 針對您企業中的用戶端電腦提供修復稽核資料。 您可以直接從 Configuration Manager 主控台或直接從 SQL Server Reporting Services。

### <a name="configuration-manager-primary-site-server"></a>Configuration Manager 主網站伺服器

System Center Configuration Manager整合功能

-   這項功能是在 Configuration Manager 主網站伺服器上所配置，這是您 Configuration Manager 基礎結構中的頂層伺服器。

-   Configuration **Manager Server** 會收集用戶端電腦的硬體庫存資訊，並用來報告用戶端電腦的 BitLocker 合規性。

-   當您執行 Microsoft BitLocker 系統管理與監控設定精靈以安裝伺服器軟體時，系統會設定在 Configuration Manager 主網站伺服器上，提供支援 IBMM 的電腦集合、設定比較基準和報表。

-   Configuration **Manager 主機** 必須安裝在您安裝該電腦之 IBMM Server 軟體的同一部電腦上。

### <a name="administration-and-monitoring-server"></a>系統管理與監控伺服器

#### <a name="administration-and-monitoring-website"></a>系統管理與監控網站

此功能是在執行伺服器Windows上。

系統 **管理與監控網站** 用於：

-   協助使用者在鎖定時重新取得電腦存取權。 (網站的這個區域通常稱為技術支援中心。) 

-   查看修復稽核報告，其中顯示用戶端電腦的修復活動。 其他報表會從 Configuration Manager 主控台進行查看。

#### <a name="self-service-portal"></a>自助入口網站

此功能是在執行伺服器Windows上。

**自助入口**網站是一個網站，可讓用戶端電腦上的使用者獨立登入網站，以在使用者失去或忘記 BitLocker 密碼時取得修復金鑰。

#### <a name="monitoring-web-services-for-this-website"></a>監控此網站的 Web 服務

這項功能會安裝在執行伺服器Windows電腦上安裝。

**監控 Web 服務**會由 SQLM Client 和網站用來與資料庫通訊。

**重要**<br>Microsoft BitLocker 系統管理與監控 () 2.5 SP1 中不再提供監控 Web 服務，因為 MICROSOFT BITLocker 網站會直接與修復資料庫通訊。 

 

### <a name="management-workstation"></a>管理工作站

#### <a name="mbam-group-policy-templates"></a>管理與管理管理小群組原則範本

-   **此為群組原則**設定，可定義用於管理 BitLocker 磁片磁碟機加密的實現設定。

-   執行 MDM 之前，您必須從如何取得 MDOP 群組原則[ (.admx) 範本](https://go.microsoft.com/fwlink/p/?LinkId=393941)下載群組原則範本，並複製到執行支援的 Windows Server 或 Windows 作業系統的伺服器或工作站。

    **注意**<br>工作站不需要是專用電腦。

     

### <a name="mbam-client-and-configuration-manager-client-computer"></a>管理與管理用戶端與 Configuration Manager 用戶端電腦

#### <a name="mbam-client-software"></a>管理與管理管理用戶端軟體

**此為 ：：**

-   使用群組原則物件在企業用戶端電腦上強制執行 BitLocker 磁片磁碟機加密。

-   收集三種資料磁碟機類型的 BitLocker 修復金鑰：作業系統磁片磁碟機、固定資料磁碟機，以及可移除的 USB 磁片磁碟機 (磁片) 金鑰。

-   收集用戶端電腦的修復資訊和電腦資訊。

#### <a name="configuration-manager-client"></a>Configuration Manager 用戶端

Configuration **Manager Client** 可讓 Configuration Manager 收集用戶端電腦的硬體相容性資料，並報告合規性資訊。

 

## <a name="differences-in-mbam-deployment-for-supported-configuration-manager-versions"></a>支援的 Configuration Manager 版本在部署中的差異


當您使用 Configuration Manager 整合拓撲部署 IBMM 時，您可以在主網站伺服器上安裝 IBMM。 不過，針對 2012 configuration Manager 和 Configuration Manager 2007，SYSTEM CENTER的安裝方式不同。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Configuration Manager 版本</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>System Center 2012 R2 Configuration Manager</p>
<p>System Center 2012 Configuration Manager</p></td>
<td align="left"><p>如果您在主網站伺服器或中央系統管理伺服器上安裝 IBMM，則該網站伺服器上所有的安裝動作都由 IBMM 執行。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Configuration Manager 2007 R2</p>
<p>Configuration Manager 2007</p></td>
<td align="left"><p>如果您在具有中央網站父伺服器之大型 Configuration Manager 階層的一部分的主網站伺服器上安裝 IBMM，則 IBMM 會識別中央網站父伺服器，並執行該父伺服器上的所有安裝動作。 安裝包括檢查先決條件及安裝 Configuration Manager 物件和報表。</p>
<p>例如，如果您在中央網站父伺服器的子級主網站伺服器上安裝 IBMM，則 IBMM 會安裝父伺服器上所有的 Configuration Manager 物件和報表。 如果您在父伺服器上安裝<a0>，則<a0></a0>的<a1> </a1> <a2>：</a2><a3></a3><a4></a4><a5></a5><a6><</p></td>
</tr>
</tbody>
</table>

 

## <a name="how-mbam-works-with-configuration-manager"></a>與 Configuration Manager 一起運作方式


與 CONFIGURATION Manager 的整合是以安裝下表所述專案的組組套件為基礎。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">安裝在 Configuration Manager 中的專案</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>組組資料</p></td>
<td align="left"><p>設定資料會安裝一個稱為「BitLocker Protection」的設定比較基準，其中包含兩個設定專案：</p>
<ul>
<li><p>BitLocker 操作系統磁碟機保護</p></li>
<li><p>BitLocker 修正資料磁碟機保護</p></li>
</ul>
<p>設定比較基準會部署至受支援之電腦集合 ，此集合也會在安裝時建立。</p>
<p>這兩個組組專案提供評估用戶端電腦合規性狀態的基礎。 此資訊在 Configuration Manager 中會進行捕獲、儲存及評估。</p>
<p>組組專案是根據作業系統磁片磁碟機和固定資料磁碟機的合規性需求。 系統會收集部署電腦所需的詳細資料，以便評估這些磁碟機類型的合規性。</p>
<p>根據預設，設定比較基準會每隔 12 小時評估合規性狀態，並將合規性資料傳送給 Configuration Manager。</p></td>
</tr>
<tr class="even">
<td align="left"><p>受支援之電腦集合</p></td>
<td align="left"><p>"管理管理」會建立一個稱為"支援電腦"的集合。 設定比較基準會以此集合中的用戶端電腦為目標。</p>
<p>這是動態集合。 根據預設，它會每 12 小時執行一次，並依據三個準則評估成員資格：</p>
<ul>
<li><p>電腦是支援的作業系統Windows版本。</p></li>
<li><p>電腦是實體電腦。 不支援虛擬機器。</p></li>
<li><p>電腦具有可 (TPM) 平臺模組。 7 版本需要相容的 TPM 1.2 或更新版本Windows版本。 Windows 10、Windows 8.1、Windows 8和Windows都不需要 TPM。</p></li>
</ul>
<p>系統會針對所有電腦評估集合，並建立相容的電腦子集，為進行合規性評估與報告提供基礎，以用於管理管理與管理管理整合。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>報告</p></td>
<td align="left"><p>當您使用 Configuration Manager 整合拓撲設定時，您可以在 Configuration Manager 中查看所有報表，但復原稽核報告除外，後者會持續在管理及監控網站中查看。 Configuration Manager 中提供的報告為：</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">報告</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>BitLocker Enterprise合規性儀表板</p></td>
<td align="left"><p>在單一報告中提供 IT 系統管理員三種資訊視圖：合規性狀態分配、不合規性 – 錯誤發佈，以及合規性狀態分配按雲端硬碟類型。 報表上的向下拉式選項，讓 IT 系統管理員按一下資料，並查看符合所選狀態的電腦清單。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker Enterprise合規性詳細資料</p></td>
<td align="left"><p>可讓 IT 系統管理員查看企業 BitLocker 加密合規性狀態的資訊，並包含每部電腦的合規性狀態。 報表上的向下拉式選項，讓 IT 系統管理員按一下資料，並查看符合所選狀態的電腦清單。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>BitLocker 電腦合規性</p></td>
<td align="left"><p>可讓 IT 系統管理員查看個別電腦，並判斷為何報告其狀態為符合或不符合。 報表也會顯示作業系統磁片磁碟機和固定資料磁碟機的加密狀態。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker Enterprise合規性摘要</p></td>
<td align="left"><p>讓 IT 系統管理員在企業中查看該企業中的管理管理規範狀態。 會評估每部電腦的狀態，而報表會顯示企業中所有電腦與該政策之合規性的摘要。 報表上的向下拉式選項，讓 IT 系統管理員按一下資料，並查看符合所選狀態的電腦清單。</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 


## <a name="related-topics"></a>相關主題


[開始使用 MBAM 2.5](getting-started-with-mbam-25.md)

[MBAM 2.5 搭配獨立拓撲的概要架構](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)

[MBAM 2.5 部署的功能圖例](illustrated-features-of-an-mbam-25-deployment.md)

 

 
## <a name="got-a-suggestion-for-mbam"></a>有關于 MM 的建議嗎？
- 在這裡新增或投票支援 [建議](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)。 
- 針對針對的 MM 問題，請使用[的是 ：。。](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)




