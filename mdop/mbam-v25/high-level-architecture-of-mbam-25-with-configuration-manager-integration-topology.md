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
ms.openlocfilehash: 75af2e22981d76568916c36acadbbb25648b1f1d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811349"
---
# MBAM 2.5 的高層次架構與 Configuration Manager 整合拓撲

本主題描述使用 Configuration Manager 整合拓撲來部署 Microsoft BitLocker 管理和監控（MBAM）的建議架構。 此拓撲會與 System Center Configuration Manager 整合 MBAM。 若要在獨立拓朴中部署 MBAM，請參閱[MBAM 2.5 的高層次架構（含獨立拓朴](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)）。

如需本主題中所述軟體支援版本的清單，請參閱[MBAM 2.5 支援](mbam-25-supported-configurations.md)的設定。

**重要** 當您使用 Configuration Manager 2007 時，Configuration Manager 整合拓撲安裝不支援 Windows To Go。

 

## 建議的伺服器數和支援的用戶端數量


在生產環境中，建議的伺服器數量及支援的用戶端數量如下：

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
<td align="left"><p>伺服器和其他電腦的數目</p></td>
<td align="left"><p>三台伺服器</p>
<p>一個工作站</p></td>
</tr>
<tr class="even">
<td align="left"><p>支援的用戶端電腦數目</p></td>
<td align="left"><p>500000</p></td>
</tr>
</tbody>
</table>

 

## Configuration Manager 整合與獨立拓朴間的差異


拓撲結構的主要差異為：

-   相容性與報告功能會從 MBAM 中移除，且可從 Configuration Manager 存取。

-   報告是從 Configuration Manager 管理主控台查看，除了復原審核報告例外之外，您仍可從 MBAM 管理和監控網站繼續進行查看。

## 建議的 MBAM 高層次架構與 Configuration Manager 整合拓撲


下列圖表與表格說明 MBAM 與 Configuration Manager 整合拓朴的建議高層次架構。 MBAM 多林部署需要單向或雙向信任。 單向信任要求伺服器網域信任用戶端網域。

![mbam2\-5](images/mbam2-5-cmserver.png)

### 資料庫伺服器

#### 復原資料庫

此功能已在執行 Windows Server 和支援的 SQL Server 實例的電腦上設定。

復原**資料庫**會儲存從 MBAM 用戶端電腦收集的復原資料。

#### 審核資料庫

此功能已在執行 Windows Server 和支援的 SQL Server 實例的電腦上設定。

**審核資料庫**會儲存從已存取復原資料的用戶端電腦收集的審核活動資料。

#### 報告

此功能已在執行 Windows Server 和支援的 SQL Server 實例的電腦上設定。

**報告**會提供企業中用戶端電腦的復原審核資料。 您可以透過 Configuration Manager 主控台或直接從 SQL Server Reporting Services 來查看報表。

### Configuration Manager 主要網站伺服器

系統中心 Configuration Manager 整合功能

-   此功能是在 Configuration Manager 主要網站伺服器（即 Configuration Manager 基礎結構中的頂層伺服器）上設定。

-   **Configuration Manager 伺服器**會從用戶端電腦收集硬體清查資訊，並使用它來報告用戶端電腦的 BitLocker 合規性。

-   當您執行 Microsoft BitLocker 管理及監視設定向導來安裝伺服器軟體時，系統會在 Configuration Manager 主要網站伺服器上設定 MBAM 支援的電腦集合、配置基線及報告。

-   **Configuration Manager 主控台**必須安裝在您安裝 MBAM Server 軟體的同一部電腦上。

### 管理和監控伺服器

#### 管理和監控網站

此功能是在執行 Windows Server 的電腦上設定。

**管理和監控網站**是用來：

-   當使用者鎖定時，協助使用者重新取得電腦存取權。（此網站區域通常稱為 [技術支援中心]。）

-   查看復原審核報告，其中顯示用戶端電腦的恢復活動。 您可以從 Configuration Manager 主控台查看其他報告。

#### 自助服務入口網站

此功能是在執行 Windows Server 的電腦上設定。

**自助式入口**網站是一種網站，可讓用戶端電腦上的使用者能夠獨立登入網站，以取得復原金鑰（如果他們遺失或忘記其 BitLocker 密碼）。

#### 監視此網站的 web 服務

此功能已安裝在執行 Windows Server 的電腦上。

MBAM 用戶端和網站會使用**監視 web 服務**來與資料庫進行通訊。

**重要**<br>在 Microsoft BitLocker 管理和監控（MBAM） 2.5 SP1 中不再提供監視 Web 服務，因為 MBAM 網站會直接與恢復資料庫通訊。 

 

### 管理工作站

#### MBAM 群組原則範本

-   **MBAM 群組原則範本**是定義 MBAM 之實現設定的群組原則設定，可讓您管理 BitLocker 磁碟機加密。

-   在執行 MBAM 之前，您必須從[如何取得 MDOP 組原則（admx）範本](https://go.microsoft.com/fwlink/p/?LinkId=393941)下載群組原則範本，並將其複製到執行支援的 Windows Server 或 Windows 作業系統的伺服器或工作站。

    **注意**<br>工作站不一定是專用電腦。

     

### MBAM 用戶端與 Configuration Manager 用戶端電腦

#### MBAM 用戶端軟體

**MBAM 用戶端**：

-   使用群組原則物件，在企業中的用戶端電腦上強制執行 BitLocker 磁碟機加密。

-   收集三種資料磁片磁碟機類型的 BitLocker 復原金鑰：操作系統磁碟機、固定資料磁碟機，以及可移動（USB）資料磁碟機。

-   收集用戶端電腦的恢復資訊和電腦資訊。

#### Configuration Manager 用戶端

**Configuration Manager 用戶端**可讓 configuration manager 收集用戶端電腦的硬體相容性資料，並報告合規性資訊。

 

## 支援的 Configuration Manager 版本的 MBAM 部署差異


當您使用 Configuration Manager 整合拓撲部署 MBAM 時，您可以在主要的網站伺服器上安裝 MBAM。 不過，MBAM 安裝在系統 Center2012 Configuration Manager 和設定 Manager2007 中的運作方式會有所不同。

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
<td align="left"><p>System Center2012 R2 Configuration Manager</p>
<p>系統 Center2012 Configuration Manager</p></td>
<td align="left"><p>如果您在主要的網站伺服器或中央管理伺服器上安裝 MBAM，MBAM 會在該網站伺服器上執行所有安裝動作。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Configuration Manager2007 R2</p>
<p>配置 Manager2007</p></td>
<td align="left"><p>如果您在擁有中央網站父伺服器的大型 Configuration Manager 階層的主要網站伺服器上安裝 MBAM，MBAM 會識別中央網站父伺服器，並在該父伺服器上執行所有安裝動作。 安裝包括檢查先決條件及安裝 Configuration Manager 物件和報告。</p>
<p>例如，如果您在主要網站伺服器上安裝 MBAM，而該伺服器是中央網站父伺服器的子網站，MBAM 會在父伺服器上安裝所有 Configuration Manager 物件和報告。 如果您在父伺服器上安裝 MBAM，MBAM 會在該父伺服器上執行所有安裝動作。</p></td>
</tr>
</tbody>
</table>

 

## MBAM 如何與 Configuration Manager 搭配運作


與 Configuration Manager 的 MBAM 整合是以安裝下表所述之專案的配置套件為基礎。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">已安裝至 Configuration Manager 的專案</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>配置資料</p></td>
<td align="left"><p>配置資料會安裝名為「BitLocker Protection」的配置比較基準，其中包含兩個設定專案：</p>
<ul>
<li><p>BitLocker 作業系統磁片磁碟機保護</p></li>
<li><p>BitLocker 固定資料磁碟機保護</p></li>
</ul>
<p>配置基線會部署到 [支援的 MBAM 電腦] 集合，也會在安裝 MBAM 時建立。</p>
<p>這兩個設定專案提供評估用戶端電腦合規性狀態的基礎。 此資訊是在 Configuration Manager 中捕獲、儲存及評估。</p>
<p>設定專案是根據作業系統磁片磁碟機和固定資料磁碟機的規範需求而定。 系統會收集已部署電腦所需的詳細資料，以便評估這些磁碟機類型的合規性。</p>
<p>根據預設，設定基準會評估合規性狀態 every12 時間，並將合規性資料傳送至 Configuration Manager。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 支援的電腦集合</p></td>
<td align="left"><p>MBAM 會建立一個名為 MBAM 支援的電腦的集合。 配置基線是針對此集合中的用戶端電腦所設定。</p>
<p>這是動態集合。 根據預設，它會根據三個準則來執行 every12 時間及評估成員資格：</p>
<ul>
<li><p>電腦是受支援版本的 Windows 作業系統。</p></li>
<li><p>電腦是物理電腦。 不支援虛擬機器。</p></li>
<li><p>電腦有可用的可信平臺模組（TPM）。 Windows7 需要相容版本的 TPM 1.2 或更新版本。 Windows10、Windows 8.1、Windows8 和 Windows To Go 不需要 TPM。</p></li>
</ul>
<p>這個集合是針對所有電腦來評估，而且會建立相容電腦的子集，這為 MBAM 整合提供合規性評估與報告的基礎。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>報告</p></td>
<td align="left"><p>當您使用 Configuration Manager 整合拓朴設定 MBAM 時，您會在 Configuration Manager 中查看所有報表，除了復原審核報告之外，您還可以在 MBAM 管理和監視網站中繼續進行查看。 [Configuration Manager] 中提供的報表如下：</p>
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
<td align="left"><p>BitLocker Enterprise 合規性儀表板</p></td>
<td align="left"><p>在單一報告中，為 IT 系統管理員提供三個資訊視圖：合規性狀態發佈、不合規性-錯誤發佈，以及依磁片磁碟機類型進行合規性狀態發佈。 報表中的向下切入選項可讓 IT 系統管理員依序按一下資料，並查看符合所選狀態的電腦清單。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker 企業合規性詳細資料</p></td>
<td align="left"><p>讓 IT 系統管理員可以查看企業的 BitLocker 加密合規性狀態相關資訊，並包括每個電腦的相容性狀態。 報表中的向下切入選項可讓 IT 系統管理員依序按一下資料，並查看符合所選狀態的電腦清單。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>BitLocker 電腦合規性</p></td>
<td align="left"><p>讓 IT 系統管理員可以查看個別的電腦，並判斷為什麼報告的狀態符合合規性或不規範。 報告也會顯示操作系統磁碟機和固定資料磁碟機的加密狀態。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker Enterprise 合規性摘要</p></td>
<td align="left"><p>讓 IT 系統管理員在企業中查看 MBAM 原則規範的狀態。 會評估每個電腦的狀態，而報告會顯示企業中所有電腦對原則的合規性摘要。 報表中的向下切入選項可讓 IT 系統管理員依序按一下資料，並查看符合所選狀態的電腦清單。</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 


## 相關主題


[開始使用 MBAM 2.5](getting-started-with-mbam-25.md)

[MBAM 2.5 搭配獨立拓撲的概要架構](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)

[MBAM 2.5 部署的功能圖例](illustrated-features-of-an-mbam-25-deployment.md)

 

 
## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




