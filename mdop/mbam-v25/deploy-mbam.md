---
title: 以獨立設定進行 MBAM 2.5 部署
description: 介紹如何在獨立式組式中部署 2.5。
author: Deland-Han
ms.reviewer: dcscontentpm
manager: dansimp
ms.author: delhan
ms.sitesec: library
ms.prod: w10
ms.date: 09/16/2019
ms.openlocfilehash: 1ceccf3973bb131484f91917c2b80cd676d1c31b
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910468"
---
# <a name="deploying-mbam-25-in-a-standalone-configuration"></a>在獨立配置中部署 OFFICEM 2.5

本文提供在獨立組式中安裝 Microsoft BitLocker 系統管理與監控 (2.5) 的逐步指示。 在本指南中，我們將使用雙伺服器組組。 這兩個伺服器之一是執行 2012 年 2012 Microsoft SQL Server伺服器。 此伺服器將託管的為 IBMM 資料庫和報表。 另一個伺服器會Windows Server 2012「系統管理與監控伺服器」和「自助入口網站」的網頁伺服器。

## <a name="preparation-steps-before-installing-mbam-25-server-software"></a>安裝 IBMM 2.5 伺服器軟體之前的準備步驟

### <a name="step-1-installation-and-configuration-of-servers"></a>步驟 1：伺服器的安裝與配置

在開始配置 IBMM 2.5 之前，我們必須確認這兩個伺服器都是根據每個 IBMM 系統需求進行配置。 請參閱 [最低系統需求 ，](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-supported-configurations#-mbam-server-system-requirements)然後選取符合這些要求的組組。 

#### <a name="step-11-deploying-prerequisites-for-database-and-reporting-server"></a>步驟 1.1：部署資料庫與報表伺服器的先決條件

1. 安裝並設定在 Windows 或更新版本上執行 Server 2008 R2 (或更新) 伺服器。

2. 安裝 Windows PowerShell 3.0。

3. 安裝 Microsoft SQL Server 2008 R2 或包含最新 Service Pack 的較新版本。 如果您要安裝適用于 SQL SERVER M 的新 SQL Server實例，請確定您安裝的 SQL Server包含 SQL_Latin1_General_CP1_CI_AS排序規則。 您必須安裝下列SQL Server功能：

    * 資料庫引擎
    * Reporting Services
    * 用戶端工具連接
    * 管理工具 – 完成

    > [!Note]
    > 您也可以選擇在 透明資料加密 (中) [TDE SQL Server。](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-security-considerations)

    SQL Server Reporting Services必須以「原生」模式安裝及安裝，而不是在未SharePoint模式。

    ![必要的SQL Server功能。](images/deploying-MBAM-1.png)

4. 如果您打算將 SSL 用於系統管理與監控網站，請確定您設定 SQL Server Reporting Services (SSRS) 使用安全通訊端層 (SSL) 通訊協定，然後再設定系統管理與監控網站。 否則，報表功能會使用未加密 (HTTP) 資料傳輸，而非加密 (HTTPS) 。

    您可以遵循在 [原生模式報表伺服器上](https://docs.microsoft.com/sql/reporting-services/security/configure-ssl-connections-on-a-native-mode-report-server?view=sql-server-2017) 設定 SSL 連線，在報表伺服器上設定 SSL。
    
    > [!Note]
    > 您可以按照您的SQL Server安裝指南來安裝SQL Server安裝SQL Server。 連結如下所示：
        > * [SQL Server 2014](https://docs.microsoft.com/sql/sql-server/install/planning-a-sql-server-installation?view=sql-server-2014)
        > * [SQL Server 2012](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/bb500442(v=sql.110))
        > * [SQL Server 2008 R2](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/bb500442(v=sql.110))

5. 在 SQL Server 安裝之後，請確定您于 SQL Server 中設定使用者帳戶，並將下列許可權指派給使用者，該使用者將設定資料庫伺服器上之 <SQLM 資料庫及報告角色。

    物件實例SQL Server：
        
    * dbcreator
    * processadmin

    實例的SQL Server Reporting Services：
    
    * 建立資料夾
    * 發佈報表

您的資料庫伺服器已準備就緒，可進行針對 2.5 個角色進行配置。 讓我們移至下一個伺服器。

#### <a name="step-12-deploying-prerequisites-for-administration-and-monitoring-server"></a>步驟 1.2：部署系統管理與監控伺服器的先決條件

選擇符合硬體組配置的伺服器，如[INM 系統需求檔所說明。](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-supported-configurations#-mbam-server-system-requirements) 它必須在 Server 2008 R2 Windows或更新的作業系統中，連同最新的 Service Pack 和更新一起執行。 伺服器準備就緒後，請安裝下列角色和功能：

##### <a name="roles"></a>角色

* Web Server (IIS) 管理工具 (選取 IIS 管理腳本和工具。) 

* Web Server 角色服務

    * 一般 HTTP 功能<br />
      靜態內容<br />
      預設檔

    * 應用程式開發<br />
      ASP.NET<br />
      .NET 可擴展<br />
      ISAPI 擴充功能<br />
      ISAPI 篩選<br />
      安全性<br />
      Windows 驗證<br />
      要求篩選

    * Web Service IIS 管理工具

##### <a name="feature"></a>功能

* .NET Framework 4.5 個功能
  
  * Microsoft .NET Framework 4.5
  
    針對 Windows Server 2012或 Windows Server 2012 R2，.NET Framework已安裝適用于這些版本的 Windows 4.5。 不過，您必須啟用它。
  
    針對 Windows Server 2008 R2，.NET Framework 4.5 不包含在 Windows伺服器 2008 R2 中。 因此，您必須下載 .NET Framework 4.5 並個別安裝。
  
  * WCF 啟用<br />
    HTTP 啟用<br />
    非 HTTP 啟用
  
  * TCP 啟用
  
  * Windows程式啟用服務：<br />
    程式模型<br />
    .NET Framework環境<br />
    組組 API

若要讓自助入口網站能夠使用，您也應該下載並安裝[ASP.NET MVC 4.0。](https://go.microsoft.com/fwlink/?linkid=392271)

下一個步驟是在 Active Directory 中建立所需的可進行區管理管理的使用者和群組。

### <a name="step-2-creating-users-and-groups-in-active-directory-domain-services"></a>步驟 2：在 Active Directory 網域服務中建立使用者和群組
 
作為先決條件的一部分，您必須定義某些角色和帳戶，以便提供特定伺服器和功能的安全性和存取權，例如 SQL Server 實例上執行的資料庫，以及系統管理與監控伺服器上執行的網頁應用程式。

在 Active Directory 中建立下列群組和使用者。  (您可以使用群組和使用者的任何名稱。) 使用者不需要擁有更大的使用者許可權。 網域使用者帳戶已足夠。 您必須在配置 2.5 的期間指定這些群組的名稱：

* **國際管理與應用管理**  

  **類型**：網域使用者

  **描述**：擁有合規性與稽核資料庫及修復資料庫讀取或寫入權限的網域使用者，可讓 Web 應用程式存取這些資料庫中的資料和報表。 應用程式庫也會用於 Web 應用程式。

  **在配置 (期間，帳戶 **角色) ：

  1. Web 服務應用程式庫網域帳戶

  2. 合規性與稽核資料庫及復原資料庫讀取/寫入報表的使用者

* **慢化管理**

  **類型**：網域使用者

  **描述**：網域使用者Read-Only合規性和稽核資料庫的存取權，讓報表能夠存取此資料庫中的合規性和稽核資料。 這也是本地登錄實例用來存取合規性SQL Server Reporting Services稽核資料庫的網域使用者帳戶。

  **在配置 (期間，帳戶 **角色) ：

  1. 報表的合規性和稽核資料庫唯讀使用者

  2. 合規性與稽核資料庫網域使用者帳戶

* **2010 年 12 月 15 日**

  **類型**：網域群組

  **描述**：：B0 進一步說明中心使用者存取群組：成員可存取系統管理與監控網站所有區域之網域使用者群組。 擁有此角色的使用者在協助使用者復原磁片磁碟機時，必須只輸入修復金鑰，而不是使用者的網域和使用者名稱。 如果使用者是同時是一個成員，且同時是 <管理及服務中心進一階段服務人員使用者群組的成員，則此為<a0>：</a1><a2></a2>。<a3></a3><a4>，</a4><a5></a5>則<<a6></a6><a7></a7><a8>進</a7><a7></a7><a8></a8><a8><A8

  **在配置 (管理 **模式時，帳戶角色) ：：管理管理中心進一步說明台使用者

* **管理與管理與管理**

  **類型**：網域群組

  **描述**：PMM Helpdesk 使用者存取群組：網域使用者群組，其成員可以存取管理 TPM 和雲端硬碟修復區域 ，以及管理及監控網站的網域使用者。 擁有此角色的人在使用任一選項時，必須填入所有欄位。 這包括使用者的網域和帳戶名稱。

  **在配置 (管理 **模式時，帳戶角色) ：

* **美國國際管理學院**

  **類型**：網域群組

  **描述**：網域使用者群組，其成員可唯讀存取系統管理與監控網站的報表區域。

  **在配置 (期間，帳戶 **角色) ：

  1. 報表唯讀網域存取群組

  2. "B0 資料包表使用者存取群組

### <a name="step-3-optional-configure-and-install-ssl-certificate-on-administration-and-monitoring-server"></a>步驟 3 (選擇性) ：在系統管理與監控伺服器上設定及安裝 SSL 憑證

雖然這是選擇性的，我們強烈建議您使用憑證，協助保護管理與監控網站與 Self-Service網站之間的通訊。 基於明顯的安全性原因，我們不建議您使用自我簽署憑證。 我們建議您從信任的憑證授權單位使用 Web Server 類型憑證。 若要這麼做，您可以參照 KB 中的 「使用憑證授權單位核准的憑證」一 [節](https://support.microsoft.com/help/2754259)2754259。

憑證發行後，您應該將憑證新加到系統管理與監控伺服器的個人存放區。 若要新增憑證，請開啟本地電腦的憑證存放區。 若要這樣做，請執行下列步驟：

1. 以右選取開始，然後選取執行。

   ![選擇。](images/deploying-MBAM-2.png)

2. 輸入 "MMC.EXE" (不含引號) ， **然後選取**確定 。

   ![執行方塊。](images/deploying-MBAM-3.png) 

3. 選取 **您** 開啟的新 MMC 中的檔案，然後選取新增 **/移除管理單元**。
   
   ![選擇。](images/deploying-MBAM-4.png)

4. 反亮 **憑證** 管理單元， **然後選取新增**。

   ![新增或移除管理單元視窗。](images/deploying-MBAM-5.png)

5. 選取電腦 **帳戶** 選項，然後選取下 **一步**。
   
   ![憑證管理視窗。](images/deploying-MBAM-6.png)

6. 選取 **下一** 個畫面上的 Local Computer， **然後選取**完成 。
   
   ![選取電腦視窗。](images/deploying-MBAM-7.png)

7. 現在，您新增了憑證管理單元。 這可支援您處理電腦憑證存放區中的任何憑證。

   ![新增或移除管理單元視窗。](images/deploying-MBAM-8.png)

8. 將 Web 服務器憑證導入電腦的憑證存放區。

   現在您可以存取憑證管理單元，您可以將 Web 服務器憑證導入到電腦的憑證存放區。 若要這麼做，請遵循下列步驟。

9. 在管理 (中) 憑證，然後流覽至 **個人** 及 **憑證**。
   
   ![ (管理) 視窗中的憑證。](images/deploying-MBAM-9.png)

   > [!Note]
   > 可能不會列出憑證管理單元。 如果沒有，系統不會安裝任何憑證。

10. 以右選取 **憑證**，選取所有 **工作**， **然後選取匯出**。

    ![ (管理) 視窗中的憑證。](images/deploying-MBAM-10.png)

11. 當精靈啟動時，選取 下 **一步**。 流覽至您建立包含伺服器憑證和私密金鑰的檔案，然後選取下一 **步**。

    ![憑證導入精靈視窗。](images/deploying-MBAM-11.png)

12. 如果您在建立檔案時為檔案指定密碼，請輸入密碼。

   ![輸入密碼視窗。](images/deploying-MBAM-12.png)

   > [!Note]
   > 如果您想要 **從此電腦再次** 匯出金鑰組，請確定已選取將金鑰標記為可匯出選項。 做為額外的安全性措施，您可能會想要清除此選項，以確保沒有人可以備份您的私密金鑰。
 
13. 選取**下**一步 ，然後**** 選取要儲存憑證的憑證存放區。

    ![憑證導入精靈視窗。](images/deploying-MBAM-13.png)

    > [!Note]
    > 您應該 **選取個人，** 因為這是 Web 服務器憑證。 如果您將憑證包含在認證階層中，也會新增到此存放區。
 
14. 選取 **下一**步，然後 **選取**完成 。

    ![憑證導入精靈視窗。](images/deploying-MBAM-14.png)

現在，您將在個人憑證清單中看到 Web 服務器的伺服器憑證。 它會以伺服器的共同名稱表示。  (您可以在憑證的主題區段找到) 

進一步參考：

[MBAM 2.5 安全性考量](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-security-considerations)

[如何保護 MBAM 網站的規劃](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites)

下一個步驟是註冊應用程式庫帳戶的服務原則名稱。

### <a name="step-4-configuring-ssl-certificate-for-mbam-web-server"></a>步驟 4：為 IBMM Web Server 組建 SSL 憑證

如果您使用的是用戶端與伺服器之間的 SSL 通訊，您應該確認憑證具有增強型金鑰使用量 (1.3.6.1.5.5.7.3.1) 和 (1.3.6.1.5.5.7.3.2) 。 也就是說，您應該確認已新增伺服器驗證和用戶端驗證。

如果您在嘗試流覽服務 URL 時收到憑證錯誤，表示您使用的是以不同名稱發行的憑證，或是使用不正確的 URL 流覽。

雖然瀏覽器可能會提示您憑證錯誤訊息，但讓您繼續操作，但此為<a0> </a0> <a1>：</a1><a2></a2><a3>，</a3><a3></a3><a4></a4><a5>的</a5> <a6> </a6> <a7></ 您將注意到在驗證憑證相關錯誤中，請于 ：：在管理管理事件記錄中，顯示與證書相關的錯誤。 如果您使用別名來連接到系統管理與監控伺服器，您應該將憑證發行給別名名稱。 也就是說，憑證的主題名稱應為別名名稱，而本機伺服器的 DNS 名稱應新加到憑證的 Subject **Alternative Name** 欄位。

範例：

如果虛擬名稱是「bitlocker.contoso.com」，而 「ADMINSERVER.CONTOSO.COM」，憑證應該會發行至 bitlocker.contoso.com (主題名稱) ，而 adminserver.contoso.com 應該新加到憑證的 「主體 **替代** 名稱」欄位。

同樣地，如果您安裝了多個系統管理與監控伺服器，以使用負載平衡器來平衡負載，您應該將 SSL 憑證發行為虛擬名稱。 也就是說，憑證的主體名稱欄位應具有虛擬名稱，且所有本機伺服器的名稱應新增到憑證的 Subject **Alternative Name** 欄位中。

範例：

如果虛擬名稱是「bitlocker.contoso.com」，而伺服器是「adminserver1.contoso.com」和「adminiserver2.contoso.com」，則憑證應發行至 bitlocker.contoso.com (主題名稱) 和 adminserver1.contoso.com，而 adminiserver2.contoso.com 應該新加到憑證的 「主體 **替代** 名稱」欄位。

下列知識庫文章 [：KB](https://support.microsoft.com/help/2754259)2754259。

### <a name="step-5-register-spns-for-the-application-pool-account-and-configure-constrained-delegation"></a>步驟 5：註冊應用程式庫帳戶的 SPNS，並設定受限制的委派

> [!Note]
> 限制式委派僅適用于 2.5，2.5 Service Pack 1 及更新版則不需要。

若要讓 IBMM 伺服器驗證來自系統管理與監控網站及 Self-Service 入口網站的通訊，您必須在 Web 應用程式資料庫使用的網域帳戶下，為主機名註冊服務主體名稱 (SPN) 。 下列文章包含註冊 SPNs 的逐步指示：規劃如何 [保護的](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites)

設定 SPN 之後，您應該在 SPN 上設定受限制的委派。 若要這樣做，請執行下列步驟：

1. 請前往 Active Directory，在先前的步驟中尋找您為 APPM 網站所配置的 App 資料庫認證。

2. 以滑鼠右鍵按一下認證，然後選取 **屬性**。

3. 選取 **委派選項卡** 。

4. 選取 Kerberos 驗證選項。

5. 選取 **流覽**，然後再次流覽您的應用程式庫認證。 接著，您應該會看到應用程式集區帳戶上設定的所有 SPNs。  (SPN 應該類似"HTTP/bitlocker.fqdn.com") 。 將 SPN 與在安裝期間指定的主機名稱稱相同，以突顯該 SPN。

6. 選取 **[確定]**。

現在，您已經做好了先決條件。 在下列步驟中，您將在伺服器上安裝並設定該軟體。

## <a name="installing-and-configuring-mbam-25-server-software"></a>安裝及配置 IBMM 2.5 伺服器軟體

### <a name="step-6-install-mbam-25-server-software"></a>步驟 6：安裝 IBMM 2.5 伺服器軟體 

若要在資料庫伺服器及系統管理與監控伺服器上使用 Microsoft BitLocker 系統管理與監控設定精靈來安裝 IBMM Server 軟體，請遵循下列步驟。

1. 在您想要安裝 IBMM 的伺服器上，執行 MBAMserversetup.exe啟動 Microsoft BitLocker 系統管理與監控設定精靈。

2. 在歡迎頁面上，選取 下 **一步**。

3. 閱讀並接受 Microsoft 軟體授權合約，然後 **選取下一** 步以繼續安裝。

4. 決定是否在檢查更新時使用 Microsoft Update，然後選取下一 **步**。

5. 決定是否要參與客戶經驗改進計畫，然後選取下 **一步**。

6. 若要開始安裝， **請選取**安裝 。

7. 若要在安裝完之後設定伺服器功能，請選取精靈關閉後執行 **IBMM Server** Configuration 核取方塊。 Or, you can configure MBAM later by using the **MBAM Server Configuration** shortcut that the server installation creates on your **Start** menu.

8. 選取 **完成**。

若要詳細資訊，請參閱 [安裝 IBMM 2.5 Server Software](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software)。

### <a name="step-7-configure-mbam-25-database-and-reports-role"></a>步驟 7：設定 SQLM 2.5 資料庫與報表角色

在此步驟中，我們將使用 "INM 精靈" 來設定 2.5 資料庫和報告元件：

1. 使用精靈設定合規性和稽核資料庫及修復資料庫：
   
   1. 在您想要設定資料庫的伺服器上，啟動 **IBMM Server Configuration 精靈**。 您可以選取**開始功能表上的 "IBMM Server Configuration"** 來開啟精靈。 ****

   2. 選取 **新增功能，** 選取合規性 **與稽核資料庫**、 **修復資料庫和報表**，然後選取下 **一步**。 精靈會檢查資料庫的所有先決條件是否都符合。

   3. 如果先決條件檢查成功，請選取下 **一** 步繼續。 否則，請解決任何遺漏的先決條件，然後再次選取 **檢查先決條件**。
   
   4. 使用下列描述，在精靈中輸入域值：

2. 合規性和稽核資料庫

   |欄位   |描述|
   |-------|-------|
   |SQL Server名稱 |您用於配置合規性和稽核資料庫的伺服器名稱。 <br /> 您必須在合規性和稽核資料庫電腦上新增例外，才能在埠上啟用SQL Server流量。 預設的埠號碼是 1433。|
   |SQL Server資料庫實例    |將儲存合規性和稽核資料的資料庫實例名稱。 如果您使用的是預設實例，您必須將此欄位留白。 您也必須指定資料庫資訊的位置。|
   |資料庫名稱   |儲存合規性資料的資料庫名稱。 您必須記下您在此指定的資料庫名稱，因為您必須在稍後的步驟中提供這項資訊。|
   |讀取/寫入權限網域使用者或群組  |在步驟 2 中指定已配置的一組使用者名稱。|
   |唯讀存取網域使用者或群組   |在步驟 2 中指定由該使用者所配置的 。。|

3. 修復資料庫。

   |欄位   |描述|
   |-----|-----|
   |SQL Server名稱 |您用於配置修復資料庫的伺服器名稱。 您必須在修復資料庫電腦上新增例外，才能在埠上啟用SQL Server流量。 預設的埠號碼是 1433。|
   |SQL Server資料庫實例    |儲存復原資料的資料庫實例名稱。 如果您使用的是預設實例，您必須將此欄位留白。 您也必須指定資料庫資訊的位置。|
   |資料庫名稱   |儲存復原資料的資料庫名稱。|
   |讀取/寫入權限網域使用者或群組  |擁有此資料庫讀取/寫入權限的網域使用者或群組，可讓 Web 應用程式存取此資料庫中的資料和報表。 <br />如果您在此欄位中輸入使用者，其值必須與設定 Web 應用程式頁面上 **的 Web 服務應用程式** 組網域帳戶 **欄位中的值相同** 。 <br />如果您在此欄位中輸入群組，則設定 Web**應用程式**頁面上的**Web 服務**應用程式組網域帳戶欄位中的值必須是您在此欄位中輸入的群組成員。|
   
   完成專案後，請選取 下 **一步**。 精靈會檢查資料庫的所有先決條件是否都符合。
   
   如果先決條件檢查成功，請選取下 **一** 步繼續。 否則，請解決任何遺漏的先決條件，然後再次選取下 **一** 步。

4. 報告。

   |欄位   |描述|
   |----|----|
   |SQL Server Reporting Services實例  |將SQL Server Reporting Services報表的一個實例。 如果您使用的是預設實例，您必須將此欄位留白。|
   |報告角色網域群組 |如步驟 2 所述，指定該名的 。。|
   |SQL Server名稱 |配置合規性和稽核資料庫的伺服器名稱。|
   |SQL Server資料庫實例    |已配置合規性和稽核資料的資料庫實例名稱。 如果您使用的是預設實例，您必須將此欄位留白。 <br />您必須在報表電腦上新增例外，才能在 Reporting Server 埠上啟用傳入流量。  (預設埠為 80.) |
   |資料庫名稱|  合規性與稽核資料庫的名稱。 根據預設，資料庫名稱為 "SQLM 合規性狀態」。|
   |合規性和稽核資料庫網域帳戶    |在步驟 2 中指定由該使用者所配置的 。。|
   
   完成專案後，請選取 下 **一步**。 精靈會檢查是否符合報告功能的所有先決條件。 選取 [下一步] 以繼續。 在摘要 **頁面上** ，查看要新增的功能。
   
   若要詳細資訊，請參閱下列文章： [如何設定：如何設定 ：2.5 資料庫](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases)。

### <a name="step-8-configure-the-mbam-25-web-applications-role"></a>步驟 8：設定 2.5 WEB 應用程式角色

1. 在您想要設定 Web 應用程式的伺服器上，啟動 IBMM Server Configuration 精靈。 您可以選取**開始功能表上的 "IBMM Server Configuration"** 來開啟精靈。 ****

2. 選取 **新增功能，** 選取 **管理與監控網站** 及自助 **入口網站**，然後選取下 **一步**。 精靈會檢查資料庫的所有先決條件是否都符合。

3. 如果先決條件檢查成功，請選取下 **一** 步繼續。 否則，請解決任何遺漏的先決條件，然後再次選取 **檢查先決條件**。

4. 使用下列描述在精靈中輸入域值。

   |欄位   |描述|
   |-----|-----|
   |安全性憑證    |在步驟 3 中選取先前建立憑證，以選擇性地加密 Web 服務與您用於管理與監控網站之伺服器之間的通訊。 如果您選取了請勿使用憑證，表示您的 Web 通訊可能不安全。|
   |主機名稱   |您用於配置系統管理與監控網站的主機名稱稱。 <br />它不需要是機器的主機名稱，可以是任何專案。 不過，如果 hostname 與電腦的 netbios 名稱不同，您必須建立 A 記錄，並確保 SPN 使用自訂主機名稱，而不是 netbios 名稱。 這是負載平衡案例的常見情況。|
   |安裝路徑   |您安裝系統管理與監控網站的路徑。|
   |連接埠    |用於網站通訊的埠號碼。 <br /> 您必須設定防火牆例外，才能透過指定的埠啟用通訊。|
   |Web 服務應用程式資料庫網域帳戶和密碼    |指定在步驟 2 中已設成的一個使用者帳戶和密碼。 <br /> 為了提升安全性，請設定認證中指定的帳號具有有限的使用者許可權。 此外，將帳戶的密碼設為永不過期。|

5. 確認內建的 IIS_IUSRS 帳戶或應用程式資料庫帳戶已新增到驗證後的類比用戶端，**** 以及以批次處理**工作**本地安全性設定登入。

   若要檢查帳戶是否已新增到本地安全性設定，請開啟 Local **Security Policy**編輯器、展開 Local **Policy**節點、選取使用者**許可權**指派節點，然後按兩下**** 驗證後類比用戶端，然後以**** 批次處理工作原則登入右側窗格中。

6. 使用下欄欄位描述來設定合規性和稽核資料庫精靈中的連接資訊。
   |欄位   |描述|
   |------|------|
   |SQL Server名稱 |配置合規性和稽核資料庫的伺服器名稱。|
   |SQL Server資料庫實例    |例如，SQL Server (，) 合規性和稽核資料庫的範例 \<Server Name\> 名稱。 如果您使用的是預設實例，請保留此空白。|
   |資料庫名稱   |合規性與稽核資料庫的名稱。 根據預設，它是「「「管理與規範狀態」。|

7. 使用下欄欄位描述來設定修復資料庫精靈中的連接資訊。
   |欄位   |描述|
   |----|----|
   |SQL Server名稱 |已建立修復資料庫的伺服器名稱。|
   |SQL Server資料庫實例    |例如，已SQL Server (復原資料庫) 實例 \<Server Name\> 的名稱。 如果您使用的是預設實例，請保留此空白。|
   |資料庫名稱   |修復資料庫的名稱。 根據預設，它是「「管理及硬體」。|

8. 使用下列描述在精靈中輸入域值，以設定系統管理與監控網站。
   |欄位   |描述|
   |----|----|
   |進位服務台角色網域群組 |在步驟 2 中指定已配置的 ：請指定該名稱。|
   |Helpdesk 角色網域群組  |在步驟 2 中指定已配置的一組名稱。|
   |使用System Center Configuration Manager整合 |選取以清除此核取方塊。     |
   |報告角色網域群組 |指定步驟 2 中所配置的一組名稱。    |
   |SQL Server Reporting ServicesURL   |指定 SSRS 伺服器的 Web 服務 URL，其中會針對該伺服器配置了該 URLM 報表。 您可以在資料庫伺服器上登陸 Reporting Services Configuration Manager，以尋找這項資訊。 <br /> 完整功能變數名稱範例： https://MyReportServer.Contoso.com/ReportServer <br />自訂主機名稱範例： https://MyReportServer/ReportServer|
   |虛擬目錄   |系統管理與監控網站的虛擬目錄。 此名稱會對應到伺服器上網站的實體目錄，並附加至網站的主機名稱稱。 例如： <br />HTTP () ：// *\<host name\>* ： *\<port\>* /HelpDesk/ <br />如果您未指定虛擬目錄，將會使用 HelpDesk 的值。     |

9. 使用下列描述在精靈中輸入域值，以設定Self-Service入口網站。

   |欄位   |描述|
   |----|----|
   |虛擬目錄   |Web 應用程式的虛擬目錄。 此名稱會對應到伺服器上網站的實體目錄，並附加至網站的主機名稱稱。 例如：<br />HTTP () ：// *\<host name\>* ： *\<port\>* /SelfService/<br /> 如果您未指定虛擬目錄，將會使用 "SelfService" 的值。|

10. 完成專案後，請選取 下 **一步**。 精靈會檢查 Web 應用程式的所有先決條件是否均符合。

11. 選取 **下一** 步以繼續。

12. 在摘要 **頁面上** ，查看要新增的功能。

13. 選取 **新增** 以將 Web 應用程式新增到伺服器， **然後選取**關閉 。

## <a name="customizing-and-validating-steps-after-installing-mbam-25-server-software"></a>安裝 IBMM 2.5 伺服器軟體後自訂及驗證步驟

### <a name="step-9-customizing-the-self-server-portal-for-your-organization"></a>步驟 9：自訂貴組織的自助伺服器入口網站

若要新增Self-Service通知文字、公司名稱、指向詳細資訊的指標等，以自訂 Self-Service 入口網站，請參閱自訂貴組織的 Self-Service [入口網站](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/customizing-the-self-service-portal-for-your-organization)。
 
### <a name="step-10-configure-the-self-server-portal-if-client-computers-cannot-access-the-cdn"></a>步驟 10：設定如果用戶端電腦無法存取CDN 

判斷用戶端電腦是否擁有 Microsoft AJAX 內容傳遞網路 (CDN) 。 此CDN為 Self-Service入口網站提供特定 JavaScript 檔案所需的存取權。 如果用戶端電腦無法存取Self-Service，您不設定 CDN入口網站，則只會顯示公司名稱和使用者所登錄的帳戶。 系統不會顯示錯誤訊息。

執行下列其中一項：

* 如果用戶端電腦能夠存取CDN，請不要執行任何操作。 您的Self-Service入口網站組組已完成。

* 如果用戶端電腦無法存取 CDN，請遵循在用戶端電腦無法存取 Microsoft Self-Service[時](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network)設定 Self-Service 入口網站中的步驟內容傳遞網路。

### <a name="step-11-validate-the-mbam-25-server-feature-configuration"></a>步驟 11：驗證 IBMM 2.5 伺服器功能組 

若要驗證您的 IBMM Server 部署以使用獨立拓撲，請遵循下列步驟。

1. 在每一個部署了一個 IBMM 功能的伺服器上，選取**控制台**  >  **程式**  >  **程式和功能**。 確認 **Microsoft BitLocker 系統管理與監控** 會顯示在程式和 **功能清單中** 。
   > [!Note]
   > 若要執行驗證，您必須在每個伺服器上使用具有本地電腦管理認證之網域帳戶。

2. 在已配置修復資料庫的伺服器上，開啟 SQL Server Management Studio，並驗證**已配置了 "IBMM 修復**與硬體" 資料庫。

3. 在已配置合規性和稽核資料庫的伺服器上，開啟 SQL Server Management Studio，並確認已配置了 [OMM 合規性狀態資料庫。

4. 在已配置報表功能的伺服器上，使用系統管理認證開啟網頁瀏覽器，然後流覽至 SQL Server Reporting Services 首頁。
   
   網站實例的預設首頁位置SQL Server Reporting Services如下：HTTP () ：// *\<MBAM Reports Server Name\>* ： *\<port\>* /Reports.aspx
   
   若要尋找實際的 URL，請使用 Reporting Services Configuration Manager 工具，然後選取在設定期間指定的實例。
   
5. 確認名為 Microsoft BitLocker 系統管理與監控的報告資料夾包含名為 MaltaDataSource 的資料來源。 此資料來源包含名稱代表語言區域 (例如 en-us) 。 報表會位在語言資料夾中。

   > [!Note]
   > 如果 SQL Server Reporting Services (SSRS) 已配置為命名實例，URL 應該類似下列專案：HTTP () ：// \<MBAM Reports Server Name\> ： \<port\> /Reports_\<SSRS Instance Name\>
   >
   > 如果 SSRS 未設定為使用安全通訊端層 (SSL) ，則當您安裝 HTTPM 伺服器時，報表的 URL 會設定為 "HTTP" 而不是 "HTTPS"。 如果您接著前往系統管理與監控網站 (又稱為 helpdesk) ，然後選取報表，您會收到下列訊息：「只顯示安全內容」。 若要顯示報表，請選取 顯示 **所有內容**。

6. 在系統管理與監控網站功能已配置的伺服器上，執行 Server Manager，流覽至角色，**** 然後選取 Web **Server (IIS) Internet Information Services (**  >  **IIS) ** Manager。

7. 在**連結**中，流覽至 \<computer name\> ，**** 然後選取  >  **網站 Microsoft BitLocker 系統管理與監控**。 確認下列專案已列出：

   * 美國管理與管理服務
   * 職稱：管理與管理
   * 請用同一個服務

8. 在系統管理與監控網站Self-Service的伺服器上，使用系統管理認證開啟網頁瀏覽器。

9. 流覽至下列網站，確認它們已成功載入：
   * HTTPs () ：// \<MBAM Administration Server Name\> ： \<port\> /HelpDesk/ (確認每個連結的流覽和報表) 
   * HTTP () ：// \<MBAM Administration Server Name\> ： \<port\> /SelfService/

   > [!Note]
   > 假設您在沒有網路加密的情況下，在預設埠上已佈建服務器功能。 如果您在不同的埠或虛擬目錄上佈建服務器功能，請變更 URL 以包含適當的埠。 例如：HTTP (s) ：// ： \<host name\> \<port\> /helpDesk/ HTTP (s \<host name\>) ：// ： \<port\> / \<virtualdirectory\> / 如果伺服器功能已配置為使用網路加密，請變更 HTTP:// HTTPs://。
   
10. 流覽至下列 Web 服務，確認它們已成功載入。 頁面隨即開啟，表示服務正在運作。 不過，頁面不會顯示中繼資料。

    * HTTP () ：// \<MBAM Administration Server Name> ： \<port> /HTTPMAdministrationService/AdministrationService.svc
    * HTTP () ：// \<MBAM Administration Server Name> ： \<port> /HTTPMUserSupportService/UserSupportService.svc
    * HTTP () ：// \<MBAM Administration Server Name> ： \<port> /HTTPMComplianceStatusService/StatusReportingService.svc
    * HTTP () ：// \<MBAM Administration Server Name> ： \<port> /HTTPMRecoveryAndWarewareService/CoreService.svc

### <a name="step-12-configure-the-mbam-group-policy-templates"></a>步驟 12：設定

若要部署 BM，您必須設定群組原則設定，以定義 BitLocker 磁片磁碟機加密的慢化管理部署設定。 若要完成這項工作，您必須將 IBMM 群組原則範本複製到可執行群組原則管理主控台 (GPMC) 或進位群組原則管理 (AGPM) 的伺服器或工作站，然後編輯設定。

> [!Important]
> 請勿變更 **BitLocker** 磁片磁碟機加密節點中的群組原則設定，否則無法正確使用。. 當您在 **MDOP MDM (BitLocker 管理) ** 節點中設定群組原則設定時，INM 會自動針對您設定 **BitLocker 磁片** 磁碟機加密設定。
 
#### <a name="copying-the-mbam-25-group-policy-templates"></a>複製 B0 B0 2.5 群群組原則範本

安裝 B0 電腦管理版用戶端之前，您必須將特定的 B0 專用群組原則物件 (GPO) 管理工作站。 這些 GPO 會定義 BitLocker 的慢化管理機制的實現設定。 您可以將群組原則範本複製到任何支援 Windows 型伺服器或用戶端電腦，且可以執行群組原則管理主控台 (GPMC) 或進位群組原則管理 (AGPM) 的伺服器或工作站。

如要詳細資訊，請參閱 [複製 B0 即為 B0 的 GROUP Policy Templates 的 2.5 群組原則範本](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/copying-the-mbam-25-group-policy-templates)。.」
 
#### <a name="editing-mbam-25-gpo-settings"></a>編輯的 2.5 GPO 設定

建立必要的 GPO 之後，您必須將 B0 即為組織的用戶端電腦部署 B0 的 B0 B0 B0 M1 群組原則設定 。 若要查看及建立 GPO，您必須安裝群組原則管理主控台 (GPMC) 或進 (群組原則管理) 。

For more information, see [Editing the MBAM 2.5 Group Policy Settings](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/editing-the-mbam-25-group-policy-settings) and [Planning for MBAM 2.5 Group Policy Requirements](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-group-policy-requirements).
 
### <a name="step-13-deploying-the-mbam-25-client"></a>步驟 13：部署管理及管理管理 2.5 用戶端

視您部署 Microsoft BitLocker 系統管理與監控用戶端軟體時的不同，您可以在組織的電腦中啟用 BitLocker，在使用者接收電腦之前，或之後，使用企業軟體部署系統來群組原則及部署 MICROSOFT BITM Client 軟體。
 
#### <a name="deploy-the-mbam-client-to-desktop-or-portable-computers"></a>將 MM 用戶端部署至桌上型電腦或可攜式電腦

設定群組原則設定之後，您可以使用企業軟體部署系統產品 ，例如 Microsoft System Center 2012 Configuration Manager 或 Active Directory Domain Services (AD DS) 來部署用於目的電腦的目的電腦中的 MICROSOFT WINDOWS Installer 檔案。 您可以使用 32 位或 64 位MbamClientSetup.exe或 32 位或 64 位MBAMClient.msi檔案。 這些專案會與一起提供，以及一起提供 。.

若要詳細資訊，請參閱[如何將電腦或膝上型電腦部署該電腦版 。.](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-25)
 
#### <a name="deploy-the-mbam-client-as-part-of-a-windows-deployment"></a>在部署中部署 WINDOWS用戶端

在接收電腦並集中進行配置的組織中，您可以在將任何使用者資料寫入之前，先在每部電腦上安裝管理 BitLocker 磁片磁碟機加密的一個。. 此程式的好處是，每部電腦都符合 BitLocker 規範。 此方法不依賴使用者動作，因為系統管理員已經加密電腦。 此案例的主要假設是，組織的政策是先安裝公司Windows圖像，再將電腦傳送給使用者。 如果群組原則設定設定為需要 PIN，系統會提示使用者在收到該政策後設定 PIN。

若要詳細資訊，請參閱[如何部署作為部署中之一部分的WINDOWS用戶端](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25)。
 
#### <a name="how-to-deploy-the-mbam-client-by-using-a-command-line"></a>如何使用命令列來部署

若要詳細資訊，請參閱 [如何使用命令列來部署此管理管理中心用戶端](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-deploy-the-mbam-client-by-using-a-command-line)。

#### <a name="post-deployment-of-clients"></a>用戶端部署後

現在，您已完成部署活動，您應該檢查下列記錄，並判斷用戶端是否成功報告給該名客戶。

## <a name="faq"></a>常見問題集

### <a name="how-to-create-a-load-balanced-iis-servers"></a>如何建立負載平衡 IIS 伺服器

* SPN 必須只註冊至 (名稱，例如：bitlocker.corp.net) ，而且不得註冊至個別 IIS 伺服器。

* 如果使用憑證，憑證必須同時將 FQDN 和 NetBIOS 名稱輸入到負載**** 平衡群組中所有 IIS 伺服器的主題替代名稱欄位中，並同時輸入為 (例如：bitlocker.corp.net) 。 否則，當您流覽負載平衡位址時，瀏覽器會報告憑證為不信任。

詳細資訊，請參閱[IIS 網路負載平衡及](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-high-availability#a-href-idbkmk-load-balanceaiis-network-load-balancing)[註冊應用程式庫帳戶的 SPNs。](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites#registering-spns-for-the-application-pool-account)

### <a name="how-to-configure-a-certificate"></a>如何設定憑證

* 您必須有兩個憑證。 一個憑證用於SQL，另一個則用於 IIS。 它們必須先安裝，才能開始安裝。

* 我們建議您使用安裝程式將憑證新增到 IIS 組web.config檔案。

* 如果憑證上的 「髮卡者」 欄位與伺服器名稱不相符，則該憑證將不會由該證書由該驗證程式接受。 在這種情況下，請從 IIS 主控台暫時建立自我簽署的憑證，並用於 Configurator。 這將會確保已安裝 SSL 和 HTTPS 的 Web App。 在此之後，您可以將憑證從 IIS 綁定變更為一個，以用於管理與管理管理管理網站。

### <a name="the-sql-permissions-requirement-for-installation"></a>安裝SQL許可權要求

建立一個帳戶，讓這個帳戶只擁有 SecurityAdmin、公用和 DBCreator 許可權。

請參閱 [：SQLM 資料庫組組 - 最低](https://blogs.technet.microsoft.com/dubaisec/2016/02/02/mbam-database-configuration-minimum-permissions/) 許可權以瞭解更多資訊。

> [!Note]
> * 在某些情況下，初始安裝和升級作業需要更多許可權。
> * 使用具有暫時 SA 的帳戶進行安裝。
> * 請勿在使用者帳戶的上下文啟動 Configurator (執行為) 沒有足夠許可權對 SQL Server 進行變更，因為這會造成安裝錯誤。
> * 您必須使用擁有帳戶許可權的帳戶登入SQL Server。 只有SQL Server或更新資料庫，才能遠端執行的  。 對於 SSRS 伺服器，您必須安裝 IBMM，並在當地執行 Configurator，以安裝或更新的就是 IBMM SSRS 報告。

### <a name="the-permission-required-for-spn-registration"></a>SPN 註冊所需的許可權

用於 IIS 入口網站安裝的帳戶必須擁有 Write ServicePrincipalName 和 Write 驗證 SPN 許可權。 沒有這些許可權，安裝會返回警告訊息，指出無法註冊 SPN。

> [!Note]
> 您會收到此警告訊息兩次。 這不表示 SPN 必須註冊兩個物件。

詳細資訊，請參閱使用「註冊 SPN 延後」錯誤訊息的[「註冊 SPN 設定失敗」。](https://support.microsoft.com/help/2754138/)

### <a name="did-i-have-to-update-the-admx-templates-to-the-latest-version"></a>我是否必須更新 ADMX 範本至最新版本？

將 ADMX 範本更新為最新版本之後，您就會在 GPO 的 <ADMM 根節點上看到多個作業系統選項。 例如，Windows 7、Windows 8.1及 Windows 10版本 1511 及更新版本。

若要進一步瞭解如何更新 ADMX 範本，請參閱下列文章：
* [如何下載及部署 MDOP 群組原則 (.admx) 範本](https://docs.microsoft.com/microsoft-desktop-optimization-pack/solutions/how-to-download-and-deploy-mdop-group-policy--admx--templates)
* [MBAM 2.5 群組原則需求規劃](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-group-policy-requirements)
* [Microsoft 桌面優化套件群組原則管理範本](https://www.microsoft.com/en-us/download/details.aspx?id=55531)
