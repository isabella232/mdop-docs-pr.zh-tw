---
title: 如何在單一伺服器上安裝及設定 MBAM
description: 如何在單一伺服器上安裝及設定 MBAM
author: dansimp
ms.assetid: 55841c63-bad9-44e7-b7fd-ea7037febbd7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 225f66493ceafce5461df3fcc6f701e9a2922a5f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810352"
---
# 如何在單一伺服器上安裝及設定 MBAM


本主題中的程式說明在單一伺服器上完整安裝 Microsoft BitLocker 管理和監控（MBAM）功能。

每個伺服器功能都有特定的先決條件。 若要確認您已符合先決條件以及硬體和軟體需求，請參閱[MBAM 1.0 部署先決條件](mbam-10-deployment-prerequisites.md)和[MBAM 1.0 支援](mbam-10-supported-configurations.md)的設定。 此外，某些功能也有一些資訊，必須在安裝過程中提供，才能成功部署該功能。 您也應該在開始 MBAM 部署之前，先複習[準備 MBAM 1.0 的環境](preparing-your-environment-for-mbam-10.md)。

**記事** 若要取得安裝記錄檔，您必須使用**msiexec**套件和 **/l** &lt; location 選項來安裝 MBAM &gt; 。 記錄檔案是在您指定的位置建立。

在安裝 MBAM 的使用者的% temp% 資料夾中，會建立其他設定記錄檔。

 

## 在單一伺服器上安裝 MBAM Server 功能


下列步驟說明如何安裝一般 MBAM 功能。

**記事** 請務必在32位伺服器上使用32位設定，以及在64位伺服器上進行64位設定。

 

**若要啟動 MBAM 伺服器功能安裝**

1.  啟動 MBAM 安裝精靈。 按一下 [歡迎] 頁面上的 [**安裝**]。

2.  閱讀並接受 Microsoft 軟體授權條款，然後按一下 **[下一步]** 繼續安裝。

3.  根據預設，所有的 MBAM 功能都已選取 [安裝]。 在同一部電腦上安裝的功能，必須同時安裝在一起。 清除您想要安裝在其他位置的功能。 您必須以下列順序安裝 MBAM 功能：

    -   恢復與硬體資料庫

    -   合規性和審核資料庫

    -   合規性審核與報告

    -   管理和監控伺服器

    -   MBAM 群組原則範本

    **記事** 安裝精靈會檢查安裝的先決條件，並顯示遺失的先決條件。 如果符合所有先決條件，安裝會繼續進行。 如果偵測到遺失的先決條件，您必須先解決遺失的先決條件，然後再次按一下 [**檢查必備元件**]。 在所有先決條件都符合之後，就會繼續安裝。

     

4.  系統會提示您設定網路通訊安全。 MBAM 可以加密復原與硬體資料庫、管理與監視伺服器以及用戶端之間的通訊。 如果您決定要加密通訊，系統會要求您選取要用來加密的頒發機構預配憑證。

5.  按 \[**下一步**\] 繼續。

6.  [MBAM 設定] 嚮導會顯示所選功能的安裝頁面。

**部署 MBAM 伺服器功能**

1.  在 [**設定復原與硬體資料庫**] 視窗中，指定 SQL Server 實例，以及將儲存恢復與硬體資料之資料庫的名稱。 您也必須同時指定資料庫檔案位置和記錄資訊位置。

2.  按 \[**下一步**\] 繼續。

3.  在 [**設定合規性和審核資料庫**] 視窗中，指定 SQL Server 的實例，以及將儲存合規性和審核資料之資料庫的名稱。 然後，指定資料庫檔案位置和記錄資訊位置。

4.  按 \[**下一步**\] 繼續。

5.  在 [**合規性與審計報告**] 視窗中，指定要使用的報表服務實例，並提供用來存取資料庫的網域使用者帳戶。 這應該是專為此用途預配的使用者帳戶。 使用者帳戶應該能夠存取 [MBAM 報告使用者] 群組中所有可用的資料。

6.  按 \[**下一步**\] 繼續。

7.  在 [**設定管理及監視伺服器**] 視窗中，輸入**埠**系結、**主機名稱**（選用），以及 MBAM 管理和監視伺服器的**安裝路徑**。

    **警告** 您指定的埠號碼必須是系統管理和監視伺服器上未使用的埠號碼（除非已指定唯一的主機標頭名稱）。

     

8.  按 \[**下一步**\] 繼續。

9.  指定是否要使用 Microsoft 更新，協助保護您的電腦安全性，然後按 **[下一步]**。 [Microsoft Update] 選項不會開啟 Windows 中的自動更新。

10. 當 [安裝精靈] 收集必要的功能資訊之後，就可以開始 MBAM 安裝了。 如果您想要查看或變更您的安裝設定，請按一下 [**返回**]，在嚮導中向後移動。 按一下 [**安裝**] 以開始安裝。 按一下 [**取消**] 結束安裝程式。 安裝程式會安裝 MBAM 功能，並通知您安裝已完成。

11. 按一下 **[完成] 結束**嚮導。

12. 安裝 MBAM server 功能之後，您必須將使用者新增至 MBAM 角色。 如需詳細資訊，請參閱[規劃 MBAM 1.0 系統管理員角色](planning-for-mbam-10-administrator-roles.md)。

**若要執行安裝後設定**

1.  安裝程式完成後，您必須新增使用者角色，以便讓使用者能夠存取 MBAM 管理網站中的功能。 在 [管理及監視伺服器] 上，將使用者新增至下列本機群組：

    -   **MBAM 硬體使用者**：此本機群組的成員可以存取 MBAM 管理網站中的硬體功能。

    -   **MBAM 支援人員**：此本機群組的成員可以存取 MBAM 管理網站中的 [磁碟機復原] 和 [管理 TPM 功能]。 [磁碟機復原] 和 [管理 TPM] 中的所有欄位都是技術支援人員的必要欄位。

    -   **MBAM 高級支援人員的使用者**：此本機群組的成員可以高級存取磁片磁碟機，並在 MBAM 管理網站中管理 TPM 功能。 針對高級支援人員的使用者，磁片磁碟機復原只需要 [金鑰識別碼] 欄位。 針對管理 TPM 使用者，只需要 [電腦網域] 欄位和 [電腦名稱稱] 欄位。

2.  在 [管理與監控伺服器]、[合規性] 和 [審核] 資料庫，以及駐留合規性和審核報告的電腦上，將使用者新增至下列本機群組，以讓他們能夠存取 MBAM 管理網站中的 [報告] 功能：

    -   **MBAM 報表使用者**：此本機群組的成員可以存取 MBAM 管理網站中的 [報表] 功能。

    **記事** **MBAM 報表**的相同使用者成員資格或群組成員資格：必須在所有電腦上保留管理和監控伺服器功能、合規性和審核資料庫，以及合規性和審核報告。

    若要在所有電腦上維持相同的成員資格，您應該建立一個網域安全性群組，並將該網域群組新增至每個當地 MBAM Report Users 群組。 如此一來，您就可以使用 [網域] 群組來管理群組成員資格。

     

## 驗證 MBAM Server 功能安裝


MBAM 安裝完成後，請確認安裝已成功設定 BitLocker 管理所需的所有必要 MBAM 功能。 使用下列程式來確認 MBAM 服務是否正常運作：

**驗證 MBAM Server 功能安裝**

1. 在部署 MBAM 功能的每個伺服器上，開啟 [**控制台**]。 按一下 [**程式**]，然後按一下 [**程式和功能**]。 確認 [**程式和功能**] 清單中出現 [ **Microsoft BitLocker 管理及監視**]。

   **注意**  
   若要驗證安裝，您必須使用在每個伺服器上都有本機電腦管理認證的網域帳戶。

     

2. 在已安裝復原與硬體資料庫的伺服器上，開啟 SQL Server Management Studio 並確認已安裝**MBAM 復原與硬體**資料庫。

3. 在已安裝合規性和審核資料庫的伺服器上，開啟 SQL Server Management Studio 並確認已安裝**MBAM 合規性和審核資料庫**。

4. 在已安裝合規性和審核報告的伺服器上，以系統管理許可權開啟網頁瀏覽器，並流覽至 SQL Server Reporting Services 網站的 "Home"。

   SQL Server Reporting Services 網站實例的預設首頁位置是 HTTP:// <em> &lt; NameofMBAMReportsServer &gt; </em> /Reports。 若要尋找實際的 URL，請使用 Reporting Services Configuration Manager 工具，然後選取在安裝期間指定的實例。

   確認已列出名為「**馬爾他規範**」的資料夾，且包含五個報表和一個資料來源。

   **注意**  
   如果 SQL Server Reporting Services 已設定為命名實例，URL 應該會類似下列內容： HTTP：//* &lt; NameofMBAMReportsServer &gt; */Reports\_* &lt; SRSInstanceName &gt; *

     

5. 在已安裝 [管理與監視] 功能的伺服器上，執行 [**伺服器管理員**] 並流覽至 [**角色**]，選取 [ **Web 服務器（iis）**]，然後按一下 [**網際網路資訊服務（iis）管理員**]。

6. 在 **[連線] 中，** 流覽至 [ * &lt; computername &gt; *]，選取 [**網站**]，然後選取 [ **Microsoft BitLocker 管理與監視**]。 確認 [ **MBAMAdministrationService**]、[ **MBAMComplianceStatusService**] 和 [ **MBAMRecoveryAndHardwareService** ] 都已列出。

7. 在已安裝 [管理及監視] 功能的伺服器上，以系統管理許可權開啟網頁瀏覽器，然後流覽至 MBAM 網站中的下列位置，以驗證它們已順利載入：

   -   *HTTP:// &lt; computername &gt; /default.aspx*並確認流覽與報告的每個連結

   -   *HTTP:// &lt; computername &gt; /MBAMAdministrationService/AdministrationService.svc*

   -   *HTTP:// &lt; computername &gt; /MBAMComplianceStatusService/StatusReportingService.svc*

   -   *HTTP:// &lt; computername &gt; /MBAMRecoveryAndHardwareService/CoreService.svc*

   **注意**  
   通常，服務會安裝在預設埠80，而不需要網路加密。 如果服務安裝在不同的埠上，請變更 Url，使其包含適當的埠。 例如，HTTP://* &lt; computername &gt; ： &lt; port &gt; */default.aspx 或 HTTP:// <em> &lt; hostheadername &gt; / </em> default .aspx。

   如果服務是以網路加密的方式安裝，請將 HTTP://變更為 HTTPs://。

     

## 相關主題


[部署 MBAM 1.0 伺服器基礎結構](deploying-the-mbam-10-server-infrastructure.md)

 

 





