---
title: 如何在分散式伺服器上安裝及設定 MBAM
description: 如何在分散式伺服器上安裝及設定 MBAM
author: dansimp
ms.assetid: 67b91e6b-ae2e-4e47-9ef2-6819aba95976
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 841b894430d14604f0fd923703708d7a3f588c07
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810328"
---
# 如何在分散式伺服器上安裝及設定 MBAM


本主題中的程式說明如何在分散式伺服器上的獨立拓撲中安裝 Microsoft BitLocker 管理和監控（MBAM）2.0。 若要查看建議架構的圖表，以及資料庫與功能的描述，請參閱[部署 MBAM 2.0 伺服器基礎結構](deploying-the-mbam-20-server-infrastructure-mbam-2.md)。 若要使用 Configuration Manager 拓撲來安裝 Microsoft BitLocker 管理及監視，請參閱[使用 Configuration Manager 部署 MBAM](deploying-mbam-with-configuration-manager-mbam2.md)。

每個伺服器功能都有特定的先決條件。 若要確認您已符合系統必備與硬體和軟體需求，請參閱[MBAM 2.0 部署先決條件](mbam-20-deployment-prerequisites-mbam-2.md)和[MBAM 2.0 支援](mbam-20-supported-configurations-mbam-2.md)的設定。 此外，部分功能需要您在安裝程式期間提供特定資訊，才能成功部署該功能。 您也應該在開始 MBAM 部署之前，先複習[規劃 MBAM 2.0 伺服器部署](planning-for-mbam-20-server-deployment-mbam-2.md)。

**注意**  
若要取得安裝記錄檔，您必須使用 Msiexec 套件和 **/l** &lt; location &gt; 選項來安裝 MBAM。 記錄檔案是在您指定的位置建立。

在安裝 MBAM 的使用者伺服器上，會在% temp% 資料夾中建立額外的設定記錄檔。



## <a href="" id="deploying-mbam-server-features-"></a>部署 MBAM Server 功能


下列步驟說明如何安裝一般 MBAM 功能。

**啟動 MBAM Server 安裝精靈**

1.  在您要安裝 Microsoft BitLocker 管理與監視的伺服器上，執行**MBAMSetup.exe**以啟動 MBAM 安裝精靈。

2.  在 [**歡迎**] 頁面上，選擇性地選取 [**客戶經驗改進計畫**]，然後按一下 [**開始**]。

3.  閱讀並接受 Microsoft 軟體授權協定，然後按一下 **[下一步]** 繼續安裝。

4.  在 [**拓撲選取範圍**] 頁面上，選取**獨立**拓朴，然後按 **[下一步]**。

    **注意**  
    如果您想要使用 Configuration Manager 整合拓撲來安裝 MBAM，請參閱[使用 Configuration Manager 部署 MBAM](deploying-mbam-with-configuration-manager-mbam2.md)。



5.  選取您要安裝的功能。 根據預設，所有的 MBAM 功能都已選取 [安裝]。 清除您想要安裝在其他位置的功能。 在同一部電腦上安裝的功能，必須同時安裝在一起。 您必須以下列順序安裝 MBAM 功能：

    -   復原資料庫

    -   合規性和審核資料庫

    -   合規性與審計報告

    -   自助服務入口網站

    -   管理和監控伺服器

    -   MBAM 群組原則範本

    **注意**  
    安裝精靈會檢查安裝的先決條件，並顯示遺失的先決條件。 如果符合所有先決條件，安裝會繼續進行。 如果偵測到遺失的先決條件，您必須先解決遺失的先決條件，然後再次按一下 [**檢查必備元件**]。 如果此時間符合所有先決條件，安裝就會繼續。



~~~
The MBAM Setup wizard displays installation pages for the features that you select. The following sections describe the installation procedures for each feature.

**Note**  
For the following instructions, it is assumed that each feature is to be installed on a separate server. If you install multiple features on a single server, you can change or eliminate some steps.
~~~



**若要安裝恢復資料庫**

1.  在 [**設定復原資料庫**] 頁面上，指定將執行 [管理及監視伺服器] 功能的電腦名稱稱。 部署管理和監視伺服器功能之後，它會使用其網域帳戶來連線至資料庫。

2.  按 \[**下一步**\] 繼續。

3.  指定要儲存恢復資料之資料庫的 SQL Server 實例名稱和名稱。 您也必須指定資料庫的位置和記錄資訊所在的位置。

4.  按一下 **[下一步**] 以繼續使用 [MBAM 設定] 嚮導。

**若要安裝合規性和審核資料庫**

1.  在 [**設定合規性和審核資料庫**] 頁面上，指定將用來存取報表資料庫的使用者帳戶。

2.  指定要執行管理和監視伺服器以及合規性與審核報告的電腦名稱稱。 管理及監視及合規性與審計報表服務器部署之後，他們就會使用其網域帳戶連線至資料庫。

    **注意**  
    如果您在沒有合規性和審核報告功能的情況下安裝合規性和審核資料庫，您必須在合規性和審核資料庫電腦上新增例外狀況，才能在 Microsoft SQL Server 埠上啟用入站流量。 預設埠號碼是1433。



3.  指定 SQL Server 實例名稱和要儲存合規性和審核資料之資料庫的名稱。 您也必須指定資料庫和記錄資訊的存放位置。

4.  按一下 **[下一步]** 以繼續使用 Microsoft BitLocker 管理及監視設定向導。

**若要安裝合規性和審核報告**

1.  在 [**設定合規性和審核報告**] 頁面上，指定 &lt; &gt; 安裝合規性和審核資料庫的遠端 SQL Server 實例名稱（例如，ServerName）。

    **注意**  
    如果您在沒有管理和監控伺服器的情況下安裝合規性和審核報告，您必須在合規性和審核報告電腦上新增例外狀況，才能在報表伺服器埠上啟用輸入流量（預設埠為80）。



2.  指定合規性和審核資料庫的名稱。 根據預設，資料庫名稱是 MBAM 合規性狀態，不過您可以在安裝合規性和審核資料庫時變更名稱。

3.  按 \[**下一步**\] 繼續。

4.  選取將安裝合規性和審核報告的 SQL Server Reporting Services 實例。 提供網域使用者帳戶和密碼以存取合規性和審核資料庫。 將此帳戶的密碼設定為永不過期。 使用者帳戶應該能夠存取 MBAM [報告使用者] 群組提供的所有資料。

5.  按一下 **[下一步]** 以繼續使用 Microsoft BitLocker 管理及監視設定向導。

**安裝自助服務入口網站**

1.  在 [**設定自助入口網站**] 頁面上，您可以選擇性地加密自助入口網站與管理與監視伺服器之間的通訊。 如果您選擇加密通訊的選項，系統會提示您選取憑證授權單位預配的憑證以用於加密。

2.  按 \[**下一步**\] 繼續。

3.  指定安裝合規性和審核資料庫的 SQL Server 遠端實例（例如* &lt; ServerName &gt; *）。

4.  指定合規性和審核資料庫的名稱。 根據預設，資料庫名稱是 MBAM 合規性狀態。 不過，您可以在安裝合規性和審核資料庫時變更名稱。

5.  按 \[**下一步**\] 繼續。

6.  指定安裝了復原資料庫的 SQL Server 遠端實例（例如， * &lt; ServerName &gt; *）。

7.  指定恢復資料庫的名稱。 根據預設，資料庫名稱是**MBAM 復原與硬體**。 不過，您可以在安裝 [恢復資料庫] 功能時變更名稱。

8.  按 \[**下一步**\] 繼續。

9.  輸入**埠號碼**、**主機名稱**（選用），以及 MBAM 管理和監視伺服器的**安裝路徑**。

    **注意**  
    除非您指定唯一主機標頭名稱，否則您指定的埠號碼必須是管理和監視伺服器上未使用的埠號碼。 如果您使用的是 Windows 防火牆，則會自動開啟埠。



10. 若要選擇性地註冊自助服務入口網站的服務主體名稱（SPN），請選取 [**使用 Active Directory 註冊此電腦的服務主體名稱（spn）] （Windows 驗證所需）**。 如果您選取此核取方塊，MBAM 安裝程式將不會嘗試註冊現有的 Spn，您可以在 MBAM 安裝之前或之後手動註冊 SPN。 如需手動登記 SPN 的指示，請參閱[手動 SPN 註冊](https://go.microsoft.com/fwlink/?LinkId=286758)。

11. 按一下 **[下一步]** 以繼續使用 Microsoft BitLocker 管理及監視設定向導。

12. 指定是否要使用 Microsoft 更新，協助保護您的電腦安全性，然後按 **[下一步]**。

13. 完成選取的 MBAM 功能資訊之後，您就可以使用 [設定] 嚮導開始進行 MBAM 安裝了。 如果您必須檢查或變更您的安裝設定，請按一下 [**返回**]，在嚮導中移動。 按一下 [**安裝**] 以開始安裝。 按一下 [**取消**] 結束嚮導。 安裝程式會安裝您所選取的 MBAM 功能，並通知您安裝已完成。

14. 按一下 **[完成] 結束**嚮導。

    **注意**  
    若要在安裝自助入口網站之後設定它，請使用您的公司名稱和其他公司特定資訊來標記自助入口網站，瞭解[如何為自助服務入口網站打造品牌](how-to-brand-the-self-service-portal.md)，以取得相關指示。



15. 如果用戶端電腦具有 Microsoft 內容傳遞網路（CDN）的存取權，讓自助服務入口網站必須存取某些 JavaScript 檔案，您就完成了自助式入口網站的安裝。 如果用戶端電腦沒有 Microsoft CDN 的存取權，請完成下一節中的步驟，將自助式入口網站設定為從易於存取的來源中參考 JavaScript 檔案。

**當使用者無法存取 Microsoft 內容傳遞網路時，設定自助服務入口網站**

1. 如果用戶端電腦具有 Microsoft 內容傳遞網路（CDN）的存取權，讓自助入口網站安裝特定 JavaScript 檔案，就會完成自助入口網站的安裝。 如果用戶端電腦沒有 Microsoft CDN 的存取權，請完成本節中的其餘步驟，將自助式入口網站設定為從易於存取的來源中參考 JavaScript 檔案。

2. 從 Microsoft CDN 下載四個 JavaScript 檔案：

   -   jQuery-1.7.2.min.js-[https://go.microsoft.com/p/fwlink/?LinkID=271736](https://go.microsoft.com/fwlink/p/?LinkID=271736)

   -   MicrosoftAjax.js –[https://go.microsoft.com/p/fwlink/?LinkId=272283](https://go.microsoft.com/fwlink/p/?LinkId=272283)

   -   MicrosoftMvcAjax.js-[https://go.microsoft.com/p/fwlink/?LinkId=272284](https://go.microsoft.com/fwlink/p/?LinkId=272284)

   -   MicrosoftMvcValidation.js- <https://go.microsoft.com/fwlink/p/?LinkId=272285>

3. 將 JavaScript 檔案複製到自助服務入口網站的 [**腳本**] 目錄。 此目錄位於 <em> &lt; MBAM 自助安裝目錄 &gt; \\ </em> 自助服務 Website\\Scripts。

4. 開啟 **[網際網路資訊服務（IIS）管理員**]。

5. 展開 [**網站** &gt; **Microsoft BitLocker 管理與監視**]，然後醒目提示 [ **SelfService**]。

   **注意**  
   *SelfService*是預設的虛擬目錄名稱。 如果您在安裝期間為此目錄選擇了其他名稱，請記得使用您所選擇的名稱來取代其餘指令中的*SelfService* 。



6. 按兩下中間窗格中的 [**應用程式設定**]。

7. 針對下列清單中的每個專案，透過 &lt; &gt; 使用/SelfService/（或您在安裝時選擇的名稱）取代虛擬目錄，來編輯應用程式設定以參照新的位置。 例如，虛擬目錄路徑會類似/selfservice/scripts/jquery-1.7.2.min.js。

   -   jQueryPath：/ &lt; virtual directory &gt; /Scripts/jQuery-1.7.2.min.js

   -   MicrosoftAjaxPath：/ &lt; virtual directory &gt; /Scripts/MicrosoftAjax.js

   -   MicrosoftMvcAjaxPath：/ &lt; virtual directory &gt; /Scripts/MicrosoftMvcAjax.js

   -   MicrosoftMvcValidationPath：/ &lt; virtual directory &gt; /Scripts/MicrosoftMvcValidation.js

**若要安裝 [管理及監視伺服器] 功能**

1. MBAM 可以加密 Web 服務與管理與監視伺服器之間的通訊。 如果您選擇加密通訊的選項，系統會提示您選取憑證授權單位預配的憑證以用於加密。

2. 按 \[**下一步**\] 繼續。

3. 指定安裝合規性和審核資料庫的 SQL Server 遠端實例（例如： * &lt; ServerName &gt; *）。

4. 指定合規性和審核資料庫的名稱。 根據預設，資料庫名稱是 MBAM 合規性狀態。 不過，您可以在安裝合規性和審核資料庫時變更名稱。

5. 按 \[**下一步**\] 繼續。

6. 指定安裝恢復資料庫的 SQL Server 遠端實例（例如： * &lt; ServerName &gt; *）。

7. 指定恢復資料庫的名稱。 根據預設，資料庫名稱是**MBAM 復原與硬體**。 不過，您可以在安裝 [恢復資料庫] 功能時變更名稱。

8. 按 \[**下一步**\] 繼續。

9. 指定 SQL Server Reporting Services （SRS）網站的 "Home" URL。 SQL Server Reporting Services 網站實例的預設首頁位置是：

   HTTP:// <em> &lt; NameofMBAMReportsServer &gt; / </em> ReportServer

   **注意**  
   如果 SQL Server Reporting Services 已設定為命名實例，URL 會類似下列： HTTP://* &lt; NameofMBAMReportsServer &gt; */ReportServer\_* &lt; SRSInstanceName &gt; *。



10. 按 \[**下一步**\] 繼續。

11. 輸入**埠號碼**、**主機名稱**（選用），以及 MBAM 管理和監視伺服器的**安裝路徑**。

    **注意**  
    除非您指定唯一主機標頭名稱，否則您指定的埠號碼必須是管理和監視伺服器上未使用的埠號碼。 如果您使用的是 Windows 防火牆，則會自動開啟埠。



12. 若要選擇性地註冊自助服務入口網站的服務主體名稱（SPN），請選取 [**使用 Active Directory 註冊此電腦的服務主體名稱（spn）] （Windows 驗證所需）**。 如果您選取此核取方塊，MBAM 安裝程式將不會嘗試註冊現有的 Spn，您可以在 MBAM 安裝之前或之後手動註冊 SPN。 如需手動登記 SPN 的指示，請參閱[手動 SPN 註冊](https://go.microsoft.com/fwlink/?LinkId=286758)。

13. 按一下 **[下一步]** 以繼續使用 Microsoft BitLocker 管理及監視設定向導。

14. 指定是否要使用 Microsoft 更新，協助保護您的電腦安全性，然後按 **[下一步]**。

15. 完成選取的 MBAM 功能資訊之後，您就可以使用 [設定] 嚮導開始進行 MBAM 安裝了。 如果您必須檢查或變更您的安裝設定，請按一下 [**返回**]，在嚮導中移動。 按一下 [**安裝**] 進行安裝。 按一下 [**取消**] 結束嚮導。 安裝程式會安裝您所選取的 MBAM 功能，並通知您安裝已完成。

16. 按一下 **[完成] 結束**嚮導。

**若要執行安裝後設定**

1.  在 [管理和監視伺服器] 上，將使用者新增至下列本機群組，以授予他們存取 MBAM 管理和監視網站上的功能。

    -   **MBAM 支援人員**：此本機群組的成員可以存取 [MBAM 管理及監視] 網站上的 [磁碟機復原] 及 [管理 TPM] 功能。 [磁碟機復原] 和 [管理 TPM] 中的所有欄位都是技術支援人員的必要欄位。

    -   **MBAM 高級支援人員的使用者**：此本機群組的成員可以高級存取磁片磁碟機，並在 [MBAM 管理] 和 [監視] 網站上管理 TPM 功能。 針對高級支援人員的使用者，磁片磁碟機復原只需要 [金鑰識別碼] 欄位。 在 [**管理 TPM**] 中，只需要 [**電腦網域**] 欄位和 [**電腦名稱稱**] 欄位。

2.  在承載管理和監控伺服器以及合規性和審核資料庫的伺服器上，以及駐留合規性和審核報告的伺服器上，將使用者新增至下列當地群組，以授予他們存取 MBAM 管理和監控網站上的 [報告] 功能。

    -   **MBAM 報表使用者**：此本機群組的成員可以存取 MBAM 管理和監控網站上的報告。

    **注意**  
    **MBAM 報告**的使用者或群組成員資格使用者的本機群組必須在已安裝 MBAM 管理和監控伺服器功能、合規性和審核資料庫以及合規性和審核報告的所有電腦上維持。



## 驗證 MBAM Server 功能安裝


當 Microsoft BitLocker 管理和監視伺服器功能安裝完成後，建議您確認安裝已成功設定 MBAM 的所有必要功能。 使用下列程式來確認 Microsoft BitLocker 管理及監視服務運作正常。

**驗證 MBAM 伺服器安裝**

1. 在部署 MBAM 功能的每個伺服器上，開啟 [**控制台**]，選取 [**程式**]，然後選取 [**程式和功能**]。 確認 [**程式和功能**] 清單中出現 [ **Microsoft BitLocker 管理及監視**]。

   **注意**  
   若要驗證 MBAM 安裝，您必須使用在每個伺服器上都有本機電腦管理認證的網域帳戶。



2. 在安裝了復原資料庫的伺服器上，開啟 SQL Server Management Studio 並確認已安裝**MBAM 復原與硬體**資料庫。

3. 在已安裝合規性和審核資料庫的伺服器上，開啟 SQL Server Management Studio 並確認已安裝**MBAM 合規性狀態資料庫**。

4. 在已安裝合規性和審核報告的伺服器上，使用系統管理認證開啟網頁瀏覽器，然後流覽至 SQL Server Reporting Services 網站的 "Home"。

   您可以在 HTTP:// <em> &lt; NameofMBAMReportsServer &gt; </em> /Reports.aspx. 中找到 SQL Server Reporting Services 網站實例的預設首頁位置。 若要尋找實際的 URL，請使用 Reporting Services Configuration Manager 工具，然後選取在安裝期間指定的實例。

   確認名為**Microsoft BitLocker 管理和監視**的報表資料夾包含名為**MaltaDataSource**的資料來源，且**en-us**資料夾包含四個報表。

   **注意**  
   如果 SQL Server Reporting Services 已設定為命名實例，URL 應該會類似下列內容： HTTP：//* &lt; NameofMBAMReportsServer &gt; */Reports\_* &lt; SRSInstanceName &gt; *



~~~
**Note**  
If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server. If you then go to the Administration and Monitoring website and select a report, the following message appears: “Only Secure Content is Displayed.” To show the report, click **Show All Content**.
~~~



5. 在已安裝 [管理及監視] 功能的伺服器上，執行 [**伺服器管理員**] 並流覽至 [**角色**]。 選取 **[Web 服務器（iis）**]，然後按一下 [**網際網路資訊服務（iis）管理員**]。

6. 在 **[連線] 中，** 流覽至 [ * &lt; computername &gt; *]，選取 [**網站**]，然後選取 [ **Microsoft BitLocker 管理與監視**]。 確認 [ **MBAMAdministrationService**]、[ **MBAMComplianceStatusService**] 和 [ **MBAMRecoveryAndHardwareService** ] 都已列出。

7. 在已安裝 [管理] 和 [監視] 功能及 [自助式入口網站] 的伺服器上，使用系統管理認證開啟網頁瀏覽器，並流覽至下列位置，以確認它們已順利載入。

   **注意**  
   以 ".svc" 結尾的 Url 不會顯示網站。 成功是由「此服務目前已停用的中繼資料發佈」或類似程式碼的資訊所指示。 如果您看到一些其他的錯誤訊息，或是找不到頁面，就沒有成功載入頁面。



~~~
-   *http://&lt;hostname&gt;/HelpDesk/default.aspx* and confirm each of the links for navigation and reports

-   *http://&lt;hostname&gt;/SelfService&gt;/*

-   *http://&lt;computername&gt;/MBAMAdministrationService/AdministrationService.svc*

-   *http://&lt;hostname&gt;/MBAMUserSupportService/UserSupportService.svc*

-   *http://&lt;computername&gt;/MBAMComplianceStatusService/StatusReportingService.svc*

-   *http://&lt;computername&gt;/MBAMRecoveryAndHardwareService/CoreService.svc*

**Note**  
It is assumed that the server features were installed on the default port without network encryption. If you installed the server features on a different port or virtual directory, change the URLs to include the appropriate port, for example, *http://&lt;hostname&gt;:&lt;port&gt;/HelpDesk/default.aspx* or*http://&lt;hostname&gt;:&lt;port&gt;/&lt;virtualdirectory&gt;/default.aspx*

If the server features were installed with network encryption, change http:// to https://.
~~~



8. 確認每個網頁都已順利載入。

## 相關主題


[部署 MBAM 2.0 伺服器基礎結構](deploying-the-mbam-20-server-infrastructure-mbam-2.md)









