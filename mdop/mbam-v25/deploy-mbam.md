---
title: 以獨立設定進行 MBAM 2.5 部署
description: 說明如何以獨立的設定部署 MBAM 2.5。
author: Deland-Han
ms.reviewer: dcscontentpm
manager: dansimp
ms.author: delhan
ms.sitesec: library
ms.prod: w10
ms.date: 09/16/2019
ms.openlocfilehash: 905eb7a40483a7a7b499d6dced8472331c87b838
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811751"
---
# 在獨立配置中部署 MBAM 2。5

本文提供在獨立設定中安裝 Microsoft BitLocker 管理和監控（MBAM）2.5 的逐步指示。 在本指南中，我們將使用雙伺服器設定。 這兩個伺服器的其中一個就是執行 Microsoft SQL Server 2012 的資料庫伺服器。 這個伺服器將裝載 MBAM 資料庫與報告。 額外的伺服器將是 Windows Server 2012，它是「管理和監控伺服器」和「自助服務入口網站」。

## 安裝 MBAM 2.5 server 軟體之前的準備步驟

### 步驟1：伺服器的安裝與設定

開始設定 MBAM 2.5 之前，我們必須確定兩個伺服器都設定為每個 MBAM 的系統需求。 請參閱[MBAM 最低系統需求](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-supported-configurations#-mbam-server-system-requirements)，然後選取符合這些需求的設定。 

#### 步驟1.1：部署資料庫和報表伺服器的先決條件

1. 安裝並設定執行 Windows Server 2008 R2 （或更新版本）作業系統的伺服器。

2. 安裝 Windows PowerShell 3.0。

3. 安裝 Microsoft SQL Server 2008 R2 或更新版本，其中包含最新的 service pack。 如果您要為 MBAM 安裝新的 SQL Server 實例，請確定您安裝的 SQL Server 包含 SQL_Latin1_General_CP1_CI_AS 的排序規則。 您必須安裝下列 SQL Server 功能：

    * 資料庫引擎
    * Reporting Services
    * 用戶端工具連線性
    * 管理工具–完成

    > [!Note]
    > 或者，您也可以[在 SQL Server 中安裝透明資料加密（TDE）功能](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-security-considerations)。

    SQL Server Reporting Services 必須安裝並設定為「原生」模式，而不是使用未設定或「SharePoint」模式。

    ![所需的 SQL Server 功能](images/deploying-MBAM-1.png)

4. 如果您打算針對管理和監控網站使用 SSL，請務必先設定 SQL Server Reporting Services （SSRS），以使用安全通訊端層（SSL）協定，然後再設定管理和監視網站。 否則，報告功能將會使用未加密（HTTPS）資料傳輸，而不是加密（HTTPS）。

    您可以遵循在原生模式報表伺服器上[設定 ssl](https://docs.microsoft.com/sql/reporting-services/security/configure-ssl-connections-on-a-native-mode-report-server?view=sql-server-2017)連線，在報表伺服器上設定 ssl。
    
    > [!Note]
    > 您可以遵循 SQL server 安裝指南中適用于您的各個版本的 SQL Server 來安裝 SQL Server。 連結如下所示：
        > * [SQL Server 2014](https://docs.microsoft.com/sql/sql-server/install/planning-a-sql-server-installation?view=sql-server-2014)
        > * [SQL Server 2012](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/bb500442(v=sql.110))
        > * [SQL Server 2008 R2](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/bb500442(v=sql.110))

5. 在 SQL Server 的安裝後，請確認您已在 SQL Server 中提供使用者帳戶，並將下列許可權指派給將在資料庫伺服器上設定 MBAM 資料庫及報告角色的使用者。

    SQL Server 實例的角色：
        
    * dbcreator
    * processadmin

    SQL Server Reporting Services 實例的許可權：
    
    * 建立資料夾
    * 發佈報表

您的資料庫伺服器已準備好可供您設定 MBAM 2.5 角色。 讓我們移至下一個伺服器。

#### 步驟1.2：部署管理和監視伺服器的先決條件

選擇符合[MBAM 系統需求檔](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-supported-configurations#-mbam-server-system-requirements)中所述之硬體設定的伺服器。 它必須執行 Windows Server 2008 R2 或更新版本的作業系統以及最新的 service pack 和更新。 在伺服器就緒之後，請安裝下列角色和功能：

##### 角色

* Web 服務器（IIS）管理工具（選取 [IIS 管理腳本與工具]）。

* Web 服務器角色服務

    * 一般 HTTP 功能<br />
      靜態內容<br />
      預設檔

    * 應用程式開發<br />
      ASP.NET<br />
      .NET 擴充性<br />
      ISAPI 延伸<br />
      ISAPI 篩選<br />
      安全性<br />
      Windows 驗證<br />
      要求篩選

    * Web 服務 IIS 管理工具

##### 功能

* .NET Framework 4.5 功能
  
  * Microsoft .NET Framework 4。5
  
    針對 Windows Server 2012 或 Windows Server 2012 R2，已針對這些版本的 Windows Server 安裝 .NET Framework 4.5。 不過，您必須啟用它。
  
    對於 Windows Server 2008 R2，Windows Server 2008 R2 中不包含 .NET Framework 4.5。 因此，您必須下載 .NET Framework 4.5 並另行安裝。
  
  * WCF 啟用<br />
    HTTP 啟用<br />
    非 HTTP 啟用
  
  * TCP 啟用
  
  * Windows Process Activation Service：<br />
    處理模型<br />
    .NET Framework 環境<br />
    配置 Api

若要讓自助服務入口網站正常運作，您也應該[下載並安裝 ASP.NET MVC 4.0](https://go.microsoft.com/fwlink/?linkid=392271)。

下一步是在 Active Directory 中建立所需的 MBAM 使用者和群組。

### 步驟2：在 Active Directory 網域服務中建立使用者和群組
 
作為先決條件的一部分，您必須定義在 MBAM 中使用的特定角色和帳戶，以提供特定伺服器與功能的安全性與存取權，例如在 SQL Server 實例上執行的資料庫，以及在管理和監視伺服器上執行的 web 應用程式。

在 Active Directory 中建立下列群組和使用者。 （您可以將任何名稱用於群組和使用者。）使用者不需要有更多的使用者權限。 網域使用者帳戶已足夠。 在 MBAM 2.5 的設定期間，您必須指定這些群組的名稱：

* **MBAMAppPool**  

  **類型**：網域使用者

  **描述**：對合規性和審核資料庫及復原資料庫擁有讀取或寫入權限的網域使用者，以讓 web 應用程式存取這些資料庫中的資料和報表。 它也會供 web 應用程式的應用程式池使用。

  **帳戶角色（在 MBAM 的配置期間）**：

  1. Web 服務應用程式池網域帳戶

  2. 合規性與審計資料庫及復原資料庫已讀/寫使用者的報告

* **MBAMROUser**

  **類型**：網域使用者

  **描述**：將能以唯讀方式存取合規性和審核資料庫的網域使用者，以讓報告能夠存取此資料庫中的合規性和審核資料。 它也會是由本機 SQL Server Reporting Services 實例用來存取合規性和審核資料庫的網域使用者帳戶。

  **帳戶角色（在 MBAM 的配置期間）**：

  1. 相容性與審核資料庫唯讀使用者的報表

  2. 合規性與審計資料庫網域使用者帳戶

* **MBAMAdvHelpDsk**

  **類型**：網域群組

  **描述**： MBAM [高級支援人員] 使用者訪問群組：其成員可以存取 [管理] 和 [監視] 網站所有區域的網域使用者群組。 擁有此角色的使用者在協助使用者復原磁片磁碟機時，只需要輸入復原金鑰，而不是使用者的網域和使用者名稱即可。 如果使用者是 MBAM [支援人員] 群組和 MBAM [高級服務台使用者] 群組的成員，MBAM [高級支援人員] 群組許可權會覆寫 MBAM [服務台] 群組的許可權。

  **帳戶角色（在 MBAM 的設定期間）**： MBAM 高級技術支援人員的使用者

* **MBAMHelpDsk**

  **類型**：網域群組

  **描述**： MBAM [支援人員] 的 [使用者] 訪問群組：網域使用者群組，其成員可以存取 MBAM 管理和監視網站的 [管理 TPM] 和 [磁片磁碟機] 恢復區域。 擁有此角色的人員在使用任一選項時，都必須填入所有欄位。 這包括使用者的網域和帳戶名稱。

  **帳戶角色（在 MBAM 的設定期間）**： MBAM 支援人員的使用者

* **MBAMRUGrp**

  **類型**：網域群組

  **描述**：其成員對 [管理] 和 [監視] 網站上的 [報表] 區域中的報表擁有唯讀存取權的網域使用者群組。

  **帳戶角色（在 MBAM 的配置期間）**：

  1. 報告唯讀網域存取群組

  2. MBAM 報表使用者存取群組

### 步驟3（選用）：在管理與監視伺服器上設定及安裝 SSL 憑證

雖然它是選擇性的，但我們強烈建議您使用憑證來協助保護 MBAM 用戶端與管理與監控網站及自助服務入口網站之間的通訊。 我們不建議您使用自行簽署的憑證，因為這是很明顯的安全性原因。 建議您使用來自受信任之憑證授權單位的 Web 服務器類型認證。 若要這樣做，您可以參考[知識庫 2754259](https://support.microsoft.com/help/2754259)中的 [使用由憑證授權單位核准的憑證] 區段。

在頒發證書之後，您應該將憑證新增到 [管理和監視伺服器] 的個人存放區。 若要新增憑證，請開啟本機電腦上的 [憑證] 存放區。 若要這樣做，請執行下列步驟：

1. 以滑鼠右鍵選取 [開始]，然後選取 [執行]。

   ![選取 ](images/deploying-MBAM-2.png)

2. 輸入 "MMC.EXE" （不加上引號），然後選取 **[確定]**。

   ![[執行] 方塊](images/deploying-MBAM-3.png) 

3. 在您開啟的新 MMC 中選取 [檔案]，**然後選取 [** 新增 **/移除管理單元**]。
   
   ![選取](images/deploying-MBAM-4.png)

4. 醒目提示 [**憑證**] 管理單元，然後選取 [**新增**]。

   ![[新增或移除管理單元] 視窗](images/deploying-MBAM-5.png)

5. 選取 [**電腦帳戶**] 選項，然後選取 **[下一步]**。
   
   ![[憑證] 管理單元視窗](images/deploying-MBAM-6.png)

6. 選取下一個畫面上的 [**本機電腦**]，然後選取 **[完成]**。
   
   ![選取電腦視窗](images/deploying-MBAM-7.png)

7. 您現在已新增 [憑證] 管理單元。 這可讓您使用電腦憑證存放區中的任何憑證。

   ![[新增或移除管理單元] 視窗](images/deploying-MBAM-8.png)

8. 將 web 伺服器憑證匯入到電腦的憑證存放區。

   現在您可以存取 [憑證] 管理單元，您可以將 web 伺服器憑證匯入到電腦的憑證存放區。 若要這樣做，請按照後續步驟進行。

9. 開啟 [憑證（本機電腦）] 管理單元，然後流覽至 [**個人**]，然後選取 [**憑證**]。
   
   ![[憑證（本機電腦）] 管理單元視窗](images/deploying-MBAM-9.png)

   > [!Note]
   > [憑證] 管理單元可能不會列出。 如果不是，則不會安裝任何憑證。

10. 以滑鼠右鍵選取 [**憑證**]，選取 [**所有任務**]，然後選取 [匯**入**]。

    ![[憑證（本機電腦）] 管理單元視窗](images/deploying-MBAM-10.png)

11. 嚮導啟動後，選取 **[下一步**]。 流覽至您所建立的包含伺服器憑證和私人金鑰的檔案，然後選取 **[下一步]**。

    ![[證書匯入] 嚮導視窗](images/deploying-MBAM-11.png)

12. 如果您在建立檔案時為其指定一個密碼，請輸入密碼。

   ![[輸入密碼] 視窗](images/deploying-MBAM-12.png)

   > [!Note]
   > 如果您想要從這台電腦再次匯出金鑰組，請確定已選取 [將**金鑰標示為可匯出**] 選項。 您可能會想要將這個選項保留為已加上的安全措施，以確保沒有人可以備份您的私人金鑰。
 
13. 選取 **[下一步]**，然後選取您要儲存憑證的**憑證存放區**。

    ![[證書匯入] 嚮導視窗](images/deploying-MBAM-13.png)

    > [!Note]
    > 您應該選取 [**個人**]，因為它是 web 伺服器憑證。 如果您已在證書階層階層中包含憑證，也會將它新增到此存放區。
 
14. 選取 **[下一步**]，然後選取 **[完成]**。

    ![[證書匯入] 嚮導視窗](images/deploying-MBAM-14.png)

您現在會在 [個人憑證] 清單中看到您網頁伺服器的伺服器憑證。 它會以伺服器的通用名稱表示。 （您可以在憑證的 [主語] 區段中找到此功能。）

如需進一步參考：

[MBAM 2.5 安全性考量](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-security-considerations)

[如何保護 MBAM 網站的規劃](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites)

下一步是登錄應用程式池帳戶的服務主體名稱。

### 步驟4：為 MBAM Web 服務器設定 SSL 憑證

如果您是在用戶端與伺服器之間使用 SSL 通訊，您應該確定憑證已增強金鑰用法 Oid （1.3.6.1.5.5.7.3.1）和（1.3.6.1.5.5.7.3.2）。 也就是說，您應該確認已新增伺服器驗證與用戶端驗證。

如果您在嘗試流覽服務 Url 時收到憑證錯誤，表示您使用的是頒發給其他名稱的憑證，或者您是使用不正確的 URL 進行流覽。

雖然瀏覽器可能會提示您輸入憑證錯誤訊息，但仍可讓您繼續，但 MBAM web 服務不會忽略憑證錯誤，並會封鎖連線。 您會在 MBAM 用戶端的 MBAM 系統管理員事件記錄檔中注意到與憑證相關的錯誤。 如果您使用別名連線至 [管理] 和 [監視伺服器]，您應該將憑證頒發給別名名稱。 也就是說，證書的受領人名稱應該是別名，而本機伺服器的 DNS 名稱則應該新增至憑證的 [ **Subject 替換名稱**] 欄位。

範例：

如果虛擬名稱是 "bitlocker.contoso.com"，而 MBAM 管理和監視伺服器名稱是「adminserver.contoso.com」，則應該將憑證頒發給 bitlocker.contoso.com （subject 名稱），而且應該將 adminserver.contoso.com 新增至憑證的 [ **Subject 備用名稱**] 欄位。

同樣地，如果您安裝了多個管理和監視伺服器來平衡負載平衡，您應該將 SSL 憑證頒發給虛擬名稱。 也就是說，證書的 [主旨名稱] 欄位應該擁有虛擬名稱，且所有的本機伺服器名稱都應該新增到憑證的 [ **Subject 替換名稱**] 欄位中。

範例：

如果虛擬名稱是 "bitlocker.contoso.com"，且伺服器為「adminserver1.contoso.com」和「adminiserver2.contoso.com」，則應該將憑證頒發給 bitlocker.contoso.com （subject 名稱）和 adminserver1.contoso.com，並將 adminiserver2.contoso.com 新增至憑證的 [ **Subject 替換名稱**] 欄位。

使用 MBAM 設定 SSL 通訊的步驟，請參閱下列知識庫文章： [KB 2754259](https://support.microsoft.com/help/2754259)。

### 步驟5：註冊應用程式池帳戶的 SPN 並設定受限制的委派

> [!Note]
> 受限制的委派只需2.5，而 2.5 Service Pack 1 及更新版本則不需要。

若要讓 MBAM 伺服器從管理和監控網站和自助服務入口網站驗證通訊，您必須在您用於 web 應用程式池的網域帳戶下，為主機名稱註冊服務主要名稱（SPN）。 下列文章包含註冊 Spn 的逐步指示：[規劃如何保護 MBAM 網站](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites)

設定 SPN 之後，您應該在 SPN 上設定受限制的委派。 若要這樣做，請執行下列步驟：

1. 移至 Active Directory，然後尋找您在先前步驟中針對 MBAM 網站所設定的應用程式池認證。

2. 以滑鼠右鍵按一下認證，然後選取 [**屬性**]。

3. 選取 [**委派**] 索引標籤。

4. 選取 Kerberos 驗證的選項。

5. 選取 **[流覽]**，然後再次流覽您的應用程式池認證。 接著，您應該會看到在應用程式集的 [憑據] 帳戶上設定的所有 Spn。 （SPN 應該與 "HTTP/bitlocker. .com" 類似）。 醒目提示 [SPN] 與您在 MBAM 安裝期間所指定的主機名稱稱相同。

6. 選取 **\[確定\]**。

現在，您已經準備好使用先決條件了。 在後續步驟中，您將在伺服器上安裝 MBAM 軟體並加以設定。

## 安裝和設定 MBAM 2.5 server 軟體

### 步驟6：安裝 MBAM 2.5 server 軟體 

若要在資料庫伺服器以及管理和監控伺服器上使用 Microsoft BitLocker 管理和監視設定向導來安裝 MBAM Server 軟體，請依照下列步驟進行。

1. 在您想要安裝 MBAM 的伺服器上，執行 MBAMserversetup.exe 以啟動 Microsoft BitLocker 管理及監視安裝程式嚮導。

2. 在 [歡迎] 頁面上，選取 **[下一步]**。

3. 閱讀並接受 Microsoft 軟體授權協定，然後選取 **[下一步]** 繼續安裝。

4. 在您檢查更新時，決定是否要使用 Microsoft Update，然後選取 **[下一步]**。

5. 決定是否要參與客戶經驗改進計畫，然後選取 **[下一步]**。

6. 若要開始安裝，請選取 [**安裝**]。

7. 若要在 MBAM Server 軟體完成安裝之後設定伺服器功能，請選取 [在**嚮導關閉後執行 MBAM 伺服器設定]** 核取方塊。 或者，您可以在稍後使用伺服器安裝在 [**開始**] 功能表上建立的 [ **MBAM 伺服器**設定] 快捷方式來設定 MBAM。

8. 選取 **[完成]**。

如需詳細資訊，請參閱[安裝 MBAM 2.5 Server 軟體](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software)。

### 步驟7：設定 MBAM 2.5 資料庫和報告角色

在此步驟中，我們將使用 [MBAM] 嚮導來設定 MBAM 2.5 資料庫和報告元件：

1. 使用嚮導來設定合規性和審核資料庫及復原資料庫：
   
   1. 在您想要設定資料庫的伺服器上，啟動 [ **MBAM 伺服器設定] 嚮導**。 您可以選取 [**開始**] 功能表上的 [ **MBAM 伺服器**設定] 來開啟嚮導。

   2. 選取 [**新增功能**]，選取 [**合規性與審計資料庫**]、[復原**資料庫及報告**]，然後選取 **[下一步]**。 嚮導會檢查資料庫的所有先決條件是否都已滿足。

   3. 如果先決條件檢查成功，請選取 **[下一步]** 繼續。 否則，請解決任何缺少的先決條件，然後**再次選取 [檢查先決條件**]。
   
   4. 使用下列說明，在嚮導中輸入欄位值：

2. 合規性和審核資料庫

   |欄位   |描述|
   |-------|-------|
   |SQL Server 名稱 |您正在設定合規性和審核資料庫之伺服器的名稱。 <br /> 您必須在合規性和審核資料庫電腦上新增例外狀況，才能在 SQL Server 埠上啟用入站流量。 預設埠號碼是1433。|
   |SQL Server 資料庫實例    |儲存合規性和審核資料之資料庫實例的名稱。 如果您使用的是預設實例，則必須將此欄位留白。 您也必須指定資料庫資訊的位置。|
   |資料庫名稱   |儲存合規性資料之資料庫的名稱。 您必須記下您在此處指定的資料庫名稱，因為您將必須在後續步驟中提供此資訊。|
   |讀取/寫入權限網域使用者或群組  |根據步驟2中的設定，指定 MBAMAppPool 使用者的名稱。|
   |唯讀存取網域使用者或群組   |根據步驟2中的設定，指定 MBAMROUser 使用者的名稱。|

3. [恢復資料庫]。

   |欄位   |描述|
   |-----|-----|
   |SQL Server 名稱 |您正在設定復原資料庫之伺服器的名稱。 您必須在復原資料庫電腦上新增例外狀況，才能在 SQL Server 埠上啟用入站流量。 預設埠號碼是1433。|
   |SQL Server 資料庫實例    |儲存恢復資料之資料庫實例的名稱。 如果您使用的是預設實例，則必須將此欄位留白。 您也必須指定資料庫資訊的位置。|
   |資料庫名稱   |儲存修復資料之資料庫的名稱。|
   |讀取/寫入權限網域使用者或群組  |擁有此資料庫讀/寫許可權的網域使用者或群組，可讓 web 應用程式存取此資料庫中的資料和報表。 <br />如果您在此欄位中輸入使用者，其值必須與 [**設定 Web 應用程式**] 頁面上的 [ **web 服務應用程式池網域帳戶**] 欄位中的值相同。 <br />如果您在此欄位中輸入群組，則 [**設定 Web 應用程式**] 頁面上的 [ **Web 服務應用程式群組網域帳戶**] 欄位中的值必須是您在這個欄位中輸入之群組的成員。|
   
   完成專案後，請選取 **[下一步**]。 嚮導會檢查資料庫的所有先決條件是否都已滿足。
   
   如果先決條件檢查成功，請選取 **[下一步]** 繼續。 否則，請解決任何缺少的先決條件，然後再次選取 **[下一步]** 。

4. 有關.

   |欄位   |描述|
   |----|----|
   |SQL Server Reporting Services 實例  |將設定報告的 SQL Server Reporting Services 實例。 如果您使用的是預設實例，則必須將此欄位留白。|
   |報告角色網域群組 |如步驟2所述，指定 MBAMRUGrp 的名稱。|
   |SQL Server 名稱 |已設定合規性和審核資料庫之伺服器的名稱。|
   |SQL Server 資料庫實例    |已設定合規性和審核資料之資料庫實例的名稱。 如果您使用的是預設實例，則必須將此欄位留白。 <br />您必須在報表電腦上新增例外狀況，才能在報表伺服器的埠上啟用傳入流量。 （預設埠是80。）|
   |資料庫名稱|  合規性和審核資料庫的名稱。 根據預設，資料庫名稱是 MBAM 合規性狀態。|
   |合規性與審計資料庫網域帳戶    |根據步驟2中的設定，指定 MBAMROUser 使用者的名稱。|
   
   完成專案後，請選取 **[下一步**]。 嚮導會檢查是否符合 [報告] 功能的所有先決條件。 選取 [下一步] 以繼續。 在 [**摘要**] 頁面上，查看將新增的功能。
   
   如需詳細資訊，請參閱下列文章：[如何設定 MBAM 2.5 資料庫](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases)。

### 步驟8：設定 MBAM 2.5 Web 應用程式角色

1. 在您想要設定 web 應用程式的伺服器上，啟動 [MBAM 伺服器設定] 嚮導。 您可以選取 [**開始**] 功能表上的 [ **MBAM 伺服器**設定] 來開啟嚮導。

2. 選取 [**新增功能**]，選取 [**管理及監視網站**與**自助式入口**網站]，然後選取 **[下一步]**。 嚮導會檢查資料庫的所有先決條件是否都已滿足。

3. 如果先決條件檢查成功，請選取 **[下一步]** 繼續。 否則，請解決任何缺少的先決條件，然後**再次選取 [檢查先決條件**]。

4. 使用下列描述在嚮導中輸入欄位值。

   |欄位   |描述|
   |-----|-----|
   |安全性憑證    |在步驟3中選取先前建立的憑證，以選擇性地將 web 服務與您要設定管理和監控網站的伺服器進行通訊。 如果您選取 [不使用憑證]，您的 web 通訊可能不安全。|
   |主機名稱   |您要在其上設定管理和監視網站的主機名稱稱。 <br />它不一定是電腦的主機名稱，可能是什麼。 不過，如果主機名稱與電腦的 netbios 名稱不同，您就必須建立 A 記錄，並確定 SPN 使用的是自訂主機名稱，而不是 netbios 名稱。 這在負載平衡案例中是常見的。|
   |安裝路徑   |您要安裝管理和監控網站的路徑。|
   |連接埠    |要用於網站通訊的埠號碼。 <br /> 您必須設定防火牆例外狀況，才能透過指定的埠進行通訊。|
   |Web 服務應用程式池網域帳戶和密碼    |根據步驟2中的設定，指定 MBAMAppPool 使用者的使用者帳戶和密碼。 <br /> 若要提高安全性，請將認證中指定的帳號設定為擁有有限的使用者權限。 此外，將帳戶的密碼設定為永不過期。|

5. 確認內建的 IIS_IUSRS 帳戶或應用程式池帳戶已新增至**驗證之後模仿用戶端**，並以**批次工作**的本機安全性設定登入。

   若要檢查是否已將帳戶新增到本機安全性設定，請開啟 [**本機安全性原則編輯器**]，展開 [**本機原則**] 節點，選取 [**使用者權利指派**] 節點，然後在驗證之後，按兩下 [**模仿用戶端**]，然後在右側窗格中**以批次工作原則登**入。

6. 使用下欄欄位描述來設定合規性和審核資料庫的嚮導中的連線資訊。
   |欄位   |描述|
   |------|------|
   |SQL Server 名稱 |已設定合規性和審核資料庫之伺服器的名稱。|
   |SQL Server 資料庫實例    |SQL Server 實例的名稱（例如 \<Server Name\> ），以及設定合規性和審核資料庫的物件。 如果您使用的是預設實例，請將此選項留白。|
   |資料庫名稱   |合規性和審核資料庫的名稱。 根據預設，它是「MBAM 合規性狀態」。|

7. 使用下欄欄位描述來設定恢復資料庫的嚮導中的連線資訊。
   |欄位   |描述|
   |----|----|
   |SQL Server 名稱 |已設定復原資料庫之伺服器的名稱。|
   |SQL Server 資料庫實例    |在其上設定復原資料庫的 SQL Server 實例名稱（例如， \<Server Name\> ）。 如果您使用的是預設實例，請將此選項留白。|
   |資料庫名稱   |恢復資料庫的名稱。 根據預設，它是「MBAM 恢復和硬體」。|

8. 使用下列描述在嚮導中輸入欄位值，以設定管理和監視網站。
   |欄位   |描述|
   |----|----|
   |[高級支援人員] 角色網域群組 |指定 MBAMAdvHelpDsk 群組的名稱，如步驟2所設定。|
   |支援人員角色網域群組  |指定 MBAMHelpDsk 群組的名稱，如步驟2所設定。|
   |使用 System Center Configuration Manager 整合 |選取以清除此核取方塊。     |
   |報告角色網域群組 |指定 MBAMRUGrp 群組的名稱，如步驟2所設定。    |
   |SQL Server Reporting Services URL   |指定要在其上設定 MBAM 報告之 SSRS 伺服器的 Web 服務 URL。 您可以在資料庫伺服器上登入 Reporting Services Configuration Manager，以找到這項資訊。 <br /> 完整功能變數名稱的範例：https://MyReportServer.Contoso.com/ReportServer <br />自訂主機名稱範例：https://MyReportServer/ReportServer|
   |虛擬目錄   |[管理] 和 [監視] 網站的虛擬目錄。 這個名稱會對應到伺服器上的網站物理目錄，並會附加到網站的主機名稱。 例如： <br />HTTP （s）：// *\<host name\>* ： *\<port\>* /HelpDesk/ <br />如果您沒有指定虛擬目錄，就會使用 [價值支援人員]。     |

9. 使用下列描述在嚮導中輸入欄位值以設定自助入口網站。

   |欄位   |描述|
   |----|----|
   |虛擬目錄   |Web 應用程式的虛擬目錄。 這個名稱會對應到伺服器上的網站物理目錄，並會附加到網站的主機名稱。 例如：<br />HTTP （s）：// *\<host name\>* ： *\<port\>* /SelfService/<br /> 如果您沒有指定虛擬目錄，則會使用值 "SelfService"。|

10. 完成專案後，請選取 **[下一步**]。 嚮導會檢查是否符合 web 應用程式的所有先決條件。

11. 選取 **[下一步]** 繼續。

12. 在 [**摘要**] 頁面上，查看將新增的功能。

13. 選取 [**新增**]，將 web 應用程式新增至伺服器，然後選取 [**關閉**]。

## 在安裝 MBAM 2.5 server 軟體之後自訂和驗證步驟

### 步驟9：自訂貴組織的自助伺服器入口網站

若要自訂自助式入口網站，只要新增自訂的指示文字、您的公司名稱、指向詳細資訊的指標等，請參閱[自訂貴組織的自助入口網站](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/customizing-the-self-service-portal-for-your-organization)。
 
### 步驟10：如果用戶端電腦無法存取 CDN，請設定自助伺服器入口網站 

判斷您的用戶端電腦是否有權存取 Microsoft AJAX 內容傳遞網路（CDN）。 CDN 為自助入口網站提供對某些 JavaScript 檔案所需的存取權。 如果您未在用戶端電腦無法存取 CDN 時設定自助入口網站，則只有公司名稱和使用者登入的帳戶才會顯示。 不會顯示任何錯誤訊息。

執行下列其中一項：

* 如果您的用戶端電腦具有 CDN 的存取權，請執行任何動作。 您的自助入口網站設定已完成。

* 如果您的用戶端電腦沒有 CDN 的存取權，請按照在[用戶端電腦無法存取 Microsoft 內容傳遞網路時，如何設定自助入口網站](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network)中的步驟進行。

### 步驟11：驗證 MBAM 2.5 伺服器功能設定 

若要驗證您的 MBAM 伺服器部署以使用獨立拓撲，請遵循下列步驟。

1. 在部署 MBAM 功能的每個伺服器上，選取 [**控制台**] 的 [程式  >  **Programs**  >  **和功能**]。 確認 [**程式和功能**] 清單中出現 [ **Microsoft BitLocker 管理及監視**]。
   > [!Note]
   > 若要執行驗證，您必須使用在每個伺服器上都有本機電腦管理認證的網域帳戶。

2. 在已設定復原資料庫的伺服器上，開啟 [SQL Server Management Studio]，然後確認已設定**MBAM 復原與硬體**資料庫。

3. 在已設定合規性和審核資料庫的伺服器 om 上，開啟 SQL Server Management Studio，然後確認已設定 MBAM 合規性狀態資料庫。

4. 在已設定報告功能的伺服器 onm 上，使用管理認證開啟網頁瀏覽器，然後流覽至 SQL Server Reporting Services 網站的首頁。
   
   SQL Server Reporting Services 網站實例的預設首頁位置如下所示： HTTP （s）：：// *\<MBAM Reports Server Name\>* ： *\<port\>* /Reports.aspx
   
   若要尋找實際的 URL，請使用 Reporting Services Configuration Manager 工具，然後選取您在安裝期間指定的實例。
   
5. 確認名為 Microsoft BitLocker 管理及監視的報表資料夾包含名為 MaltaDataSource 的資料來源。 此資料來源包含的資料夾的名稱代表語言地區（例如，en-us）。 報告位於 [語言] 資料夾中。

   > [!Note]
   > 如果 SQL Server Reporting Services （SSRS）設定為命名實例，URL 應如下所示： HTTP （s）// \<MBAM Reports Server Name\> ： \<port\> /Reports_\<SSRS Instance Name\>
   >
   > 如果未將 SSRS 設定為使用安全通訊端層（SSL），當您安裝 MBAM 伺服器時，報告的 URL 將會設定為 "HTTP"，而不是 "HTTPS"。 如果您接著移至 [管理和監控] 網站（又稱為 [支援人員]）並選取報告，您會收到下列訊息：「只會顯示安全內容」。 若要顯示報表，請選取 [**顯示所有內容**]。

6. 在已設定 [管理及監視網站] 功能的伺服器上，執行 [伺服器管理員]，流覽至 [**角色**]，然後選取 [ **Web server （iis）**  >  **Internet information Services （IIS）** 管理員]。

7. 在 **[連線] 中，** 流覽至 [網站]， \<computer name\> 然後選取 [**網站**  >  **Microsoft BitLocker 管理與監視**]。 確認下列專案已列出：

   * MBAMAdministrationService
   * MBAMComplianceStatusService
   * MBAMRecoveryAndHardwareService

8. 在已設定 [管理] 和 [監視] 和 [自助式入口網站] 的伺服器上，使用管理認證開啟網頁瀏覽器。

9. 流覽至下列網站，確認他們已順利載入：
   * HTTPs （s） \<MBAM Administration Server Name\> ：：//： \<port\> /HelpDesk/（請確認流覽和報告的每個連結）
   * HTTP （s）：// \<MBAM Administration Server Name\> ： \<port\> /SelfService/

   > [!Note]
   > 假設您已在不含網路加密的情況下，在預設埠上設定伺服器功能。 如果您已將伺服器功能設定在不同的埠或虛擬目錄，請變更 Url，以包含適當的埠。 例如： HTTP （s）// \<host name\> ： \<port\> /HelpDesk/HTTP （s）：// \<host name\> ： \<port\> / \<virtualdirectory\> /如果伺服器功能已設定為使用網路加密，請將 HTTP://變更為 HTTPs://。
   
10. 流覽至下列 web 服務，確認他們已順利載入。 隨即會開啟一個頁面，指出服務正在執行。 不過，此頁面不會顯示中繼資料。

    * HTTP （s）：// \<MBAM Administration Server Name> ： \<port> /MBAMAdministrationService/AdministrationService.svc
    * HTTP （s）：// \<MBAM Administration Server Name> ： \<port> /MBAMUserSupportService/UserSupportService.svc
    * HTTP （s）：// \<MBAM Administration Server Name> ： \<port> /MBAMComplianceStatusService/StatusReportingService.svc
    * HTTP （s）：// \<MBAM Administration Server Name> ： \<port> /MBAMRecoveryAndHardwareService/CoreService.svc

### 步驟12：設定 MBAM 群組原則範本

若要部署 MBAM，您必須設定定義 BitLocker 磁片磁碟機加密之 MBAM 實現設定的 [組原則] 設定。 若要完成這項工作，您必須將 MBAM 群組原則範本複製到可執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）的伺服器或工作站，然後編輯設定。

> [!Important]
> 請勿變更**BitLocker 磁片磁碟機加密**節點中的群組原則設定，否則 MBAM 將無法正常運作。 當您在**MDOP MBAM （BitLocker 管理）** 節點中設定群組原則設定時，MBAM 會自動為您設定**BitLocker 磁片磁碟機加密**設定。
 
#### 複製 MBAM 2.5 群組原則範本

在您安裝 MBAM 用戶端之前，您必須將 MBAM 專用的群組原則物件（Gpo）複製到管理工作站。 這些 Gpo 定義 BitLocker 的 MBAM 實現設定。 您可以將群組原則範本複製到所有受支援 Windows 型伺服器或用戶端電腦的伺服器或工作站，而且可以執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）。

如需詳細資訊，請參閱[複製 MBAM 2.5 群組原則範本](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/copying-the-mbam-25-group-policy-templates)。
 
#### 編輯 MBAM 2.5 GPO 設定

在您建立必要的 Gpo 之後，您必須將 MBAM 群組原則設定部署到貴組織的用戶端電腦。 若要查看和建立 Gpo，您必須已安裝群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）。

如需詳細資訊，請參閱[編輯 MBAM 2.5 群組原則設定](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/editing-the-mbam-25-group-policy-settings)及[規劃 MBAM 2.5 群組原則需求](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-group-policy-requirements)。
 
### 步驟13：部署 MBAM 2.5 用戶端

視您部署 Microsoft BitLocker 管理和監視用戶端軟體的情況而定，您可以在使用者接收電腦前，或在此後使用企業軟體部署系統來部署 MBAM 用戶端軟體，在您組織的電腦上啟用 BitLocker。
 
#### 將 MBAM 用戶端部署到桌上型電腦或可擕式電腦

在您設定群組原則設定之後，您可以使用企業軟體部署系統產品（例如 Microsoft System Center 2012 Configuration Manager 或 Active Directory 網域服務（AD DS）），將 MBAM 用戶端安裝 Windows 安裝程式檔案部署至目的電腦。 您可以使用32位或64位 MbamClientSetup.exe 檔案，或是32位或64位 MBAMClient.msi 檔案。 這些與 MBAM 用戶端軟體一起提供。

如需詳細資訊，請參閱[如何將 MBAM 用戶端部署到桌上型電腦或膝上型電腦](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-25)。
 
#### 部署 MBAM 用戶端做為 Windows 部署的一部分

在已集中接收和設定電腦的組織中，您可以安裝 MBAM 用戶端，在每個電腦上管理 BitLocker 磁碟機加密，然後再寫入任何使用者資料。 此程式的優點是，每個電腦都符合 BitLocker 規範。 這個方法不依賴使用者的動作，因為系統管理員已經將電腦加密。 這個案例的主要假設是組織原則是在電腦傳送給使用者之前，先安裝公司的 Windows 影像。 如果將群組原則設定設定為 [需要 PIN]，系統會在收到原則之後提示使用者設定 PIN。

如需詳細資訊，請參閱[如何在 Windows 部署中部署 MBAM 用戶端](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25)。
 
#### 如何使用命令列部署 MBAM 用戶端

如需詳細資訊，請參閱[如何使用命令列部署 MBAM 用戶端](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-deploy-the-mbam-client-by-using-a-command-line)。

#### 用戶端部署之後

現在您已完成部署活動，您應該查看下列記錄，並判斷用戶端是否已成功向 MBAM 資料庫報告。

## 常見問題集

### 如何建立負載平衡的 IIS 伺服器

* SPN 必須只登錄到易記的名稱（例如： bitlocker.corp.net），而且不能登錄到個別的 IIS 伺服器。

* 如果使用了憑證，憑證必須在 [匯入平衡] 群組中的所有 IIS 伺服器的 [ **Subject 替換名稱**] 欄位中，輸入 FQDN 和 NetBIOS 名稱，也就是易記的名稱（例如： bitlocker.corp.net）。 否則，當您流覽負載平衡位址時，瀏覽器就會將憑證報告為不受信任。

如需詳細資訊，請參閱[IIS 網路負載平衡](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-high-availability#a-href-idbkmk-load-balanceaiis-network-load-balancing)及[註冊應用程式池帳戶的 spn](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites#registering-spns-for-the-application-pool-account)。

### 如何設定憑證

* 您必須有兩個憑證。 其中一個證書用於 SQL server，另一個用於 IIS。 啟動 MBAM 安裝之前，必須先安裝它們。

* 我們建議您使用安裝程式將憑證新增至 IIS 配置，而不是手動編輯 web.config 檔案。

* 如果憑證上的「頒發給」欄位與伺服器的名稱不相符，則 MBAM 配置器就不會接受證書。 在這種情況下，暫時從 IIS 主控台建立自我簽署憑證，然後在配置器中使用它。 這會讓 nsure 針對 SSL 和 HTTPS 安裝 Web 應用程式。 之後，您可以將證書從 MBAM 網站的 IIS 系結變更為另一個。

### 安裝的 SQL 許可權需求

為 MBAM 應用程式池建立帳戶，並僅提供 SecurityAdmin、Public 和 DBCreator 許可權。

如需詳細資訊，請參閱[MBAM 資料庫配置–最低許可權](https://blogs.technet.microsoft.com/dubaisec/2016/02/02/mbam-database-configuration-minimum-permissions/)。

> [!Note]
> * 在某些情況下，初始安裝和升級作業需要有更多許可權。
> * 使用具有暫時 SA 的帳戶進行安裝。
> * 請勿在沒有足夠許可權來變更 SQL Server 的使用者帳戶內容中啟動配置器，因為這會造成安裝錯誤。
> * 您必須使用在 SQL Server 上擁有許可權的帳戶登入。 您可以透過遠端執行 MBAM 配置器來建立或更新 SQL Server 資料庫。 若是 SSRS server，您必須安裝 MBAM 並在本機執行配置程式，才能安裝或更新 MBAM SSRS 報告。

### SPN 註冊所需的許可權

用於 IIS 入口安裝的帳戶必須具有寫入 ServicePrincipalName 並寫入驗證的 SPN 許可權。 如果沒有這些許可權，安裝會傳回一則警告訊息，指出它無法註冊 SPN。

> [!Note]
> 您將會收到這則警告訊息兩次。 這並不表示 SPN 必須有兩個註冊物件。

如需詳細資訊，請參閱[MBAM 安裝失敗，並顯示「註冊 SPN 延遲」的錯誤訊息](https://support.microsoft.com/help/2754138/)。

### 我是否需要將 ADMX 範本更新為最新版本？

在您將 ADMX 範本更新為其最新版本之後，您會在 GPO 的 [MBAM 根節點] 中看到多個 OS 選項。 例如，Windows 7、Windows 8.1、Windows 10 版本1511及更新版本。

如需如何更新 ADMX 範本的詳細資訊，請參閱下列文章：
* [如何下載及部署 MDOP 群組原則 (.admx) 範本](https://docs.microsoft.com/microsoft-desktop-optimization-pack/solutions/how-to-download-and-deploy-mdop-group-policy--admx--templates)
* [MBAM 2.5 群組原則需求規劃](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-group-policy-requirements)
* [Microsoft 桌面優化套件群群組原則管理範本](https://www.microsoft.com/en-us/download/details.aspx?id=55531)
