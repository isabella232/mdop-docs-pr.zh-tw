---
title: 如何部署 App-V 用戶端
description: 如何部署 App-V 用戶端
author: dansimp
ms.assetid: 981f57c9-56c3-45da-8261-0972bfad3e5b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: ea216f6b86820f752e0c0ac693470eac72cb847a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800515"
---
# 如何部署 App-V 用戶端


使用下列程式來安裝 Microsoft Application Virtualization （App-v）5.1 用戶端和遠端桌面服務用戶端。 您必須安裝與目的電腦作業系統相符的用戶端版本。

<a href="" id="bkmk-clt-install-prereqs"></a>**開始之前的做法**

1. 審查並安裝軟體先決條件：

   安裝與您要安裝的 App-v 版本相對應的必備軟體：

   -   [關於 App-V 5.1](about-app-v-51.md)

   -   [App-V 5.1 必要條件](app-v-51-prerequisites.md)

2. 查看用戶端共存與不支援的案例（適用于您的安裝）：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p>部署共存的 App-v 用戶端</p></td>
   <td align="left"><p><a href="planning-for-the-app-v-51-sequencer-and-client-deployment.md" data-raw-source="[Planning for the App-V 5.1 Sequencer and Client Deployment](planning-for-the-app-v-51-sequencer-and-client-deployment.md)">為 App-V 5.1 Sequencer 與 Client 部署進行規劃</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>不支援或有限的安裝案例</p></td>
   <td align="left"><p>請參閱 <a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)"> app-v 5.1 支援的設定中的 [用戶端] 區段</a></p></td>
   </tr>
   </tbody>
   </table>



3. 查看用戶端登錄的位置、記錄及疑難排解資訊：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>用戶端登錄資訊</p></td>
<td align="left"><ul>
<li><p>根據預設，在您安裝 App-V 5.1 用戶端之後，用戶端資訊會儲存在下列登錄機碼中：</p>
<p><strong>HKEY_LOCAL_MACHINE \ 軟體 \ MICROSOFT \ APPV \ 用戶端</strong></p></li>
<li><p>當您將虛擬化套件部署到執行 App-v 用戶端的電腦時，相關聯的套件資料會儲存在下列位置：</p>
<p><strong>C： \ ProgramData \ App-V</strong></p>
<p>不過，您可以使用下列登錄機碼來重新設定此位置：</p>
<p><strong>HKEY_LOCAL_MACHINE \ 軟體 \ MICROSOFT \ 軟體 \ MICROSOFT \ APPV \ 用戶端 \ 資料流程 \ PACKAGEINSTALLATIONROOT</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>用戶端記錄檔</p></td>
<td align="left"><ul>
<li><p>針對與 App-v 5.1 用戶端相關聯的記錄檔資訊，請在下列記錄中搜尋：</p>
<p><strong>事件記錄/應用程式和服務記錄/Microsoft/AppV</strong></p></li>
<li><p>在 App-v 5.0 SP3 中，部分記錄已整合並移到下列位置：</p>
<p><strong>事件記錄/應用程式和服務記錄/Microsoft/AppV/ServiceLog</strong></p>
<p>如需已移動之記錄的清單，請參閱 <a href="about-app-v-50-sp3.md#bkmk-event-logs-moved" data-raw-source="[About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)"> 關於 App-V 5.0 SP3 </a> 。</p></li>
<li><p>在執行 App-v 5.1 用戶端的電腦上，目前儲存在電腦上的套件會儲存到下列位置：</p>
<p><strong>C:\ProgramData\App-V &amp; lt; 封裝 id &gt; &amp; lt; 版本識別碼&gt;</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>用戶端安裝疑難排解資訊</p></td>
<td align="left"><p>請參閱 <strong> % temp% 資料夾中的錯誤記錄 </strong> 。 若要查看記錄檔，請按一下 [ <strong> 開始] </strong> ，輸入 <strong> % temp% </strong> ，然後尋找 <strong> appv_ 記錄 </strong> 。</p></td>
</tr>
</tbody>
</table>



**若要安裝應用程式-V 5.1 用戶端**

1.  將 App-v 5.1 用戶端安裝檔案複製到安裝該檔案的電腦上。 從下列用戶端類型中選擇：

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">用戶端類型</th>
    <th align="left">要使用的檔案</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>用戶端的標準版</p></td>
    <td align="left"><p><strong>appv_client_setup.exe</strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>用戶端的遠端桌面服務版本</p></td>
    <td align="left"><p><strong>appv_client_setup_rds.exe</strong></p></td>
    </tr>
    </tbody>
    </table>



2.  按兩下安裝檔，然後按一下 [**安裝**]。 安裝開始之前，安裝程式會檢查電腦是否有任何缺少[的 app-v 5.1 先決條件](app-v-51-prerequisites.md)。

3.  查看並接受軟體授權條款，選擇是否要使用 Microsoft Update，以及是否要參與 Microsoft 客戶經驗改進計畫，然後按一下 [**安裝**]。

4.  在 [**成功完成設定**] 頁面上，按一下 [**關閉**]。

    安裝會在**程式**中為 app-v 用戶端建立下列專案：

    -   **.exe**

    -   **.msi**

    -   **語言套件**

        **注意**  
        安裝之後，只能卸載 .exe 檔案。



**使用腳本安裝 App-V 5.1 用戶端**

1. 在目的電腦上安裝所有必要的必備軟體。 [開始之前，](#bkmk-clt-install-prereqs)請參閱處理方式。 如果您使用 .msi 檔案安裝用戶端，則如果缺少任何先決條件，安裝就會失敗。

2. 若要使用腳本來安裝 App-V 5.1 用戶端，請在**appv\_client\_setup.exe**使用下列參數。

   **注意**  
   用戶端 Windows 安裝程式（.msi）除了 **/log**參數以外，支援相同的一組開關。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p>/INSTALLDIR</p></td>
   <td align="left"><p>指定安裝目錄。 範例用法： <strong> /INSTALLDIR = C:\Program Files\AppV 用戶端</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/CEIPOPTIN</p></td>
   <td align="left"><p>可參與客戶經驗改進計畫。 範例用法： <strong> /CEIPOPTIN = [0 | 1]</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/MUOPTIN</p></td>
   <td align="left"><p>啟用 Microsoft Update。 範例用法： <strong> /MUOPTIN = [0 | 1]</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/PACKAGEINSTALLATIONROOT</p></td>
   <td align="left"><p>指定要安裝所有新應用程式和更新的目錄。 範例用法： <strong> /PACKAGEINSTALLATIONROOT =&#39;C:\App-V 套件&#39;</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/PACKAGESOURCEROOT</p></td>
   <td align="left"><p>覆寫下載套件內容的來源位置。 範例用法： <strong> /PACKAGESOURCEROOT =&#39;<a href="http://packageStore" data-raw-source="http://packageStore"> http://packageStore </a>&#39;</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/AUTOLOAD</p></td>
   <td align="left"><p>指定在特定電腦上由 App-v 5.1 載入新套件的方式。 已啟用下列選項： [1];自動載入所有套件 [2];或自動載入無套件 [0]。 <strong>範例用法：/AUTOLOAD = [0 | 1 | 2]</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/SHAREDCONTENTSTOREMODE</p></td>
   <td align="left"><p>指定不會將流式套件內容儲存到本機硬碟。 範例用法： <strong> /SHAREDCONTENTSTOREMODE = [0 | 1]</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/MIGRATIONMODE</p></td>
   <td align="left"><p>允許 App-v 5.1 用戶端修改與使用舊版建立之套件相關聯的快捷方式與 FTAs。 範例用法： <strong> /MIGRATIONMODE = [0 | 1]</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/ENABLEPACKAGESCRIPTS</p></td>
   <td align="left"><p>啟用要執行的套件資訊清單檔案或設定檔中定義的腳本。 範例用法： <strong> /ENABLEPACKAGESCRIPTS = [0 | 1]</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/ROAMINGREGISTRYEXCLUSIONS</p></td>
   <td align="left"><p>指定不會與使用者設定檔一起漫遊的登錄路徑。 範例用法： <strong> /ROAMINGREGISTRYEXCLUSIONS = software\classes; software\clients</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/ROAMINGFILEEXCLUSIONS</p></td>
   <td align="left"><p>指定相對於% userprofile% （不會與使用者&#39;s 設定檔漫遊）的檔路徑。 範例用法： <strong> /ROAMINGFILEEXCLUSIONS &#39;桌面; 我的圖片&#39;</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/S [1-5] PUBLISHINGSERVERNAME</p></td>
   <td align="left"><p>顯示發佈伺服器的名稱。 範例用法： <strong> /S2PUBLISHINGSERVERNAME = MyPublishingServer</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/S [1-5] PUBLISHINGSERVERURL</p></td>
   <td align="left"><p>顯示發佈伺服器的 URL。 範例用法： <strong> /S2PUBLISHINGSERVERURL = \pubserver</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/S [1-5] GLOBALREFRESHENABLED-</p></td>
   <td align="left"><p>啟用全域發佈重新整理。 範例用法： <strong> /S2GLOBALREFRESHENABLED = [0 | 1]</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/S [1-5] GLOBALREFRESHONLOGON</p></td>
   <td align="left"><p>在使用者登入時，啟動全域發佈重新整理。 範例用法： <strong> /S2LOGONREFRESH = [0 | 1]</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/S [1-5] GLOBALREFRESHINTERVAL-</p></td>
   <td align="left"><p>指定發佈重新整理間隔，其中 <strong> 0 </strong> 代表不定期重新整理。 範例用法： <strong> /S2PERIODICREFRESHINTERVAL = [0-744]</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/S [1-5] GLOBALREFRESHINTERVALUNIT</p></td>
   <td align="left"><p>指定間隔單位（小時 [0]，天 [1]）。 範例用法： <strong> /S2GLOBALREFRESHINTERVALUNIT = [0 | 1]</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/S [1-5] USERREFRESHENABLED</p></td>
   <td align="left"><p>啟用使用者發佈重新整理。 範例用法： <strong> /S2USERREFRESHENABLED = [0 | 1]</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/S [1-5] USERREFRESHONLOGON</p></td>
   <td align="left"><p>在使用者登入時，啟動使用者發佈重新整理。 範例用法： <strong> /S2LOGONREFRESH = [0 | 1]</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/S [1-5] USERREFRESHINTERVAL-</p></td>
   <td align="left"><p>指定發佈重新整理間隔，其中 <strong> 0 </strong> 代表不定期重新整理。 範例用法： <strong> /S2PERIODICREFRESHINTERVAL = [0-744]</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/S [1-5] USERREFRESHINTERVALUNIT</p></td>
   <td align="left"><p>指定間隔單位（小時 [0]，天 [1]）。 範例用法： <strong> /S2USERREFRESHINTERVALUNIT = [0 | 1]</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/Log</p></td>
   <td align="left"><p>指定儲存記錄資訊的位置。 預設位置是% Temp%。 範例用法： <strong> /Log C:\logs\log.log</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/q</p></td>
   <td align="left"><p>指定無人參與的安裝。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/REPAIR</p></td>
   <td align="left"><p>修復先前的用戶端安裝。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/NORESTART</p></td>
   <td align="left"><p>防止電腦在用戶端安裝之後重新開機。</p>
   <p>在安裝每個更新之後，此參數會防止使用者電腦重新開機，並可讓您在方便時排程重新開機。 例如，您可以安裝 App-v 5.1，然後安裝修複程式套件 Y，而不在 Service Pack 安裝之後重新開機。 安裝之後，您必須先重新開機，才能開始使用 app-v。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/UNINSTALL</p></td>
   <td align="left"><p>卸載用戶端。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/ACCEPTEULA</p></td>
   <td align="left"><p>接受授權合約。 這對於無操作安裝是必要的。 範例用法： <strong> /ACCEPTEULA </strong> 或 <strong> /ACCEPTEULA = 1 </strong> 。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/LAYOUT</p></td>
   <td align="left"><p>指定相關聯的版面配置動作。 它也會將 Windows Installer （.msi）及腳本檔案解壓縮至資料夾，但不安裝 App-v 5.1。 不需要任何值。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/LAYOUTDIR</p></td>
   <td align="left"><p>指定版面配置目錄。 需要字串值。 範例用法： <strong> /LAYOUTDIR = "C:\Application Virtualization 用戶端" </strong> 。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/？、/h、/help</p></td>
   <td align="left"><p>要求上一個安裝參數的相關協助。</p></td>
   </tr>
   </tbody>
   </table>



**使用 Windows Installer （.msi）檔案安裝 App-v 5.1 用戶端**

1.  在目的電腦上安裝必要的先決條件。 [開始之前，](#bkmk-clt-install-prereqs)請參閱處理方式。 如果未滿足任何先決條件，安裝將會失敗。

2.  在使用 App-v 5.1 Windows 安裝程式（.msi）檔案安裝用戶端之前，請確定目的電腦沒有任何掛起的重新開機。 Windows Installer 檔案不會標示掛起的重新開機。

3.  將下列其中一個 Windows 安裝程式檔案部署到目的電腦。 您指定的檔案必須符合目的電腦的設定。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">部署類型</th>
    <th align="left">部署此檔案</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>電腦正在執行32位 Microsoft Windows 作業系統</p></td>
    <td align="left"><p>appv_client_MSI_x86.msi</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>電腦正在執行64位 Microsoft Windows 作業系統</p></td>
    <td align="left"><p>appv_client_MSI_x64.msi</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>您要部署 App-v 5.1 遠端桌面服務用戶端</p></td>
    <td align="left"><p>appv_client_rds_MSI_x64.msi</p></td>
    </tr>
    </tbody>
    </table>



4.  使用下表中的資訊，根據目的電腦所需的語言選取適當的語言套件（msi）來安裝 **。** 資料表中的**xxxx**參照語言套件的目的地區域設定。

    **開始之前的須知：**

    -   標準 App-V 5.1 用戶端和 App-V 5.1 用戶端的遠端桌面服務版本都有語言套件。

    -   如果您使用 **.exe**安裝 app-v 5.1 用戶端，安裝程式將只部署與目的電腦上執行之作業系統相符的語言套件。

    -   若要在目的電腦上部署其他語言套件，請使用**Windows 安裝程式（.msi）檔案，使用安裝 app-v 5.1 用戶端的程式**。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">部署類型</th>
    <th align="left">部署此檔案</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>電腦正在執行32位 Microsoft Windows 作業系統</p></td>
    <td align="left"><p>appv_client_LP_xxxx_ x86.msi</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>電腦正在執行64位 Microsoft Windows 作業系統</p></td>
    <td align="left"><p>appv_client_LP_xxxx_ x64.msi</p></td>
    </tr>
    </tbody>
    </table>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 相關主題


[部署 App-V 5.1](deploying-app-v-51.md)

[關於 Client 組態設定](about-client-configuration-settings51.md)

[如何解除安裝 App-V 5.1 Client](how-to-uninstall-the-app-v-51-client.md)









