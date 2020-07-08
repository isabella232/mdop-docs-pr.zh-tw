---
title: MBAM 2.0 SP1 版本資訊
description: MBAM 2.0 SP1 版本資訊
author: dansimp
ms.assetid: b39002ba-33c6-45ec-9d1b-464327b60f5c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 54a77fc7a493b36217ae2cdc875226b25fdc6e7b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811241"
---
# MBAM 2.0 SP1 版本資訊


若要搜尋這些版本筆記，請按 Ctrl + F。

安裝 Microsoft BitLocker 管理與監控（MBAM） 2.0 Service Pack 1 （SP1）之前，請先閱讀這些版本資訊。 這些版本資訊包含成功安裝 BitLocker 管理和監控 2.0 SP1 所需的資訊，且包含產品檔中不提供的資訊。 如果這些版本資訊與其他 MBAM 2.0 SP1 檔有差異，最新的變更應該視為權威性。 這些版本資訊取代本產品隨附的內容。

## <a href="" id="---------mbam-2-0-sp1-known-issues"></a> MBAM 2.0 SP1 已知問題


本節包含 MBAM 2.0 SP1 的已知問題。

### 將 Configuration Manager 整合拓朴的 MBAM 升級至 MBAM 2.0 SP1 需要手動移除 Configuration Manager 物件

如果您是使用 MBAM 與 Configuration Manager，且想要升級至 MBAM 2.0 SP1，您必須手動移除已安裝到 Configuration Manager 的所有 Configuration Manager 物件，作為 MBAM 安裝的一部分。 您必須手動移除的物件是 [MBAM] 報告、MBAM 支援的電腦集合，以及 BitLocker 保護設定基準及其相關的設定項目。

因應**措施：完成**下列步驟以升級 Configuration Manager 物件：

1.  將現有的合規性資料備份到外部檔案，如下列步驟所述。

    **記事** 當您在 Configuration Manager 中刪除現有的比較基準時，將會刪除所有現有的 BitLocker 相容性資料。 資料會隨著時間重新產生，但建議您儲存一份資料複本，以防在您需要特定電腦的合規性資料之後，才能重新產生合規性資料。

     

    1.  若要儲存已記錄的 BitLocker 合規性資料，請開啟**Bitlocker 企業合規性詳細**資料包告。

    2.  按一下報表中的 [**儲存**] 圖示，然後選取 [ **Excel**]。

        儲存的報告將會包含以下資料，例如電腦名稱稱、功能變數名稱、合規性狀態、豁免、裝置使用者、合規性狀態詳細資料，以及最後一個連絡人的日期/時間。 某些資訊（例如詳細的大量資訊和加密強度）不會儲存。

2.  使用**MBAM**安裝程式從伺服器卸載**MBAM** 。

3.  從 Configuration Manager 手動刪除下列物件：

    -   MBAM 支援的電腦集合

    -   BitLocker 保護比較基準

    -   BitLocker 作業系統磁片磁碟機保護設定專案

    -   BitLocker 固定資料磁碟機保護設定專案

4.  手動刪除 Configuration Manager SQL Server Reporting Services 網站中的 [MBAM 報表] 資料夾。 做法如下：

    1.  使用 Internet Explorer 流覽至 reporting services 點，例如，HTTP:// &lt; yourcmserver &gt; /reports。

    2.  按一下適當的 Configuration Manager [網站程式碼] 連結。

    3.  刪除 [MBAM] 資料夾。

5.  使用 MBAM 伺服器安裝程式重新安裝 Configuration Manager 整合物件。 用戶端電腦將會在一段時間後再次開始上傳 BitLocker 合規性資料。

### 自助版入口網站上的 [Submit] （提交）按鈕無法在網際網路 Explorer10 中運作

當您使用網際網路 Explorer10 存取管理和監控網站時，網站上的 [Submit] （**提交**）按鈕無法運作。

因應**措施：在**您安裝 [管理及監視] 網站的伺服器上，安裝[ASP.NET 瀏覽器定義檔案的修復程式](https://go.microsoft.com/fwlink/?LinkId=317798)。

### 不支援國際功能變數名稱

MBAM 2.0 SP1 不支援國際功能變數名稱。

因應**措施：無**。

### 如果未在 SSRS 中設定 SSL，系統管理和監控網站中的報告會顯示警告

如果 SQLServer Reporting Services （SSRS）未設定為使用安全通訊端層（SSL），那麼當您安裝 MBAM 伺服器時，會將報表的 URL 設定為 HTTP，而不是 HTTPS。 如果您接著流覽至 [管理及監視] 網站並選取報告，則會顯示下列訊息：「只會顯示安全內容」。

因應**措施：若**要修正此問題，請在安裝了 SQLServer reporting SERVICES 的 MBAM 伺服器上，設定**Reporting Services 組態管理員**中的 SSL。 卸載並重新安裝 [管理及監視伺服器] 網站。

### 按一下 [合規性摘要] 報告中的 [返回] 可能會產生錯誤

如果您向下切入至 [達標摘要] 報告，然後按一下 SSRS 報表中的 [**返回**] 連結，可能會發生錯誤。

因應**措施：無**。

### 只有使用中的空間加密無法正常運作

如果您在安裝 MBAM 用戶端後第一次將電腦加密，且已將群組原則物件設定為只執行加密，請 MBAM 錯誤地加密整個磁片，而不是只加密磁片的已使用空間。 如果電腦已在安裝 MBAM 用戶端之前使用 [僅限已使用空間] 加密，且您已將相同的已使用空間設定為「加密」群組原則物件，則 MBAM 會辨識該設定，並在合規性報告中正確報告加密。

因應**措施：無**。

### 密碼強度在電腦合規性報告中無法正確顯示

如果您沒有在 [**選擇磁片磁碟機加密方法] 和 [密碼強度**] 群群組原則物件中設定特定的密碼強度，即使密碼強度使用預設的128位加密，Configuration Manager 整合拓撲中的電腦合規性報告也會不**會顯示密碼**強度。 如果您在群組原則物件中設定特定的密碼強度，報告會顯示正確的密碼強度。

因應**措施：在**[**選擇磁片磁碟機加密方法及密碼強度**] 群群組原則物件中，永遠都要設定特定的密碼強度。

### 依磁片磁碟機類型進行合規性狀態發佈會在您更新設定專案後顯示舊資料

更新 SystemCenter2012 ConfigurationManager 中的 MBAM 設定專案之後，由 BitLocker Enterprise 合規性儀表板上的 [磁碟機類型] 橫條圖顯示的 [遵從性狀態發佈] 會顯示以舊版本的設定項目資訊為基礎的資料。

因應**措施：無**。 不支援修改 MBAM 設定專案，而且報告可能不會如預期所示。

### [增強的安全性設定] 可能會導致報告無法正確顯示

如果開啟 Internet Explorer 增強的安全性設定（ESC），當您嘗試在 MBAM 伺服器上查看報告時，可能會出現「**拒絕存取**」訊息。 根據預設，增強的安全性設定是通過將伺服器暴露在網頁內容和應用程式腳本中可能會發生的可能攻擊，來保護伺服器。

因應**措施：如果**在您嘗試在 MBAM 伺服器上查看報告時出現 [**拒絕存取**] 訊息，您可以在影像中設定群組原則物件或手動變更預設值，以停用增強的安全性設定。 您也可以在未啟用增強安全性設定的另一部電腦上，視需要查看報告。

### <a href="" id="-------------mbam-server-installation-fails-when-you-upgrade-from-sql-server-2008-to-sql-server-2012"></a> 從 SQLServer2008 升級至 SQLServer2012 時，MBAM 伺服器安裝失敗

如果您從 SQLServer2008 升級到 SQLServer2012，然後嘗試安裝合規性和審核資料庫或復原資料庫，安裝就會失敗並回滾。 發生失敗的原因是，在 SQLServer 升級期間已移除所需的 SQLCMD.exe 檔案，且 MBAM 安裝程式無法找到該檔案。 MSI 記錄檔行可能看起來類似下列：

RunDbInstallScript 復原資料庫 CA： BinDir-E:\\MSSQL\\100\\Tools\\Binn\\SqlCmd.exeRunDbInstallScript 復原資料庫 CA： dbInstance-xxxxxx\\I01RunDbInstallScript Recovery Db CA： sqlScript-C:\\program files Files\\Microsoft\\Microsoft _HardwareRunDbInstallScript _and _Recovery \ [\ Monitoring\\Setup\\KeyRecovery.sqlRunDbInstallScript db ca： dbName-MBAM \ _Recovery \ _and _HardwareRunDbInstallScript Recovery Db CA： DefaultFileName-MBAMI01\\MSSQL\\DATA\\RunDbInstallScript Recovery Db CA： defaultLogPath-K:\\MSSQL\\MSSQL10。I01\\MSSQL\\Data\\RunDbInstallScript 復原資料庫 CA： scriptLogPath-C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log-e-E-S xxxxxxx\\I01-i "C:\\program files Files\\Microsoft\\Microsoft BitLocker 管理和 Monitoring\\Setup\\KeyRecovery.sql"-v DatabaseName = "MBAM \ _Recovery \ _and \ _Hardware" DefaultFileName = "MBAM \ _Recovery \ _and \ _Hardware" DefaultDataPath = "F:\\MSSQL\\MSSQL10。I01\\MSSQL\\DATA\\ "DefaultLogPath =" K:\\MSSQL\\MSSQL10。I01\\MSSQL\\Data\\ "-o" C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log "RunDbInstallScript 復原資料庫 ca：開始執行恢復資料庫的安裝 scriptRunDbInstallScript 復原資料庫 CA： Sqlcmd 記錄檔案位於 C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\\\InstallKeyRecoveryDatabase.logRunDbInstallScript 復原 Db CA 例外狀況：安裝復原資料庫自訂操作命令列輸出例外狀況：系統找不到指定的檔案

您可以在 [HKLM\\Software\\Microsoft\\Microsoft] 下的 [登錄] 底下的 [Path 字串] 值中查看 MBAM 伺服器 Windows 安裝程式，以尋找 SQLCMD.exe 路徑。 從 SQLServer2008 到 SQLServer2012 的遷移期間，該金鑰仍然存在，但資料值所參照的路徑不會包含 SQLCMD.exe 檔案，因為 SQLupgrade 程式已移除檔案。

因應**措施：暫時**將 HKLM\\Software\\Microsoft\\Microsoft SQLServer\\100\\Tools\\ClientSetup path 字串值重新命名為**path \ _old**，然後再次在 MBAM 伺服器上執行 Windows Installer。 當安裝成功完成並在 SQLServer2012 中建立資料庫時，重新命名**路徑 \ _old**至**path**。

## MBAM 2.0 SP1 的修補程式和知識庫文章


本節包含適用于 MBAM 2.0 SP1 的修補程式和知識庫文章。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>知識庫文章</strong></th>
<th align="left">Title</th>
<th align="left"><strong>連結</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>2831166</p></td>
<td align="left"><p>安裝 Microsoft BitLocker 管理和監控（MBAM）2.0 失敗， &quot; 已安裝 System CENTER CM 物件&quot;</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2831166/EN-US" data-raw-source="[support.microsoft.com/kb/2831166/EN-US](https://support.microsoft.com/kb/2831166/EN-US)">support.microsoft.com/kb/2831166/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2870849</p></td>
<td align="left"><p>使用者無法使用 MBAM 2.0 自助服務入口網站來取得 BitLocker 復原金鑰</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870849/EN-US" data-raw-source="[support.microsoft.com/kb/2870849/EN-US](https://support.microsoft.com/kb/2870849/EN-US)">support.microsoft.com/kb/2870849/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2756402</p></td>
<td align="left"><p>事件描述中的 MBAM 用戶端將無法使用事件 ID 4 和錯誤碼0x8004100E</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2756402/EN-US" data-raw-source="[support.microsoft.com/kb/2756402/EN-US](https://support.microsoft.com/kb/2756402/EN-US)">support.microsoft.com/kb/2756402/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2620287</p></td>
<td align="left"><p>按一下 MBAM 中的 [報表] 索引標籤時，出現「/Reports ' 應用程式」的 [伺服器錯誤] 錯誤訊息</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620287/EN-US" data-raw-source="[support.microsoft.com/kb/2620287/EN-US](https://support.microsoft.com/kb/2620287/EN-US)">support.microsoft.com/kb/2620287/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2639518</p></td>
<td align="left"><p>在 MBAM 中開啟企業或電腦合規性報告時發生錯誤</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2639518/EN-US" data-raw-source="[support.microsoft.com/kb/2639518/EN-US](https://support.microsoft.com/kb/2639518/EN-US)">support.microsoft.com/kb/2639518/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2620269</p></td>
<td align="left"><p>MBAM 企業報告無法取得更新</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620269/EN-US" data-raw-source="[support.microsoft.com/kb/2620269/EN-US](https://support.microsoft.com/kb/2620269/EN-US)">support.microsoft.com/kb/2620269/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2712461</p></td>
<td align="left"><p>不支援在網網域控制站上安裝 MBAM</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2712461/EN-US" data-raw-source="[support.microsoft.com/kb/2712461/EN-US](https://support.microsoft.com/kb/2712461/EN-US)">support.microsoft.com/kb/2712461/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2876732</p></td>
<td align="left"><p>您在獨立或 Configuration Manager 集成設定 MBAM 2.0 期間收到錯誤代碼0x80071a90</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2876732/EN-US" data-raw-source="[support.microsoft.com/kb/2876732/EN-US](https://support.microsoft.com/kb/2876732/EN-US)">support.microsoft.com/kb/2876732/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2754259</p></td>
<td align="left"><p>MBAM 及安全的網路通訊</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2754259/EN-US" data-raw-source="[support.microsoft.com/kb/2754259/EN-US](https://support.microsoft.com/kb/2754259/EN-US)">support.microsoft.com/kb/2754259/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2870842</p></td>
<td align="left"><p>MBAM 2.0 安裝程式在 Configuration Manager 整合案例中使用 SQL Server 2008 失敗</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870842/EN-US" data-raw-source="[support.microsoft.com/kb/2870842/EN-US](https://support.microsoft.com/kb/2870842/EN-US)">support.microsoft.com/kb/2870842/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2668533</p></td>
<td align="left"><p>如果未正確設定 SQL SSRS，則 MBAM 安裝程式會失敗</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2668533/EN-US" data-raw-source="[support.microsoft.com/kb/2668533/EN-US](https://support.microsoft.com/kb/2668533/EN-US)">support.microsoft.com/kb/2668533/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2870847</p></td>
<td align="left"><p>MBAM 2.0 安裝失敗， &quot; 檢索 &#39;Reporting Services Point&#39; 角色的 Configuration Manager 伺服器角色設定時發生錯誤&quot;</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870847/EN-US" data-raw-source="[support.microsoft.com/kb/2870847/EN-US](https://support.microsoft.com/kb/2870847/EN-US)">support.microsoft.com/kb/2870847/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2870839</p></td>
<td align="left"><p>由於 SQL 作業 CreateCache 失敗，所以無法在 MBAM 2.0 獨立拓朴中重新整理 MBAM 2.0 企業報告</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870839/EN-US" data-raw-source="[support.microsoft.com/kb/2870839/EN-US](https://support.microsoft.com/kb/2870839/EN-US)">support.microsoft.com/kb/2870839/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2620269</p></td>
<td align="left"><p>MBAM 企業報告無法取得更新</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620269/EN-US" data-raw-source="[support.microsoft.com/kb/2620269/EN-US](https://support.microsoft.com/kb/2620269/EN-US)">support.microsoft.com/kb/2620269/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2935997</p></td>
<td align="left"><p>MBAM 支援的電腦合規性報告不正確包含不支援的產品</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2935997/EN-US" data-raw-source="[support.microsoft.com/kb/2935997/EN-US](https://support.microsoft.com/kb/2935997/EN-US)">support.microsoft.com/kb/2935997/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2612822</p></td>
<td align="left"><p>在 MBAM 中，電腦記錄遭到拒絕</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2612822/EN-US" data-raw-source="[support.microsoft.com/kb/2612822/EN-US](https://support.microsoft.com/kb/2612822/EN-US)">support.microsoft.com/kb/2612822/EN-US</a></p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[關於 MBAM 2.0 SP1](about-mbam-20-sp1.md)

 

 





