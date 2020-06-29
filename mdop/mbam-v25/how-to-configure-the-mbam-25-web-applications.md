---
title: 如何設定 MBAM 2.5 Web 應用程式
description: 如何設定 MBAM 2.5 Web 應用程式
author: dansimp
ms.assetid: 909bf2d3-028c-4ac1-9247-171532a1eeae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0336d24f51167a00c8565ccd081f4bc5dfb2c4cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810592"
---
# 如何設定 MBAM 2.5 Web 應用程式


本主題說明如何使用下列其中一種方法，將 Microsoft BitLocker 管理和監控（MBAM） 2.5 web 應用程式設定為適用于[MBAM 2.5 的最高層次架構](high-level-architecture-for-mbam-25.md)：

-   Windows PowerShell Cmdlet

-   [MBAM 伺服器設定] 嚮導

Web 應用程式包含下列網站及其對應的 web 服務：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Website</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>管理和監控網站</p></td>
<td align="left"><p>已指定使用者可以在其中查看報告並協助使用者在忘記 PIN 或密碼時復原電腦的網站</p></td>
</tr>
<tr class="even">
<td align="left"><p>自助服務入口網站</p></td>
<td align="left"><p>如果使用者忘記其 PIN 或密碼，就能獨立地重新取得其電腦存取權的網站</p></td>
</tr>
</tbody>
</table>



**開始設定前：**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">步驟</th>
<th align="left">取得指示的位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>針對 MBAM 查看建議的架構。</p></td>
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)">MBAM 2.5 的概要架構</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>查看 MBAM 支援的設定。</p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 支援的組態</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>在每個伺服器上完成必要的先決條件。</p>
<div class="alert">
<strong>注意</strong><br/><p>在設定管理和監視網站之前，請務必將 SQL ServerReporting Services （SSRS）設定為使用安全通訊端層（SSL）。 否則，報表功能將會使用 HTTP，而不是 HTTPS。</p>
</div>
<div>

</div></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)">僅適用于 Configuration Manager 整合拓朴的 MBAM 2.5 Server 必備元件 </a> （如果適用）</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>針對網站的應用程式池帳戶，註冊服務主要名稱（Spn）。 如果您在 Active Directory 網域服務（AD DS）中沒有系統管理網域許可權，您就必須執行此步驟。 如果您在 AD DS 中有這些許可權，MBAM 會為您建立 Spn。</p></td>
<td align="left"><p><a href="planning-how-to-secure-the-mbam-websites.md#bkmk-regvirtualspn" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md#bkmk-regvirtualspn)">如何保護 MBAM 網站的規劃</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>在您要設定 MBAM 伺服器功能的每個伺服器上安裝 MBAM Server 軟體。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果您打算在一台伺服器上安裝網站，並在另一台伺服器上安裝 web 服務，您就可以使用 <strong> Enable-MbamWebApplication </strong> Windows PowerShell Cmdlet 來設定它們。 MBAM Server 設定向導不支援在個別伺服器上設定這些專案。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">安裝 MBAM 2.5 伺服器軟體</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>如果您打算使用 Cmdlet 來設定 MBAM 伺服器功能，請參閱使用 Windows PowerShell 的先決條件。</p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能</a></p></td>
</tr>
</tbody>
</table>



**使用 Windows PowerShell 來設定 web 應用程式**

1.  開始設定前，請參閱[使用 Windows powershell 設定 MBAM 2.5 Server 功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)，以查看使用 windows powershell 的先決條件。

2.  使用**Enable-MbamWebApplication** Cmdlet 來設定使用 Windows PowerShell 的 web 應用程式。 若要取得此 Cmdlet 的相關資訊，請輸入**Get-help Enable-MbamWebApplication**。

**使用嚮導設定所有 web 應用程式的設定**

1. 在您想要設定 web 應用程式的伺服器上，啟動 [MBAM 伺服器設定] 嚮導。 您可以從 [**開始**] 功能表選取 [ **MBAM 伺服器**設定] 來開啟嚮導。

2. 按一下 [**新增功能**]，選取 [**管理及監視網站**與**自助式入口**網站]，然後按一下 **[下一步]**。 嚮導會檢查是否符合 web 應用程式的所有先決條件。

3. 如果先決條件檢查成功，請按 **[下一步]** 繼續。 否則，請解決任何缺少的先決條件，然後**再次按一下 [檢查先決條件**]。

4. 使用下列描述在嚮導中輸入欄位值。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><strong>欄位</strong></th>
   <th align="left">描述</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>安全性憑證</strong></p></td>
   <td align="left"><p>選取先前建立的憑證，以選擇性地加密 web 服務與您要設定網站之伺服器之間的通訊。 如果您選擇 [不要 <strong> 使用憑證] </strong> ，您的 web 通訊可能不安全。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>主機名稱</strong></p></td>
   <td align="left"><p>您正在設定網站的主機名稱稱。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>安裝路徑</strong></p></td>
   <td align="left"><p>您要安裝網站的路徑。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>連接埠</strong></p></td>
   <td align="left"><p>要用於網站與服務通訊的埠號碼。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>您必須設定防火牆例外狀況，才能透過指定的埠進行通訊。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>Web 服務應用程式池網域帳戶和密碼</strong></p></td>
   <td align="left"><p>[Web 服務] 應用程式池的網域使用者帳戶和密碼。</p>
   <p>如果您在 <strong> [設定資料庫] 頁面上的 [讀/寫存取權網域使用者或群組] 欄位中輸入使用者名稱 </strong> <strong> </strong> ，您必須在這個欄位中輸入相同的值。</p>
   <p>如果您在 <strong> [設定資料庫] 頁面上的 [讀/寫存取網域] 或 [群組] 欄位中輸入組名 </strong> <strong> </strong> ，您在這個欄位中輸入的值必須是該群組的成員。</p>
   <p>如果您沒有指定認證，則會使用為先前啟用的任何 web 應用程式所指定的認證。 所有 web 應用程式都必須使用相同的應用程式池認證。 如果您針對不同的 web 應用程式指定不同的認證，則會使用最近指定的值。</p>
   <div class="alert">
   <strong>重要</strong><br/><p>若要提高安全性，請將認證中指定的帳號設定為擁有有限的使用者權限。 此外，將帳戶的密碼設定為永不過期。</p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



5. 確認內建的 IIS \ _IUSRS 帳戶或應用程式池帳戶已新增至**驗證之後類比用戶端**，並以**批次工作**的本機安全性設定登入。

   若要檢查是否已將它新增到本機安全性設定，請開啟 [**本機安全性原則編輯器**]，展開 [**本機原則**] 節點，按一下 [**使用者權利指派**] 節點，然後按兩下 [**在驗證之後類比用戶端**]，然後在右窗格中**以批次工作原則登**入。

**使用嚮導設定資料庫的連線資訊**

1.  使用下欄欄位描述來設定合規性和審核資料庫的嚮導中的連線資訊。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">欄位</th>
    <th align="left">描述</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>SQL Server 名稱</strong></p></td>
    <td align="left"><p>已設定合規性和審核資料庫之伺服器的名稱。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>SQL Server 資料庫實例</strong></p></td>
    <td align="left"><p>在其中設定合規性和審核資料庫的 SQL Server 實例名稱。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>資料庫名稱</strong></p></td>
    <td align="left"><p>合規性和審核資料庫的名稱。</p></td>
    </tr>
    </tbody>
    </table>



2.  使用下欄欄位描述來設定恢復資料庫的嚮導中的連線資訊。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">欄位</th>
    <th align="left">描述</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>SQL Server 名稱</strong></p></td>
    <td align="left"><p>在其中設定恢復資料庫的伺服器名稱。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>SQL Server 資料庫實例</strong></p></td>
    <td align="left"><p>在其中設定復原資料庫的 SQL Server 實例名稱。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>資料庫名稱</strong></p></td>
    <td align="left"><p>恢復資料庫的名稱。</p></td>
    </tr>
    </tbody>
    </table>



**使用嚮導來設定 web 應用程式**

1. 使用下列描述在嚮導中輸入欄位值，以設定管理和監視網站。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">欄位</th>
   <th align="left">描述</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>[高級支援人員] 角色網域群組</strong></p></td>
   <td align="left"><p>網域使用者群組，其成員可以存取管理和監控網站的所有區域（[報表] 區域除外）。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>支援人員角色網域群組</strong></p></td>
   <td align="left"><p>網域使用者群組，其成員可以存取 <strong> </strong> 管理和監控網站的 [管理 TPM] 和 [ <strong> 磁碟機恢復] </strong> 區域。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>使用 System Center Configuration Manager 整合</strong></p></td>
   <td align="left"><p>如果您是使用 Configuration Manager 整合拓撲設定 MBAM，請選取此核取方塊。 選取此核取方塊後，除了復原審核報告之外，所有的報告都會出現在 Configuration Manager 中，而不是在 [管理] 和 [監視] 網站中顯示。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>報告角色網域群組</strong></p></td>
   <td align="left"><p>其成員擁有 [管理] 和 [監視] 網站 [報告] 區域之唯讀存取權的網域使用者群組。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>SQL Server Reporting Services URL</strong></p></td>
   <td align="left"><p>已設定 MBAM 報告之 SSRS 伺服器的 URL。</p>
   <p>報表 Url 的範例：</p>
   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">主機名稱類型</th>
   <th align="left">範例</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>含完全限定功能變數名稱的範例</p></td>
   <td align="left"><p><a href="https://MyReportServer.Contoso.com/ReportServer" data-raw-source="https://MyReportServer.Contoso.com/ReportServer">https://MyReportServer.Contoso.com/ReportServer</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>含自訂主機名稱的範例</p></td>
   <td align="left"><p><a href="https://MyReportServer/ReportServer" data-raw-source="https://MyReportServer/ReportServer">https://MyReportServer/ReportServer</a></p></td>
   </tr>
   </tbody>
   </table>
   <p> </p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>虛擬目錄</strong></p></td>
   <td align="left"><p>[管理] 和 [監視] 網站的虛擬目錄。 這個名稱會對應到伺服器上的網站物理目錄，並會附加到網站的主機名稱，例如：</p>
   <p>HTTP （s）// &lt; <em> hostname </em> &gt; ： &lt; <em> 埠 </em> &gt; /HelpDesk/</p>
   <p>如果您沒有指定虛擬目錄，就會使用 [價值 <strong> 支援人員] </strong> 。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>資料移轉角色網域群組 </strong> （選用）</p></td>
   <td align="left"><p>其成員有權使用 Mbam * 資訊 Cmdlet 來透過此端點寫入復原資訊的網域使用者群組。</p></td>
   </tr>
   </tbody>
   </table>



2. 使用下列描述在嚮導中輸入欄位值以設定自助入口網站。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">欄位</th>
   <th align="left">描述</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>虛擬目錄</strong></p></td>
   <td align="left"><p>Web 應用程式的虛擬目錄。 這個名稱會對應到伺服器上的網站物理目錄，並會附加到網站的主機名稱，例如：</p>
   <p>HTTP （s）// &lt; <em> hostname </em> &gt; ： &lt; <em> 埠 </em> &gt; /SelfService/</p>
   <p>如果您沒有指定虛擬目錄，將會使用 [值 <strong> SelfService] </strong> 。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>公司名稱</p></td>
   <td align="left"><p>為自助服務入口網站指定公司名稱，例如：</p>
   <p>Contoso IT</p>
   <p>此公司名稱是由所有自助門戶使用者查看。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>支援人員 URL 文字</p></td>
   <td align="left"><p>指定將使用者引導至貴組織的技術支援網站的文字語句，例如：</p>
   <p>聯絡支援人員或 IT 部門</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>支援人員 URL</p></td>
   <td align="left"><p>指定貴組織的技術支援網站的 URL，例如：</p>
   <p>HTTP （s）// &lt; <em> companyHelpdeskURL</em>&gt;/</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>[注意事項] 文字檔</p></td>
   <td align="left"><p>在自助入口網站登陸頁面上，選取包含您想要向使用者顯示之通知的檔案。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>不要向使用者顯示通知文字</p></td>
   <td align="left"><p>選取此核取方塊，以指定不會向使用者顯示通知文字。</p></td>
   </tr>
   </tbody>
   </table>



3. 完成專案後，請按 **[下一步**]。

   嚮導會檢查是否符合 web 應用程式的所有先決條件。

4. 按 \[**下一步**\] 繼續。

5. 在 [**摘要**] 頁面上，查看將新增的功能。

   **注意**  
   若要為您所製作的專案建立 Windows PowerShell 腳本，請按一下 [**匯出 PowerShell 腳本**] 並儲存腳本。



6. 按一下 [**新增**]，將 web 應用程式新增至伺服器，然後按一下 [**關閉**]。

   若要自訂自助式入口網站，只要新增自訂的指示文字、您的公司名稱、指向詳細資訊的指標等，請參閱[自訂貴組織的自助入口網站](customizing-the-self-service-portal-for-your-organization.md)。

**在用戶端電腦無法存取 CDN 的情況下，設定自助服務入口網站**

1.  判斷您是否正在執行 Microsoft BitLocker 管理和監控（MBAM） 2.5 SP1。 如果是這樣，請不要執行任何動作。 您的自助入口網站設定已完成。

    **注意**  
    Microsoft BitLocker 管理和監控（MBAM） 2.5 SP1 會在安裝程式中安裝 JavaScript 檔案，因此不需要連線至 Microsoft Ajax 內容傳遞網路，就能設定自助入口網站。 只有在 SP1 之前使用版本的 Microsoft BitLocker 管理和監控（MBAM）2.5 時，才能執行下列步驟。



2.  判斷您的用戶端電腦是否有權存取 Microsoft Ajax 內容傳遞網路（CDN）。

    CDN 為自助入口網站提供對某些 JavaScript 檔案所需的存取權。 如果您未在用戶端電腦無法存取 CDN 時設定自助入口網站，則只會顯示公司名稱和使用者登入的帳戶。 不會顯示任何錯誤訊息。

3.  執行下列其中一項：

    -   如果您的用戶端電腦具有 CDN 的存取權，請執行任何動作。 您的自助入口網站設定已完成。

    -   如果您的用戶端電腦沒有 CDN 的存取權，請完成在[用戶端電腦無法存取 Microsoft 內容傳遞網路時，如何設定自助入口網站](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)中的步驟。


## 相關主題


[伺服器事件記錄檔](server-event-logs.md)

[設定 MBAM 2.5 伺服器功能](configuring-the-mbam-25-server-features.md)

[如何在用戶端電腦無法存取 Microsoft 內容傳遞網路時設定自助入口網站](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)

[為組織自訂自助入口網站](customizing-the-self-service-portal-for-your-organization.md)

[驗證 MBAM 2.5 伺服器功能設定](validating-the-mbam-25-server-feature-configuration.md)



## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





