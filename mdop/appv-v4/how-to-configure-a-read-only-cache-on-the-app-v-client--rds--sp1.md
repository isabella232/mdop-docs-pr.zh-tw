---
title: 如何在 App-V 用戶端 (RDS) 上設定唯讀快取
description: 如何在 App-V 用戶端 (RDS) 上設定唯讀快取
author: dansimp
ms.assetid: b6607fe2-6f92-4567-99f1-d8e3c8a591e0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a44844ae9ffc3497151be7713f6a43fda0ccd8fa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801621"
---
# 如何在 App-V 用戶端 (RDS) 上設定唯讀快取


**重要** 您必須執行 App-V 4.6、SP1，才能使用此程式。

 

您可以使用已填入所有使用者所需的所有應用程式的共用快取來部署 App-v 用戶端。 然後，將 App-v 遠端桌面服務（RDS）用戶端設定為使用相同的快取檔案。 使用者可以使用 App-v 發佈程式來獲准存取特定的應用程式。 因為已預先預先載入所有應用程式的快取，所以當使用者啟動應用程式時，不會發生任何資料流程。 不過，您必須將用來預裝快取的套件放在支援即時資料流通訊協定（RTSP）資料流程的 App-v 伺服器上，並授予 App-v 用戶端的存取權限。 如果您使用 App-v 管理伺服器發佈應用程式，您可以使用它來提供此資料流程函數。

**記事** 這些程式中所述的詳細資料僅做為範例。 您可能會使用不同的方法來完成整個程式。

 

## 在 RDS 案例中部署 App-v 用戶端


部署程式是由四個主要任務所組成：

-   建立及填充主共用的快取檔案

-   將共用的快取檔案複製到伺服器儲存體

-   配置 App-v 用戶端軟體

-   在初始部署之後管理共用快取檔案的更新部署週期

這些工作需要謹慎規劃。 我們建議您為您的組織準備並記錄可重複使用的程式，以供貴組織追蹤。 這對於主共用快取檔案的準備及部署尤為重要，而且對於應用程式更新的持續管理，每一個都需要更新主共用快取。 使用下列程式完成這些主要任務。

**記事** 雖然您可以使用數種不同的方法發佈應用程式，但下列程式是以您使用 App-v 管理伺服器來發佈的程式為基礎。

 

**針對初始部署設定唯讀快取**

1. 設定和設定 App-v 管理伺服器來提供使用者驗證及發佈支援。

2. 以所有使用者所需的所有應用程式套件填入此管理伺服器的 [內容] 資料夾。

3. 設定已安裝應用程式 V 用戶端的暫存電腦。 使用可存取所有應用程式的帳戶登入暫存電腦，以便將一組完整的應用程式發佈到電腦，然後將應用程式流式處理成可完全載入。

   **重要**  
   暫存電腦所使用的作業系統類型和系統架構必須與應用程式 V 用戶端將執行的 Vm 所使用的相同。

     

4. 在安全模式中重新開機暫存電腦，以確保驅動程式未啟動，因為這會鎖定快取檔案。

   **注意**  
   或者，您可以停止並停用應用程式虛擬化服務，然後重新開機電腦。 複製檔案之後，請記住要啟用並再次啟動該服務。

     

5. 將 Sftfs fsd cache 檔案複製到 SAN，其中所有 RDS 伺服器都可以存取，例如共用資料夾。 針對將管理快取檔案更新的管理員，將 [資料夾存取許可權] 設定為 [所有人都能使用唯讀] 和 [完全控制]。 可以從 registry AppFS\\FileName. 取得快取檔案的位置

   **重要**  
   您必須將 FSD 檔案放在具有與本機附加儲存效能（例如 SAN）相同的回應與可靠性等位置。

     

6. 在每個 RDS 伺服器上安裝 app-v RDS 用戶端，然後將下列登錄機碼值新增到用戶端的 AppFS 鍵，將其設定為使用唯讀快取。 AppFS 鍵位於 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\\] Microsoft\\SoftGrid\\4.5\\Client\\AppFS 32 位電腦，以及 HKEY \ _LOCAL \ 64 位電腦的 \\software\\wow6432node\\microsoft\\softgrid\\4.5\\client\\appfs \ \ _MACHINE。

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
   <td align="left"><p>指定共用快取檔案的路徑，例如 \RDSServername\Sharefolder\SFTFS。FSD （必要）。</p></td>
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

     

7. 將伺服器陣列中的每個 RDS 伺服器設定為使用發佈伺服器，並在使用者登入時使用發佈更新。 當使用者登入 RDS 伺服器時，會發生發佈更新週期併發布其帳戶已獲得授權的所有應用程式。 這些應用程式是從共用的快取中執行。

**設定 RDS 用戶端以進行套件升級**

1.  完成應用程式套件的升級與測試。

2.  在 App-V 伺服器上升級套件。 然後，在暫存電腦上將新版本的應用程式發佈並資料流程到用戶端，讓它們完全載入到快取中。

3.  在安全模式中重新開機暫存電腦，以確保驅動程式不會啟動。

    **記事** 或者，您可以先停止並停用 services.msc 中的 Application Virtualization 服務，然後重新開機電腦。 複製檔案之後，請記得再次啟用並啟動該服務。

     

4.  將 Sftfs fsd cache 檔案複製到 SAN，其中所有 RDS 伺服器都可以存取，例如共用資料夾。 您可以使用不同的檔案名，例如，SFTFS \ _V2。FSD，以區別新版本。

5.  若要在伺服器陣列中的每個 RDS 伺服器上設定 App-v RDS 用戶端，以使用更新的共用快取檔案，請將 AppFS 登錄項 FILENAME 值，以指向更新檔案的位置，例如 \\\\RDSServername\\Sharefolder\\SFTFS\ _V2。FSD. 這可保證在應用程式 Vclient 的驅動程式重新開機時，每個 RDS 伺服器都會收到更新的快取複本。

    **重要** 您必須重新開機 RDS 伺服器，才能使用更新的共用快取檔案。

     

## 如何在升級快取時使用符號連結


您可以在下列作業系統中使用符號連結，而不是在每次部署新的快取檔案時，不會變更 AppFS 金鑰檔案名值： Windows Vista、Windows 7 和 Windows Server 2008。 如需符號連結的詳細資訊，請參閱[符號連結](https://go.microsoft.com/fwlink/?LinkId=157626)（ https://go.microsoft.com/fwlink/?LinkId=157626) 。 相反地，Windows XP 不支援使用符號連結，而且您必須改用連接點。 如需交接的詳細資訊，請參閱 Microsoft 知識庫中的[文章 205524](https://go.microsoft.com/fwlink/?LinkId=182553) （以及 https://go.microsoft.com/fwlink/?LinkId=182553) 工具[交叉口 v 1.05](https://go.microsoft.com/fwlink/?LinkId=182554) （） https://go.microsoft.com/fwlink/?LinkId=182554) 。

**設定符號連結以參照快取**

1.  在初始部署階段中，以 RDS 伺服器主機作業系統上的本機系統管理員身分開啟命令提示字元視窗。

2.  使用 MKLINK 命令建立符號連結，然後將它設定為指向 Sftfs fsd 檔案。

    **     mklink symlinkname \\\\rdshostserver\\sharefolder\\sftfs.fsd**

3.  在 VDI 主 VM 影像中，使用 [**以系統管理員身分執行**] 選項來開啟命令提示字元視窗，然後授與遠端連結許可權，讓 VM 可以存取 VDI 主機作業系統上的符號連結。 根據預設，遠端連結許可權是停用的。

    **fsutil behavior set SymlinkEvaluation R2R：1**

    **記事** 在 storage server 上，必須啟用適當的連結許可權。 視連結的位置和 Sftfs 的 fsd 檔案而定，許可權是**L2L： 1**或**L2R：** 1 或**R2L** ：1或 R2R： 1**或：1。**

     

4.  當您設定 App-v RDS 用戶端時，請將 AppFS 項 FILENAME 值設為等於使用符號連結之 FSD 檔案的 UNC 路徑。 例如，將檔案名設定為 \\\\VDIHostserver\\Symlinkname。 當 App-v 用戶端第一次存取快取時，符號連結會傳送到用戶端的快取檔案控制碼。 只要用戶端執行，用戶端就會繼續使用該控制碼。 即使現有用戶端已開啟舊的共用快取，您也可以安全地更新符號連結的值。

5.  當您必須升級套件，或將新套件新增至快取時，請依照升級程式的步驟1到4進行。 然後，刪除符號連結，然後重新建立，以指向共用快取檔案的新版本。 這可確保當 App-v server 驅動程式重新開機時，每個 RDS 伺服器都會收到更新的快取複本。 當您重新開機 RDS 伺服器時，App-v 用戶端會接收更新的快取複本複本，因為用戶端會使用包含更新符號連結的路徑。 然後，使用者可以存取新的和更新的應用程式。

## 相關主題


[如何安裝 Application Virtualization Management Server](how-to-install-application-virtualization-management-server.md)

[如何手動安裝 Application Virtualization Client](how-to-manually-install-the-application-virtualization-client.md)

[如何使用命令列安裝用戶端](how-to-install-the-client-by-using-the-command-line-new.md)

 

 





