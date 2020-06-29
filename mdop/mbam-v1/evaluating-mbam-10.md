---
title: 評估 MBAM 1.0
description: 評估 MBAM 1.0
author: dansimp
ms.assetid: a1e2b674-eda9-4e1c-9b4c-e748470c71f2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: f09b06af52f5738fd50bfe727987b760d98552d9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811043"
---
# 評估 MBAM 1.0


在您將 Microsoft BitLocker 管理和監控（MBAM）部署到生產環境之前，您應該先在實驗室環境中評估它。 您可以使用本主題中的資訊，在單一伺服器實驗室環境中設定 MBAM，僅供評估之用。

雖然實際的部署步驟與在[單一伺服器上安裝和設定 MBAM](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md)的案例非常類似，本主題包含其他資訊，讓您在最少的時間內設定 MBAM 評估環境。

## 設定實驗室環境


即使在實驗室環境中設定非生產的 MBAM 實例，您仍然應該確認您已滿足部署的先決條件以及硬體和軟體需求。 如需詳細資訊，請參閱[MBAM 1.0 部署先決條件](mbam-10-deployment-prerequisites.md)和[MBAM 1.0 支援](mbam-10-supported-configurations.md)的設定。 您也應該在開始 MBAM 評估部署之前，先複習[準備 MBAM 1.0 的環境](preparing-your-environment-for-mbam-10.md)。

### 規劃 MBAM 評估部署

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">工作</th>
<th align="left">參考資料</th>
<th align="left">附註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>在開始進行部署規劃之前，請先查看 MBAM 的快速入門資訊，以深入瞭解產品。</p></td>
<td align="left"><p><a href="getting-started-with-mbam-10.md" data-raw-source="[Getting Started with MBAM 1.0](getting-started-with-mbam-10.md)">開始使用 MBAM 1.0</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p></p>
<p>為 MBAM 安裝準備您的計算環境。 若要這樣做，您必須在將裝載 MBAM 資料庫的 SQL Server 實例上啟用透明資料加密（TDE）。 若要在您的實驗室環境中啟用 TDE，您可以建立一個 .sql 檔案，以針對在 MBAM 將使用之 SQL Server 實例上裝載的主資料庫執行。</p>
<div class="alert">
<strong>注意</strong><br/><p>您可以使用下列範例，為您的實驗室環境建立 .sql 檔案，以便在將裝載 MBAM 資料庫的 SQL Server 實例上快速啟用 TDE。 這些 SQL Server 命令會使用本機簽署的 SQL Server 憑證來啟用 TDE。 請務必將 TDE 憑證及其相關的加密金鑰備份到 C:\Backup 的本機備份路徑 <em> </em> 。 當復原資料庫或將憑證和金鑰移至有適當的 TDE 加密的另一台伺服器時，必須有 TDE 憑證和金鑰。</p>
</div>
<div>

</div>
<pre class="syntax" space="preserve"><code>USE master;
GO
CREATE MASTER KEY ENCRYPTION BY PASSWORD = &#39;P@55w0rd&#39;;
GO
CREATE CERTIFICATE tdeCert WITH SUBJECT = &#39;TDE Certificate&#39;;
GO
BACKUP CERTIFICATE tdeCert TO FILE = &#39;C:\Backup\TDECertificate.cer&#39;
   WITH PRIVATE KEY (
         FILE = &#39;C:\Backup\TDECertificateKey.pvk&#39;,
         ENCRYPTION BY PASSWORD = &#39;P@55w0rd&#39;);
GO</code></pre></td>
<td align="left"><p><a href="mbam-10-deployment-prerequisites.md" data-raw-source="[MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md)">MBAM 1.0 部署必要條件</a></p>
<p><a href="https://go.microsoft.com/fwlink/?LinkId=269703" data-raw-source="[Database Encryption in SQL Server 2008 Enterprise Edition](https://go.microsoft.com/fwlink/?LinkId=269703)">SQL Server 2008 企業版中的資料庫加密</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>規劃及設定 MBAM 群組原則需求。</p></td>
<td align="left"><p><a href="planning-for-mbam-10-group-policy-requirements.md" data-raw-source="[Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md)">MBAM 1.0 群組原則需求規劃</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>規劃及建立必要的 Active Directory 網域服務安全性群組，並規劃 MBAM 的本地安全性群組成員資格需求。</p></td>
<td align="left"><p><a href="planning-for-mbam-10-administrator-roles.md" data-raw-source="[Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md)">MBAM 1.0 系統管理員角色規劃</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>規劃 MBAM Server 功能部署。</p></td>
<td align="left"><p><a href="planning-for-mbam-10-server-deployment.md" data-raw-source="[Planning for MBAM 1.0 Server Deployment](planning-for-mbam-10-server-deployment.md)">MBAM 1.0 伺服器部署規劃</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>規劃 MBAM 用戶端部署。</p></td>
<td align="left"><p><a href="planning-for-mbam-10-client-deployment.md" data-raw-source="[Planning for MBAM 1.0 Client Deployment](planning-for-mbam-10-client-deployment.md)">MBAM 1.0 用戶端部署規劃</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



### 執行 MBAM 評估部署

完成所需的規劃和軟體必備元件安裝後，若要為 MBAM 安裝準備您的計算環境，您可以開始進行 MBAM 評估部署。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>查看 MBAM 支援的設定資訊，以確保 MBAM 功能安裝支援所選取的用戶端和伺服器電腦。</p></td>
<td align="left"><p><a href="mbam-10-supported-configurations.md" data-raw-source="[MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md)">MBAM 1.0 支援的組態</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>若要評估，請執行 MBAM 安裝程式，在單一伺服器上部署 MBAM 伺服器功能。</p></td>
<td align="left"><p><a href="how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md" data-raw-source="[How to Install and Configure MBAM on a Single Server](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md)">如何在單一伺服器上安裝及設定 MBAM</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>將您在規劃階段建立的 Active Directory 網域服務安全性群組新增至新 MBAM 伺服器上適當的本機 MBAM 伺服器功能本機群組。</p></td>
<td align="left"><p><a href="planning-for-mbam-10-administrator-roles.md" data-raw-source="[Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md)">規劃 MBAM 1.0 系統管理員角色 </a> ，以及 <a href="how-to-manage-mbam-administrator-roles-mbam-1.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-1.md)"> 如何管理 MBAM 系統管理員角色</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>建立及部署所需的 MBAM 群組原則物件。</p></td>
<td align="left"><p><a href="deploying-mbam-10-group-policy-objects.md" data-raw-source="[Deploying MBAM 1.0 Group Policy Objects](deploying-mbam-10-group-policy-objects.md)">部署 MBAM 1.0 群組原則物件</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>部署 MBAM 用戶端軟體。</p></td>
<td align="left"><p><a href="deploying-the-mbam-10-client.md" data-raw-source="[Deploying the MBAM 1.0 Client](deploying-the-mbam-10-client.md)">部署 MBAM 1.0 用戶端</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## 設定實驗室電腦進行 MBAM 評估


您可以使用 [登錄編輯程式] 變更 MBAM 用戶端狀態報表上的頻率設定。 不過，這些修改只能用於測試目的。

**警告**  
本主題說明如何使用 [登錄編輯程式] 變更 Windows 登錄。 如果您不正確地變更 Windows 登錄，可能會導致嚴重的問題，可能需要重新安裝 Windows。 變更登錄前，您應該先製作一份登錄檔案（系統 .dat 和使用者 .dat）的備份複本。 Microsoft 不能保證變更註冊表時可能會發生的問題，可以解決。 變更註冊表的風險由您自行承擔。



### <a href="" id="modify-the-frequency-settings-on-mbam-client-status-reporting-"></a>在 MBAM 用戶端狀態報表上修改頻率設定

當 MBAM 用戶端的 [喚醒] 和 [狀態報表] 頻率設定為使用 [群組原則] 時，其最小值為90分鐘。 您可以在 MBAM 用戶端電腦上變更這些頻率，方法是將 Windows 登錄編輯為較低的值，這有助於加快測試速度。 若要在 MBAM 用戶端狀態報表上修改頻率設定，請使用登錄編輯程式流覽至**HKLM\\Software\\Policies\\FVE\\MDOPBitLockerManagement**，將**ClientWakeupFrequency**和**StatusReportingFrequency**的值變更為**1** ，以取得最小用戶端支援的值，然後重新開機 BitLocker 管理用戶端服務。 當您進行此變更時，MBAM 用戶端會每分鐘報告一次。 您可以在登錄中手動執行此動作時，將值設定為 [低]。

### <a href="" id="modify-the-startup-delay-on-mbam-client-service-"></a>修改 MBAM 用戶端服務的啟動延遲

除了 MBAM 用戶端喚醒和狀態報表頻率之外，在用戶端電腦上啟動 MBAM 用戶端代理服務時，會有最多90分鐘的隨機延遲。 如果您不想要隨機延遲，請在 [ **HKLM\\Software\\Microsoft\\MBAM**] 下建立**NoStartupDelay**的**DWORD**值，將它的值設定為**1**，然後重新開機 BitLocker 管理用戶端服務。

## 相關主題


[開始使用 MBAM 1.0](getting-started-with-mbam-10.md)









