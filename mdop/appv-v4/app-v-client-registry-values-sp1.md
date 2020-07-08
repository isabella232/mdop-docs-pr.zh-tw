---
title: App-V 用戶端登錄值
description: App-V 用戶端登錄值
author: dansimp
ms.assetid: 46af5209-9762-47b9-afdb-9a2947e013f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 05cd807ff9882bc478aca07abc4a28cdea83086a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802365"
---
# App-V 用戶端登錄值


Microsoft Application Virtualization （App-v）用戶端將其設定儲存在註冊表中。 如果您瞭解註冊表中的資料格式，就可以收集一些有關用戶端的有用資訊。 您也可以透過變更登錄專案來設定多個用戶端動作。 本主題列出所有應用程式虛擬化（App-v）用戶端登錄機碼，並說明其用法。

**重要**  
在執行64位作業系統的電腦上，下列各節中所述的金鑰和值將會位於 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\Client。



## 設定鍵


下表提供與 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration 金鑰有關之註冊表值的相關資訊。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名稱</th>
<th align="left">類型</th>
<th align="left">資料（範例）</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ProductName</p></td>
<td align="left"><p>字串</p></td>
<td align="left"><p>Microsoft Application Virtualization 桌面用戶端</p></td>
<td align="left"><p>請勿修改。</p></td>
</tr>
<tr class="even">
<td align="left"><p>版本 </p></td>
<td align="left"><p>字串 </p></td>
<td align="left"><p>4.5.0.xxx </p></td>
<td align="left"><p>請勿修改。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>驅動程式 </p></td>
<td align="left"><p>字串 </p></td>
<td align="left"><p>Sftfs.sys </p></td>
<td align="left"><p>如果此項值存在，則會包含上次啟動核心時導致停止錯誤的驅動程式名稱。 修正停止錯誤之後，您必須刪除此金鑰值，才能開始 sftlist。</p></td>
</tr>
<tr class="even">
<td align="left"><p>InstallPath </p></td>
<td align="left"><p>字串 </p></td>
<td align="left"><p>預設 = C:\Program Files\Microsoft Application Virtualization 用戶端</p></td>
<td align="left"><p>用戶端的安裝位置。 請勿修改。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>LogFileName </p></td>
<td align="left"><p>字串 </p></td>
<td align="left"><p>預設 = CSIDL_COMMON_APPDATA \Microsoft\Application 虛擬化 Client\sftlog.txt</p></td>
<td align="left"><p>用戶端記錄檔的路徑和名稱。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果您執行的是舊版 App-v 4.6、SP1，且您修改了記錄檔案名或位置，您必須重新開機 sftlist 服務，變更才會生效。</p>
</div>
<div>

</div>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p>LogMinSeverity </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>預設值 = 4，資訊</p></td>
<td align="left"><p>控制要寫入記錄的訊息。 此值表示記錄的閾值，即記錄小於或等於該值的所有專案。 例如，0x3 （Warning）的值表示記錄警告（0x3）、錯誤（0x2）及嚴重錯誤（0x1）。</p>
<p>值範圍： 0x0 = 無，0x1 = 臨界，0x2 = 錯誤，0x3 = Warning，0x4 = 資訊（預設值），0x5 = Verbose。</p>
<p>記錄層級可從應用程式虛擬化（App-v）用戶端主控台和命令提示字元進行設定。 在命令提示字元中，sftlist.exe/verboselog 的命令會將記錄層級增加到詳細。 如需有關命令列詳細資料的詳細資訊，請參閱</p>
<p><a href="https://go.microsoft.com/fwlink/?LinkId=141467https://go.microsoft.com/fwlink/?LinkId=141467" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=141467https://go.microsoft.com/fwlink/?LinkId=141467">https://go.microsoft.com/fwlink/?LinkId=141467https://go.microsoft.com/fwlink/?LinkId=141467</a></p>
<p>.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LogRolloverCount</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 4</p></td>
<td align="left"><p>定義要在重設時保留的記錄檔案備份複本數。 有效範圍為0到9999。 預設值為4。 值為0表示不會保留任何複本。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LogMaxSize</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 256</p></td>
<td align="left"><p>在重設前，定義記錄檔可能會增長的最大大小（MB）。 預設大小為 256 MB。 達到此大小時，系統會在下一次寫入嘗試時強制進行記錄重設。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SystemEventLogLevel</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設值 = 0x4 （App-v 4.5）</p>
<p>預設值 = 0x3 （App-v 4.6）</p></td>
<td align="left"><p>指出記錄層級，日誌訊息會寫入 NT 事件記錄。 此值表示記錄的閾值，也就是等於或小於該值的所有專案都會登入。 例如，0x3 （Warning）的值表示記錄警告（0x3）、錯誤（0x2）及嚴重錯誤（0x1）。</p>
<p>值範圍</p>
<p>0x0 = None</p>
<p>0x1 = 危急</p>
<p>0x2 = 錯誤</p>
<p>0x3 = 警告</p>
<p>0x4 = 資訊（預設值）</p>
<p>0x5 = 詳細</p></td>
</tr>
<tr class="even">
<td align="left"><p>AllowIndependentFileStreaming</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 0</p></td>
<td align="left"><p>指示是否要啟用來自檔案的資料流程，不論用戶端是否已使用 APPLICATIONSOURCEROOT 參數進行設定。 如果設定為 FALSE，即使 OSD HREF 或 APPLICATIONSOURCEROOT 參數包含檔案路徑，傳輸也不會啟用檔案的資料流程。</p>
<p>0x0 = False （預設值）</p>
<p>0x1 = True</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ApplicationSourceRoot</p></td>
<td align="left"><p>字串</p></td>
<td align="left"><p>rtsps://mainserver:322/prodapps</p>
<p><a href="https://mainserver:443/prodapps" data-raw-source="https://mainserver:443/prodapps">https://mainserver:443/prodapps</a></p>
<p>檔案：//\uncserver\share\prodapps</p>
<p>檔案：//\uncserver\share</p></td>
<td align="left"><p>啟用系統管理員或電子軟體發佈（ESD）系統，以確保根據拓撲管理配置來執行應用程式載入。 使用此金鑰值來覆寫應用程式的 HREF 元素（例如，來源位置）的 OSD 基本代碼。 應用程式來源根目錄支援 Url 和通用命名慣例（UNC）路徑格式。</p>
<p>URL 路徑的正確格式為 protocol：：（port） [/path] [/]，其中的埠和路徑是選擇性的。 如果沒有指定埠，則會使用通訊協定的預設埠。 只會取代 OSD URL 中的通訊協定：//server：埠部分。 </p>
<p>UNC 路徑的正確格式為 \computername\sharefolder [folder] []，其中資料夾是選擇性的。 電腦名稱稱可以是完整的功能變數名稱（FQDN）或 IP 位址，而 sharefolder 可以是磁片磁碟機盤符。 只會取代 OSD 路徑的 \computername\sharefolder 或磁片磁碟機盤符部分。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>OSDSourceRoot</p></td>
<td align="left"><p>字串</p></td>
<td align="left"><p>\computername\sharefolder\resource</p>
<p>\computername\content</p>
<p>C:\foldername</p>
<p><a href="http://computername/productivity/" data-raw-source="http://computername/productivity/">http://computername/productivity/</a></p>
<p><a href="https://computername/productivity/" data-raw-source="https://computername/productivity/">https://computername/productivity/</a></p></td>
<td align="left"><p>可讓系統管理員在發佈期間為已排序的應用程式套件指定 OSD 檔案檢索的來源位置。 OSDSourceRoot 的可接受格式包括 UNC 路徑和 Url （HTTP 或 HTTPs）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>IconSourceRoot</p></td>
<td align="left"><p>字串</p></td>
<td align="left"><p>\computername\sharefolder\resource</p>
<p>\computername\content</p>
<p>C:\foldername</p>
<p><a href="http://computername/productivity/" data-raw-source="http://computername/productivity/">http://computername/productivity/</a></p>
<p><a href="https://computername/productivity/" data-raw-source="https://computername/productivity/">https://computername/productivity/</a></p></td>
<td align="left"><p>可讓系統管理員在發佈期間指定已排序之應用程式套件的圖示檔案檢索來源位置。 IconSourceRoot 的可接受格式包括 UNC 路徑和 Url （HTTP 或 HTTPs）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AutoLoadTriggers</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 5</p></td>
<td align="left"><p>AutoLoad 是用戶端執行時間原則設定參數，可讓虛擬化應用程式的次要功能區塊在背景自動流入用戶端。 AutoLoad 觸發程式是標誌，用來表示啟動自動載入應用程式的事件。 AutoLoad 會隱式使用背景資料流程，讓應用程式完全載入到快取中。 首先會載入主要功能區塊，並在背景中載入其餘的功能區塊，以啟用前景作業（例如與應用程式互動的使用者），並提供最佳的感知效能。</p>
<p>位元遮罩值：</p>
<p>（0）永不：不會設定任何位（值為0），不會執行自動載入，因為沒有設定任何觸發程式。</p>
<p>（1） OnLaunch：使用者啟動應用程式時開始載入。</p>
<p>（2） OnRefresh：應用程式發佈時開始載入。 每當新增或更新套件記錄時，就會發生這種情況，例如，當進行發佈重新整理時。</p>
<p>（4） OnLogin：使用者登入時開始載入。</p>
<p>（5） OnLaunch 和 OnLogin： Default。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AutoLoadTarget</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 1</p></td>
<td align="left"><p>指示在任何指定的 AutoLoad 觸發程式發生時，將會自動載入哪些內容。 位元遮罩值：</p>
<p>（0）無：不會自動載入，不論可能會設定哪些觸發程式。</p>
<p>（1） PreviouslyUsed （預設值）：如果已啟用任何 AutoLoad 觸發程式，請只載入套件中之前已使用過之至少一個應用程式的套件，即已開始或 precached。</p>
<p>（2）全部：如果已啟用任何 AutoLoad 觸發程式，套件（每個套件）或所有套件（針對用戶端設定）的所有應用程式都會自動載入，不論它們是否曾啟動。</p></td>
</tr>
<tr class="even">
<td align="left"><p>RequireAuthorizationIfCached</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 1</p></td>
<td align="left"><p>表示無論是否已在快取中，都必須擁有授權。 可能的值：</p>
<p>0 = False：總是嘗試連線到伺服器。 如果無法建立伺服器連線，用戶端仍可讓使用者啟動先前載入到快取中的應用程式。</p>
<p>1 = True （預設值）：應用程式永遠必須在啟動時授權。 針對 RTSP 流程式應用程式，會將使用者授權權杖傳送到伺服器以進行授權。 對於以檔案為基礎的應用程式，檔案 Acl 會控制使用者是否可存取應用程式。</p>
<p>重新開機 sftlist 服務，變更才會生效。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>UserDataDirectory </p></td>
<td align="left"><p>字串 </p></td>
<td align="left"><p>APPDATA</p></td>
<td align="left"><p>儲存圖示快取及使用者設定的位置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>GlobalDataDirectory </p></td>
<td align="left"><p>字串 </p></td>
<td align="left"><p>C:\Users\Public\Documents </p></td>
<td align="left"><p>用於全域 App-v 資料的目錄，包括適用于 OSD 檔案、圖示檔案、快速鍵資訊及 SystemGuard 資源（例如 .ini 檔案）的緩存。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AllowCrashes </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>0 或 1 </p></td>
<td align="left"><p>預設 = 0：值為0表示用戶端嘗試捕捉內部程式例外狀況，以便讓其他使用者應用程式在發生當機時能復原並繼續。 值為1表示用戶端允許內部程式例外狀況發生，以便在偵錯工具中捕獲它們。</p></td>
</tr>
<tr class="even">
<td align="left"><p>CoreInternalTimeout </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>60</p></td>
<td align="left"><p>核心與前端之間的內部 IPC 要求超時（以秒為單位）。 請勿修改。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>DefaultSuiteCombineTime </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>第</p></td>
<td align="left"><p>這個值是用來指出啟動程式可以關閉的時間，以及在相同套件中的另一個應用程式執行時，不會產生任何錯誤訊息。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>SerializedSuiteLaunchTimeout </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>預設 = 60000</p></td>
<td align="left"><p>定義用戶端在同一個套件中開始序列化程式時，要等待的時間（以毫秒為單位）。 如果用戶端超時，程式將會繼續執行，但不會將其序列化。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>ScriptTimeout </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>300</p></td>
<td align="left"><p>如果 WAIT = TRUE，則在 OSD 檔案中的腳本預設超時時間（以秒為單位）。 您可以使用超時（而不是 [等待]）來指定每腳本超時。 值為0表示沒有等待，而0xFFFFFFFF 則表示 [永久等待]。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>LaunchRecordLogPath </p></td>
<td align="left"><p>字串 </p></td>
<td align="left"><p></p></td>
<td align="left"><p>如果在 HKLM 或 HKCU 底下，此值包含記錄檔的有效路徑，SFTTray 將會在程式啟動、關閉、無法啟動時寫入此記錄，並進入或離開中斷模式。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LaunchRecordMask </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>0x1A （26）記錄啟動錯誤和中斷模式進入與結束活動。</p>
<p>0x1F （31）記錄所有內容。</p>
<p>0x0 （0）不記錄任何內容。 </p></td>
<td align="left"><p>指定記錄五個事件中的哪一個（位元遮罩值）：</p>
<p>啟動程式1</p>
<p>2代表啟動失敗錯誤</p>
<p>4供關閉</p>
<p>8用於進入斷開連接模式</p>
<p>將 [退出中斷模式] 重新連線到伺服器的16</p>
<p>新增這些數位的任何組合，以開啟個別的訊息。 如果不在註冊表中，則預設為0x1F。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>LaunchRecordWriteTimeout </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>預設 = 3000</p></td>
<td align="left"><p>指定在嘗試寫入開機記錄記錄檔（如果有另一個程式正在使用它）時，紙盒會等待的時間（以毫秒為單位）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ImportSearchPath </p></td>
<td align="left"><p>字串 </p></td>
<td align="left"><p>d:\files;C:\documents 和 settings\user1\SFTs </p></td>
<td align="left"><p>在提示使用者選取目錄前，最多五個目錄的分號分隔清單，以搜尋便攜 SFT 檔案。 路徑中的尾部反斜線是選擇性的。 此值預設不存在，且必須手動設定。</p></td>
</tr>
<tr class="even">
<td align="left"><p>UserImportPath</p></td>
<td align="left"><p>字串 </p></td>
<td align="left"><p>D:\SFTs\ </p></td>
<td align="left"><p>僅在 HKCU 下有效。 尋找封裝匯入的 SFT 檔案時，使用者流覽到的最後一個位置。 如果成功找到 SFT，就會自動設定。 當您嘗試自動找到 SFT 檔案時，會針對連續的匯入使用此功能。</p></td>
</tr>
</tbody>
</table>



## 共用金鑰


HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Shared 鍵會控制跨 App V 元件共用的值。 下表提供與共享金鑰相關聯之註冊表值的相關資訊。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名稱 </th>
<th align="left">類型 </th>
<th align="left">資料（範例） </th>
<th align="left">描述 </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>DumpPath </p></td>
<td align="left"><p>字串 </p></td>
<td align="left"><p>Default = C：\ </p></td>
<td align="left"><p>在例外狀況中產生小型處理常式時，建立轉儲檔案的預設路徑。 預設值為 C：\如果未指定的話。 用戶端安裝程式會將此金鑰設定為 &lt; 應用程式虛擬化全域資料目錄 &gt; \Dumps。 Sequencer 安裝程式會將此金鑰設定為安裝目錄。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>DumpPathSizeLimit </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>1000</p></td>
<td align="left"><p>指定可用於儲存 minidumps 的最大磁碟空間總量（以 mb 為單位）。 預設 = 1000 MB。</p></td>
</tr>
</tbody>
</table>



## 網路金鑰


HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network 鍵會控制各種與網路相關的參數。 此金鑰主要是由網路傳輸代理程式所使用。 下表提供與網路金鑰相關聯之註冊表值的相關資訊。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名稱 </th>
<th align="left">類型 </th>
<th align="left">資料（範例） </th>
<th align="left">描述 </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Online</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 1</p></td>
<td align="left"><p>啟用或停用離線模式。 如果設為0，用戶端將無法與 App-v 管理伺服器或發佈伺服器進行通訊。 在中斷連接的操作中，用戶端可以啟動已載入的應用程式，即使未連線到 App-v 管理伺服器也一樣。 在離線模式中，用戶端不會嘗試連線到 App-v 管理伺服器或發佈伺服器。 您必須允許斷開連接的操作能夠離線工作。 預設值為1（線上），而0則停用（離線）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AllowDisconnectedOperation </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>預設 = 1</p></td>
<td align="left"><p>啟用或停用中斷式的操作。 預設值為1，且停用0。 當中斷式作業啟用時，App-v 用戶端可以啟動已載入的應用程式（即使它未連線到 App-v 管理伺服器）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>FastConnectTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 1000</p></td>
<td align="left"><p>這個值會指定 TCP 連接逾時（以毫秒為單位），以判斷何時進入中斷式作業模式。 這個值可以用來覆寫預設的 ConnectTimeout 為20秒（網路事務的 App-v 連接逾時），或是系統的 TCP 超時大約25秒的時間。 這樣就能快速地將用戶端連線到 [中斷連線] 作業模式。 在下一次連接時套用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LimitDisconnectedOperation</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 1 </p></td>
<td align="left"><p>只有在 AllowDisconnectedOperation 為1時才適用。 這個值會判斷在中斷連接的操作中，允許用戶端執行多久時間的時間限制。 1 = 有限。 0 = 無限制。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DOTimeoutMinutes</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 129600</p></td>
<td align="left"><p>指出應用程式在中斷式作業模式中可使用的分鐘數。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>有效值為1至999999，以分鐘為單位（1–1439998560分鐘）。 預設值為90天或129600分鐘。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>通訊協定</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設值 = 8</p></td>
<td align="left"><p>要使用的預設通訊協定（TCP 與 SSL）。 [選項] 對話方塊中的 [設定]。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ReadTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>20</p></td>
<td align="left"><p>讀取網路交易的超時時間（以秒為單位）。 請勿修改。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>WriteTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>20</p></td>
<td align="left"><p>寫入網路交易的超時時間（以秒為單位）。 請勿修改。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ConnectTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>20</p></td>
<td align="left"><p>連接網路交易的超時時間（以秒為單位）。 請勿修改。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ReestablishmentRetries</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>3</p></td>
<td align="left"><p>嘗試重新建立刪除的會話的次數。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ReestablishmentInterval</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>工資</p></td>
<td align="left"><p>嘗試重新建立已刪除的會話之間所等待的秒數。</p></td>
</tr>
</tbody>
</table>



## Http 金鑰


HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\Http 鍵會控制與 Http 資料流程相關的參數。 此金鑰主要是由網路傳輸代理程式使用。 下表提供與 Http 金鑰相關聯之註冊表值的相關資訊。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名稱 </th>
<th align="left">類型 </th>
<th align="left">資料（範例） </th>
<th align="left">描述 </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>LaunchIfNotFound</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 0</p></td>
<td align="left"><p>控制 HTTP 資料流程連線與 HTTP 伺服器的連線，以及資料包檔案在 HTTP 伺服器上不再存在的行為。 如果該值不存在，或者如果未設定為1，則 App-v 用戶端不會讓您啟動先前載入到快取中的應用程式。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>sr-1</p></td>
<td align="left"><p>如果此值設定為1，則 App-v 用戶端可讓您啟動先前載入到快取中的應用程式。</p></td>
</tr>
</tbody>
</table>



## 檔案系統金鑰


HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS 參數所含的值控制 App-v 的檔案系統參數。 下表提供與 AppFS 金鑰相關聯之註冊表值的相關資訊。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名稱 </th>
<th align="left">類型 </th>
<th align="left">資料（範例） </th>
<th align="left">描述 </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>FileSize </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>4096</p></td>
<td align="left"><p>檔案系統快取檔案的大小上限（mb）。 如果您在註冊表中變更這個值，您必須將狀態設為0並重新啟動。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>FileName </p></td>
<td align="left"><p>字串 </p></td>
<td align="left"><p>C:\Users\Public\Documents\SoftGrid Client\sftfs.fsd </p></td>
<td align="left"><p>檔案系統快取檔案的位置。 如果您在註冊表中變更這個值，您必須將 FileSize 保持不變，然後重新開機或將狀態設定為0並重新啟動。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>DriveLetter </p></td>
<td align="left"><p>字串 </p></td>
<td align="left"><p>Q： </p></td>
<td align="left"><p>將掛載 app-v 檔案系統的磁片磁碟機（如果有的話）。 此值是由監聽器或安裝程式所設定，且會由檔案系統讀取。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>狀態 </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>0x100 </p></td>
<td align="left"><p>檔案系統的狀態。 設定為0並重新啟動，以完全清除檔案系統快取。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>FileSystemStorage </p></td>
<td align="left"><p>字串 </p></td>
<td align="left"><p>C:\Profiles\Joe\SG </p></td>
<td align="left"><p>Symlinks 的路徑，請在 [HKCU] 下設定。 請勿修改（使用 [設定] 底下的 [資料目錄] 來變更）。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>GlobalFileSystemStorage </p></td>
<td align="left"><p>字串 </p></td>
<td align="left"><p>C:\Users\Public\Documents\SoftGrid Client\AppFS 儲存體 </p></td>
<td align="left"><p>通用檔案系統資料的路徑。 請勿修改。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>MaxPercentToLockInCache </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>預設值 = 90 </p></td>
<td align="left"><p>指定可鎖定之檔案系統快取檔案的最大百分比。 請勿修改。</p></td>
</tr>
<tr class="even">
<td align="left"><p>UnloadLeastRecentlyUsed</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 1</p></td>
<td align="left"><p>檔案系統快取空間管理功能使用最近最常使用的（LRU）演算法，且預設為啟用。 如果新套件所需的空間會超過快取中的可用空間，App-v 用戶端會使用這項功能來判斷它可以從快取中刪除的現有套件（如果有的話），為新套件騰出空間。 用戶端會刪除最舊的最近存取日期的套件（如果它比 MinPkgAge 註冊表值中指定的值還舊）。 值為0（停用）和1（預設值為啟用）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MinPackageAge</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>sr-1</p></td>
<td align="left"><p>若要判斷何時可以選取要捨棄的套件，請將此登錄值設定為在最近一次存取套件之後所要經過的最少天數。 您最近使用的套件將不會遭到捨棄。</p></td>
</tr>
</tbody>
</table>



## 許可權金鑰


為了協助防止使用者犯錯誤，系統管理員可以使用 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Permissions 鍵來控制對非系統管理使用者的部分動作，例如防止使用者不小心卸載程式。 具有系統管理許可權的使用者可以為自己提供下列任何一種許可權。 在共用系統上（例如遠端桌面工作階段主機（RD 工作階段主機）伺服器（舊稱終端伺服器）系統），請謹慎向使用者授予其他許可權，因為其中一些許可權可以讓使用者控制系統上所有使用者所使用的應用程式。 這些設定的可能值為1（允許）和0（不允許）。

[許可權金鑰] 設定會控制啟用命名動作的所有介面。 這包括 [選項] 對話方塊、[SFTTray] 和 [SFTMime]。 這些設定不會影響系統管理員。 下表提供與許可權金鑰相關聯之註冊表值的相關資訊。

名稱類型資料（範例）描述 ChangeFSDrive

DWORD

預設 = 0

值為1時，可讓使用者挑選不同的磁片磁碟機盤符作為檔案系統磁片磁碟機。

ChangeCacheSize

DWORD

預設 = 0

值1可讓使用者變更快取大小。

ChangeLogSettings

DWORD

預設 = 0

值1可讓使用者修改記錄層級、變更其位置，以及透過使用者介面將其重設。

AddApp

DWORD

預設 = 0

值1可讓使用者明確地新增應用程式。 這不會影響透過發佈重新整理所新增的應用程式，也不會防止使用者開始（也不是隱式新增）尚未新增的應用程式。 值為0或1。

LoadApp 

DWORD 

0

不允許使用者載入應用程式。 這是 RD 工作階段主機的預設值。 如果您是行動使用者，您可能會想要將您的應用程式完全載入在快取中，以便在斷開式作業或離線模式時使用。 若要從 App-v 管理伺服器或 App-v 流式處理伺服器對流進行應用程式，您必須連線到伺服器才能載入應用程式。

sr-1

允許使用者載入應用程式。 這是 Windows 桌上型電腦的預設值。 

UnloadApp 

DWORD 

0

不允許使用者卸載應用程式。 當您載入或卸載套件時，套件中的所有應用程式都會載入或從快取中移除。

sr-1

允許使用者卸載應用程式。 

LockApp 

DWORD 

0

不允許使用者鎖定和解除鎖定應用程式。 這是 RD 工作階段主機的預設值。 無法從快取中移除鎖定的應用程式，為新的應用程式騰出空間。 若要從適用于遠端桌面服務（舊稱終端服務）快取的 App-v 桌面或用戶端移除鎖定的應用程式，您必須解除鎖定。

sr-1

允許使用者鎖定和解除鎖定應用程式。 這是 Windows 桌上型電腦的預設值。 

ManageTypes 

DWORD 

0

不允許使用者單獨新增、編輯或移除該使用者的檔案類型關聯。 這是 RD 工作階段主機的預設值。 

sr-1

允許使用者只新增、編輯及移除該使用者的檔案類型關聯，而不是全域。 這是 Windows 桌上型電腦的預設值。 

RefreshServer 

DWORD 

0

不允許使用者觸發 MIME 設定的重新整理。 這是 RD 工作階段主機的預設值。 

sr-1

讓使用者觸發 MIME 設定的重新整理。 這是 Windows 桌上型電腦的預設值。 

UpdateOSDFile

DWORD

預設 = 0

值為1時，使用者可以使用修改過的 OSD 檔案。

ImportApp 

DWORD 

0

不允許使用者將應用程式匯入快取。 [載入] 與 [匯入] 之間的差異是，觸發載入時，用戶端會從位於 OSD、ASR 或 Override URL 中的目前設定位置取得套件。 使用匯入時，必須指定從中取得套件的位置。 

sr-1

允許使用者將應用程式匯入快取。 

ChangeRefreshSettings

DWORD

預設 = 0

值1可讓使用者修改伺服器的重新整理設定（[登入] 和 [定期重新整理] 時重新整理）。 這並不表示使用者可以修改其他伺服器設定（path、host 等）。

ManageServers

DWORD

預設 = 0

如果值為1，則使用者可以新增、編輯及移除伺服器，除了編輯由 ChangeRefreshSettings 許可權控制的重新整理設定以外。

PublishShortcut

DWORD

預設 = 0

值1可讓使用者透過使用者介面發佈快速鍵。 這不會影響在發佈更新期間發佈的快捷方式。

ViewAllApplications

DWORD

預設 = 0

值1會透過使用者介面顯示所有應用程式;否則，只會顯示使用者的應用程式。

RepairApp

DWORD

預設 = 1

值1可讓使用者在 SFTMime 或用戶端管理主控台上的應用程式上使用修復動作。 當您修復應用程式時，您會移除任何自訂的使用者設定，並還原預設設定。 這個動作不會變更或刪除快速鍵或檔案類型關聯，也不會從快取中移除應用程式。

ClearApp

DWORD

預設 = 1

如果值為1，則使用者可以在 SFTMime 或用戶端管理主控台中使用應用程式的 Clear 操作。 當您從主控台清除應用程式時，您將無法再使用該應用程式。 不過，應用程式仍會保留在快取中，而且在同一系統上仍可供其他使用者使用。 在發佈重新整理之後，清除的應用程式就會再次提供給您使用。

DeleteApp

DWORD

預設 = 0

值1可讓使用者在 SFTMime 或用戶端管理主控台上的應用程式上使用 [刪除] 動作。 當您刪除應用程式時，所選的應用程式將無法再供該用戶端上的任何使用者使用。 快捷方式和檔案類型關聯隨即刪除，並從快取中刪除應用程式。 不過，如果另一個應用程式參照檔案系統快取或所選應用程式的設定資料中的資料，這些專案就不會被刪除。

更新發佈之後，已刪除的應用程式就會再次提供給您使用。

ToggleOfflineMode

DWORD

值1可讓使用者選取以離線模式執行用戶端。 在離線模式中，應用程式虛擬化用戶端可以啟動已載入的應用程式（即使它未連線到 Application Virtualization 伺服器）。



## 自訂設定


HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\CustomSettings 鍵包含前端元件專用的值。 所有的自訂設定都是以字串形式儲存。 下表提供與 CustomSettings 金鑰相關聯之註冊表值的相關資訊。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名稱 </th>
<th align="left">類型 </th>
<th align="left">資料（範例） </th>
<th align="left">描述 </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>TrayErrorDelay </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>預設 = 30 </p></td>
<td align="left"><p>應用程式虛擬化通知區域將會顯示錯誤訊息（例如啟動失敗）的時間（以秒為單位） &quot; &quot; 。 1的最小值。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>TraySuccessDelay </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>預設值 = 10 </p></td>
<td align="left"><p>Appvmed 通知區域會顯示成功訊息（例如 &quot; Word 啟動 &quot; 或 &quot; Excel 關閉）的時間（秒） &quot; 。 如果是0，則會禁止顯示這些訊息。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>TrayVisibility</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 0</p></td>
<td align="left"><p>0 = 在使用虛擬化應用程式時顯示盤匣。</p>
<p>1 = 顯示紙盒（總是）。</p>
<p>2 = 永不顯示紙盒。</p></td>
</tr>
<tr class="even">
<td align="left"><p>TrayShowRefresh</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p></p></td>
<td align="left"><p>當存在並設定為1值時，允許功能表項目重新整理應用程式顯示在工作列功能表上，且可供使用者存取。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>TrayShowLoad</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p></p></td>
<td align="left"><p>當存在並設定為1值時，允許功能表項目載入應用程式顯示在工作列功能表上，且可供使用者存取。</p></td>
</tr>
</tbody>
</table>



## 報告設定


HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Reporting 鍵包含向 App-v 管理伺服器報告的特定值。 下表提供與報告金鑰相關聯之註冊表值的相關資訊。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名稱 </th>
<th align="left">類型 </th>
<th align="left">資料（範例） </th>
<th align="left">描述 </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>DataCacheLimit</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設值 = 20</p></td>
<td align="left"><p>此值指定要儲存報告資訊的 XML 快取大小上限（MB）。 此大小會套用到記憶體中的快取。 當達到限制時，記錄檔案將會滾過。 新增新記錄時（清單的底部），一或多個最舊的記錄（清單的頂端）將會被刪除，以留出空間。 當您第一次發生此情況時，會在用戶端記錄和事件日誌中記錄一個警告，直到在傳輸成功清除快取且記錄再次填滿之後，才會再次記錄。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DataBlockSize</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 65536</p></td>
<td align="left"><p>此值指定在發佈重新整理時，傳送到伺服器的最大大小（以位元組為單位），以避免在記錄達到巨大大小時永久傳輸失敗。 預設值為65536。 將報表資料傳送到伺服器時，應用程式記錄的一個區塊（小於或等於 XML 資料的組塊大小）會從快取中移除並傳送到伺服器。 每個區塊都將會有一般用戶端資料和全域套件清單資料，且這些資料不會影響區塊大小計算。極大的封裝清單可能存在，導致無法透過低頻寬或不可靠的連線傳送失敗。</p></td>
</tr>
</tbody>
</table>



## 相關主題


[Application Virtualization Client 參考資料](application-virtualization-client-reference.md)









