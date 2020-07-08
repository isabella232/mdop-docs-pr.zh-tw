---
title: 驗證 MBAM 2.5 伺服器功能設定
description: 驗證 MBAM 2.5 伺服器功能設定
author: dansimp
ms.assetid: f4983a33-ce18-4186-a471-dd6415940504
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f955e0b9ccb7952995574e4aa981674f7c7667fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812141"
---
# 驗證 MBAM 2.5 伺服器功能設定


當您完成 Microsoft BitLocker 管理和監控（MBAM） 2.5 Server 功能部署時，建議您驗證部署，以確保所有功能都已成功設定。 使用與您部署的拓撲（獨立或系統中心 Configuration Manager 整合）相符的程式。

## 使用獨立拓朴驗證 MBAM 伺服器部署


使用下列步驟，透過獨立拓朴驗證您的 MBAM 伺服器部署。

**驗證獨立的 MBAM 伺服器部署**

1.  在部署 MBAM 功能的每個伺服器上，按一下 [**控制台**] 中的 [程式 &gt; **Programs** &gt; **和功能**]。 確認 [**程式和功能**] 清單中出現 [ **Microsoft BitLocker 管理及監視**]。

    **注意**  
    若要進行驗證，您必須使用在每個伺服器上都有本機電腦管理認證的網域帳戶。



2.  在已設定恢復資料庫的伺服器上，開啟 SQL Server Management Studio，並確認已設定**MBAM 復原與硬體**資料庫。

3.  在已設定合規性和審核資料庫的伺服器上，開啟 SQL Server Management Studio 並確認已設定**MBAM 合規性狀態資料庫**。

4.  在已設定 [報表] 功能的伺服器上，使用系統管理認證開啟網頁瀏覽器，然後流覽至 SQL Server Reporting Services 網站的 "Home"。

    SQL Server Reporting Services 網站實例的預設首頁位置是：

    HTTP （s）// &lt; *MBAMReportsServerName* &gt; ： &lt; *埠* &gt; /Reports.aspx

    若要尋找實際的 URL，請使用 Reporting Services Configuration Manager 工具，然後選取您在安裝期間指定的實例。

5.  確認名為**Microsoft BitLocker 管理和監視**的報表資料夾包含名為**MaltaDataSource**及語言資料夾的資料來源。 資料來源包含的資料夾的名稱代表語言（例如，en-us）。 報告位於 [語言] 資料夾中。

    **注意**  
    如果 SQL Server Reporting Services （SSRS）設定為命名實例，URL 應如下所示： HTTP （s）// &lt; *MBAMReportsServerName* &gt; ： &lt; *port* &gt; /Reports\_ &lt; *SSRSInstanceName*&gt;



~~~
**Note**  
If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server. If you then go to the Administration and Monitoring Website (also known as Help Desk) and select a report, the following message appears: "Only Secure Content is Displayed." To show the report, click **Show All Content**.
~~~



6. 在已設定 [管理及監視網站] 功能的伺服器上，執行 [**伺服器管理員**]，流覽至 [**角色**]，然後選取 [ **Web server （iis）** &gt; **Internet information Services （IIS）管理員**]。

7. 在 [連線] 中，流覽至 [ * &lt; 電腦名稱稱 &gt; * **]，然後**選取 [**網站** &gt; **Microsoft BitLocker 管理及監視**]。 確認下列專案已列出：

   -   **MBAMAdministrationService**

   -   **MBAMComplianceStatusService**

   -   **MBAMRecoveryAndHardwareService**

8. 在已設定 [管理] 和 [監視] 網站及自助服務入口網站的伺服器上，使用系統管理認證開啟網頁瀏覽器。

9. 流覽至下列網站，確認他們已順利載入：

   -   HTTPs （s）// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *port* &gt; /HelpDesk/-確認流覽與報告的每個連結

   -   HTTP （s）// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *埠* &gt; /SelfService/

   **注意**  
   假設您已在不含網路加密的情況下，在預設埠上設定伺服器功能。 如果您已將伺服器功能設定在不同的埠或虛擬目錄，請將 Url 變更為包含適當的埠，例如：

   HTTP （s）// &lt; *主機名稱* &gt; ： &lt; *埠* &gt; /HelpDesk/

   HTTP （s）// &lt; *主機名稱* &gt; ： &lt; *埠* &gt; / &lt; *virtualdirectory*&gt;/

   如果伺服器功能已設定網路加密，請將 HTTP://變更為 HTTPs://。



10. 流覽至下列 web 服務，確認他們已順利載入。 隨即會開啟一個頁面，指出服務正在執行，但頁面不會顯示任何中繼資料。

    -   HTTP （s）// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *埠* &gt; /MBAMAdministrationService/AdministrationService.svc

    -   HTTP （s）// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *埠* &gt; /MBAMUserSupportService/UserSupportService.svc

    -   HTTP （s）// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *埠* &gt; /MBAMComplianceStatusService/StatusReportingService.svc

    -   HTTP （s）// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *埠* &gt; /MBAMRecoveryAndHardwareService/CoreService.svc

## 使用 Configuration Manager 整合拓朴驗證 MBAM 伺服器部署


使用下列步驟，透過 Configuration Manager 整合拓朴驗證您的 MBAM 部署。 完成符合您所使用之 Configuration Manager 版本的驗證步驟。

### <a href="" id="validating-the-mbam-server-deployment-with-system-center-2012-configuration-manager-"></a>使用 System Center 2012 Configuration Manager 驗證 MBAM Server 部署

當您將 MBAM 與 System Center 2012 Configuration Manager 搭配使用時，請使用這些步驟來驗證您的 MBAM 伺服器部署。

**驗證 Configuration Manager 整合 MBAM 伺服器部署– System Center 2012 Configuration Manager**

1.  在部署 System Center 2012 Configuration Manager 的伺服器上，在 [**控制台**] 中開啟 [**程式和功能**]，然後確認出現 [ **Microsoft BitLocker 管理與監視**]。

    **注意**  
    若要驗證配置，您必須使用在每個伺服器上都有本機電腦管理認證的網域帳戶。



2.  在 Configuration Manager 主控台中，按一下 [**資產] 和 [合規性**工作區] &gt; **裝置集合**，確認會顯示名為 [ **MBAM 支援的電腦**] 的新集合。

3.  在 Configuration Manager 主控台中，按一下 [**監視**工作區 &gt; **報表**] &gt; **Reports** &gt; **MBAM**。

4.  確認**MBAM**資料夾包含子資料夾，且名稱代表不同語言，且下列報表列在每個語言子資料夾中：

    -   BitLocker 電腦合規性

    -   BitLocker Enterprise 合規性儀表板

    -   BitLocker 企業合規性詳細資料

    -   BitLocker Enterprise 合規性摘要

5.  在 Configuration Manager 主控台中，按一下 [**資產與合規性**工作區 &gt; **合規性設定] 設定** &gt; **配置基線**，然後確認已列出 [設定比較基準**BitLocker] 保護**。

6.  在 Configuration Manager 主控台中，按一下 [**資產與合規性**工作區 &gt; **合規性設定] 設定** &gt; **專案**，並確認顯示下列新的設定專案：

    -   BitLocker 固定資料磁碟機保護

    -   BitLocker 作業系統磁片磁碟機保護

### 驗證 Configuration Manager 2007 的 MBAM 伺服器部署

當您將 MBAM 與 Configuration Manager 2007 搭配使用時，請使用這些步驟來驗證您的 MBAM 伺服器部署。

**驗證 Configuration Manager 整合 MBAM 伺服器部署-Configuration Manager 2007**

1.  在部署 Configuration Manager 2007 的伺服器上，在 [**控制台**] 上開啟 [**程式和功能**]，然後確認出現 [ **Microsoft BitLocker 管理和監視**]。

    **注意**  
    若要驗證配置，您必須使用在每個伺服器上都有本機電腦管理認證的網域帳戶。



2.  在 Configuration Manager 主控台中，按一下 [**網站資料庫 &lt; SiteCode &gt;  -  &lt; 伺服器 &gt; （ &lt; SiteName）]、[ &gt; 電腦管理**]，然後確認顯示稱為 [ **MBAM 支援的電腦**] 的新集合。

3.  在 Configuration Manager 主控台中，按一下 [**報告** &gt; **服務** &gt; ** \\\\ &lt; 伺服器 &gt; 名稱伺服器** &gt; **報告資料夾** &gt; **MBAM**]。

    確認**MBAM**資料夾包含子資料夾，且名稱代表不同語言，且下列報表列在每個語言子資料夾中：

    -   BitLocker 電腦合規性

    -   BitLocker Enterprise 合規性儀表板

    -   BitLocker 企業合規性詳細資料

    -   BitLocker Enterprise 合規性摘要

4.  在 Configuration Manager 主控台中，按一下 [**所需**的設定管理設定 &gt; **基準**]，並確認已列出 [設定比較基準**BitLocker] 保護**。

5.  在 Configuration Manager 主控台中，按一下 [**所需**的設定管理設定 &gt; **專案**]，然後確認顯示下列新的設定專案：

    -   BitLocker 固定資料磁碟機保護

    -   BitLocker 作業系統磁片磁碟機保護



## 相關主題


[設定 MBAM 2.5 伺服器功能](configuring-the-mbam-25-server-features.md)


## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。






