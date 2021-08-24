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
ms.openlocfilehash: 4dffe2e2dcb82866b86a3ac281aca8a0dcaab686
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910658"
---
# <a name="how-to-install-and-configure-mbam-on-a-single-server"></a>如何在單一伺服器上安裝及設定 MBAM


本主題中的程式說明如何在單一伺服器上 (拓撲中安裝 MICROSOFT BitLocker 系統管理與) 管理與監控應用程式。 只在測試環境中使用單一伺服器組式。 針對生產環境，請使用兩個或多個伺服器。 如果您是使用 Configuration Manager 拓撲來安裝 Microsoft BitLocker 系統管理與監控，請參閱使用 Configuration Manager 部署[MICROSOFT BITLocker 。](deploying-mbam-with-configuration-manager-mbam2.md)

下圖顯示單一伺服器架構的範例。 有關資料庫和功能的描述，請參閱[適用于 2.0 的高層級架構。](high-level-architecture-for-mbam-20-mbam-2.md)

![管理 2 單一伺服器部署拓撲。](images/mbam2-1-server.gif)

每個伺服器功能都有特定的先決條件。 若要確認您符合先決條件和硬體和軟體需求，請參閱[：：請見 《部署](mbam-20-deployment-prerequisites-mbam-2.md)先決條件》 和 "受支援群組原則」的 "部署先決條件"和["2.0 支援的配置」。](mbam-20-supported-configurations-mbam-2.md) 此外，某些功能也有在安裝過程中必須提供的資訊，以成功部署此功能。 您也應該在開始部署時，先檢查[準備您的環境以準備您的環境以用於 2.0。](preparing-your-environment-for-mbam-20-mbam-2.md)

**注意**  
若要取得設定記錄檔案，您可以使用 Msiexec 套件和 **/L** &lt; 位置 &gt; 選項來安裝 MSM。 記錄檔案會以您指定的位置建立。

其他設定記錄檔案會建立于安裝 IBMM 的使用者伺服器上 %temp% 資料夾中。



## <a name="to-install-mbam-server-features-on-a-single-server"></a>若要在單一伺服器上安裝 IBMM Server 功能


下列步驟說明如何安裝一般 <管理及管理管理計畫>功能。

**若要開始安裝 IBMM Server 功能**

1.  在您想要安裝 IBMM 的伺服器上，執行 **MBAMSetup.exe以啟動 ** 該 IBMM 安裝精靈。

2.  在 [ **歡迎使用** > 頁面上，選擇選取 [ **客戶經驗改進計畫**>，然後按一下 [ **開始**> 。

3.  閱讀並接受 Microsoft 軟體授權合約，然後按一下 **[下** 一步？

4.  在 [**拓撲選取範圍」** 頁面上****，選取獨立拓撲，然後按一下 [下**一步**。

5.  在選取 **要安裝的功能頁面上** ，選取您想要安裝的功能。 根據預設，已選取所有用於安裝的的  。 在同一部電腦上安裝的功能必須同時安裝。 清除您想要在其他地方安裝的任何功能的核取方塊。 您必須按照下列順序安裝 ：：

    -   修復資料庫

    -   合規性與稽核資料庫

    -   合規性和稽核報告

    -   Self-Service伺服器

    -   系統管理與監控伺服器

    -   B0 B0 B0 B0 B0 B0 B0 B0 B

    **注意**  
    安裝精靈會檢查安裝的先決條件，並顯示遺漏的先決條件。 如果符合所有先決條件，安裝會繼續。 如果偵測到缺少的先決條件，您必須解決缺少的先決條件，然後再按一下 **[檢查先決條件**> 。 如果這次符合所有先決條件，安裝會繼續。



6.  在設定 **網路通訊安全性頁面上** ，選擇是否要加密管理與監控伺服器與用戶端上的 Web 服務之間的通訊。 如果您決定加密通訊，請選取憑證授權單位所提供之憑證以用於加密。 您必須在此步驟之前建立憑證，才能在此頁面上選取憑證。

    **注意**  
    只有在您選取了 Self-Service 功能頁面上的入口網站或系統管理與監控伺服器功能時，此頁面 **才能** 顯示。



7.  按一下 **[下**一步），然後繼續下一組步驟來設定 [IBMM Server」 功能。

**若要設定 IBMM Server 功能**

1.  在設定**修復資料庫**頁面上，指定SQL Server實例名稱，以及儲存復原資料的資料庫名稱。 您也必須同時指定資料庫檔案的位置，以及記錄資訊的位置。

2.  按 \[**下一步**\] 繼續。

3.  在設定**合規性**和稽核資料庫頁面上，指定SQL Server實例名稱，以及儲存合規性和稽核資料的資料庫名稱。 您也必須指定資料庫檔案的位置，以及記錄資訊的位置。

4.  按 \[**下一步**\] 繼續。

5.  在設定**合規性**和稽核報告頁面上，指定 SQL Server Reporting Services 安裝合規性和稽核報告的實例，並提供網域使用者帳戶和密碼以存取合規性和稽核資料庫。 設定此帳戶的密碼永不過期。 使用者帳戶應該可以存取所有可供 "資料表使用者" 群組使用的資料。

6.  按 \[**下一步**\] 繼續。

7.  在設定入口 **Self-Service** 頁面上，輸入入口網站之埠號碼、主機名稱、虛擬目錄名稱Self-Service路徑。

    **注意**  
    您指定的埠號碼必須是系統管理與監控伺服器上未使用的埠號碼，除非您指定唯一的主機頭名稱。 如果您使用的是防火牆Windows，就會自動開啟埠。



8.  按 \[**下一步**\] 繼續。

9.  指定是否要使用 Microsoft Updates 來協助保護您的電腦安全性，然後按一下 [下 **一步**。 這不會在 Windows 中開啟自動更新。

10. 在設定 **管理與監控伺服器** 頁面上，輸入技術支援中心網站的埠號碼、主機名稱、虛擬目錄名稱和安裝路徑。

    **注意**  
    您指定的埠號碼必須是系統管理與監控伺服器上未使用的埠號碼，除非您指定唯一的主機頭名稱。 如果您使用的是防火牆Windows，就會自動開啟埠。



11. 在 [**安裝摘要」** 頁面上，查看要安裝的功能清單，然後按一下 [安裝**** 中以開始安裝該 M1 功能。 如果您 **必須** 檢查或變更安裝設定，請按一下 [返回以在精靈中移回，或按一下 **[取消** 以離開安裝程式> 。 安裝程式會安裝的  ，並通知您安裝已完成。

12. 按一下 **[完成** 並結束精靈。 安裝 Microsoft BitLocker 系統管理和監控伺服器功能之後，請繼續下一節並完成步驟，將使用者新加入 Microsoft BitLocker 系統管理與監控角色。 有關角色詳細資訊，請參閱[規劃適用于管理管理員角色的 。。](planning-for-mbam-20-administrator-roles-mbam-2.md)

**若要執行安裝後組**

1.  在系統管理與監控伺服器上，將使用者新增到下列本地群組，讓他們能夠存取 IBMM 技術支援中心網站功能：

    -   **PMM Helpdesk 使用者**：此本地群組的成員可以存取位於 PMM 系統管理與監控網站的雲端硬碟修復及管理 TPM 功能。 雲端硬碟修復及管理 TPM 中的所有欄位都是 Helpdesk User 的必要欄位。

    -   **PMM 進一步支援人員使用者**：此本地群組的成員可進一步存取位於 PMM 系統管理與監控網站的雲端硬碟修復及管理 TPM 功能。 針對進一步服務台使用者，在雲端硬碟修復中只需要金鑰 **識別碼** 欄位。 在管理 TPM 中，只需要電腦 **網** 域欄位和 **電腦名稱稱** 欄位。

2.  在系統管理與監控伺服器上，將使用者新增到下列本地群組，讓他們能夠存取在 IBMM 系統管理與監控網站上的報告功能：

    -   **B0 網管報告使用者**：此本地群組的成員可以存取該區管理與監控網站上的報告功能。

    -   使用Self-Service名稱、注意事項文字及其他公司特定資訊將網站商標。 有關指示，請參閱 [如何為網站入口網站Self-Service品牌](how-to-brand-the-self-service-portal.md)。

    **注意**  
    您必須在已安裝的 IBMM 系統管理與監控伺服器功能、合規性和稽核資料庫，以及合規性和稽核報告的所有電腦上，維護**同一個同一個使用者或群組的成員資格。.** 建議這麼做的方式是建立網域安全性群組，並新增該網域群組至每個本地的 "DNSM 報表使用者"群組。 當您使用此程式時，請以網域群組的方式管理群組成員資格。



## <a name="validating-the-mbam-server-feature-installation"></a>驗證安裝的 IBMM Server 功能


完成 Microsoft BitLocker 系統管理與監控安裝後，請驗證安裝已成功設定 BitLocker 管理所需的所有必要的 <企業管理的<a0> </a0> <a1> </a1> <a2>。</a2> 請使用下列程式來確認該服務是否運作。

**若要驗證安裝的 IBMM Server 功能**

1. 在部署了一個 IBMM 功能的每一個伺服器上，開啟 **控制台**。 選取 **程式**，然後選取 **程式和功能**。 確認 **Microsoft BitLocker 系統管理與監控** 會顯示在程式和 **功能清單中** 。

   **注意**  
   若要驗證安裝，您必須在每個伺服器上使用具有本地電腦管理認證之網域帳戶。



2. On the server where the Recovery Database is installed, open SQL Server Management Studio, and verify that the **MBAM Recovery and Hardware** database is installed.

3. On the server where the Compliance and Audit Database is installed, open SQL Server Management Studio, and verify that the **MBAM Compliance Status Database** is installed.

4. 在安裝合規性和稽核報表的伺服器上，開啟具有系統管理認證的網頁瀏覽器，然後流覽至該網站的「SQL Server Reporting Services」。

   網站實例的預設主SQL Server Reporting Services位於 <em> &lt; Nameof導 HTTP:// ReportsServer &gt; </em> /Reports。 若要尋找實際的 URL，請使用 Reporting Services Configuration Manager 工具，然後選取在設定期間指定的實例。

   確認名為 Microsoft BitLocker 系統管理與監控的報表資料夾包含稱為 **MaltaDataSource** 的資料來源，且 **en-us** 資料夾包含四個報表。

   **注意**  
   如果SQL Server Reporting Services為已命名實例，URL 應該應該類似下列專案：HTTP://* &lt; NAMEOF金銀MReportsServer &gt; */Reports\_* &lt; SRSInstanceName &gt; *



~~~
**Note**  
If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server. If you then go to the Administration and Monitoring website and select a report, the following message appears: “Only Secure Content is Displayed.” To show the report, click **Show All Content**.
~~~



5. 在已安裝系統管理與監控功能的伺服器上，執行 **Server Manager** 並流覽至 **角色**。 選取 **[web Server (IIS) ，** 然後按一下 **[IIS Internet Information Services ([) Manager> 。**

6. 在**連接中，** 流覽至* &lt; 電腦 &gt; 名稱*，選取**網站**，然後選取**Microsoft BitLocker 系統管理與監控**。 確認**已列出以下專案：即：已列出 ：：即是 ：：：已**列出 ：即是******：：一**項作業，一項是一項作業。」 ****

7. 在安裝系統管理與監控功能與Self-Service入口網站的伺服器上，開啟具有系統管理認證的網頁瀏覽器，並流覽至下列位置，確認它們已成功載入：

   -   *HTTP:// &lt; 主機名稱 &gt; /HelpDesk/default.aspx* 並確認流覽和報表的每個連結

   -   *HTTP:// &lt; 主機名稱 &gt; /SelfService&gt;/*

   -   *HTTP:// &lt; 電腦名稱稱 &gt; /A0/2012/4008/444-2013-2013-2013-2013-2013-2013*

   -   *HTTP:// &lt; 主機名稱 &gt; /*

   -   *HTTP:// &lt; 電腦名稱稱 &gt; /*

   -   *HTTP:// &lt; 電腦名稱稱 &gt; /*

   **注意**  
   假設伺服器功能是安裝在預設埠上，沒有網路加密。 如果您在不同的埠或虛擬目錄上安裝伺服器功能，請變更 URL 以包含適當的埠，例如*HTTP:// &lt; hostname &gt; ： port &lt; &gt; /helpDesk/default.asp*x 或 HTTP://* &lt; &gt; hostname：port &lt; &gt; / &lt; virtualdirectory &gt; /default.aspx*

   如果伺服器功能是使用網路加密安裝，請變更 HTTP:// HTTPs://。



## <a name="related-topics"></a>相關主題


[部署 MBAM 2.0 伺服器基礎結構](deploying-the-mbam-20-server-infrastructure-mbam-2.md)









