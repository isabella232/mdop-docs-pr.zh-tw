---
title: 如何在分散式伺服器上安裝及設定 MBAM
description: 如何在分散式伺服器上安裝及設定 MBAM
author: dansimp
ms.assetid: 9ee766aa-6339-422a-8d00-4f58e4646a5e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 51f56a12d4e59226f834c7e474af0f1e96c1e8e9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811288"
---
# 如何在分散式伺服器上安裝及設定 MBAM


本主題中的程式說明分散式伺服器上的 Microsoft BitLocker 管理與監視（MBAM）功能的完整安裝。

每個伺服器功能都有特定的先決條件。 若要確認您已符合系統必備與硬體和軟體需求，請參閱[MBAM 1.0 部署先決條件](mbam-10-deployment-prerequisites.md)和[MBAM 1.0 支援](mbam-10-supported-configurations.md)的設定。 此外，部分功能需要您在安裝程式期間提供特定資訊，才能成功部署該功能。

**注意**  
若要取得安裝記錄檔，您必須使用**msiexec**套件和 **/l &lt; LOCATION &gt; **選項來安裝 MBAM。 記錄檔案是在您指定的位置建立。

在執行 MBAM 安裝的使用者的% temp% 資料夾中，會建立其他設定記錄檔。



## <a href="" id="deploy-the-mbam-server-features-"></a>部署 MBAM 伺服器功能


下列步驟說明如何安裝一般 MBAM 功能。

**注意**  
請務必在32位伺服器上使用32位設定，以及在64位伺服器上進行64位設定。



**部署 MBAM 伺服器功能**

1.  啟動 [MBAM 安裝] 嚮導，然後按一下 [歡迎] 頁面上的 [**安裝**]。

2.  閱讀並接受 Microsoft 軟體授權條款，然後按一下 **[下一步]** 繼續安裝。

3.  根據預設，所有的 MBAM 功能都已選取 [安裝]。 清除您想要安裝在其他位置的功能。 您要在同一部電腦上安裝的功能，必須同時安裝所有功能。 MBAM 功能必須以下列順序安裝：

    -   恢復與硬體資料庫

    -   合規性和審核資料庫

    -   合規性審核與報告

    -   管理和監控伺服器

    -   MBAM 群組原則範本

    **注意**  
    安裝精靈會檢查安裝的先決條件，並顯示遺失的先決條件。 如果符合所有先決條件，安裝會繼續進行。 如果偵測到遺失的先決條件，您必須先解決遺失的先決條件，然後再次按一下 [**檢查必備元件**]。 如果此時間符合所有先決條件，安裝將會繼續。



4.  [MBAM 設定] 嚮導會顯示所選功能的安裝頁面。 下列各節說明每個功能的安裝程式。

    **注意**  
    一般來說，每個功能都安裝在不同的伺服器上。 如果您想要在單一伺服器上安裝多項功能，您可以變更或刪除下列部分步驟。



~~~
**To install the Recovery and Hardware Database**

1.  Choose an option for MBAM communication encryption. MBAM can encrypt the communication between the Recovery and Hardware Database and the Administration and Monitoring servers. If you choose the option to encrypt communication, you are asked to select the authority-provisioned certificate that is used for encryption.

2.  Click **Next** to continue.

3.  Specify the names of the computers that will be running the Administration and Monitoring Server feature, to configure access to the Recovery and Hardware Database.. Once the Administration and Monitoring Server feature is deployed, it connects to the database by using its domain account.

4.  Click **Next** to continue.

5.  Specify the **Database Configuration** for the SQL Server instance that stores the recovery and hardware data. You must also specify where the database will be located and where the log information will be located.

6.  Click **Next** to continue with the MBAM Setup wizard.

**To install the Compliance and Audit Database**

1.  Choose an option for the MBAM communication encryption. MBAM can encrypt the communication between the Compliance and Audit Database and the Administration and Monitoring servers. If you choose the option to encrypt communication, you are asked to select the authority-provisioned certificate that will be used for encryption.

2.  Click **Next** to continue.

3.  Specify the user account that will be used to access the database for reports.

4.  Click **Next** to continue.

5.  Specify the computer names of the computers that you want to run the Administration and Monitoring Server and the Compliance and Audit Reports, to configure the access to the Compliance and Audit Database.. After the Administration and Monitoring and the Compliance and Audit Reports Server are deployed, they will connect to the databases by using their domain accounts.

6.  Specify the **Database Configuration** for the SQL Server instance that will store the compliance and audit data. You must also specify where the database will be located and where the log information will be located.

7.  Click **Next** to continue with the MBAM Setup wizard.

**To install the Compliance and Audit Reports**

1.  Specify the remote SQL Server instance. For example, *&lt;ServerName&gt;*,where the Compliance and Audit Database are installed.

2.  Specify the name of the Compliance and Audit Database. By default, the database name is “MBAM Compliance Status”, but you can change the name when you install the Compliance and Audit Database.

3.  Click **Next** to continue.

4.  Select the SQL Server Reporting Services instance where the Compliance and Audit Reports will be installed. Provide the username and password used to access the compliance database.

5.  Click **Next** to continue with the MBAM Setup wizard.

**To install the Administration and Monitoring Server feature**

1.  Choose an option for the MBAM communication encryption. MBAM can encrypt the communication between the Recovery and Hardware Database and the Administration and Monitoring servers. If you choose the option to encrypt communication, you are asked to select the authority-provisioned certificate that is used for encryption.

2.  Click **Next** to continue.

3.  Specify the remote SQL Server instance, For example, *&lt;ServerName&gt;*, where the Compliance and Audit Database are installed.

4.  Specify the name of the Compliance and Audit Database. By default, the database name is MBAM Compliance Status, but, you can change the name when you install the Compliance and Audit Database.

5.  Click **Next** to continue.

6.  Specify the remote SQL Server instance. For example, *&lt;ServerName&gt;*,where the Recovery and Hardware Database are installed.

7.  Specify the name of the Recovery and Hardware Database. By default, the database name is **MBAM Recovery and Hardware**, but you can change the name when you install the Recovery and Hardware Database feature.

8.  Click **Next** to continue.

9.  Specify the URL for the “Home” of the SQL Server Reporting Services (SRS) site. The default Home location of a SQL Server Reporting Services site instance is at:

    http://*&lt;NameofMBAMReportsServer&gt;/*ReportServer

    **Note**  
    If you configured the SQL Server Reporting Services as a named instance, the URL resembles the following:http://*&lt;NameofMBAMReportsServer&gt;*/ReportServer\_*&lt;SRSInstanceName&gt;*



10. Click **Next** to continue.

11. Enter the **Port Number**, the **Host Name** (optional), and the **Installation Path** for the MBAM Administration and Monitoring server

    **Warning**  
    The port number that you specify must be an unused port number on the Administration and Monitoring server, unless you specify a unique host header name.



12. Click **Next** to continue with the MBAM Setup wizard.
~~~

5. 

   指定是否要使用 Microsoft 更新，協助保護您的電腦安全性，然後按 **[下一步]**。

6. 當選取的 MBAM 功能資訊完成後，您就可以使用 [設定] 嚮導開始進行 MBAM 安裝了。 如果您必須檢查或變更您的安裝設定，請按一下 [**返回**]，在嚮導中移動。 按一下 [**安裝**] 以開始安裝。 按一下 [**取消**] 結束嚮導。 安裝程式會安裝您所選取的 MBAM 功能，並通知您安裝已完成。

7. 按一下 **[完成] 結束**嚮導。

8. 在安裝 MBAM 伺服器功能之後，將使用者新增至適當的 MBAM 角色。 如需詳細資訊，請參閱[規劃 MBAM 1.0 系統管理員角色](planning-for-mbam-10-administrator-roles.md)。

**安裝後的設定**

1.  MBAM 安裝完成後，您必須先新增使用者角色，才能在使用者存取 MBAM 管理網站中的功能。 在 [管理及監視伺服器] 上，將使用者新增至下列本機群組。

    -   **MBAM 硬體使用者**：此本機群組的成員可以存取 MBAM 管理網站中的硬體功能。

    -   **MBAM 支援人員**：此本機群組的成員可以存取 MBAM 管理網站中的 [磁碟機復原] 和 [管理受信任的平臺模組（TPM）] 功能。 [磁碟機復原] 和 [管理 TPM] 中的所有欄位都是技術支援人員的必要欄位。

    -   **MBAM 高級支援人員的使用者**：此本機群組的成員可以高級存取磁片磁碟機，並在 MBAM 管理網站中管理 TPM 功能。 針對高級支援人員的使用者，磁片磁碟機復原只需要 [金鑰識別碼] 欄位。 在 [管理 TPM] 中，只需要 [電腦網域] 欄位和 [電腦名稱稱] 欄位。

2.  在 [管理與監控伺服器]、[合規性] 和 [審核] 資料庫，以及駐留合規性和審核報告的伺服器上，將使用者新增至下列當地群組，以授予他們存取 MBAM 管理網站中的 [報告] 功能。

    -   **MBAM 報表使用者**：此本機群組的成員可以存取 MBAM 管理網站中的報表。

    **注意**  
    **MBAM 報告**的使用者或群組成員資格使用者的本機群組必須在已安裝 MBAM 管理和監控伺服器功能、合規性和審核資料庫以及合規性和審核報告的所有電腦上維持。



## 驗證 MBAM 伺服器功能安裝


當 MBAM 伺服器功能安裝完成後，您應該確認安裝已成功設定 MBAM 的所有必要功能。 使用下列程式來確認 MBAM 服務是否正常運作。

**驗證 MBAM 安裝**

1. 在每個已部署 MBAM 功能的伺服器上，開啟 [**控制台**]，按一下 [**程式**]，然後按一下 [**程式和功能**]。 確認 [**程式和功能**] 清單中出現 [ **Microsoft BitLocker 管理及監視**]。

   **注意**  
   若要驗證 MBAM 安裝，您必須使用在每個伺服器上都有本機電腦管理認證的網域帳戶。



2. 在已安裝復原與硬體資料庫的伺服器上，開啟 SQL Server Management Studio 並確認已安裝**MBAM 復原與硬體**資料庫。

3. 在已安裝合規性和審核資料庫的伺服器上，開啟 SQL Server Management Studio 並確認已安裝**MBAM 合規性狀態**資料庫。

4. 在已安裝合規性和審核報告的伺服器上，以系統管理許可權開啟網頁瀏覽器，並流覽至 SQL Server Reporting Services 網站的 "Home"。

   SQL Server Reporting Services 網站實例的預設首頁位置可以在 HTTP:// <em> &lt; NameofMBAMReportsServer &gt; </em> /Reports.aspx. 中找到 若要尋找實際的 URL，請使用 Reporting Services Configuration Manager 工具，然後選取在安裝期間指定的實例。

   確認已列出名為「**馬爾他規範**」的資料夾，且包含五個報表和一個資料來源。

   **注意**  
   如果 SQL Server Reporting Services 已設定為命名實例，URL 應該會類似下列內容： HTTP：//* &lt; NameofMBAMReportsServer &gt; */Reports\_* &lt; SRSInstanceName &gt; *



5. 在已安裝 [管理及監視] 功能的伺服器上，執行 [**伺服器管理員**] 並流覽至 [**角色**]，選取 [ **Web 服務器（iis）**]，然後按一下 [**網際網路資訊服務（iis）管理員**]。 在 **[連線**] 中流覽至 [ * &lt; computername &gt; *]，按一下 [**網站**]，然後按一下 [ **Microsoft BitLocker 管理與監視**]。 確認 [ **MBAMAdministrationService**]、[ **MBAMComplianceStatusService**] 和 [ **MBAMRecoveryAndHardwareService** ] 都已列出。

6. 在已安裝 [管理及監視] 功能的伺服器上，以系統管理許可權開啟網頁瀏覽器，並流覽至 MBAM 網站中的下列位置，確認他們已順利載入：

   -   *HTTP:// &lt; computername &gt; /default.aspx*並確認流覽與報告的每個連結

   -   *HTTP:// &lt; computername &gt; /MBAMAdministrationService/AdministrationService.svc*

   -   *HTTP:// &lt; computername &gt; /MBAMComplianceStatusService/StatusReportingService.svc*

   -   *HTTP:// &lt; computername &gt; /MBAMRecoveryAndHardwareService/CoreService.svc*

   **注意**  
   通常，服務會安裝在預設埠80，而不需要網路加密。 如果服務安裝在不同的埠上，請變更 Url，使其包含適當的埠。 例如，HTTP://* &lt; computername &gt; ： &lt; port &gt; */default.aspx 或 HTTP:// <em> &lt; hostheadername &gt; / </em> default .aspx

   如果服務是以網路加密的方式安裝，請將 HTTP://變更為 HTTPs://。



~~~
Verify that each web page loads successfully.
~~~

## 相關主題


[部署 MBAM 1.0 伺服器基礎結構](deploying-the-mbam-10-server-infrastructure.md)









