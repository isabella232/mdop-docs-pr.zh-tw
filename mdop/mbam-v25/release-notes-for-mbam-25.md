---
title: MBAM 2.5 版本資訊
description: MBAM 2.5 版本資訊
author: dansimp
ms.assetid: fcaf03e6-5e39-4771-af3c-a3cd468f3961
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4bcc17d6295b14a7f3276146d5630b869b94b7f0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810881"
---
# MBAM 2.5 版本資訊


若要搜尋這些版本筆記，請按 Ctrl + F。

在安裝 Microsoft BitLocker 管理和監控（MBAM）2.5 之前，請先閱讀這些版本資訊。 這些版本資訊包含成功安裝 MBAM 所需的資訊，而且可能包含產品檔中不提供的資訊。 如果這些版本資訊與其他 MBAM 2.5 檔不同，請考慮將最新變更設為權威性。 這些版本資訊取代本產品隨附的內容。

## <a href="" id="---------mbam-2-5-known-issues"></a> MBAM 2.5 已知問題


本節包含適用于 MBAM 2.5 的版本資訊。

### 在無意中以系統管理員身分執行網頁瀏覽器

MBAM Server 組態工具中的 [說明] 連結會導致瀏覽器視窗以系統管理員許可權開啟。

因應措施 **：** 在流覽至其他網站前，請先啟用 Internet Explorer 增強的安全性設定（IESC）或關閉您的網頁瀏覽器。

**記事** 這個問題已在 MBAM 2.5 SP1 中修正。

 

### <a href="" id="-------------mbam-reports-as-noncompliant-a-client-encrypted-with-aes-256-bit-encryption-keys-and-diffuser"></a> 將報表 MBAM 為不相容已使用 AES 256 位加密金鑰和擴散器加密的用戶端

如果電腦已安裝 MBAM 2.5 用戶端，且是使用具有擴散器密碼強度的 AES 256 位加密，則 MBAM 用戶端會在 MBAM 合規性報告中報告為不相容。

因應措施 **：** 在[KB2975636](https://go.microsoft.com/fwlink/?LinkId=511972)安裝此熱修復程式。

### <a href="" id="-------------mbam-fails-to-encrypt-a-volume-and-reports-an-error-if-you-set-a-tpm---pin-protector-on-a-tablet-device"></a> 如果您在平板電腦裝置上設定 TPM + PIN 保護器，MBAM 無法加密某個卷，並報告錯誤

如果使用者嘗試在平板電腦裝置上設定 TPM + PIN 保護器，MBAM 無法加密，且會報告錯誤。 這個問題是因為平板電腦裝置沒有預啟動環境鍵盤。

因應措施 **：** 啟用 [**啟用在平板電腦上使用 [在平板電腦上預啟動鍵盤輸入**] 策略設定的 BitLocker 驗證。 此設定是 BitLocker 群組原則設定，且無法在 MBAM 群組原則範本中使用。

### 所有服務帳戶都需要使用者主要名稱

您必須針對 MBAM 中的所有服務帳戶設定使用者主體名稱（UPN）。 如果您無法建立帳戶的 UPN，在設定過程中會出現錯誤訊息，指出在 Active Directory 中找不到該使用者或群組。

因應措施 **：** 將 UPN 新增至服務帳戶。

### 如果用戶端電腦無法存取 Microsoft Ajax 內容傳遞網路，自助服務入口網站需要進行其他配置

如果您的用戶端電腦無法存取 Microsoft Ajax 內容傳遞網路（CDN），提供自助入口網站對某些 JavaScript 檔案所需的存取權，您必須設定自助入口網站，以參照來自易於存取之來源的 JavaScript 檔案。 如果您未在用戶端電腦無法存取 CDN 時設定自助入口網站，則只會顯示公司名稱和您登入的帳戶。 不會出現錯誤訊息。

因應措施 **：** 安裝 MBAM 2.5 SP1。 或遵循下列指示來設定自助入口網站：[如何在用戶端電腦無法存取 Microsoft 內容傳遞網路時，設定自助入口網站](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)。

### 在您升級 IIS 至 .NET Framework 4.5 之後，無法開啟自助服務入口網站與管理和監控網站

當您將網際網路資訊服務（IIS）升級至 Microsoft .NET Framework 4.5 時，系統不會開啟自助入口網站與管理與監控網站。

因應措施 **：** 在[您安裝 .Net Framework 4.0：「無法載入類型 ' system.servicemodel. HttpModule ' 之後](https://go.microsoft.com/fwlink/?LinkId=393568)，請參閱文章錯誤訊息。

### [管理及監視網站] 會在未設定報表時顯示「找不到報表」的錯誤訊息

如果您設定了 [管理及監視] 網站，然後嘗試先查看報表，但不需先設定報表功能，則錯誤訊息會指出找不到該報表。

因應措施 **：** 設定 web 應用程式之前，請先設定 [報告] 功能。

### 如果未在 SSRS 中設定 SSL，系統管理和監控網站中的報告會顯示警告

如果 SQL Server Reporting Services （SSRS）未設定為使用安全通訊端層（SSL），當您設定 MBAM 伺服器時，會將報表功能的 URL 改為 HTTP，而不是 HTTPS。 如果您接著開啟 [管理及監視] 網站並選取報告，就會出現下列錯誤訊息：「只會顯示安全內容」。

因應措施 **：** 若要顯示報表，請按一下 [**顯示所有內容**]。 若要修正此問題，請移至安裝 SQL Server Reporting Services 的 MBAM 電腦，執行**Reporting Services Configuration Manager**，然後按一下 [ **Web 服務 URL**]。 針對伺服器選取適當的 SSL 憑證，輸入適當的 SSL 埠（預設埠是443），**然後按一下 [** 套用]。

### 按一下 [BitLocker 規範摘要] 報告中的 [上一步] 可能會引發錯誤

如果您向下切入 BitLocker 相容性摘要報告，然後按一下 SSRS 報表中的**Back**連結，可能會引發錯誤。

因應措施 **：** 所有.

### 只有使用中的空間加密無法正常運作

如果您在安裝 MBAM 用戶端後第一次將電腦加密，且已將群組原則設定設為只執行加密，請 MBAM 錯誤地加密整個磁片，而不是只加密磁片的已使用空間。 如果電腦已在您安裝 MBAM 用戶端且已設定相同的群組原則設定的情況下經過加密，而您已設定相同的群組原則設定，MBAM 會報告磁片磁碟機已正確加密，且不會嘗試重新加密磁片磁碟機。

因應措施 **：** 所有.

### 密碼強度在 BitLocker 電腦合規性報告上無法正確顯示

如果您沒有在 [**選擇磁片磁碟機加密方法] 與 [密碼強度**] 群群組原則物件中設定特定的密碼強度，即使密碼強度使用預設的128位加密，Configuration Manager 整合拓撲中的 BitLocker 電腦合規性報告仍會顯示密碼強度 "unknown"。 如果您在群組原則物件中設定特定的密碼強度，報告會顯示正確的密碼強度。

因應措施 **：** 在 [**選擇磁片磁碟機加密方法及密碼強度**] 群群組原則物件中，一定要設定特定的密碼強度。

### 依磁片磁碟機類型進行合規性狀態發佈會在您更新設定專案後顯示舊資料

更新 SystemCenter2012 ConfigurationManager 中的 MBAM 設定專案之後，由 BitLocker Enterprise 合規性儀表板上的 [磁碟機類型] 橫條圖顯示的 [遵從性狀態發佈] 會顯示以舊版本的設定項目資訊為基礎的資料。

因應措施 **：** 所有. 不支援修改 MBAM 設定專案，而且報告可能不會如預期所示。

### [增強的安全性設定] 可能會導致報告無法正確顯示錯誤訊息

如果開啟 Internet Explorer 增強的安全性設定（ESC），當您嘗試在 MBAM 伺服器上查看報告時，可能會出現「拒絕存取」錯誤訊息。 根據預設，ESC 會開啟以保護伺服器，方法是將伺服器暴露在網頁內容和應用程式腳本中可能會發生的可能攻擊。

因應措施 **：** 當您嘗試在 MBAM 伺服器上查看報告時，如果出現「拒絕存取」錯誤訊息，您可以在影像中設定群組原則物件或手動變更預設值，以停用增強的安全性設定。 您也可以在未啟用 ESC 的另一部電腦上，查看報表。

## <a href="" id="hotfixes-and-knowledge-base-articles-for-mbam-2-5-"></a>MBAM 2.5 的修補程式和知識庫文章


下表列出 MBAM 2.5 的修正程式和知識庫文章。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>知識庫文章</strong></th>
<th align="left">Title</th>
<th align="left"><strong>連結</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>2975636</p></td>
<td align="left"><p>Microsoft BitLocker 管理和監視2.5 的修補程式套件1</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2975636/EN-US" data-raw-source="[support.microsoft.com/kb/2975636/EN-US](https://support.microsoft.com/kb/2975636/EN-US)">support.microsoft.com/kb/2975636/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>3015477</p></td>
<td align="left"><p>BitLocker 管理和監視2.5 的修補程式套件2</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3015477" data-raw-source="[support.microsoft.com/kb/3015477](https://support.microsoft.com/kb/3015477)">support.microsoft.com/kb/3015477</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>3011022</p></td>
<td align="left"><p>如果 SSRS 實例的名稱包含底線，MBAM 2.5 安裝或 Configuration Manager 報告就會失敗</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3011022/EN-US" data-raw-source="[support.microsoft.com/kb/3011022/EN-US](https://support.microsoft.com/kb/3011022/EN-US)">support.microsoft.com/kb/3011022/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2756402</p></td>
<td align="left"><p>事件描述中的 MBAM 用戶端將無法使用事件 ID 4 和錯誤碼0x8004100E</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2756402/EN-US" data-raw-source="[support.microsoft.com/kb/2756402/EN-US](https://support.microsoft.com/kb/2756402/EN-US)">support.microsoft.com/kb/2756402/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2639518</p></td>
<td align="left"><p>在 MBAM 中開啟企業或電腦合規性報告時發生錯誤</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2639518/EN-US" data-raw-source="[support.microsoft.com/kb/2639518/EN-US](https://support.microsoft.com/kb/2639518/EN-US)">support.microsoft.com/kb/2639518/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2870842</p></td>
<td align="left"><p>MBAM 2.0 安裝程式在 Configuration Manager 整合案例中使用 SQL Server 2008 失敗</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870842/EN-US" data-raw-source="[support.microsoft.com/kb/2870842/EN-US](https://support.microsoft.com/kb/2870842/EN-US)">support.microsoft.com/kb/2870842/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2975472</p></td>
<td align="left"><p>當許多 MBAM 用戶端連線至 MBAM 復原資料庫時，會發生 SQL 鎖死</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2975472/EN-US" data-raw-source="[support.microsoft.com/kb/2975472/EN-US](https://support.microsoft.com/kb/2975472/EN-US)">support.microsoft.com/kb/2975472/EN-US</a></p></td>
</tr>
</tbody>
</table>

 


## 相關主題


[關於 MBAM 2.5](about-mbam-25.md)

 

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





