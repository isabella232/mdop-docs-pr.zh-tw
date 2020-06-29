---
title: 如何部署 App-V 用戶端
description: 如何部署 App-V 用戶端
ms.author: dansimp
author: dansimp
ms.assetid: 9c4e67ae-ddaf-4e23-8c16-72d029a74a27
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/05/2018
ms.openlocfilehash: 4e246e13bf59f167eade77200afd866c6a3c41fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800514"
---
# 如何部署 App-V 用戶端


使用下列程式來安裝 Microsoft Application Virtualization （App-v）5.0 用戶端和遠端桌面服務用戶端。 您必須安裝與目的電腦作業系統相符的用戶端版本。

<a href="" id="bkmk-clt-install-prereqs"></a>**開始之前的做法**

1. 審查並安裝軟體先決條件：

   安裝與您要安裝的 App-v 版本相對應的必備軟體：

   - [關於 App-V 5.0 SP3](about-app-v-50-sp3.md)

   - App-v 5.0 SP1 和 App-v 5.0 SP2-這些版本中都沒有新的先決條件

   - [App-V 5.0 必要條件](app-v-50-prerequisites.md)

2. 查看用戶端共存與不支援的案例（適用于您的安裝）：


   |                                               |                                                                                                                            |
   |-----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
   |      部署共存的 App-v 用戶端       | [為 App-V 5.0 Sequencer 與 Client 部署進行規劃](planning-for-the-app-v-50-sequencer-and-client-deployment.md) |
   | 不支援或有限的安裝案例 |                         [App-V 5.0 支援的組態](app-v-50-supported-configurations.md)                         |

   ---

3. 查看用戶端登錄的位置、記錄及疑難排解資訊：

#### 用戶端登錄資訊
<ul><li>根據預設，在您安裝 App-V 5.0 用戶端之後，用戶端資訊會儲存在下列登錄機碼中：<p><p><code>HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\APPV\CLIENT</code></li><li>當您將虛擬化套件部署到執行 App-v 用戶端的電腦時，相關聯的套件資料會儲存在下列位置：<p><p><code>C:\ProgramData\App-V</code><p><p>不過，您可以使用下列登錄機碼來重新設定此位置：<p><p><code>HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\SOFTWARE\MICROSOFT\APPV\CLIENT\STREAMING\PACKAGEINSTALLATIONROOT</code></li></ul>

#### 用戶端記錄檔                  
<ul><li>針對與 App-v 5.0 用戶端相關聯的記錄檔資訊，請在下列記錄中搜尋：<p><p><code>Event logs/Applications and Services Logs/Microsoft/AppV</code></li><li>在 App-v 5.0 SP3 中，部分記錄已整合並移到下列位置：<p><p><code>Event logs/Applications and Services Logs/Microsoft/AppV/ServiceLog</code><p><p>如需已移動之記錄的清單，請參閱[關於 App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)。</li><li>在執行 App-v 5.0 用戶端的電腦上，目前儲存在電腦上的套件會儲存到下列位置：<p><p><code>C:\ProgramData\App-V\<<em>package id</em>>\<<em>version id</em>></code></li></ul>

#### 用戶端安裝疑難排解資訊
- 請參閱 **% temp%** 資料夾中的錯誤記錄。 
- 若要查看記錄檔，請按一下 [**開始**]，輸入 **% temp%**，然後尋找**appv_ 記錄**。 

## 若要安裝應用程式-V 5.0 用戶端

1. 將 App-v 5.0 用戶端安裝檔案複製到安裝該檔案的電腦上。<p><p>從下列用戶端類型中選擇：


   |                  用戶端類型                  |          要使用的檔案          |
   |-----------------------------------------------|-------------------------------|
   |        用戶端的標準版         |   **appv_client_setup.exe**   |
   | 用戶端的遠端桌面服務版本 | **appv_client_setup_rds.exe** |

   ---

2. 按兩下安裝檔，然後按一下 [**安裝**]。 安裝開始之前，安裝程式會檢查電腦是否有任何缺少[的 app-v 5.0 先決條件](app-v-50-prerequisites.md)。

3. 查看並接受軟體授權條款，選擇是否要使用 Microsoft Update，以及是否要參與 Microsoft 客戶經驗改進計畫，然後按一下 [**安裝**]。

4. 在 [**成功完成設定**] 頁面上，按一下 [**關閉**]。

   安裝會在**程式**中為 app-v 用戶端建立下列專案：

   -   **.exe**

   -   **.msi**

   -   **語言套件**

   >[!NOTE]
   >安裝之後，只能卸載 .exe 檔案。


## 使用腳本安裝 App-V 5.0 用戶端

1. 在目的電腦上安裝所有必要的必備軟體。 [開始之前，](#bkmk-clt-install-prereqs)請參閱處理方式。 如果您使用 .msi 檔案安裝用戶端，則如果缺少任何先決條件，安裝就會失敗。

2. 若要使用腳本來安裝 App-V 5.0 用戶端，請在**appv\_client\_setup.exe**使用下列參數。

   >[!NOTE]
   >用戶端 Windows 安裝程式（.msi）除了 **/log**參數以外，支援相同的一組開關。

   |                                  |                                                                                                                                                                                                                                                                                                                                                                                                                                     |
   |----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |           /INSTALLDIR            |                                                                                                                                                               指定安裝目錄。 範例用法：<p><p>**/INSTALLDIR = C:\Program Files\AppV 用戶端**                                                                                                                                                                |
   |            /CEIPOPTIN            |                                                                                                                                                          可參與客戶經驗改進計畫。 範例用法：<p><p>**/CEIPOPTIN = [0 \ | 1 \]**                                                                                                                                                           |
   |             /MUOPTIN             |                                                                                                                                                                                 啟用 Microsoft Update。 範例用法：<p><p>**/MUOPTIN = [0 \ | 1 \]**                                                                                                                                                                                  |
   |     /PACKAGEINSTALLATIONROOT     |                                                                                                                                         指定要安裝所有新應用程式和更新的目錄。 範例用法： <p><p>**/PACKAGEINSTALLATIONROOT = "C:\App-V 套件"**                                                                                                                                         |
   |        /PACKAGESOURCEROOT        |                                                                                                                                                  覆寫下載套件內容的來源位置。 範例用法：<p><p>**/PACKAGESOURCEROOT = " <http://packageStore> "**                                                                                                                                                  |
   |            /AUTOLOAD             |                                                                                           指定在特定電腦上由 App-v 5.0 載入新套件的方式。 已啟用下列選項： [1];自動載入所有套件 [2];或自動載入無套件 [0]。 範例用法：<p><p>**/AUTOLOAD = [0 \ | 1 \ | 2 \]**                                                                                           |
   |     /SHAREDCONTENTSTOREMODE      |                                                                                                                                           指定不會將流式套件內容儲存到本機硬碟。 範例用法： <p><p>**/SHAREDCONTENTSTOREMODE = [0 \ | 1 \]**                                                                                                                                            |
   |          /MIGRATIONMODE          |                                                                                                                     允許 App-v 5.0 用戶端修改與使用舊版建立之套件相關聯的快捷方式與 FTAs。 範例用法：<p><p>**/MIGRATIONMODE = [0 \ | 1 \]**                                                                                                                     |
   |      /ENABLEPACKAGESCRIPTS       |                                                                                                                                   啟用要執行的套件資訊清單檔案或設定檔中定義的腳本。 範例用法：<p><p>**/ENABLEPACKAGESCRIPTS = [0 \ | 1 \]**                                                                                                                                   |
   |    /ROAMINGREGISTRYEXCLUSIONS    |                                                                                                                                      指定不會與使用者設定檔一起漫遊的登錄路徑。 範例用法：<p><p>**/ROAMINGREGISTRYEXCLUSIONS = software\classes; software\clients**                                                                                                                                      |
   |      /ROAMINGFILEEXCLUSIONS      |                                                                                                                                  指定相對於% userprofile% （不會與使用者的設定檔漫遊）的檔路徑。 範例用法： <p><p>**/ROAMINGFILEEXCLUSIONS ' 桌面; 我的圖片」**                                                                                                                                   |
   |   /S [1-5] PUBLISHINGSERVERNAME    |                                                                                                                                                           顯示發佈伺服器的名稱。 範例用法：<p><p>**/S2PUBLISHINGSERVERNAME = MyPublishingServer**                                                                                                                                                            |
   |    /S [1-5] PUBLISHINGSERVERURL    |                                                                                                                                                                顯示發佈伺服器的 URL。 範例用法：<p><p>**/S2PUBLISHINGSERVERURL = \\pubserver**                                                                                                                                                                |
   |   /S [1-5] GLOBALREFRESHENABLED    |                                                                                                                                                                    啟用全域發佈重新整理。 範例用法：<p><p>**/S2GLOBALREFRESHENABLED = [0 \ | 1 \]**                                                                                                                                                                     |
   |   /S [1-5] GLOBALREFRESHONLOGON    |                                                                                                                                                             在使用者登入時，啟動全域發佈重新整理。 範例用法：<p><p>**/S2LOGONREFRESH = [0 \ | 1 \]**                                                                                                                                                              |
   |   /S [1-5] GLOBALREFRESHINTERVAL   |                                                                                                                                         指定發佈重新整理間隔，其中**0**代表不定期重新整理。 範例用法： **/S2PERIODICREFRESHINTERVAL = [0-744]**                                                                                                                                         |
   | /S [1-5] GLOBALREFRESHINTERVALUNIT |                                                                                                                                                            指定間隔單位（小時 [0]，天 [1]）。 範例用法：<p><p>**/S2GLOBALREFRESHINTERVALUNIT = [0 \ | 1 \]**                                                                                                                                                            |
   |    /S [1-5] USERREFRESHENABLED     |                                                                                                                                                                          啟用使用者發佈重新整理。 範例用法： **/S2USERREFRESHENABLED = [0 \ | 1 \]**                                                                                                                                                                          |
   |    /S [1-5] USERREFRESHONLOGON     |                                                                                                                                                              在使用者登入時，啟動使用者發佈重新整理。 範例用法：<p><p>**/S2LOGONREFRESH = [0 \ | 1 \]**                                                                                                                                                               |
   |    /S [1-5] USERREFRESHINTERVAL    |                                                                                                                                         指定發佈重新整理間隔，其中**0**代表不定期重新整理。 範例用法： **/S2PERIODICREFRESHINTERVAL = [0-744]**                                                                                                                                         |
   |  /S [1-5] USERREFRESHINTERVALUNIT  |                                                                                                                                                             指定間隔單位（小時 [0]，天 [1]）。 範例用法：<p><p>**/S2USERREFRESHINTERVALUNIT = [0 \ | 1 \]**                                                                                                                                                             |
   |               /Log               |                                                                                                                                                指定儲存記錄資訊的位置。 預設位置是% Temp%。 範例用法：<p><p>**/log C:\logs\log.log**                                                                                                                                                |
   |                /q                |                                                                                                                                                                                                指定無人參與的安裝。                                                                                                                                                                                                |
   |             /REPAIR              |                                                                                                                                                                                               修復先前的用戶端安裝。                                                                                                                                                                                               |
   |            /NORESTART            | 防止電腦在用戶端安裝之後重新開機。<p><p>在安裝每個更新之後，此參數會防止使用者電腦重新開機，並可讓您在方便時排程重新開機。 例如，您可以安裝 App-v 5.0 SPX，然後安裝修補程式套件 Y，不需要在 Service Pack 安裝之後重新開機。 安裝之後，您必須先重新開機，才能開始使用 app-v。 |
   |            /UNINSTALL            |                                                                                                                                                                                                       卸載用戶端。                                                                                                                                                                                                        |
   |           /ACCEPTEULA            |                                                                                                                                              接受授權合約。 這對於無操作安裝是必要的。 範例用法：<p><p>**/ACCEPTEULA**或 **/ACCEPTEULA = 1**                                                                                                                                               |
   |             /LAYOUT              |                                                                                                                               指定相關聯的版面配置動作。 它也會將 Windows Installer （.msi）及腳本檔案解壓縮至資料夾，但不安裝 App-v 5.0。 不需要任何值。                                                                                                                                |
   |            /LAYOUTDIR            |                                                                                                                                                 指定版面配置目錄。 需要字串值。 範例用法：<p><p>**/LAYOUTDIR = "C:\Application Virtualization 用戶端"**                                                                                                                                                  |
   |          /？、/h、/help           |                                                                                                                                                                                      要求上一個安裝參數的相關協助。                                                                                                                                                                                      |

   ---

## 使用 Windows Installer （.msi）檔案安裝 App-v 5.0 用戶端

1. 在目的電腦上安裝必要的先決條件。 [開始之前，](#bkmk-clt-install-prereqs)請參閱處理方式。 如果未滿足任何先決條件，安裝將會失敗。

2. 在使用 App-v 5.0 Windows 安裝程式（.msi）檔案安裝用戶端之前，請確定目的電腦沒有任何掛起的重新開機。 Windows Installer 檔案不會標示掛起的重新開機。

3. 將下列其中一個 Windows 安裝程式檔案部署到目的電腦。 您指定的檔案必須符合目的電腦的設定。


   |                       部署類型                        |      部署此檔案       |
   |-----------------------------------------------------------------|-----------------------------|
   | 電腦正在執行32位 Microsoft Windows 作業系統 |   appv_client_MSI_x86.msi   |
   | 電腦正在執行64位 Microsoft Windows 作業系統 |   appv_client_MSI_x64.msi   |
   | 您要部署 App-v 5.0 遠端桌面服務用戶端  | appv_client_rds_MSI_x64.msi |

   ---

4. 使用下表中的資訊，根據目的電腦所需的語言選取適當的語言套件（msi）來安裝 **。** 資料表中的**xxxx**參照語言套件的目的地區域設定。

   **開始之前的須知：** 

   -  標準 App-V 5.0 用戶端和 App-V 5.0 用戶端的遠端桌面服務版本都有語言套件。

   -  如果您使用 **.exe**安裝 app-v 5.0 用戶端，安裝程式將只部署與目的電腦上執行之作業系統相符的語言套件。

   -  若要在目的電腦上部署其他語言套件，請使用**Windows 安裝程式（.msi）檔案，使用安裝 app-v 5.0 用戶端的程式**。

   |                       部署類型                        |       部署此檔案       |
   |-----------------------------------------------------------------|------------------------------|
   | 電腦正在執行32位 Microsoft Windows 作業系統 | appv_client_LP_xxxx_ x86.msi |
   | 電腦正在執行64位 Microsoft Windows 作業系統 | appv_client_LP_xxxx_ x64.msi |

   ---

   您**有應用程式-V 的建議**嗎？ 新增或投票[建議](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)。 <p><p>**有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[部署 App-V 5.0](deploying-app-v-50.md)

[關於 Client 組態設定](about-client-configuration-settings.md)

[如何解除安裝 App-V 5.0 Client](how-to-uninstall-the-app-v-50-client.md)
