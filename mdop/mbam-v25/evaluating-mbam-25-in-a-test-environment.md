---
title: 在測試環境中評估 MBAM 2.5
description: 在測試環境中評估 MBAM 2.5
author: dansimp
ms.assetid: 72959b7a-e55f-4797-91b3-5be23c8c2844
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d7ba8a62f5ddecf85fe56e04fc16a6bae374ba9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809783"
---
# 在測試環境中評估 MBAM 2.5


本主題描述如何在獨立或 System Center Configuration Manager 整合拓撲中設定測試環境來評估 Microsoft BitLocker 管理和監控（MBAM）2.5。

## 使用獨立拓朴評估 MBAM 2。5


若要使用獨立拓朴評估 MBAM，請使用下清單格中的資訊來安裝 MBAM 伺服器軟體，然後在測試環境中設定 MBAM 伺服器功能。

**使用獨立拓朴評估 MBAM 2。5**

1. 在安裝 MBAM 前，請執行下列動作：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">工作</th>
   <th align="left">取得指示的位置</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>確定您已安裝所有必備軟體。</p></td>
   <td align="left"><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>檢查所需的硬體、RAM 及其他規格。</p></td>
   <td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 支援的組態</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>如果您打算使用 Cmdlet 來設定 MBAM，請查看使用 Windows PowerShell 的先決條件。</p></td>
   <td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能</a></p></td>
   </tr>
   </tbody>
   </table>



2. 安裝 MBAM Server 軟體，然後設定您想要的功能。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">工作</th>
   <th align="left">取得指示的位置</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>在您想要設定 MBAM 伺服器功能的每個伺服器上安裝 MBAM Server 軟體。</p></td>
   <td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">安裝 MBAM 2.5 伺服器軟體</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>設定合規性和審核資料庫及恢復資料庫。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)">如何設定 MBAM 2.5 資料庫</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>設定 [報告] 功能。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)">如何設定 MBAM 2.5 報告</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>設定 web 應用程式。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)">如何設定 MBAM 2.5 Web 應用程式</a></p></td>
   </tr>
   </tbody>
   </table>



3. 在用戶端電腦上，執行下列動作：

   1.  在用戶端電腦上安裝 MBAM 用戶端。

   2.  將 MBAM 群組原則物件（Gpo）套用到電腦。

   3.  設定下列登錄機碼，強制 MBAM 用戶端更快速地喚醒，且定期進行：

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement
       "ClientWakeupFrequency"=dword:00000001
       "StatusReportingFrequency"=dword:00000001
       ```

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM]
       "NoStartupDelay"=dword:00000001
       ```

       **注意**  
       由於這些金鑰會在每分鐘喚醒 MBAM 用戶端，因此我們建議您只在測試環境中使用這些登錄金鑰設定。



   4.  重新開機**BitLocker 管理用戶端服務**。

## 使用 System Center 2012 Configuration Manager 整合拓朴來評估 MBAM 2。5


若要使用 Configuration Manager 整合拓撲來評估 MBAM，請使用下清單格中的資訊來安裝 MBAM 伺服器軟體，然後在測試環境中設定 MBAM 伺服器功能。 在用戶端電腦上安裝 MBAM 用戶端之後，您將會完成其他步驟，強制 MBAM 用戶端更快速地向 MBAM 報告電腦的狀態。

**使用系統中心 2012 Configuration Manager 整合拓撲來評估 MBAM 2。5**

1. 在安裝 MBAM 之前，請先查看必備軟體和支援的設定。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">工作</th>
   <th align="left">取得指示的位置</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>確定您已安裝所有必備軟體。</p></td>
   <td align="left"><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</a></p>
   <p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)">僅適用於 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>檢查所需的硬體、RAM 及其他規格。</p></td>
   <td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 支援的組態</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>如果您打算使用 Cmdlet 來設定 MBAM，請查看使用 Windows PowerShell 的先決條件。</p></td>
   <td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>建立或編輯 mof 檔案。</p></td>
   <td align="left"><p><a href="edit-the-configurationmof-file-mbam-25.md" data-raw-source="[Edit the Configuration.mof File](edit-the-configurationmof-file-mbam-25.md)">編輯 Configuration.mof 檔案</a></p>
   <p><a href="create-or-edit-the-sms-defmof-file-mbam-25.md" data-raw-source="[Create or Edit the Sms_def.mof File](create-or-edit-the-sms-defmof-file-mbam-25.md)">建立或編輯 Sms_def.mof 檔案</a></p></td>
   </tr>
   </tbody>
   </table>



2. 安裝 MBAM Server 軟體，然後設定您想要的功能。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">工作</th>
   <th align="left">取得指示的位置</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>在您想要設定 MBAM 伺服器功能的每個伺服器上安裝 MBAM Server 軟體。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>您可以使用 Windows PowerShell 或匯出的資料層應用程式（DAC）套件，將資料庫安裝至遠端 SQL Server 電腦。 如需有關 DAC 套件的詳細資訊，請參閱 <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)"> 資料層應用程式 </a> 。</p>
   </div>
   <div>

   </div></td>
   <td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">安裝 MBAM 2.5 伺服器軟體</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>設定合規性和審核資料庫及恢復資料庫。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)">如何設定 MBAM 2.5 資料庫</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>設定 [報告] 功能。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)">如何設定 MBAM 2.5 報告</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>設定 web 應用程式。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)">如何設定 MBAM 2.5 Web 應用程式</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>設定系統中心 Configuration Manager 來安裝 Configuration Manager 物件。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md" data-raw-source="[How to Configure the MBAM 2.5 System Center Configuration Manager Integration](how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md)">如何設定 MBAM 2.5 System Center Configuration Manager 整合</a></p></td>
   </tr>
   </tbody>
   </table>



3. 在用戶端電腦上，執行下列動作：

   1.  在用戶端電腦上安裝 MBAM 用戶端和 Configuration Manager 用戶端。

   2.  將 MBAM 群組原則物件套用到電腦。

   3.  設定下列登錄機碼，強制 MBAM 用戶端更快速地喚醒，且定期進行：

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement
       "ClientWakeupFrequency"=dword:00000001
       "StatusReportingFrequency"=dword:00000001
       ```

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM]
       "NoStartupDelay"=dword:00000001
       ```

       **注意**  
       由於這些金鑰會在每分鐘喚醒 MBAM 用戶端，因此我們建議您只在測試環境中使用這些登錄金鑰設定。



   4.  重新開機**BitLocker 管理用戶端服務**。

   5.  在 [控制台] 中，開啟 [ **Configuration Manager**]，然後按一下 [**動作**] 索引標籤。

   6.  選取 [**硬體清查週期**]，然後按一下 [**立即執行**]。 這個步驟會使用您匯入到 mof 檔案中的新類別來執行硬體清查，然後將資料傳送到 Configuration Manager 伺服器。

   7.  選取 [**機器原則檢索] & 評估週期**]，然後按一下 [**立即執行**] 來套用與該用戶端電腦相關的群組原則物件。



4. 在 Configuration Manager 主控台中，執行下列動作：

   1.  在 [功能窗格] 中，以滑鼠右鍵按一下 [ **MBAM 支援的電腦**]，按一下 [**更新成員資格**]，然後按一下 **[是]** 強迫用戶端電腦立即報告其成員資格。

   2.  在 [功能窗格] 中，按一下 [ **MBAM 支援的電腦**]，確認該用戶端電腦出現在集合中。

5. 在用戶端電腦上，按一下 [控制台] 中的 [再次開啟**Configuration Manager** ]，然後執行下列動作：

   1.  按一下 [**動作**] 索引標籤，然後重新執行**電腦原則檢索 & 評估週期**。

   2.  按一下 [**設定**] 索引標籤，選取 [BitLocker 比較基準]，然後按一下 [**評估**]。

6. 在 Configuration Manager 主控台中，確認用戶端電腦出現在企業合規性報告上：如下所示：

   1.  在 [功能窗格] 中，選取 [**監視**] 工作區。

   2.  在主控台樹中，展開 **[一覽** &gt; **報告** &gt; **報告]** &gt; **MBAM**。

   3.  選取代表您要在其中查看報表之語言的資料夾，然後在 [結果] 窗格中選取報表。

## 使用 System Center Configuration Manager 2007 整合拓朴來評估 MBAM 2。5


若要使用 Configuration Manager 整合拓撲來評估 MBAM，請遵循相同的步驟，在您的測試環境中安裝和設定 MBAM，就像在生產環境中使用一樣。 在用戶端電腦上安裝 MBAM 用戶端之後，請完成本主題中的其他步驟，以讓 MBAM 用戶端開始將電腦的狀態報表到 MBAM 的速度。

**使用 Configuration Manager 2007 整合拓撲來評估 MBAM**

1. 在安裝 MBAM 之前，請執行下列動作：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">工作</th>
   <th align="left">取得指示的位置</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>確定您已安裝所有必備軟體。</p></td>
   <td align="left"><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</a></p>
   <p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)">僅適用於 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>檢查所需的硬體、RAM 及其他規格。</p></td>
   <td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 支援的組態</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>建立或編輯 mof 檔案。</p></td>
   <td align="left"><p><a href="edit-the-configurationmof-file-mbam-25.md" data-raw-source="[Edit the Configuration.mof File](edit-the-configurationmof-file-mbam-25.md)">編輯 Configuration.mof 檔案</a></p>
   <p><a href="create-or-edit-the-sms-defmof-file-mbam-25.md" data-raw-source="[Create or Edit the Sms_def.mof File](create-or-edit-the-sms-defmof-file-mbam-25.md)">建立或編輯 Sms_def.mof 檔案</a></p></td>
   </tr>
   </tbody>
   </table>



2. 安裝 MBAM Server 軟體，然後設定您想要的功能。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">工作</th>
   <th align="left">取得指示的位置</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>在您想要設定 MBAM 伺服器功能的每個伺服器上安裝 MBAM Server 軟體。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>您可以使用 Windows PowerShell 或匯出的資料層應用程式（DAC）套件，將資料庫安裝至遠端 SQL Server 電腦。 如需有關 DAC 套件的詳細資訊，請參閱 <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)"> 資料層應用程式 </a> 。</p>
   </div>
   <div>

   </div></td>
   <td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">安裝 MBAM 2.5 伺服器軟體</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>設定合規性和審核資料庫及恢復資料庫。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)">如何設定 MBAM 2.5 資料庫</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>設定 [報告] 功能。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)">如何設定 MBAM 2.5 報告</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>設定 web 應用程式。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)">如何設定 MBAM 2.5 Web 應用程式</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>設定系統中心 Configuration Manager 來安裝 Configuration Manager 物件。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md" data-raw-source="[How to Configure the MBAM 2.5 System Center Configuration Manager Integration](how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md)">如何設定 MBAM 2.5 System Center Configuration Manager 整合</a></p></td>
   </tr>
   </tbody>
   </table>



3. 在用戶端電腦上，執行下列動作：

   1.  在用戶端電腦上安裝 MBAM 用戶端。

   2.  將 MBAM 群組原則物件套用到電腦。

   3.  設定下列登錄機碼，強制 MBAM 用戶端更快速地醒來，並以更快的間隔進行：

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement
       "ClientWakeupFrequency"=dword:00000001
       "StatusReportingFrequency"=dword:00000001
       ```

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM]
       "NoStartupDelay"=dword:00000001
       ```

       **注意**  
       由於這些金鑰會在每分鐘喚醒 MBAM 用戶端，因此我們建議您只在評估環境中使用這些登錄金鑰設定。



   4.  重新開機**BitLocker 管理用戶端服務**。

   5.  在 [控制台] 中，開啟 [ **Configuration Manager**]，然後按一下 [**動作**] 索引標籤。

   6.  選取 [**機器原則檢索] & 評估週期**]，然後按一下 [**立即執行**] 來套用與該用戶端電腦相關的群組原則物件。

   7.  選取 [**硬體清查週期**]，然後按一下 [**立即執行**]。 這個步驟會使用您匯入到 mof 檔案中的新類別來執行硬體清查，然後將資料傳送到 Configuration Manager 伺服器。

4. 在 Configuration Manager 主控台中，執行下列動作：

   1.  在 [功能窗格] 中，以滑鼠右鍵按一下 [ **MBAM 支援的電腦**]，按一下 [**更新成員資格**]，然後按一下 **[是]** 強迫用戶端電腦立即報告其成員資格。

   2.  在 [功能窗格] 中，按一下 [ **MBAM 支援的電腦**]，確認該用戶端電腦出現在集合中。

5. 在用戶端電腦上，按一下 [控制台] 中的 [再次開啟**Configuration Manager** ]，然後執行下列動作：

   1.  按一下 [**動作**] 索引標籤，然後重新執行**電腦原則檢索 & 評估週期**。

   2.  按一下 [**設定**] 索引標籤，選取 [BitLocker 比較基準]，然後按一下 [**評估**]。

6. 在 Configuration Manager 主控台中，確認用戶端電腦出現在企業合規性報告上，如下所示

   1.  在 [功能窗格] 中，展開 [**電腦管理** &gt; **報告** &gt; **服務** &gt; ** &lt; 伺服器名稱 &gt; MBAM**]。

   2.  在**MBAM**節點中，選取代表您要在其中查看報表之語言的資料夾，然後從 [結果] 窗格中選取報表。


## 相關主題


[開始使用 MBAM 2.5](getting-started-with-mbam-25.md)


## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。





