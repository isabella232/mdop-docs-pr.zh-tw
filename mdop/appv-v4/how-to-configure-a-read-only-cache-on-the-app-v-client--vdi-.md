---
title: 如何在 App-V 用戶端 (VDI) 上設定唯讀快取
description: 如何在 App-V 用戶端 (VDI) 上設定唯讀快取
author: dansimp
ms.assetid: 7a41e017-9e23-4a6a-a659-04d23f008b83
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 114f9dfbf55a3f62b6bc8bec6b37a659ffbfaf56
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801618"
---
# 如何在 App-V 用戶端 (VDI) 上設定唯讀快取


在 Microsoft Application Virtualization （App-v）4.6 中，用戶端支援使用共用的唯讀快取快取。 共用唯讀快取可讓用戶端能在虛擬桌面基礎結構（VDI）系統中高效地使用磁碟空間，使用者可以在其中執行資料中心伺服器環境中託管的虛擬機器（VM）上的應用程式，並在儲存區域網路（SAN）上共用網路儲存空間。 下列程式會提供在其中一個主要 VDI 架構（稱為「彙集 VM」或「靜態 VM」）中實現 App-v 用戶端所需程式的概覽。 假設您熟悉 App-v system 及其元件的規劃、部署及操作，以及 VDI 伺服器的操作與管理。。。。 如需 App-v 的詳細資訊，請參閱[應用程式虛擬化](https://go.microsoft.com/fwlink/?LinkId=122939)（https://go.microsoft.com/fwlink/?LinkId=122939)

**記事** 這些程式中所述的詳細資料僅做為範例。 您可能會使用不同的方法來完成整個程式。

 

## 在 VDI 案例中部署 App-v 用戶端


您可以在 VDI 案例中部署 app-v 用戶端，方法是使用已填入所有使用者所需的所有應用程式的共用唯讀快取。 接著您可以設定 VDI 主 VM 影像，讓所有 App-v 用戶端都使用相同的快取檔案。 使用者可以使用 App-v 發佈程式來獲准存取特定的應用程式。 由於快取已預先載入所有的應用程式，因此當使用者啟動應用程式時，不會發生任何資料流程。 不過，您必須將用來預裝快取的套件放在支援即時資料流通訊協定（RTSP）資料流程的 App-v 伺服器上，並授予 App-v 用戶端的存取權限。 如果您使用 App-v 管理伺服器發佈應用程式，您可以使用它來提供此資料流程函數。

部署程式是由四個主要任務所組成：

-   建立及填充主共用的快取檔案

-   將共用的快取檔案複製到 VDI 伺服器儲存體

-   在 VDI 主映射上配置 app-v 用戶端軟體

-   在初始部署之後管理共用快取檔案的更新部署週期

這些工作需要謹慎規劃。 我們建議您為您的組織準備並記錄可重複使用的程式，以供貴組織追蹤。 這對於主共用快取檔案的初始準備與部署尤為重要，且針對應用程式更新的日常管理，每一個都需要更新主共用快取。 使用下列程式完成這些主要任務。

**記事** 雖然您可以使用數種不同的方法發佈應用程式，但下列程式是以使用 App-v 管理伺服器來發佈的方式為基礎。

 

**在共用 VM VDI 或靜態 VM VDI 案例中設定唯讀快取以進行初始部署**

1. 在 VDI 伺服器的 VM 中設定和設定 App-v 管理伺服器，以提供使用者驗證及發佈支援。

2. 以所有使用者所需的所有應用程式套件填入此管理伺服器的 [內容] 資料夾。

3. 設定已安裝應用程式 V 用戶端的暫存電腦。 使用可存取所有應用程式的帳戶登入暫存電腦，以便將一組完整的應用程式發佈到電腦，然後將應用程式流式處理成可完全載入。

   **重要**  
   暫存電腦所使用的作業系統類型和系統架構必須與應用程式 V 用戶端將執行的 Vm 所使用的相同。

     

4. 在安全模式中重新開機暫存電腦，以確保驅動程式未啟動，這會鎖定快取檔案。

   **注意**  
   或者，您可以停止並停用應用程式虛擬化服務，然後重新開機電腦。 複製檔案之後，請記得再次啟用並啟動該服務。

     

5. 將 Sftfs fsd cache 檔案複製到 VDI 伺服器的 SAN 中，所有 Vm 都可以存取，例如共用資料夾。 針對將管理快取檔案更新的管理員，將 [資料夾存取許可權] 設定為 [所有人都能使用唯讀] 和 [完全控制]。 可以從 registry AppFS\\FileName. 取得快取檔案的位置

   **重要**  
   您必須將 FSD 檔案放在具有對本機附加儲存效能（例如 SAN）同等回應與可靠性的位置。

     

6. 在 VDI 主 VM 影像上安裝 App-v Desktop 用戶端，然後將下列登錄機碼值新增到用戶端的 AppFS 鍵，將其設定為使用唯讀快取。 AppFS 鍵位於 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\\ [Wow6432Node\\\] Microsoft\\SoftGrid\\4.5\\Client\\AppFS。

   <table>
   <colgroup>
   <col width="25%" />
   <col width="25%" />
   <col width="25%" />
   <col width="25%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">索引鍵</th>
   <th align="left">類型</th>
   <th align="left">值</th>
   <th align="left">用途</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>FileName</p></td>
   <td align="left"><p>字串</p></td>
   <td align="left"><p>FSD 路徑</p></td>
   <td align="left"><p>指定共用快取檔案的路徑，例如 \VDIServername\Sharefolder\SFTFS。FSD （必要）。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>ReadOnlyFSD</p></td>
   <td align="left"><p>DWORD</p></td>
   <td align="left"><p>sr-1</p></td>
   <td align="left"><p>將用戶端配置為以唯讀模式運作。 這可確保用戶端不會嘗試將更新資料流程傳輸到套件快取。 (必要項)</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>ErrorLogLocation</p></td>
   <td align="left"><p>字串</p></td>
   <td align="left"><p>錯誤記錄（.etl）檔案的路徑</p></td>
   <td align="left"><p>用來指定錯誤記錄路徑的專案。 採用. 使用本機路徑（例如 C:\Logs\Sftfs.etl）。</p></td>
   </tr>
   </tbody>
   </table>

     

7. 將主 VM 影像用戶端設定為使用發佈伺服器，並在登入時使用發佈重新整理。 當使用者登入 VDI 系統，且其 VM 是從主 VM 影像建立時，會發生發佈重新整理迴圈，併發布其帳戶已獲得授權的所有應用程式。 這些應用程式是從共用的快取中執行。

**在共用 VM 案例中設定用戶端進行套件升級**

1.  完成應用程式套件的升級與測試。

2.  在 App-V 伺服器上升級套件。 然後，在暫存電腦上將新版本的應用程式發佈並資料流程到用戶端，讓它們完全載入到快取中。

3.  在安全模式中重新開機暫存電腦，以確保驅動程式不會啟動。

    **記事** 或者，您可以在 services.msc 中停止並停用應用程式虛擬化服務，然後重新開機電腦。 複製檔案之後，請記得再次啟用並啟動該服務。

     

4.  將 Sftfs fsd cache 檔案複製到 VDI 伺服器的 SAN 中，所有 Vm 都可以存取，例如共用資料夾。 您可以使用不同的檔案名，例如，SFTFS \ _V2。FSD，以區別新版本。

5.  若要在 VDI 主 VM 影像上設定 App-v Desktop 用戶端，以使用更新的共用快取檔案，請將 AppFS 登錄項檔案名值設為指向更新檔案的位置，例如 \\\\VDIServername\\Sharefolder\\SFTFS\ _V2。FSD. 當使用者登出後再重新登入時，會使用更新的主映射建立新的 VM。 其所有使用者設定將會保留並套用至新的 VM。 然後他們就能存取已更新的應用程式。

**在靜態 VM 案例中設定用戶端進行套件升級**

1.  完成應用程式套件的升級與測試。

2.  在 App-V 伺服器上升級套件。 然後，在暫存電腦上將新版本的應用程式發佈並資料流程到用戶端，讓應用程式完全載入到快取中。

3.  在安全模式中重新開機暫存電腦，以確保驅動程式不會啟動。

    **記事** 或者，您可以在 services.msc 中停止並停用應用程式虛擬化服務，然後重新開機電腦。 複製檔案之後，請記得再次啟用並啟動該服務。

     

4.  將 Sftfs fsd cache 檔案複製到 VDI 伺服器的 SAN 中，所有 Vm 都可以存取，例如共用資料夾。 您可以使用不同的檔案名，例如，SFTFS \ _V2。FSD，以區別新版本。

5.  若要在 VDI 主 VM 影像上設定 App-v Desktop 用戶端，以使用更新的共用快取檔案，請將 AppFS 登錄項檔案名值設為指向更新檔案的位置，例如 \\\\VDIServername\\Sharefolder\\SFTFS\ _V2。FSD. 這可確保新使用者能取得新版本。

6.  建立編輯 AppFS 鍵檔案名值的腳本，以將其設定為更新快取的位置，例如，\\\\VDIServername\\Sharefolder\\SFTFS\ [_V2]。FSD. 將此腳本設定為在使用者登入或登入時執行，讓它在 App V 用戶端驅動程式啟動之前執行，例如使用群組原則設定。 當使用者登出並再次登入時，他們現有的 VM 就會更新，而且會使用更新的快取複本。 然後，他們就能存取已更新的應用程式。

## 如何在升級快取時使用符號連結


您可以在下列作業系統中使用符號連結，而不是在每次部署新的快取檔案時，不修改 AppFS 金鑰檔案名值： Windows Vista、Windows 7 和 Windows Server 2008。 如需符號連結的詳細資訊，請參閱[符號連結](https://go.microsoft.com/fwlink/?LinkId=157626)（ https://go.microsoft.com/fwlink/?LinkId=157626) 。 相反地，Windows XP 不支援使用符號連結，而且您必須改用連接點。 如需交接的詳細資訊，請參閱 Microsoft 知識庫中的[文章 205524](https://go.microsoft.com/fwlink/?LinkId=182553) （以及 https://go.microsoft.com/fwlink/?LinkId=182553) 工具[交叉口 v 1.05](https://go.microsoft.com/fwlink/?LinkId=182554) （） https://go.microsoft.com/fwlink/?LinkId=182554) 。

**設定符號連結以參照快取**

1.  在初始部署階段中，以 VDI 伺服器主機作業系統上的本機系統管理員身分開啟命令提示字元視窗。

2.  使用 MKLINK 命令建立符號連結，然後將它設定為指向 Sftfs fsd 檔案。

    **     mklink symlinkname \\\\vdihostserver\\sharefolder\\sftfs.fsd**

3.  在 VDI 主 VM 影像中，使用 [**以系統管理員身分執行**] 選項來開啟命令提示字元視窗，然後授與遠端連結許可權，讓 VM 可以存取 VDI 主機作業系統上的符號連結。 根據預設，遠端連結許可權是停用的。

    **fsutil behavior set SymlinkEvaluation R2R：1**

    **記事** 在 storage server 上，必須啟用適當的連結許可權。 視連結的位置和 Sftfs 的 fsd 檔案而定，許可權是**L2L： 1**或**L2R：** 1 或**R2L** ：1或 R2R： 1**或：1。**

     

4.  當您在 VDI 主 VM 影像上設定 App-v Desktop 用戶端時，請將 AppFS 項 FILENAME 值設為等於使用符號連結之 FSD 檔案的 UNC 路徑;例如，將它設定為 \\\\VDIHostserver\\Symlinkname。 當 App-v 用戶端第一次存取快取時，符號連結會傳送到用戶端的快取檔案控制碼。 只要用戶端執行，用戶端就會繼續使用該控制碼。 即使現有用戶端已開啟舊的共用快取，您也可以安全地更新符號連結的值。

5.  當您必須升級套件，或將新套件新增至快取時，請針對靜態 VM 或彙集 VM 案例，執行步驟1到5的升級程式。 然後，刪除符號連結，然後重新建立，以指向共用快取檔案的新版本。 當 VM 重新開機時，用戶端會收到更新的快取複本複本，因為 VM 使用的路徑包含已更新的符號連結。 然後，使用者可以存取新的和更新的應用程式。

## 相關主題


[如何安裝 Application Virtualization Management Server](how-to-install-application-virtualization-management-server.md)

[如何手動安裝 Application Virtualization Client](how-to-manually-install-the-application-virtualization-client.md)

[如何使用命令列安裝用戶端](how-to-install-the-client-by-using-the-command-line-new.md)

 

 





