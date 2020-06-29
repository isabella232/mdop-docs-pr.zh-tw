---
title: 如何在單一伺服器上安裝及設定 MBAM
description: 如何在單一伺服器上安裝及設定 MBAM
author: dansimp
ms.assetid: 45e6a012-6c8c-4d90-902c-d09de9a0cbea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 53e170f421bdce8dd6f771af3902af627a15a085
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810334"
---
# 如何在單一伺服器上安裝及設定 MBAM


本主題中的程式說明如何在單一伺服器上的獨立拓撲中安裝 Microsoft BitLocker 管理和監控（MBAM）。 只能在測試環境中使用單伺服器設定。 在生產環境中，請使用兩個或多個伺服器。 如果您是使用 Configuration Manager 拓撲來安裝 Microsoft BitLocker 管理和監視，請參閱使用[Configuration Manager 部署 MBAM](deploying-mbam-with-configuration-manager-mbam2.md)。

下圖顯示單一伺服器結構的範例。 如需資料庫與功能的描述，請參閱[MBAM 2.0 的高層架構](high-level-architecture-for-mbam-20-mbam-2.md)。

![mbam 2 單伺服器部署拓朴](images/mbam2-1-server.gif)

每個伺服器功能都有特定的先決條件。 若要確認您已符合系統必備與硬體和軟體需求，請參閱[MBAM 2.0 部署先決條件](mbam-20-deployment-prerequisites-mbam-2.md)和[MBAM 2.0 支援](mbam-20-supported-configurations-mbam-2.md)的設定。 此外，某些功能也有一些資訊，必須在安裝過程中提供，才能成功部署該功能。 您也應該在開始 MBAM 部署之前，先複習[準備 MBAM 2.0 的環境](preparing-your-environment-for-mbam-20-mbam-2.md)。

**注意**  
若要取得安裝記錄檔，您必須使用 Msiexec 套件和 **/l** &lt; location &gt; 選項來安裝 MBAM。 記錄檔案是在您指定的位置建立。

在安裝 MBAM 的使用者伺服器上，會在% temp% 資料夾中建立額外的設定記錄檔。



## 在單一伺服器上安裝 MBAM Server 功能


下列步驟說明如何安裝一般 MBAM 功能。

**啟動 MBAM Server 功能安裝**

1.  在您要安裝 MBAM 的伺服器上，執行**MBAMSetup.exe** ，啟動 [MBAM 安裝] 嚮導。

2.  在 [**歡迎**] 頁面上，選擇性地選取 [**客戶經驗改進計畫**]，然後按一下 [**開始**]。

3.  閱讀並接受 Microsoft 軟體授權協定，然後按一下 **[下一步]** 繼續安裝。

4.  在 [**拓撲選取範圍**] 頁面上，選取**獨立**拓朴，然後按 **[下一步]**。

5.  在 [**選取要安裝的功能**] 頁面上，選取您要安裝的功能。 根據預設，所有的 MBAM 功能都已選取 [安裝]。 在同一部電腦上安裝的功能，必須同時安裝在一起。 針對您想要安裝到其他位置的任何功能，清除其核取方塊。 您必須以下列順序安裝 MBAM 功能：

    -   復原資料庫

    -   合規性和審核資料庫

    -   合規性與審計報告

    -   自助服務伺服器

    -   管理和監控伺服器

    -   MBAM 群組原則範本

    **注意**  
    安裝精靈會檢查安裝的先決條件，並顯示遺失的先決條件。 如果符合所有先決條件，安裝會繼續進行。 如果偵測到遺失的先決條件，您必須先解決遺失的先決條件，然後再次按一下 [**檢查必備元件**]。 如果此時間符合所有先決條件，安裝就會繼續。



6.  在 [**設定網路通訊安全性**] 頁面上，選擇是否要加密管理與監視伺服器與用戶端的 Web 服務之間的通訊。 如果您決定要加密通訊，請選取憑證授權單位預配的憑證以用於加密。 您必須先建立憑證，才能在此頁面上選取。

    **注意**  
    只有當您在 [**選取要安裝的功能**] 頁面上選取 [自助式入口網站] 或 [管理及監視伺服器] 功能時，才會顯示此頁面。



7.  按一下 **[下一步**]，然後繼續進行下一組步驟來設定 MBAM 伺服器功能。

**設定 MBAM 伺服器功能**

1.  在 [**設定復原資料庫**] 頁面上，指定 SQL Server 實例名稱和要儲存恢復資料的資料庫名稱。 您也必須指定資料庫檔案所在的位置和記錄資訊所在的位置。

2.  按 \[**下一步**\] 繼續。

3.  在 [**設定合規性和審核資料庫**] 頁面上，指定要儲存合規性與審核資料之資料庫的 SQL Server 實例名稱和名稱。 您也必須指定資料庫檔案的所在位置及記錄資訊所在的位置。

4.  按 \[**下一步**\] 繼續。

5.  在 [**設定合規性和審核報告**] 頁面上，指定要安裝合規性和審核報告的 SQL Server Reporting Services 實例，並提供用於存取合規性和審核資料庫的網域使用者帳戶和密碼。 將此帳戶的密碼設定為永不過期。 使用者帳戶應該能夠存取 [MBAM 報告使用者] 群組中所有可用的資料。

6.  按 \[**下一步**\] 繼續。

7.  在 [**設定自助入口網站**] 頁面上，輸入自助服務入口網站的埠號碼、主機名稱、虛擬目錄名稱和安裝路徑。

    **注意**  
    除非您指定唯一主機標頭名稱，否則您指定的埠號碼必須是管理和監視伺服器上未使用的埠號碼。 如果您使用的是 Windows 防火牆，則會自動開啟埠。



8.  按 \[**下一步**\] 繼續。

9.  指定是否要使用 Microsoft 更新，協助保護您的電腦安全性，然後按 **[下一步]**。 這不會在 Windows 中開啟自動更新。

10. 在 [**設定管理和監視伺服器**] 頁面上，輸入 [技術支援中心] 網站的埠號碼、主機名稱、虛擬目錄名稱和安裝路徑。

    **注意**  
    除非您指定唯一主機標頭名稱，否則您指定的埠號碼必須是管理和監視伺服器上未使用的埠號碼。 如果您使用的是 Windows 防火牆，則會自動開啟埠。



11. 在 [**安裝摘要**] 頁面上，查看將要安裝的功能清單，然後按一下 [**安裝**] 以開始安裝 MBAM 功能。 如果您必須檢查或變更您的安裝設定，請按一下 [**返回**]，回到嚮導中，或按一下 [**取消**] 結束安裝程式。 安裝程式會安裝 MBAM 功能，並通知您安裝已完成。

12. 按一下 **[完成] 結束**嚮導。 安裝 Microsoft BitLocker 管理和監視伺服器功能之後，請繼續閱讀下一節，並完成步驟，以將使用者新增至 Microsoft BitLocker 管理和監視角色。 如需有關角色的詳細資訊，請參閱[規劃 MBAM 2.0 系統管理員角色](planning-for-mbam-20-administrator-roles-mbam-2.md)。

**若要執行安裝後設定**

1.  在 [管理及監視伺服器] 上，將使用者新增至下列當地群組，以授予他們存取 MBAM 技術支援中心網站功能的許可權：

    -   **MBAM 支援人員**：此本機群組的成員可以存取 [MBAM 管理及監視] 網站上的 [磁碟機復原] 及 [管理 TPM] 功能。 [磁碟機復原] 和 [管理 TPM] 中的所有欄位都是技術支援人員的必要欄位。

    -   **MBAM 高級支援人員的使用者**：此本機群組的成員可以高級存取磁片磁碟機，並在 [MBAM 管理] 和 [監視] 網站上管理 TPM 功能。 針對高級支援人員的使用者，磁片磁碟機復原只需要 [**金鑰識別碼**] 欄位。 在 [管理 TPM] 中，只需要 [**電腦網域**] 欄位和 [**電腦名稱稱**] 欄位。

2.  在 [管理及監視伺服器] 上，將使用者新增至下列本機群組，讓他們能夠存取 MBAM 管理和監控網站上的 [報告] 功能：

    -   **MBAM 報表使用者**：此本機群組的成員可以存取 MBAM 管理和監控網站上的 [報表] 功能。

    -   使用您的公司名稱、注意事項文字及其他公司特定資訊，為自助服務入口網站加上品牌。 如需相關指示，請參閱[如何為自助服務入口網站打造品牌](how-to-brand-the-self-service-portal.md)。

    **注意**  
    **MBAM 報告**的使用者或群組成員資格使用者的本機群組必須在已安裝 MBAM 管理和監控伺服器功能、合規性和審核資料庫以及合規性和審核報告的所有電腦上維持。 建議的做法是建立網域安全性群組，並將該網域群組新增至每個當地 MBAM 的 [使用者] 群組。 當您使用這個程式時，請依網域群組的方式管理群組成員資格。



## 驗證 MBAM Server 功能安裝


當 Microsoft BitLocker 管理和監視安裝完成後，請確認安裝已成功設定 BitLocker 管理所需的所有必要 MBAM 功能。 使用下列程式來確認 MBAM 服務是否正常運作。

**驗證 MBAM 伺服器功能安裝**

1. 在部署 MBAM 功能的每個伺服器上，開啟 [**控制台**]。 選取 [**程式**]，然後選取 [**程式和功能**]。 確認 [**程式和功能**] 清單中出現 [ **Microsoft BitLocker 管理及監視**]。

   **注意**  
   若要驗證安裝，您必須使用在每個伺服器上都有本機電腦管理認證的網域帳戶。



2. 在安裝了復原資料庫的伺服器上，開啟 [SQL Server Management Studio]，然後確認已安裝**MBAM 復原與硬體**資料庫。

3. 在已安裝合規性和審核資料庫的伺服器上，開啟 SQL Server Management Studio，並確認已安裝**MBAM 合規性狀態資料庫**。

4. 在已安裝合規性和審核報告的伺服器上，使用系統管理認證開啟網頁瀏覽器，然後流覽至 SQL Server Reporting Services 網站的 "Home"。

   SQL Server Reporting Services 網站實例的預設首頁位置是 HTTP:// <em> &lt; NameofMBAMReportsServer &gt; </em> /Reports。 若要尋找實際的 URL，請使用 Reporting Services Configuration Manager 工具，然後選取在安裝期間指定的實例。

   確認名為 Microsoft BitLocker 管理和監視的報表資料夾包含名為**MaltaDataSource**的資料來源，且**en-us**資料夾包含四個報表。

   **注意**  
   如果 SQL Server Reporting Services 已設定為命名實例，URL 應該會類似下列： HTTP://* &lt; NameofMBAMReportsServer &gt; */Reports\_* &lt; SRSInstanceName &gt; *



~~~
**Note**  
If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server. If you then go to the Administration and Monitoring website and select a report, the following message appears: “Only Secure Content is Displayed.” To show the report, click **Show All Content**.
~~~



5. 在已安裝 [管理及監視] 功能的伺服器上，執行 [**伺服器管理員**] 並流覽至 [**角色**]。 選取 **[Web 服務器（iis）**]，然後按一下 [**網際網路資訊服務（iis）管理員]。**

6. 在 [連線] 中 **，** 流覽至 [ * &lt; 電腦名稱稱 &gt; *]，選取 [**網站**]，然後選取 [ **Microsoft BitLocker 管理與監視**]。 確認 [ **MBAMAdministrationService**]、[ **MBAMUserSupportService**]、[ **MBAMComplianceStatusService**] 和 [ **MBAMRecoveryAndHardwareService** ] 都已列出。

7. 在已安裝 [管理] 和 [監視] 功能及 [自助式入口網站] 的伺服器上，使用系統管理認證開啟網頁瀏覽器，並流覽至下列位置，確認載入成功：

   -   *HTTP:// &lt; hostname &gt; /HelpDesk/default.aspx*並確認流覽和報告的每個連結

   -   *HTTP:// &lt; hostname &gt; /SelfService&gt;/*

   -   *HTTP:// &lt; computername &gt; /MBAMAdministrationService/AdministrationService.svc*

   -   *HTTP:// &lt; hostname &gt; /MBAMUserSupportService/UserSupportService.svc*

   -   *HTTP:// &lt; computername &gt; /MBAMComplianceStatusService/StatusReportingService.svc*

   -   *HTTP:// &lt; computername &gt; /MBAMRecoveryAndHardwareService/CoreService.svc*

   **注意**  
   假設伺服器功能已安裝在預設埠上，而不需要網路加密。 如果您已將伺服器功能安裝在不同的埠或虛擬目錄，請將 url 變更為包含適當的埠，例如， *HTTP:// &lt; hostname &gt; ： &lt; port &gt; /HelpDesk/default.asp*x 或*HTTP:// &lt; hostname &gt; ： &lt; port &gt; / &lt; virtualdirectory &gt; /default.aspx*

   如果伺服器功能是使用網路加密來安裝，請將 HTTP://變更為 HTTPs://。



## 相關主題


[部署 MBAM 2.0 伺服器基礎結構](deploying-the-mbam-20-server-infrastructure-mbam-2.md)









