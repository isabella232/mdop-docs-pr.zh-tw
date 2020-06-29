---
title: MBAM 2.5 群組原則需求規劃
description: MBAM 2.5 群組原則需求規劃
author: dansimp
ms.assetid: 82d545dc-3fbf-4b46-b62f-47fe178a7c44
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4beeb9f88f16e7d48d145861c398a90fa29f3491
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810154"
---
# MBAM 2.5 群組原則需求規劃


使用下列資訊來判斷您可以用來管理企業中 Microsoft BitLocker 管理和監控（MBAM）用戶端電腦的 BitLocker 保護器類型。

## MBAM 支援的 BitLocker 保護器類型


MBAM 支援下列類型的 BitLocker 保護器。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">磁片磁碟機或卷的類型</th>
<th align="left">支援的 BitLocker 保護器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>作業系統量</p></td>
<td align="left"><ul>
<li><p><strong>信賴平台模組 (TPM)</strong></p></li>
<li><p><strong>TPM + PIN</strong></p></li>
<li><p><strong></strong>只有在安裝 MBAM 之前已加密作業系統卷，才能支援 TPM + USB 金鑰</p></li>
<li><p><strong></strong> - 只有在安裝 MBAM 之前已加密作業系統卷，才支援 TPM + PIN + USB 金鑰</p></li>
<li><p><strong></strong> - 只有 Windows To Go 裝置、固定資料磁碟機、windows 8、windows 8.1 和 windows 10 裝置（沒有 TPM）支援密碼</p></li>
<li><p><strong>自動套用數位密碼 </strong> - 作為大量加密的一部分，而且不需要在 Windows 7 上的 FIPS 模式中進行設定。</p></li>
<li><p><strong>資料修復代理程式（DRA）</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>固定資料磁碟機</p></td>
<td align="left"><ul>
<li><p><strong>密碼</strong></p></li>
<li><p><strong>自動解除鎖定</strong></p></li>
<li><p><strong>自動套用數位密碼 </strong> - 作為大量加密的一部分，而且不需要在 Windows 7 上的 FIPS 模式中進行設定。</p></li>
<li><p><strong>資料修復代理程式（DRA）</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>抽取式磁碟磁碟機</p></td>
<td align="left"><ul>
<li><p><strong>密碼</strong></p></li>
<li><p><strong>自動解除鎖定</strong></p></li>
<li><p><strong>自動套用數位密碼 </strong> - 作為大量加密的一部分，而且不需要進行設定</p></li>
<li><p><strong>資料修復代理程式（DRA）</strong></p></li>
</ul></td>
</tr>
</tbody>
</table>



### 支援已使用的空間加密 BitLocker 原則

在 MBAM 2.5 SP1 中，如果您透過 BitLocker 群組原則啟用 [使用空間加密]，MBAM 用戶端就會接受這項功能。

這個群組原則設定稱為**在操作系統磁碟機上強制執行磁片磁碟機加密類型**，且位於下列 GPO 節點： [**電腦設定] 系統** &gt; **管理範本** &gt; **Windows 元件**（ &gt; **BitLocker 磁片磁碟機加密** &gt; **操作系統磁碟機**）。 如果您啟用此原則，並選取 [**僅限已使用的空間**] 加密的加密類型，MBAM 將會服從原則，而 BitLocker 將只會將在該卷上使用的磁碟空間加密。

## 如何取得 MBAM 群組原則範本並編輯設定


當您準備好要設定您想要的 MBAM 組原則設定時，請執行下列動作：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">後續步驟</th>
<th align="left">取得指示的位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>從 <a href="https://go.microsoft.com/fwlink/p/?LinkId=393941" data-raw-source="[How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941)"> 如何取得 MDOP 組原則（admx）範本，複製 MBAM 群組原則範本 </a> ，並將其安裝在能夠執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）的電腦上。</p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)">複製 MBAM 2.5 群組原則範本</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>設定您想要在企業中使用的群組原則設定。</p></td>
<td align="left"><p><a href="editing-the-mbam-25-group-policy-settings.md" data-raw-source="[Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md)">編輯 MBAM 2.5 群組原則設定</a></p></td>
</tr>
</tbody>
</table>



## MBAM 群組原則設定的描述


**MDOP MBAM （BitLocker 管理）** GPO 節點包含四個全域原則設定和四個子 GPO 節點：**用戶端管理**、**固定磁片**磁碟機、**作業系統磁片磁碟機**及**抽取式磁碟磁碟機**。 下列各節說明 MBAM 群組原則設定的設定並提供建議。

**重要**  
請勿變更**BitLocker 磁片磁碟機加密**節點中的群組原則設定，否則 MBAM 將無法正常運作。 當您設定在**MDOP MBAM （BitLocker 管理）** 節點中的設定時，MBAM 會自動設定此節點中的設定。



### 通用群組策略定義

本節說明下列 GPO 節點上的 MBAM 通用群組原則定義：**電腦**設定 &gt; **原則** &gt; **管理範本** &gt; **Windows 元件** &gt; **MDOP MBAM （BitLocker 管理）**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">原則名稱</th>
<th align="left">概覽及建議的群組原則設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>選擇磁片磁碟機加密方法與密碼強度</p></td>
<td align="left"><p>建議的設定： <strong> 已啟用</strong></p>
<p>將此原則設定為使用特定的加密方法與密碼強度。</p>
<p>如果未設定此原則，BitLocker 會使用預設的加密方法： AES 128 位與擴散器。</p>
<div class="alert">
<strong>注意</strong><br/><p>BitLocker 電腦合規性報告的問題會使其顯示 &quot; 密碼強度的 [未知] &quot; ，即使您使用的是預設值也一樣。 若要解決此問題，請確定您已啟用此設定，並設定密碼強度的值。</p>
</div>
<div>

</div>
<ul>
<li><p>僅適用于 Windows 7 的 AES 128 位（含擴散器）</p></li>
<li><p>適用于 Windows 8、Windows 8.1 和 Windows 10 的 AES 128</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>在重新開機時避免記憶體覆寫</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>設定此原則以改善重新開機效能，而不在重新開機時覆寫記憶體中的 BitLocker 機密。</p>
<p>如果未設定此原則，當電腦重新開機時，會從記憶體中移除 BitLocker 密碼。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>驗證智慧卡憑證使用規則</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>設定此原則以使用以智慧卡憑證為基礎的 BitLocker 保護。</p>
<p>如果未設定此原則，則會使用預設的物件識別碼1.3.6.1.4.1.311.67.1.1 來指定憑證。</p></td>
</tr>
<tr class="even">
<td align="left"><p>為您的組織提供唯一識別碼</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>將此原則設定為使用以憑證為基礎的資料復原代理程式或 BitLocker To Go reader。</p>
<p>如果未設定此原則， <strong> </strong> 就不會使用 [識別] 欄位。</p>
<p>如果您的公司需要較高的安全性測量，您可以設定 <strong> 識別 </strong> 欄位，以確保所有 USB 裝置都已設定此欄位，並與此群組原則設定對齊。</p></td>
</tr>
</tbody>
</table>



### 用戶端管理群組原則定義

本節說明 MBAM 在下列 GPO 節點的用戶端管理原則定義：**電腦**設定 &gt; **策略** &gt; **管理範本** &gt; **Windows 元件** &gt; **MDOP MBAM （BitLocker Management）** &gt; **用戶端管理**。

您可以針對獨立和系統中心 Configuration Manager 整合拓朴設定相同的群組原則設定，但有一個例外狀況：如果您使用的是 Configuration Manager 整合拓撲，請停用 [設定**MBAM 服務 &gt; MBAM 狀態報表服務端點**] 設定，如下表所示。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">原則名稱</th>
<th align="left">概覽及建議的群組原則設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>設定 MBAM 服務</p></td>
<td align="left"><p>建議的設定： <strong> 已啟用</strong></p>
<ul>
<li><p><strong>MBAM [恢復與硬體服務] 端點 </strong> 。 使用此設定來啟用 MBAM 用戶端 BitLocker 加密管理。 輸入與下列範例類似的端點位置： <strong> HTTP （s）// </strong><em> &lt; MBAM 管理和監視伺服器名稱 &gt; </em><strong> ： </strong><em> &lt; web 服務系結至/MBAMRecoveryAndHardwareService/CoreService.svc 的埠 &gt; </em><strong> </strong> 。</p></li>
<li><p><strong>選取要儲存的 BitLocker 復原資訊 </strong> 。 此原則設定可讓您設定金鑰復原服務來備份 BitLocker 復原資訊。 您也可以使用它來設定收集報表的狀態報表服務。 原則提供一種系統管理方法，可復原由 BitLocker 加密的資料，避免由於缺少重要資訊而造成資料遺失。 狀態報表和金鑰復原活動會自動及自動傳送到已設定的報表伺服器位置。</p>
<p>如果您未設定或停用此原則設定，就不會儲存金鑰復原資訊，且不會向伺服器報告狀態報表和金鑰復原活動。 當此設定設定為 [復原 <strong> 密碼及金鑰套件] 時 </strong> ，系統會自動將復原密碼及金鑰套件備份到已設定的金鑰復原伺服器位置。</p></li>
<li><p><strong>輸入用戶端檢查狀態頻率（分鐘） </strong> 。 此原則設定會管理用戶端檢查用戶端電腦上的 BitLocker 保護原則和狀態的頻率。 此原則也會管理將用戶端合規性狀態儲存到伺服器的頻率。 用戶端會檢查用戶端電腦上的 BitLocker 保護原則和狀態，同時也會以設定的頻率來備份用戶端復原金鑰。</p>
<p>根據貴公司設定的需求來設定此頻率，瞭解如何檢查電腦的合規性狀態，以及備份用戶端復原金鑰的頻率。</p></li>
<li><p><strong>MBAM 狀態報表服務端點：</strong></p>
<p><strong>針對獨立拓朴中的 MBAM </strong> ：您必須設定此設定，才能啟用 MBAM 用戶端 BitLocker 加密管理。</p>
<p>輸入與下列範例類似的端點位置：</p>
<p><strong>HTTP （s）// </strong><em> &lt; MBAM 管理和監視伺服器名稱 &gt; </em><strong> ： </strong><em> &lt; web 服務系結到/MBAMComplianceStatusService/StatusReportingService.svc 的埠 &gt; </em><strong></strong></p>
<p><strong>針對 Configuration Manager 整合拓撲中的 MBAM </strong> ：停用此設定。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>設定使用者豁免原則</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>此原則設定可讓您設定網站位址、電子郵件地址或電話號碼，以指示使用者從 BitLocker 加密要求例外。</p>
<p>如果您啟用此原則設定並提供網站位址、電子郵件地址或電話號碼，使用者會看到一個對話方塊，其中包含如何針對 BitLocker 保護申請免除的指示。 如需針對使用者啟用 BitLocker 加密免除的詳細資訊，請參閱 <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-25.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-25.md)"> 如何管理使用者 Bitlocker 加密免除 </a> 。</p>
<p>如果您停用或不設定此原則設定，就不會向使用者顯示免除要求指示。</p>
<div class="alert">
<strong>注意</strong><br/><p>使用者豁免是針對每個使用者管理，而不是針對每個電腦。 如果有多個使用者登入同一部電腦，且任何一位使用者都沒有免除，電腦就會經過加密。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>設定客戶經驗改進計畫</p></td>
<td align="left"><p>建議的設定： <strong> 已啟用</strong></p>
<p>此原則設定可讓您設定 MBAM 使用者如何加入客戶經驗改進計畫。 這個程式會收集電腦硬體的相關資訊，以及使用者如何使用 MBAM，而不會中斷他們的工作。 此資訊可協助 Microsoft 識別要改善的 MBAM 功能。 Microsoft 不會使用這種資訊來識別或與 MBAM 使用者。</p>
<p>如果您啟用此原則設定，使用者可以加入客戶經驗改進計畫。</p>
<p>如果您停用此原則設定，使用者就無法加入客戶經驗改進計畫。</p>
<p>如果您未設定此原則設定，使用者可以加入宣告客戶經驗改進計畫。</p></td>
</tr>
<tr class="even">
<td align="left"><p>提供安全性原則連結的 URL</p></td>
<td align="left"><p>建議的設定： <strong> 已啟用</strong></p>
<p>使用此原則設定，指定顯示給最終使用者的 URL，作為名稱為 [ &quot; 公司安全性原則] 的連結。 &quot;連結指向您公司的內部安全性原則，並為使用者提供加密需求的相關資訊。 當 MBAM 提示使用者加密磁片磁碟機時，就會出現該連結。</p>
<p>如果您啟用此原則設定，您可以設定安全性原則連結的 URL。</p>
<p>如果您停用或不設定此原則設定，就不會向使用者顯示 [安全性原則] 連結。</p></td>
</tr>
</tbody>
</table>



### 固定磁片磁碟機群組原則定義

本節說明在下列 GPO 節點上進行 Microsoft BitLocker 管理和監視的固定磁片磁碟機策略定義：**電腦**設定 &gt; **策略**系統 &gt; **管理範本** &gt; **Windows 元件** &gt; **MDOP MBAM （BitLocker Management）** 已固定的 &gt; **磁片磁碟機**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">原則名稱</th>
<th align="left">概覽及建議的群組原則設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>固定資料磁片磁碟機加密設定</p></td>
<td align="left"><p>建議的設定： <strong> 已啟用</strong></p>
<p>此原則設定可讓您管理固定資料磁碟機是否必須加密。</p>
<p>如果需要加密作業系統卷，請按一下 [ <strong> 啟用自動解鎖固定資料磁碟機] </strong> 。</p>
<p>當您啟用此原則時， <strong> </strong> 除非您要啟用或要求對固定資料磁碟機使用自動解鎖，否則您不能停用 [設定固定資料磁碟機使用密碼] 原則。</p>
<p>如果您必須針對固定資料磁碟機使用自動解鎖，您必須設定要加密的作業系統卷。</p>
<p>如果您啟用此原則設定，使用者必須將所有固定資料磁碟機放在 BitLocker 保護之下，然後再加密資料磁片磁碟機。</p>
<p>如果您未設定此原則設定，則不需要使用者將固定的資料磁碟機放在 BitLocker 保護之下。 如果您在已加密固定資料磁碟機之後套用此原則，則 MBAM agent 會將加密的固定資料磁碟機解密。</p>
<p>如果您停用此原則設定，使用者就無法將其固定資料磁碟機放在 BitLocker 保護底下。</p></td>
</tr>
<tr class="even">
<td align="left"><p>拒絕寫入存取不受 BitLocker 保護的固定式磁碟機</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>此原則設定決定固定資料磁碟機是否需要 BitLocker 保護，才能在電腦上寫入。 當您開啟 BitLocker 時，就會套用此原則設定。</p>
<p>如果未設定原則，電腦上所有的固定資料磁碟機都會以讀取/寫入權限掛載。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>允許從較舊版本的 Windows 存取受 BitLocker 保護的固定磁片磁碟機</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>啟用此原則，以便在執行 Windows Server 2008、Windows Vista、windows XP （含 SP3）或 Windows XP 的電腦上，解除鎖定與 FAT 檔案系統的固定磁片磁碟機。</p>
<p>如果已啟用或未設定原則，就可以在執行 Windows Server 2008、Windows Vista、windows XP （含 SP3）或 Windows XP 的電腦上，解除鎖定以 FAT 檔案系統格式化的固定磁片磁碟機。 這些作業系統擁有受 BitLocker 保護的磁片磁碟機的唯讀許可權。</p>
<p>當原則停用時，使用 FAT 檔案系統格式化的固定磁片磁碟機將無法解除鎖定，而且無法在執行 Windows Server 2008、Windows Vista、Windows XP （含 SP3）的電腦上，或使用 SP2 的 Windows XP 中查看其內容。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定在固定磁片磁碟機使用密碼</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>使用此原則來指定是否需要密碼來解除鎖定受 BitLocker 保護的固定資料磁碟機。</p>
<p>如果您啟用此原則設定，使用者可以設定符合您所定義需求的密碼。 BitLocker 可讓使用者以磁片磁碟機上可用的任何保護器解除鎖定磁片磁碟機。</p>
<p>當您開啟 BitLocker，而不是當您解除鎖定時，就會強制執行這些設定。</p>
<p>如果您停用此原則設定，就不允許使用者使用密碼。</p>
<p>如果未設定原則，預設設定就會支援密碼，這不會包含密碼複雜性需求，且只需要八個字元。</p>
<p>若要獲得較高的安全性，請啟用此原則，然後選取 [ <strong> 針對固定資料磁碟機需要密碼] </strong> ，按一下 <strong> [需要密碼複雜性] </strong> ，然後設定 <strong> </strong> 您想要的最小密碼長度。</p>
<p>如果您停用此原則設定，就不允許使用者使用密碼。</p>
<p>如果您未設定此原則設定，則會支援密碼（預設設定），不包含密碼複雜性需求，且只需要八個字元。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>選擇如何復原受 BitLocker 保護的固定磁片磁碟機</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>設定此原則以啟用 BitLocker 資料復原代理程式，或將 BitLocker 復原資訊儲存至 Active Directory 網域服務（AD DS）。</p>
<p>如果未設定原則，就會允許 BitLocker 資料復原代理程式，且不會將復原資訊備份到 AD DS。 MBAM 不需要將復原資訊備份到 AD DS。</p></td>
</tr>
<tr class="even">
<td align="left"><p>加密原則強制設定</p></td>
<td align="left"><p>建議的設定： <strong> 已啟用</strong></p>
<p>使用此原則設定來設定固定資料磁碟機可保持不相容的天數，直到強制符合 MBAM 原則為止。 使用者在寬限期之後，不能推遲所需的動作，也不能要求其例外狀況。 當固定資料磁碟機被認為不相容時，寬限期就會開始。 不過，除非操作系統磁碟機符合規範，否則系統不會強制執行固定資料磁碟機原則。</p>
<p>如果寬限期已到期，且固定資料磁碟機仍不合規，則使用者不能選擇推遲或要求免除。 如果加密程式需要使用者輸入，則會顯示一個對話方塊，讓使用者無法關閉，直到它們提供所需的資訊為止。</p>
<p><strong> </strong> 在 [設定固定磁碟機的不符合寬限期天數] 中輸入0， <strong> </strong> 即可強制在作業系統磁片磁碟機的寬限期到期後立即開始加密程式。</p>
<p>如果您停用或不設定此設定，使用者就不會強制遵守 MBAM 原則。</p>
<p>如果不需要使用者互動，即可新增保護器，則在寬限期到期之後，就會在背景中開始加密。</p></td>
</tr>
</tbody>
</table>



### 作業系統磁片磁碟機群組原則定義

本節說明 Microsoft BitLocker 在下列 GPO 節點上進行管理和監控的作業系統磁片磁碟機原則定義：**電腦**設定 &gt; **策略** &gt; **管理範本** &gt; **Windows 元件** &gt; **MDOP MBAM （BitLocker Management）** &gt; **作業系統磁片磁碟機**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">原則名稱</th>
<th align="left">概覽及建議的群組原則設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>作業系統磁片磁碟機加密設定</p></td>
<td align="left"><p>建議的設定： <strong> 已啟用</strong></p>
<p>此原則設定可讓您管理作業系統磁片磁碟機是否必須經過加密。</p>
<p>若要獲得較高的安全性，請考慮在 <strong> </strong> &gt; <strong> </strong> &gt; <strong> </strong> 使用 TPM + PIN 保護器啟用系統電源管理睡眠設定時停用下列原則設定：</p>
<ul>
<li><p>在休眠（電源開啟）時允許待機狀態（S1-S3）</p></li>
<li><p>在睡眠時允許待機狀態（S1-S3）（使用電池）</p></li>
</ul>
<p>如果您執行的是 Microsoft Windows 8 或更新版本，而您想要在沒有 TPM 的電腦上使用 BitLocker，請選取 [ <strong> 允許沒有相容的 tpm 的 bitlocker] </strong> 核取方塊。 在此模式中，啟動需要密碼。 如果您忘記密碼，您必須使用其中一個 BitLocker 復原選項來存取磁片磁碟機。</p>
<p>在有相容的 TPM 的電腦上，啟動時可以使用兩種類型的驗證方法，為加密資料提供額外的保護。 電腦啟動時，只能使用 TPM 進行驗證，或者也可能需要輸入個人識別碼（PIN）。</p>
<p>如果您啟用此原則設定，使用者必須將操作系統磁碟機放在 BitLocker 保護之下，然後再加密磁片磁碟機。</p>
<p>如果您停用這個原則，使用者就無法將操作系統磁碟機放在 BitLocker 保護下。 如果您在作業系統磁片磁碟機經過加密之後套用此原則，就會解密磁片磁碟機。</p>
<p>如果您未設定此原則，則不需要在 BitLocker 保護下放置作業系統磁片磁碟機。</p></td>
</tr>
<tr class="even">
<td align="left"><p>允許增強的 Pin 以進行啟動</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>使用此原則設定來設定是否與 BitLocker 搭配使用增強的啟動 Pin。 增強的啟動 Pin 允許使用字元，包括大寫及小寫字母、符號、數位和空格。 當您開啟 BitLocker 時，就會套用此原則設定。</p>
<p>如果您啟用此原則設定，所有新的 BitLocker 啟動 Pin 設定將會讓使用者能夠建立增強的 Pin。 不過，並非所有電腦都能在預先引導環境中支援增強的 Pin。 我們強烈建議管理員先評估其系統是否與此功能相容，才能啟用其使用。</p>
<p>選取 [ <strong> 需要 ASCII 專用 pin] </strong> 核取方塊，以協助將增強的 pin 與限制可在預先啟動環境中輸入之字元類型或字元數的電腦相容。</p>
<p>如果您停用或不設定此原則設定，就不會使用增強的 Pin。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>選擇可如何復原受 BitLocker 保護的操作系統磁碟機</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>設定此原則以啟用 BitLocker 資料復原代理程式，或將 BitLocker 復原資訊儲存至 Active Directory 網域服務（AD DS）。</p>
<p>如果未設定此原則，就可以使用資料復原代理程式，且不會將復原資訊備份到 AD DS。</p>
<p>MBAM 操作不需要將復原資訊備份到 AD DS。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定作業系統磁片磁碟機的密碼使用</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>使用此原則設定來設定用來解除鎖定受 BitLocker 保護之作業系統磁片磁碟機之密碼的限制。 如果在作業系統磁片磁碟機上允許非 TPM 保護器，您可以為密碼設定密碼、強制執行複雜性需求，以及設定密碼的最小長度。 為了使複雜性需求設定生效，您也必須啟用 [電腦設定] 中的 [群組原則設定 &quot; 密碼必須符合複雜性需求] （ &quot; 位於 [電腦設定] 中的 [ &gt; 設定 &gt; 安全設定] &gt; 帳戶原則 &gt; 密碼原則中）。</p>
<div class="alert">
<strong>注意</strong><br/><p>當您開啟 BitLocker，而不是當您解除鎖定時，就會強制執行這些設定。 BitLocker 可讓您使用磁片磁碟機上可用的任何保護器解除鎖定磁片磁碟機。</p>
</div>
<div>

</div>
<p>如果您啟用此原則設定，使用者可以設定符合您所定義需求的密碼。 若要強制密碼的複雜性需求，按一下 [ <strong> 需要密碼複雜性] </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>針對 BIOS 式固件配置設定 TPM 平臺驗證設定檔</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>此原則設定可讓您設定電腦&#39;s 受信任的平臺模組（TPM）安全性硬體保護 BitLocker 加密金鑰的方式。 如果電腦沒有相容的 TPM，或已使用 TPM 保護開啟 BitLocker，此原則設定就不適用。</p>
<div class="alert">
<strong>重要</strong><br/><p>這個群組原則設定僅適用于具備 BIOS 設定的電腦，或使用啟用相容性服務模組（CSM）的具備 UEFI 固件的電腦。 使用原生 UEFI 固件配置的電腦會將不同的值儲存在平臺設定寄存器（PCRs）中。 使用 [ &quot; 設定適用于原生 uefi 固件配置的 tpm 平臺驗證設定檔] &quot; 群群組原則設定，以設定適用于使用原生 UEFI 固件之電腦的 tpm PCR 設定檔。</p>
</div>
<div>

</div>
<p>如果您在開啟 BitLocker 之前啟用此原則設定，您可以先設定 TPM 驗證的啟動元件，才能解除鎖定 BitLocker 加密操作系統磁碟機的存取權。 如果在 BitLocker 保護生效時，有任何元件變更，則 TPM 不會放開加密金鑰來解除鎖定磁片磁碟機，電腦則改為顯示 BitLocker 復原主機，並要求您提供恢復密碼或復原金鑰來解除鎖定磁片磁碟機。</p>
<p>如果您停用或不設定此原則設定，BitLocker 會使用預設平臺驗證設定檔或由安裝腳本指定的平臺驗證設定檔。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定 TPM 平臺驗證設定檔</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>此原則設定可讓您設定電腦&#39;s 受信任的平臺模組（TPM）安全性硬體保護 BitLocker 加密金鑰的方式。 如果電腦沒有相容的 TPM，或已使用 TPM 保護開啟 BitLocker，此原則設定就不適用。</p>
<p>如果您在開啟 BitLocker 之前啟用此原則設定，您可以先設定 TPM 驗證的啟動元件，才能解除鎖定 BitLocker 加密操作系統磁碟機的存取權。 如果在 BitLocker 保護生效時，有任何元件變更，則 TPM 不會放開加密金鑰來解除鎖定磁片磁碟機，電腦則改為顯示 BitLocker 復原主機，並要求您提供恢復密碼或復原金鑰來解除鎖定磁片磁碟機。</p>
<p>如果您停用或不設定此原則設定，BitLocker 會使用預設平臺驗證設定檔或由安裝腳本指定的平臺驗證設定檔。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>針對原生 UEFI 固件配置設定 TPM 平臺驗證設定檔</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>此原則設定可讓您設定電腦&#39;s 受信任的平臺模組（TPM）安全性硬體保護 BitLocker 加密金鑰的方式。 如果電腦沒有相容的 TPM，或已使用 TPM 保護開啟 BitLocker，此原則設定就不適用。</p>
<div class="alert">
<strong>重要</strong><br/><p>這個群組原則設定僅適用于具有原生 UEFI 固件配置的電腦。</p>
</div>
<div>

</div>
<p>如果您在開啟 BitLocker 之前啟用此原則設定，您可以先設定 TPM 驗證的啟動元件，才能解除對 BitLocker 加密操作系統磁碟機的存取。 如果在 BitLocker 保護生效時，有任何元件變更，則 TPM 不會放開加密金鑰來解除鎖定磁片磁碟機，電腦則改為顯示 BitLocker 復原主機，並要求您提供恢復密碼或復原金鑰來解除鎖定磁片磁碟機。</p>
<p>如果您停用或不設定此原則設定，BitLocker 會使用預設平臺驗證設定檔或由安裝腳本指定的平臺驗證設定檔。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在 BitLocker 恢復之後重設平臺驗證資料</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>使用此原則設定，控制在 BitLocker 復原後啟動 Windows 時，是否要重新整理 platform 驗證資料。</p>
<p>如果您啟用此原則設定，當 Windows 在 BitLocker 恢復之後啟動時，平臺驗證資料就會重新整理。 如果您停用此原則設定，當 Windows 在 BitLocker 恢復之後啟動時，平臺驗證資料就不會重新整理。 如果您未設定此原則設定，則會在 BitLocker 恢復後啟動 Windows 時，重新整理平臺驗證資料。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>使用增強型啟動設定資料驗證設定檔</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>此原則設定可讓您選擇要在平臺驗證期間進行驗證的特定開機設定資料（BCD）設定。</p>
<p>如果您啟用此原則設定，您可以新增其他設定、移除預設設定，或兩者皆移除。 如果您停用此原則設定，電腦會還原為與 Windows 7 所使用的預設 BCD 設定檔類似的 BCD 設定檔。 如果您未設定此原則設定，電腦會驗證預設的 Windows BCD 設定。</p>
<div class="alert">
<strong>注意</strong><br/><p>當 BitLocker 使用安全啟動來進行平臺與啟動配置資料（BCD）完整性驗證時，如 [ &quot; 允許完整性驗證的安全引導] 原則所定義 &quot; ，則 &quot; 會忽略 [使用增強型引導設定資料驗證設定檔 &quot; 原則]。</p>
</div>
<div>

</div>
<p>控制引導調試（0x16000010）的設定總是經過驗證，且在提供的欄位中包含它時不會有任何作用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>加密原則強制設定</p></td>
<td align="left"><p>建議的設定： <strong> 已啟用</strong></p>
<p>使用此原則設定，以設定使用者可針對其作業系統磁片磁碟機遵循 MBAM 原則而延遲的天數。 寬限期在第一次偵測到作業系統為不相容時開始。 此寬限期到期之後，使用者就無法推遲所需的動作，或要求它提出例外狀況。</p>
<p>如果加密程式需要使用者輸入，則會顯示一個對話方塊，讓使用者無法關閉，直到它們提供所需的資訊為止。</p>
<p>如果您停用或不設定此設定，使用者就不會強制遵守 MBAM 原則。</p>
<p>如果不需要使用者互動，即可新增保護器，則在寬限期到期之後，就會在背景中開始加密。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>設定預先啟動的恢復訊息和 URL</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>啟用此原則設定以設定自訂的復原訊息，或指定當操作系統磁碟機已鎖定時，在預啟動 BitLocker 恢復畫面上顯示的 URL。 這個設定只能在執行 Windows 10 的用戶端電腦上使用。</p>
<p>啟用此原則時，您可以針對預啟動還原訊息選取下列其中一個選項：</p>
<ul>
<li><p><strong>使用自訂的復原訊息 </strong> ：選取這個選項，即可在 [預啟動 BitLocker 恢復] 畫面中包含自訂訊息。 在 [ <strong> 自訂復原訊息] 選項方塊中 </strong> ，輸入您要顯示的訊息。 如果您也想要指定復原 URL，請將它包含在您的自訂復原訊息中。</p></li>
<li><p><strong>使用自訂的復原 URL </strong> ：選取這個選項，以取代 [預啟動 BitLocker 恢復] 畫面中顯示的預設 URL。 在 [ <strong> 自訂恢復 URL] 選項方塊中 </strong> ，輸入您要顯示的 URL。</p></li>
<li><p><strong>使用預設的復原訊息和 URL </strong> ：選取這個選項，即可在 [啟動前的 bitlocker 恢復] 畫面中顯示預設的 BitLocker 復原訊息和 URL。 如果您先前已設定自訂的復原訊息或 URL，且想要還原為預設訊息，您必須啟用此原則，然後選取 [ <strong> 使用預設的復原訊息與 URL] </strong> 選項。</p></li>
</ul>
<div class="alert">
<strong>注意</strong><br/><p>在預引導中不支援所有的字元和語言。 我們建議您在預啟動 BitLocker 恢復畫面上，測試您在自訂訊息或 URL 所使用的字元是否正確顯示。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



### 抽取式磁碟磁碟機群組原則定義

本節說明 Microsoft BitLocker 管理和監視下列 GPO 節點的抽取式磁碟磁碟機組原則定義： [**電腦**設定 &gt; **策略**] &gt; **管理範本** &gt; **Windows 元件** &gt; **MDOP MBAM （BitLocker 管理）** &gt; **抽取式磁碟磁碟機**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">原則名稱</th>
<th align="left">概覽及建議的群組原則設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在抽取式磁碟磁碟機上控制 BitLocker 的使用</p></td>
<td align="left"><p>建議的設定： <strong> 已啟用</strong></p>
<p>此原則控制如何在可移動資料磁碟機上使用 BitLocker。</p>
<p>按一下 [ <strong> 允許使用者在可移動資料磁碟機上套用 bitlocker 保護 </strong> ]，可讓使用者在可移除的資料磁碟機上執行 bitlocker 設定向導。</p>
<p>按一下 [ <strong> 允許使用者暫停並解密可移動資料磁碟機上的 bitlocker]， </strong> 可讓使用者從磁片磁碟機移除 bitlocker 磁片磁碟機加密，或在執行維護時暫停加密。</p>
<p>啟用此原則時，當您按一下 <strong> [允許使用者在可移動資料磁碟機上套用 BitLocker 保護] 時 </strong> ，MBAM 用戶端會將抽取式磁碟磁碟機的復原資訊儲存至 MBAM 金鑰復原伺服器，並允許使用者在密碼遺失時復原磁片磁碟機。</p></td>
</tr>
<tr class="even">
<td align="left"><p>拒絕寫入存取不受 BitLocker 保護的抽取式磁碟機</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>啟用此原則，只允許將寫入權限給受 BitLocker 保護的磁片磁碟機。</p>
<p>如果啟用此原則，電腦上所有的可移動資料磁碟機都必須先加密，才能允許寫入權限。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>允許從舊版 Windows 存取受 BitLocker 保護的抽取式磁碟磁碟機</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>啟用此原則可讓使用 FAT 檔案系統的固定磁片磁碟機解除鎖定，並在執行 Windows Server 2008、Windows Vista、Windows XP （含 SP3）或 Windows XP （含 SP2）的電腦上進行查看。</p>
<p>如果未設定此原則，則可以在執行 Windows Server 2008、Windows Vista、Windows XP （含 SP3）或 Windows XP （含 SP2）的電腦上解除鎖定使用 FAT 檔案系統格式化的抽取式磁碟磁碟機，並且能夠查看其內容。 這些作業系統擁有受 BitLocker 保護的磁片磁碟機的唯讀許可權。</p>
<p>當原則停用時，無法在執行 Windows Server 2008、Windows Vista、windows XP 的電腦上，或使用 SP2，在執行 Windows Server、Windows Vista、Windows XP 或 Windows XP 的電腦上，查看以 FAT 檔案系統格式化的抽取式磁碟磁碟機。</p></td>
</tr>
<tr class="even">
<td align="left"><p>針對可移動資料磁碟機設定密碼的使用方式</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>啟用此原則，在可移動資料磁碟機上設定密碼保護。</p>
<p>如果未設定此原則，預設設定就會支援密碼，這不會包含密碼複雜性需求，且只需要八個字元。</p>
<p>若要提高安全性，您可以啟用此原則，然後選取 [ <strong> 移除資料磁片磁碟機需要密碼] </strong> 、按一下 <strong> [需要密碼複雜性] </strong> ，然後設定首選的 <strong> 最小密碼長度 </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>選擇可如何復原受 BitLocker 保護的抽取式磁碟磁碟機</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>設定此原則以啟用 BitLocker 資料復原代理程式，或將 BitLocker 復原資訊儲存至 Active Directory 網域服務（AD DS）。</p>
<p>如果設定為 [未設定] <strong> </strong> ，則允許資料修復代理程式，且不會將復原資訊備份到 AD DS。</p>
<p>MBAM 操作不需要將復原資訊備份到 AD DS。</p></td>
</tr>
</tbody>
</table>




## 相關主題


[MBAM 2.5 的環境準備](preparing-your-environment-for-mbam-25.md)

[MBAM 2.5 部署必要條件](mbam-25-deployment-prerequisites.md)


## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。






