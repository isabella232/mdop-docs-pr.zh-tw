---
title: Application Virtualization 5.0 的效能指引
description: Application Virtualization 5.0 的效能指引
author: dansimp
ms.assetid: 6b3a3255-b957-4b9b-8bfc-a93fe8438a81
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 3b0f5ef07935fc34adce772e7b2fff85a12b01dc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800368"
---
# Application Virtualization 5.0 的效能指引


瞭解如何設定 App-V 5.0 以取得最佳效能、優化虛擬 App 套件，以及使用 RDS 和 VDI 提供較佳的使用者體驗。

實現多個方法可協助您改善最終使用者體驗。 不過，您的環境可能不支援所有方法。

閱讀此檔之前，您應該閱讀並瞭解下列資訊。

-   [Microsoft Application Virtualization 5.0 系統管理員指南](microsoft-application-virtualization-50-administrators-guide.md)

-   [App-v 5 SP2 應用程式發佈與用戶端互動](https://go.microsoft.com/fwlink/?LinkId=395206)

-   [Microsoft Application Virtualization 5.0 排序指南](https://go.microsoft.com/fwlink/?LinkId=269953)

**注意**  
根據外部來源和內容，此檔中使用的一些字詞可能會有不同的含義。 如需本檔中所使用之術語的詳細資訊，後面加上星號 **\\** * 請參閱本檔的[Application Virtualization 效能指南術語](#bkmk-terms1)一節。



最後，本檔將提供資訊來設定執行 App-v 5.0 用戶端的電腦，以及最佳效能。 使用 sequencer 來優化您的虛擬應用程式套件，並瞭解如何使用使用者體驗虛擬化（UE-V）或其他使用者環境管理技術，以在遠端桌面服務（RDS）和非持久性虛擬桌面基礎結構（VDI）中使用 App-v 5.0 提供最佳的使用者體驗。

若要協助判斷與您的環境相關的資訊，您應該查看每個區段的簡短概述及適用性檢查清單。

## <a href="" id="---------app-v-5-0-in-stateful--non-persistent-deployments"></a> 在狀態 \ * 非持續性部署中的 app-v 5。0


本節提供一種方法的相關資訊，協助確保使用者在登入後的幾秒鐘內就能存取所有的虛擬應用程式。 如此一來，就能以唯一的方式來解決經常執行的 App-v 5.0 發佈重新整理。 您會發現此方法的基礎，這是最快的發佈重新整理，就是不需要實際執行任何動作。 必須符合幾個條件，並遵循步驟來提供最佳的使用者體驗。

如需詳細資訊，請使用下一節中的資訊：

[使用案例](#bkmk-us)-當您查看兩種情況時，請記住這些是最極端的方法。 根據您的使用需求，您可以選擇將這些步驟套用至使用者和/或虛擬應用程式套件的子集。

-   針對效能優化-若要提供最佳的體驗，您可以預期基本影像包含部分 App-v 虛擬應用程式套件。 本文將討論這及其他需求。

-   針對儲存進行優化-如果您關心儲存空間的影響，請遵循這個案例將協助解決這些問題。

[準備您的環境](#bkmk-pe)

-   準備基本映射的步驟（無論是在非持久性 VDI 或 RDSH 環境中），基本映射中必須完成幾個步驟，才能啟用此方法。

-   使用 UE-V 2.0 做為應用程式 V 方法的使用者設定檔管理（UPM）方案–這種方法的基礎是 UEM 解決方案只保留幾個註冊表和檔案位置的內容的能力。 這些位置組成使用者整合 \ *。 請務必審查 UPM 方案的特定需求。

[使用者體驗逐步指導](#bkmk-uewt)

-   逐步引導–這是 App V 與 UE-V 作業的逐步逐步引導，以及使用者應該擁有的預期。

-   結果–這會說明預期的結果。

[對套件生命週期的影響](#bkmk-plc)

[透過效能優化/調整來加強 VDI 體驗](#bkmk-evdi)

### <a href="" id="applicability-checklist-"></a>適用性檢查清單

部署環境

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>非持久性 VDI 或 RDSH。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>使用者體驗虛擬化（UE-V）、其他 UPM 解決方案或使用者設定檔磁片（UPD）。</p></td>
</tr>
</tbody>
</table>



預期配置

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>使用者體驗虛擬化（UE-V），其中已啟用 App-v 使用者狀態範本或使用者設定檔管理（UPM）軟體。 非 UE-V UPM 軟體必須能夠在登入或處理/應用程式啟動和登出時觸發。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>App-V 共用的內容存儲區（SCS）已設定或可設定。</p></td>
</tr>
</tbody>
</table>



IT 管理

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>系統管理員可能需要定期更新 VM 基本影像，以確保最佳效能或系統管理員可能需要管理不同使用者群組的多個影像。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-us"></a>使用案例

當您複習這兩種情況時，請記住，這些是最極端的做法。 根據您的使用需求，您可以選擇將這些步驟套用到使用者的子集、虛擬應用程式套件，或兩者。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">針對效能優化</th>
<th align="left">針對儲存進行優化</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>為了提供最佳的使用者體驗，此方法會利用 UPM 方案的功能，而且需要額外的影像管理額外負荷。</p>
<p>下列說明在狀態非持續性部署中的許多效能改善。 如需詳細資訊，請參閱 <strong> 此檔的 [請參閱] 區段中的 [針對發佈效能優化套件的先後順序步驟 </strong> 和 <strong> App-V 5.0 排序指南] </strong> <strong> 一節 </strong> 。</p></td>
<td align="left"><p>上述案例的一般預期仍會適用于這裡。 不過，請記住，VM 影像通常會儲存在非常昂貴的陣列中;已對此方法進行一些輕微的變更。 請勿在基本影像中預先設定以使用者為目標的虛擬應用程式套件。</p>
<p>這項變更的影響將在這份檔的 [使用者經驗] 演練一節中詳細說明。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-pe"></a>準備您的環境

下表顯示準備基本映射與 UE-V 或該方法的其他 UPM 方案所需的步驟。

**準備基底影像**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">針對效能優化</th>
<th align="left">針對儲存進行優化</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p></p>
<ul>
<li><p>針對應用程式虛擬化 5.0 SP2 用戶端版本安裝修補程式套件4。</p></li>
<li><p>安裝 UE-V，然後從 UE-V 範本庫下載 App-v 設定範本，請參閱下列步驟。</p></li>
<li><p>針對共用內容儲存區（SCS）模式進行設定。 如需詳細資訊，請參閱 <a href="how-to-install-the-app-v-50-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.0 Client for Shared Content Store Mode](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md)"> 如何安裝 App-V 5.0 用戶端以取得共用內容存放區模式 </a> 。</p></li>
<li><p>設定 [在登入登錄註冊表中保留使用者整合] DWORD。</p></li>
<li><p>預先設定所有的使用者和全域目標套件（例如， <strong> 附加 AppvClientPackage） </strong> 。</p></li>
<li><p>預先設定所有使用者和全域目標連線群組（例如， <strong> 附加 AppvClientConnectionGroup） </strong> 。</p></li>
<li><p>預先發佈所有全域目標套件。</p>
<p></p>
<p>當然</p>
<ul>
<li><p>執行全域發佈/重新整理。</p></li>
<li><p>執行使用者發佈/重新整理。</p></li>
<li><p>取消發佈所有以使用者為目標的套件。</p></li>
<li><p>刪除下列使用者虛擬檔案系統（VFS）專案。</p></li>
</ul>
<p><code>AppData\Local\Microsoft\AppV\Client\VFS</code></p>
<p><code>AppData\Roaming\Microsoft\AppV\Client\VFS</code></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>針對應用程式虛擬化 5.0 SP2 用戶端版本安裝修補程式套件4。</p></li>
<li><p>安裝 UE-V，然後從 UE-V 範本庫下載 App-v 設定範本，請參閱下列步驟。</p></li>
<li><p>針對共用內容儲存區（SCS）模式進行設定。 如需詳細資訊，請參閱 <a href="how-to-install-the-app-v-50-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.0 Client for Shared Content Store Mode](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md)"> 如何安裝 App-V 5.0 用戶端以取得共用內容存放區模式 </a> 。</p></li>
<li><p>設定 [在登入登錄註冊表中保留使用者整合] DWORD。</p></li>
<li><p>預先設定所有全域目標套件（例如， <strong> 附加 AppvClientPackage） </strong> 。</p></li>
<li><p>預先設定所有全域目標連線群組（例如， <strong> 附加 AppvClientConnectionGroup） </strong> 。</p></li>
<li><p>預先發佈所有全域目標套件。</p>
<p></p></li>
</ul></td>
</tr>
</tbody>
</table>



**配置**-適用于重要的 App-v 用戶端設定，若想要更多內容和操作說明，請參閱下列資訊：

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">配置設定</th>
<th align="left">這會有什麼作用？</th>
<th align="left">我該如何使用它？</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>共用內容存放區（SCS）模式</p>
<ul>
<li><p>可在 PowerShell 中使用 <strong> AppvClientConfiguration </strong> -SharedContentStoreMode <strong> 設定 </strong> ，或</p></li>
<li><p>安裝 App-v 5.0 用戶端的過程中。</p></li>
</ul></td>
<td align="left"><p>在執行 [共用內容存放區] 時，只會在硬碟上維護髮布資料其他虛擬應用程式資產會保留在記憶體（RAM）中。</p>
<p>這有助於節省本機儲存空間，並將每秒最小化磁片 i/o （IOPS）。</p></td>
<td align="left"><p>當 App-v 用戶端和 SCS 內容伺服器（SAN）之間提供低延遲連線時，建議您這麼做。</p></td>
</tr>
<tr class="even">
<td align="left"><p>PreserveUserIntegrationsOnLogin</p>
<ul>
<li><p>在 [ <strong> HKEY_LOCAL_MACHINE </strong>  \  <strong> 軟體 </strong>  \  <strong> Microsoft </strong>  \  <strong> AppV </strong>  \  <strong> 用戶端 </strong>  \  <strong> 整合 </strong> ] 下的 [登錄] 中進行設定。</p></li>
<li><p><strong>使用值1建立 DWORD 值 PreserveUserIntegrationsOnLogin </strong> <strong> </strong> 。</p></li>
<li><p>重新開機應用程式-V 用戶端服務，或重新開機執行 App-v 用戶端的電腦。</p></li>
</ul></td>
<td align="left"><p>如果您尚未預先設定（ <strong> 載入 AppvClientPackage </strong> ）特定的套件，且未設定此設定，App-v 用戶端將會解除整合 *，然後重新整合 *。</p>
<p>針對符合上述條件的每個套件，有效地將作業的兩倍，在發佈/重新整理期間完成。</p></td>
<td align="left"><p>如果您不打算預先設定基本影像中每個可用的使用者套件，請使用此設定。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MaxConcurrentPublishingRefresh</p>
<ul>
<li><p>在 [ <strong> HKEY_LOCAL_MACHINE </strong> &lt; 強 &gt; 軟體 </strong>  \  <strong> Microsoft </strong>  \  <strong> AppV </strong> &lt; 加強 &gt; 用戶端 </strong>  \  <strong> 發佈 </strong> ] 底下的 [登錄] 中進行設定。</p></li>
<li><p><strong> </strong> 以所需的併發發佈更新數量限制，建立 DWORD 值 MaxConcurrentPublishingrefresh。</p></li>
<li><p>App-v 用戶端服務和電腦不需要重新開機。</p></li>
</ul></td>
<td align="left"><p>這個設定決定了可以同時執行發佈重新整理/同步處理的使用者數目。 預設設定為 [無限制]。</p></td>
<td align="left"><p>限制併發發佈的重新整理數可避免過度使用的 CPU 使用量，這可能會影響電腦效能。 建議在 RDS 環境中使用這個限制，多個使用者可以同時登入同一部電腦並執行發佈重新整理同步處理。</p>
<p>如果達到併發發佈重新整理閾值，發佈新應用程式時所需的時間，並在使用者登入時將它們提供給最終使用者，可能會有不確定的時間長度。</p></td>
</tr>
</tbody>
</table>



### 針對 App-v 方法設定 UE-V 解決方案

我們建議使用 Microsoft 使用者體驗虛擬化（UE-V）來捕獲並集中特定使用者的應用程式設定和 Windows 作業系統設定。 然後，這些設定會套用到使用者所存取的不同電腦，包括桌上型電腦、膝上型電腦和虛擬桌面基礎結構（VDI）會話。 UE-V 已針對 RDS 和 VDI 案例進行優化。

如需詳細資訊，請參閱[使用者體驗虛擬化的快速入門 2.0](https://technet.microsoft.com/library/dn458936.aspx)

實質上，您只需要安裝 UE-V 用戶端，然後從[Microsoft 使用者經驗虛擬化（ue-v）範本庫](https://gallery.technet.microsoft.com/Authored-UE-V-Settings-bb442a33)下載下列 microsoft 撰寫的 app-v 設定範本。 註冊範本。 如需 UE-V 範本的詳細資訊，請參閱[用於取得及註冊範本的 ue-v 特定資源](https://technet.microsoft.com/library/dn458936.aspx)。

**注意**  
若不執行額外的設定步驟，Microsoft 使用者環境虛擬化（UE-V）將無法同步處理目的電腦上的開始功能表快速鍵（.lnk 檔案）。 預設會排除 .lnk 檔案類型。

UE-V 只支援從 RDS 和 VDI 案例中的排除清單中移除 .lnk 檔案類型，而每個使用者的裝置都將有一組相同的應用程式安裝在相同的位置，且每個 .lnk 檔案對於所有使用者的裝置都是有效的。 例如，UE-V 目前不支援下列2種案例，因為最終結果是該快速鍵將在一個（而非所有）裝置上生效。

-   如果使用者已在一部裝置上安裝應用程式，且在另一個裝置上安裝了相同的原生應用程式，且已啟用 .lnk 檔案的不同安裝根目錄。

-   如果使用者已在一部裝置上安裝應用程式，但沒有已啟用 .lnk 檔案的其他應用程式。



**重要**  
本主題說明如何使用 [登錄編輯程式] 變更 Windows 登錄。 如果您不正確地變更 Windows 登錄，可能會導致嚴重的問題，可能需要重新安裝 Windows。 變更登錄前，您應該先製作一份登錄檔案（系統 .dat 和使用者 .dat）的備份複本。 Microsoft 不能保證變更註冊表時可能會發生的問題，可以解決。 變更註冊表的風險由您自行承擔。



使用 Microsoft Registry Editor （regedit.exe）流覽至**HKEY \ _LOCAL \ _MACHINE**  \\  **軟體**  \\  **Microsoft**  \\  **UEV**  \\  **Agent**設定  \\  **Configuration**  \\  **ExcludedFileTypes**並從排除的檔案類型中移除 **.lnk** 。

**針對 App-v 方法設定其他使用者設定檔管理（UPM）方案**

在有狀態的環境中的預期是已實現 UPM 方案，而且可支援跨會話和登錄之間的使用者資料持續性。

UPM 方案的需求如下所示。

若要啟用優化的登入體驗（例如使用者的 app-v 5.0 方法），解決方案必須具備下列各項：

-   在使用者設定檔/角色中保留下列使用者整合。

-   在登入（或應用程式啟動）時觸發使用者設定檔同步處理，可保證在發佈/重新整理開始前已套用所有使用者整合，或者

-   附加與分離使用者設定檔磁片（UPD）或包含使用者集成的類似技術。

-   在會話登出之前，捕獲對位置所做的變更，這些位置組成使用者整合。

在您新增發佈伺服器時，使用 App-v 5.0 （**載入 AppvPublishingServer**），您可以設定同步處理，例如在登入期間進行重新整理，或在指定的重新整理間隔之後進行重新整理。 在這兩種情況下，都會建立排程任務。

在舊版 App-V 5.0 中，兩個排程的任務都是使用 VBScript 來啟動使用者和全域重新整理。 針對應用程式虛擬化5.0 的修復程式套件4，使用者會在登錄時重新整理（由**SyncAppvPublishingServer.exe**啟動）。 引入此變更是為了提供 UPM 解決方案的觸發程式。 這個處理常式會延遲發佈/refresh，讓 UPM 方案能夠套用使用者整合。 發佈/重新整理完成後，就會結束。

**使用者整合**

Registry – HKEY \ _CURRENT \ _USER

-   路徑-Software\\Classes

    [排除]：本機設定、ActivatableClasses、AppX \ *

-   路徑-Software\\Microsoft\\AppV

-   路徑 Software\\Microsoft\\Windows\\CurrentVersion\\App 路徑

**檔案位置**

-   Root-"環境變數" APPDATA

    Path – Microsoft\\AppV\\Client\\Catalog

-   Root-"環境變數" APPDATA

    Path – Microsoft\\AppV\\Client\\Integration

-   Root-"環境變數" APPDATA

    Path-Microsoft\\Windows\\Start Menu\\Programs

-   （若要保留所有桌面快速鍵、虛擬和非虛擬）

    Root-"KnownFolder" {B4BFCC3A-DB2C-424C-B029-7FE99A87C641} FileMask-\ * .lnk

**Microsoft 使用者體驗虛擬化（UE-V）**

此外，我們建議使用 Microsoft 使用者體驗虛擬化（UE-V）來捕獲與集中特定使用者的應用程式設定和 Windows 作業系統設定。 然後，這些設定會套用到使用者所存取的不同電腦，包括桌上型電腦、膝上型電腦和虛擬桌面基礎結構（VDI）會話。

如需詳細資訊，請參閱[使用者體驗虛擬化1.0 快速入門](https://technet.microsoft.com/library/jj680015.aspx)和[使用 Ue-v 範本庫共用設定位置範本](https://technet.microsoft.com/library/jj679972.aspx)。

### <a href="" id="bkmk-uewt"></a>使用者體驗逐步指導

以下是 App-V 與 UPM 作業的逐步逐步說明，以及使用者預期的預期。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">針對效能優化</th>
<th align="left">針對儲存進行優化</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在 VDI/RDSH 環境中實現此方法之後，請在第一次登入時，</p>
<ul>
<li><p>一道啟動使用者發佈/重新整理。 認為如果這是使用者第一次發佈的虛擬應用程式（例如非永久性），這將會採取發佈/重新整理的一般持續時間。</p></li>
<li><p>一道在發佈/重新整理之後，UPM 方案會捕獲使用者整合。 認為視 UPM 方案的設定方式而定，這可能會在登出程式中發生。 這將會產生與使用者狀態保持不變相同/類似的額外負荷。</p></li>
</ul>
<p>在後續的登錄：</p>
<ul>
<li><p>一道在發佈/重新整理前，UPM 解決方案會將使用者整合套用至系統。</p>
<p>認為桌面或 [開始] 功能表中將會顯示快捷方式，這會立即起作用。 發佈/重新整理完成後（亦即封裝權利變更），部分可能會消失。</p></li>
<li><p>一道發佈/重新整理會處理使用者套件權利變更的取消發佈及發佈作業。 認為如果沒有任何權利變更，publishing1 將會在幾秒內完成。 否則，發佈/重新整理會相對於虛擬應用程式的數量和複雜性 * 而增加</p></li>
<li><p>一道UPM 解決方案將在登出時再次捕獲使用者整合。 認為與上一節相同。</p></li>
</ul>
<p>¹發佈作業（ <strong> 發佈 AppVClientPackage）會 </strong> 將專案新增至使用者目錄、將權利對應給使用者、識別當地商店，以及完成任何整合步驟完成。</p></td>
<td align="left"><p>在 VDI/RDSH 環境中實現此方法之後，請在第一次登入時，</p>
<ul>
<li><p>一道啟動使用者發佈/重新整理。 認為</p>
<ul>
<li><p>如果這是使用者第一次發佈虛擬應用程式（例如，非永久性），這將會採取發佈/重新整理的一般持續時間。</p></li>
<li><p>首先，系統會根據預先設定套件（新增/重新整理）來影響後續的登錄。</p>
<p></p></li>
</ul></li>
<li><p>一道在發佈/重新整理之後，UPM 方案會捕獲使用者整合。 認為視 UPM 方案的設定方式而定，這可能會在登出程式中發生。 這將會產生與使用者狀態保持不變的相同/類似負荷</p></li>
</ul>
<p>在後續的登錄：</p>
<ul>
<li><p>一道在發佈/重新整理前，UPM 解決方案會將使用者整合套用至系統。</p></li>
<li><p>一道[新增/重新整理] 必須預先設定所有由使用者為目標的應用程式。 認為</p>
<ul>
<li><p>這可能會顯著增加應用程式可用性的時間（10秒的順序）。</p></li>
<li><p>這會增加相對於虛擬應用程式數目和複雜性 * 的發佈重新整理時間。</p>
<p></p></li>
</ul></li>
<li><p>一道發佈/重新整理將處理取消發佈及發佈作業，以變更使用者套件權利的變更。</p></li>
</ul></td>
</tr>
</tbody>
</table>



<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">負面</th>
<th align="left">負面</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p></p>
<ul>
<li><p>因為使用者整合完全保持不變，所以不需要進行任何工作，例如發佈/重新整理完成的整合。 所有虛擬應用程式將在登入後的幾秒鐘內提供。</p></li>
<li><p>發佈/重新整理會將變更處理給擁有虛擬應用程式的使用者，這些使用者會影響體驗。</p></li>
</ul></td>
<td align="left"><p>因為 [新增/重新整理] 必須重新設定所有虛擬應用程式至 VM，所以每個登入的發佈重新整理時間都會得到延伸。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-plc"></a>影響封裝的生命週期

升級套件是套件生命週期的一個重要層面。 若要協助使用者能存取適當升級（已發佈）或降級（未發佈）虛擬應用程式套件，建議您更新基本映射以反映這些變更。 若要瞭解為什麼要查看下列章節：

App-v 5.0 SP2 引進了擱置狀態的概念。 在過去，

-   如果系統管理員變更了 [權利] 或 [建立新版本的套件（已升級）]，且在打包期間進行發佈/重新整理時，將無法使用 [取消發佈] 或 [發佈] 作業。

-   現在，如果套件是在使用中，則會暫停該作業。 [取消發佈] 和 [發佈-待定] 作業將會在服務重新開機時處理，或在發出另一個發佈或取消發佈命令時進行處理。 在後一種情況下，如果虛擬應用程式是在使用中，則虛擬應用程式將會保持擱置狀態。 針對全域發佈的套件，通常需要重新開機（或重新開機服務）。

在非持久性環境中，不可能會處理這些暫停的作業。 暫停的作業（例如工作）會在**HKEY \ _CURRENT \ _USER**  \\  **軟體**  \\  **Microsoft**  \\  **AppV**  \\  **用戶端**  \\  ** **] 下捕獲。 雖然此位置是由 UPM 解決方案所保留，但在登入前未將它套用到環境，否則就不會處理它。

### <a href="" id="bkmk-evdi"></a>透過效能優化調整來增強 VDI 體驗

下列各節包含 Microsoft 檔和下載相關資訊的清單，這些資訊在優化您的環境以提高效能時可能會很有用。

**.NET NGEN 博客及腳本（強烈建議）**

關於 NGEN 技術

-   [如何加速 NGEN 優化](https://blogs.msdn.com/b/dotnet/archive/2013/08/06/wondering-why-mscorsvw-exe-has-high-cpu-usage-you-can-speed-it-up.aspx)

-   [指令碼](https://aka.ms/DrainNGenQueue)

**Windows Server 和伺服器角色**

伺服器效能調整指導方針

-   [Microsoft Windows Server 2012 R2](https://msdn.microsoft.com/library/windows/hardware/dn529133.aspx)

-   [Microsoft Windows Server 2012](https://download.microsoft.com/download/0/0/B/00BE76AF-D340-4759-8ECD-C80BC53B6231/performance-tuning-guidelines-windows-server-2012.docx)

-   [Microsoft Windows Server 2008 R2](https://download.microsoft.com/download/6/B/2/6B2EBD3A-302E-4553-AC00-9885BBF31E21/Perf-tun-srv-R2.docx)

**伺服器角色**

-   [遠端桌面虛擬化主機](https://msdn.microsoft.com/library/windows/hardware/dn567643.aspx)

-   [遠端桌面工作階段主機](https://msdn.microsoft.com/library/windows/hardware/dn567648.aspx)

-   [IIS 關聯性： App-v 管理、發佈、報告 Web 服務](https://msdn.microsoft.com/library/windows/hardware/dn567678.aspx)

-   [檔案伺服器（SMB）關聯性：如果用於在 SCS 模式中使用 App-v 內容儲存與傳遞](https://technet.microsoft.com/library/jj134210.aspx)

**Windows 用戶端（來賓 OS）效能調整指導方針**

-   [Microsoft Windows 7](https://download.microsoft.com/download/E/5/7/E5783D68-160B-4366-8387-114FC3E45EB4/Performance Tuning Guidelines for Windows 7 Desktop Virtualization v1.9.docx)

-   [優化腳本：（由 Microsoft 支援人員提供）](https://blogs.technet.com/b/jeff_stokes/archive/2012/10/15/the-microsoft-premier-field-engineer-pfe-view-on-virtual-desktop-vdi-density.aspx)

-   [Microsoft Windows 8](https://download.microsoft.com/download/6/0/1/601D7797-A063-4FA7-A2E5-74519B57C2B4/Windows_8_VDI_Image_Client_Tuning_Guide.pdf)

-   [優化腳本：（由 Microsoft 支援人員提供）](https://blogs.technet.com/b/jeff_stokes/archive/2013/04/09/hot-off-the-presses-get-it-now-the-windows-8-vdi-optimization-script-courtesy-of-pfe.aspx)

## 針對發佈效能優化套件的先後順序步驟


App-v 5.0 和 App-v 5.0 SP2 在其各自的發行中提供重要的價值。 有數個功能可協助新案例或啟用新的客戶部署案例。 下列功能可能會影響發佈與啟動作業的效能。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">步驟</th>
<th align="left">考量</th>
<th align="left">權益</th>
<th align="left">負面</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>沒有功能區塊1（FB1，也稱為主要的 FB）</p></td>
<td align="left"><p>[無 FB1] 表示應用程式將立即啟動，資料流程錯誤（應用程式需要檔案、DLL 且必須在網路上向下拉入）。如果有網路限制，FB1 將會：</p>
<ul>
<li><p>減少當您第一次啟動應用程式時所使用的資料流程錯誤和網路頻寬數目。</p></li>
<li><p>延遲啟動，直到整個 FB1 都已流入為止。</p></li>
</ul></td>
<td align="left"><p>資料流程錯誤減少了啟動時間。</p></td>
<td align="left"><p>已設定 FB1 的虛擬應用程式套件將需要重新排序。</p></td>
</tr>
</tbody>
</table>



### 移除 FB1

移除 FB1 不需要原始應用程式安裝程式。 完成下列步驟之後，建議您將執行 sequencer 的電腦還原為乾淨的快照。

**SEQUENCER UI** -建立新的虛擬應用程式套件。

1.  完成進行自訂資料流程的先後順序步驟 &gt; 。

2.  在 [資料流程] 步驟中，請勿選取 **[在低速或不可靠的網路上針對部署來優化套件**]。

3.  如有需要，請移至**目標作業系統**。

**修改現有的虛擬應用程式套件**

1.  完成排序步驟直至進行流式處理。

2.  請勿選取 **[在慢速或不可靠的網路上優化套件以進行部署**]。

3.  移至 [**建立套件**]。

**PowerShell** -更新現有的虛擬應用程式套件。

1.  開啟提升許可權的 PowerShell 會話。

2.  匯入-模組**appvsequencer**。

3.  **更新-AppvSequencerPackage**  - **AppvPackageFilePath**

    "C:\\Packages\\MyPackage.appv"-安裝程式

    "C:\\PackageInstall\\PackageUpgrade.exe empty.exe"-OutputPath

    "C:\\UpgradedPackages"

    **注意**  
    這個 Cmdlet 需要可執行檔（.exe）或批次處理檔案（.bat）。 您必須提供空白（無任何）可執行檔或批次處理檔案。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">步驟</th>
<th align="left">考量</th>
<th align="left">權益</th>
<th align="left">負面</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>發佈時不安裝 SXS （預先安裝的 SxS 元件）</p></td>
<td align="left"><p>虛擬應用程式套件不需要重新排序。 SxS 元件可以保留在虛擬應用程式套件中。</p></td>
<td align="left"><p>在發佈時不會安裝 SxS 元件相依性。</p></td>
<td align="left"><p>必須預先安裝 SxS 元件相依性。</p></td>
</tr>
</tbody>
</table>



### 在 sequencer 上建立新的虛擬應用程式套件

如果在排序器監視期間，在應用程式的安裝過程中會安裝一個 SxS 元件（例如 VC + + 執行時間），則會自動偵測並包含在套件中的 SxS 元件。 系統管理員會收到通知，並提供排除 SxS 元件的選項。

**用戶端**：

發佈虛擬應用程式套件時，App-v 5.0 SP2 用戶端會偵測到是否已安裝所需的 SxS 相依性。 如果相依性在電腦上無法使用，且包含在套件中，則是傳統的 Windows 安裝程式（.**msi**）將會啟動 SxS 元件的安裝。 如先前所述，只需在執行用戶端的電腦上安裝相依性，以確保不會發生 Windows Installer （.msi）安裝。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">步驟</th>
<th align="left">考量</th>
<th align="left">權益</th>
<th align="left">負面</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>選擇性地使用動態設定檔</p></td>
<td align="left"><p>App-v 5.0 用戶端必須分析並處理這些動態設定檔。</p>
<p>關注檔案的大小與複雜性（腳本執行、VREG 包含/排除）。</p>
<p>許多虛擬應用程式套件可能已經擁有使用者或電腦專用的動態配置檔案。</p></td>
<td align="left"><p>如果有選擇性地使用這些檔案或根本不使用，發佈時間就會得到改善。</p></td>
<td align="left"><p>虛擬應用程式套件需要個別重新配置，或是透過 App V 伺服器管理主控台來移除相關聯的動態設定檔案。</p></td>
</tr>
</tbody>
</table>



### 使用 Powershell 停用動態設定

-   在已發佈的套件中，您可以使用 `Set-AppVClientPackage –Name Myapp –Path c:\Packages\Apps\MyApp.appv` 不含

    **-DynamicDeploymentConfiguration**參數

-   同樣地，當您使用來新增套件時 `Add-AppVClientPackage –Path c:\Packages\Apps\MyApp.appv` ，請不要使用

    **-DynamicDeploymentConfiguration**參數。

如需有關如何套用動態設定的檔，請參閱：

-   [如何使用 PowerShell 來套用使用者設定檔案](how-to-apply-the-user-configuration-file-by-using-powershell.md)

-   [如何使用 PowerShell 來套用部署設定檔案](how-to-apply-the-deployment-configuration-file-by-using-powershell.md)

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">步驟</th>
<th align="left">考量</th>
<th align="left">權益</th>
<th align="left">負面</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在套件生命週期期間執行同步腳本的帳戶。</p></td>
<td align="left"><p>如果將腳本宣傳資料內嵌在套件中，Add （Powershell）可能會有很大的下降速度。</p>
<p>在虛擬應用程式啟動期間執行腳本（StartVirtualEnvironment、StartProcess）和/或 Add + 發佈會影響在一或多個這些週期作業期間的感知效能。</p></td>
<td align="left"><p>使用非同步（無封鎖）腳本可確保週期作業能有效完成。</p></td>
<td align="left"><p>這個步驟需要使用內嵌的腳本宣傳資料（具有相關聯的動態配置檔案，以及同步處理及執行腳本）的所有虛擬應用程式套件的相關資訊。</p></td>
</tr>
<tr class="even">
<td align="left"><p>從套件中移除無關的虛擬字型。</p></td>
<td align="left"><p>App-V 產品小組所調查的大部分應用程式都包含少量字型，通常少於20個。</p></td>
<td align="left"><p>虛擬字型會影響發佈更新效能。</p></td>
<td align="left"><p>需要在本機啟用/安裝所需的字型。 如需相關指示，請參閱安裝或卸載字型。</p></td>
</tr>
</tbody>
</table>



### 判斷套件中存在哪些虛擬字型

-   製作套件的複本。

-   將套件 \ _copy 的 appv 重新命名為 Package\_copy.zip

-   開啟 AppxManifest.xml 並找出下列專案：

    &lt;appv：延伸類別 = "AppV. Fonts"&gt;

    &lt;appv：字型&gt;

    &lt;appv：字型路徑 = "\ [{Fonts} \] \\private\\CalibriL.ttf" DelayLoad = "true" &gt; &lt; /Appv： Font&gt;

    **注意**  
    如果有標示為**DelayLoad**的字型，這些字型將不會影響第一次啟動。



~~~
&lt;/appv:Fonts&gt;
~~~

### 從套件中排除虛擬字型

針對電腦上所有使用者、特定使用者或使用者的使用者設定，使用最符合使用者範圍的動態設定檔。

-   使用 [部署] 或 [使用者設定] 停用字型。

字型

--&gt;

&lt;已啟用的字型 = "false"/&gt;

&lt;!--

## <a href="" id="bkmk-terms1"></a> App-V 5.0 效能指南術語


描述與 App-v 5.0 效能優化相關的概念和動作時，會用到下列字詞。

-   **複雜性**–指的是一或多個在預設定（**AppvClientPackage**）或整合（**Publish-AppvClientPackage**）期間可能會影響效能的封裝特性。 一些範例特性包括：資訊清單大小、虛擬字型數、檔案數目。

-   **取消整合**–移除使用者整合

-   **重新整合**–運用使用者整合。

-   **非持久，彙集**-在每次登入時，建立執行虛擬環境的電腦。

-   **Persistent，個人**–執行虛擬環境的電腦，每次登入都保持不變。

-   [有**狀態**-適用于此檔]，表示使用者整合是在會話之間保留，而使用者環境管理技術則與非持久性 RDSH 或 VDI 搭配使用。

-   **無狀態**–代表沒有在會話之間保留任何使用者狀態的情況。

-   **Trigger** –（或原生動作觸發程式）。 UPM 使用這些類型的觸發程式來啟動監視或同步處理作業。

-   **使用者體驗**-在 App-V 5.0 的內容中，使用者體驗（quantitatively）是下列各部分的總和：

    -   使用者在能操縱桌面時，啟動登入的點。

    -   在使用 App-v 5.0 full server 基礎結構時，從桌面可以與發佈重新整理開始（在 PowerShell 術語中為同步處理）的點。 在獨立實例中，啟動 [**載入 AppVClientPackage** ] 和 [**發佈-AppVClientPackage] Powershell**命令。

    -   [從開始-完成] 發佈重新整理。 在獨立實例中，這是第一次發佈的虛擬應用程式。

    -   從可從快捷方式啟動虛擬應用程式的位置。 或者，它是從已登錄檔案類型關聯的點開始，並啟動指定的虛擬應用程式。

-   **使用者設定檔管理**–管理與環境相關的使用者元件的可控與結構化方法。 例如，使用者設定檔、喜好設定與原則管理、應用程式控制和應用程式部署。 您可以使用腳本或協力廠商解決方案視需要設定環境。






## 相關主題


[Microsoft Application Virtualization 5.0 系統管理員指南](microsoft-application-virtualization-50-administrators-guide.md)









