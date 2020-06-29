---
title: MBAM 2.0 群組原則需求規劃
description: MBAM 2.0 群組原則需求規劃
author: dansimp
ms.assetid: f5e19dcb-eb15-4722-bb71-0734b3799eb8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f6092507996fe6f0234178c8b1abae5cea7bf836
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800191"
---
# MBAM 2.0 群組原則需求規劃


若要管理 Microsoft BitLocker 管理與監控（MBAM）用戶端電腦，您需要考慮您要在組織中支援的 BitLocker 保護器類型，然後設定您要套用的對應群組原則設定。 本主題說明當您使用 Microsoft BitLocker 管理和監視來管理企業中的 BitLocker 磁碟機加密時可使用的群組原則設定。

MBAM 支援下列作業系統磁片磁碟機的 BitLocker 保護器類型：受信任的平臺模組（TPM）、TPM + PIN、TPM + USB 金鑰，以及 TPM + PIN + USB 金鑰、密碼、數位密碼及資料修復代理程式。 只有 Windows To Go 裝置以及沒有 TPM 的 Windows 8 裝置支援密碼保護器。 只有在安裝 MBAM 之後才會加密作業系統標籤，MBAM 才支援 TPM + USB 金鑰和 TPM + PIN + USB 金鑰保護器。

MBAM 支援下列固定資料磁碟機類型的 BitLocker 保護器：密碼、自動解鎖、數位密碼及資料修復代理程式。

數位密碼保護程式會自動套用為大量加密的一部分，而且不需要加以設定。

**重要**  
MBAM 不會使用預設的 Windows BitLocker 磁碟機加密群組原則物件（GPO）設定，而且可能會造成衝突行為（如果已啟用的話）。 若要啟用 MBAM 來管理 BitLocker，您必須在安裝 MBAM 群組原則範本之後，才能定義 MBAM 群組原則設定。



增強的啟動 Pin 可以包含字元，例如大寫、小寫字母和數位。 與 BitLocker 不同的是，MBAM 不支援使用符號和空格來增強針腳。

在能夠執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM） MDOP 技術的電腦上，安裝 MBAM 群組原則範本。 若要編輯啟用 MBAM 功能的 GPO 設定，您必須先安裝 MBAM 群組原則範本，然後開啟 GPMC 或 AGPM 來編輯適用的 gpo，然後流覽至下列 GPO 節點： [電腦設定**Computer Configuration** \\ **原則**] \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker Management）。**

MDOP MBAM （BitLocker 管理） GPO 節點包含四個全域原則設定和四個子 GPO 設定節點：用戶端管理、固定磁片磁碟機、作業系統磁片磁碟機及抽取式磁碟磁碟機。 下列各節提供原則定義及建議的原則設定，以協助您規劃 MBAM GPO 原則設定需求。

**注意**  
如需設定最小（建議的） GPO 設定以啟用 MBAM 以管理 BitLocker 加密的詳細資訊，請參閱[如何編輯 MBAM 2.0 GPO 設定](how-to-edit-mbam-20-gpo-settings-mbam-2.md)。



## 全域原則定義


本節說明在下列 GPO 節點上找到的 MBAM 全域原則定義：**電腦**設定 \\ **策略** \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker Management）**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">原則名稱</th>
<th align="left">[概覽] 和 [建議的原則] 設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>選擇磁片磁碟機加密方法與密碼強度</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>將此原則設定為使用特定的加密方法與密碼強度。</p>
<p>如果未設定此原則，BitLocker 會將 AES 128 位的預設加密方法與擴散器或由安裝腳本指定的加密方法結合使用。</p></td>
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
<p>如果未設定此原則，則會使用預設物件識別碼1.3.6.1.4.1.311.67.1.1 來指定憑證。</p></td>
</tr>
<tr class="even">
<td align="left"><p>為您的組織提供唯一識別碼</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>將此原則設定為使用以憑證為基礎的資料復原代理程式或 BitLocker To Go reader。</p>
<p>如果未設定此原則， <strong> </strong> 就不會使用 [識別] 欄位。</p>
<p>如果您的公司需要較高的安全性測量，您可能會想要設定 <strong> 識別 </strong> 欄位，以確保所有的 USB 裝置都有此欄位集，且與此群組原則設定一致。</p></td>
</tr>
</tbody>
</table>



## 用戶端管理原則定義


本節說明 Microsoft BitLocker 管理和監控在下列 GPO 節點上找到的用戶端管理原則定義：**電腦**設定 \\ **策略**系統 \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker Management）** \\ **用戶端管理**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">原則名稱</th>
<th align="left">概覽和建議的原則設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>設定 MBAM 服務</p></td>
<td align="left"><p>建議的設定： <strong> 已啟用</strong></p>
<ul>
<li><p><strong>MBAM [恢復與硬體服務] 端點 </strong> 。 使用此設定來啟用 MBAM 用戶端 BitLocker 加密管理。 輸入與下列範例類似的端點位置： <strong> HTTP:// </strong><em> &lt; MBAM 管理及監視伺服器名稱 &gt; </em><strong> ： </strong><em> &lt; 埠該 web 服務已系結至 &gt; </em><strong> /MBAMRecoveryAndHardwareService/CoreService.svc </strong> 。</p></li>
<li><p><strong>選取要儲存的 BitLocker 復原資訊 </strong> 。 此原則設定可讓您設定金鑰復原服務來備份 BitLocker 復原資訊。 它也可讓您設定狀態報表服務，以收集合規性和審核報告。 原則提供一種系統管理方法，可復原由 BitLocker 加密的資料，避免由於缺少重要資訊而造成資料遺失。 狀態報表和金鑰復原活動將會自動傳送到已設定的報表伺服器位置。</p>
<p>如果您未設定或停用此原則設定，就不會儲存金鑰復原資訊，且狀態報表和金鑰復原活動將不會報告給伺服器。 當此設定設定為 [復原 <strong> 密碼及金鑰套件] 時，系統會自動將復原 </strong> 密碼及金鑰套件備份到已設定的金鑰復原伺服器位置。</p></li>
<li><p><strong>輸入用戶端檢查狀態頻率（分鐘） </strong> 。 此原則設定會管理用戶端檢查用戶端電腦上的 BitLocker 保護原則和狀態的頻率。 此原則也會管理將用戶端合規性狀態儲存到伺服器的頻率。 用戶端會檢查用戶端電腦上的 BitLocker 保護原則和狀態，同時也會以設定的頻率來備份用戶端復原金鑰。</p>
<p>根據貴公司所設定的需求來設定此頻率，以查看電腦合規性狀態的頻率，以及備份用戶端復原金鑰的頻率。</p></li>
<li><p><strong>MBAM 狀態報表服務端點 </strong> 。 您必須設定此設定，才能啟用 MBAM 用戶端 BitLocker 加密管理。 輸入與下列範例類似的端點位置： <strong> HTTP:// </strong><em> &lt; MBAM 管理及監視伺服器名稱 &gt; </em><strong> ： </strong><em> &lt; 埠該 web 服務已系結至 &gt; </em><strong> /MBAMComplianceStatusService/StatusReportingService.svc </strong> 。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>設定使用者豁免原則</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>此原則設定可讓您設定網站位址、電子郵件地址或電話號碼，這將會指示使用者從 BitLocker 加密要求例外。</p>
<p>如果您啟用此原則設定並提供網站位址、電子郵件地址或電話號碼，使用者將會看到一個對話方塊，提供給他們如何針對 BitLocker 保護申請免除的指示。 如需針對使用者啟用 BitLocker 加密免除的詳細資訊，請參閱 <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md)"> 如何管理使用者 Bitlocker 加密免除 </a> 。</p>
<p>如果您停用或不設定此原則設定，就不會向使用者顯示免除要求指示。</p>
<div class="alert">
<strong>注意</strong><br/><p>使用者豁免是針對每個使用者管理，而不是針對每個電腦。 如果有多個使用者登入同一部電腦，而任何一個使用者並未免除，電腦將會經過加密。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>設定客戶經驗改進計畫</p></td>
<td align="left"><p>此原則設定可讓您設定 MBAM 使用者如何加入客戶經驗改進計畫。 這個程式會收集電腦硬體的相關資訊，以及使用者如何使用 MBAM，而不會中斷他們的工作。 此資訊可協助 Microsoft 識別要改善的 MBAM 功能。 Microsoft 不會使用這種資訊來識別或與 MBAM 使用者。</p>
<p>如果您啟用此原則設定，使用者將能夠加入客戶經驗改進計畫。</p>
<p>如果您停用此原則設定，使用者將無法加入客戶經驗改進計畫。</p>
<p>如果您未設定此原則設定，使用者將可以加入宣告客戶經驗改進計畫。</p></td>
</tr>
</tbody>
</table>



## 固定的磁片磁碟機原則定義


本節說明在下列 GPO 節點上找到的 Microsoft BitLocker 管理和監視的固定磁片磁碟機原則定義：**電腦**設定 \\ **策略**系統 \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker Management）** 已固定的 \\ **磁片磁碟機**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">原則名稱</th>
<th align="left">[概覽] 和 [建議的原則] 設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>固定資料磁片磁碟機加密設定</p></td>
<td align="left"><p>建議的設定： <strong> 已啟用</strong></p>
<p>此原則設定可讓您管理是否必須加密固定的磁片磁碟機。</p>
<p>如果需要加密作業系統卷，請選取 [ <strong> 啟用自動解鎖固定資料磁碟機] </strong> 選項。</p>
<p>啟用此原則時， <strong> </strong> 除非允許或需要在固定資料磁碟機上使用自動解鎖，否則您不能停用 [設定使用密碼來固定資料磁碟機策略]。</p>
<p>如果您需要在固定資料磁碟機上使用自動解鎖，您必須設定要加密的作業系統卷。</p>
<p>如果您啟用此原則設定，使用者必須將所有固定磁碟機放在 BitLocker 保護之下，且這些磁碟機將會經過加密。</p>
<p>如果您未設定此原則設定，則不需要使用者將固定磁片放在 BitLocker 保護之下。 如果您在已加密固定資料磁碟機之後套用此原則，則 MBAM agent 會將加密的固定磁片磁碟機解密。</p>
<p>如果您停用此原則設定，使用者將無法將其固定資料磁碟機放在 BitLocker 保護底下。</p></td>
</tr>
<tr class="even">
<td align="left"><p>拒絕寫入存取不受 BitLocker 保護的固定式磁碟機</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>此原則設定決定在電腦上，固定磁片磁碟機是否需要進行 BitLocker 保護。 當您開啟 BitLocker 時，就會套用此原則設定。</p>
<p>如果未設定原則，電腦上所有的固定資料磁碟機都會以讀取和寫入存取權掛載。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>允許從較舊版本的 Windows 存取受 BitLocker 保護的固定磁片磁碟機</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>啟用此原則可在執行 Windows Server 2008、Windows Vista、windows XP （含 SP3）或 Windows XP （含 SP2）的電腦上解除鎖定並查看含有 FAT 檔案系統的固定磁片磁碟機。</p>
<p>如果已啟用或未設定原則，就可以在執行 Windows Server 2008、Windows Vista、windows XP （含 SP3）或 Windows XP 的電腦上，解除鎖定使用 FAT 檔案系統格式化的固定磁片磁碟機，以及其內容。 這些作業系統擁有受 BitLocker 保護的磁片磁碟機的唯讀存取權。</p>
<p>當原則停用時，使用 FAT 檔案系統格式化的固定磁片磁碟機將無法解除鎖定，而且無法在執行 Windows Server 2008、Windows Vista、Windows XP （含 SP3）的電腦上，或使用 SP2 的 Windows XP 中查看其內容。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定在固定磁片磁碟機使用密碼</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>使用此原則來指定是否需要密碼來解除鎖定受 BitLocker 保護的固定資料磁碟機。</p>
<p>如果您啟用此原則設定，使用者可以設定符合您所定義需求的密碼。 BitLocker 將允許使用者使用磁片磁碟機上提供的任何保護程式來解除鎖定磁片磁碟機。</p>
<p>當您開啟 BitLocker 時，就會強制執行這些設定，而不是在解除音量鎖定時。</p>
<p>如果您停用此原則設定，就不允許使用者使用密碼。</p>
<p>如果未設定原則，預設設定就會支援密碼，這不會包含密碼複雜性需求，且只需要八個字元。</p>
<p>若要獲得較高的安全性，請啟用此原則，並選取 [ <strong> 需要密碼才能修正資料磁碟機] </strong> ，選取 <strong> [需要密碼複雜性] </strong> ，然後設定所需的 <strong> 最小密碼長度 </strong> 。</p>
<p>如果您停用此原則設定，就不允許使用者使用密碼。</p>
<p>如果您未設定此原則設定，系統會支援密碼，預設設定不包含密碼複雜性需求，且只需要八個字元。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>選擇如何復原受 BitLocker 保護的固定磁片磁碟機</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>設定此原則以啟用 BitLocker 資料復原代理程式，或將 BitLocker 復原資訊儲存至 Active Directory 網域服務（AD DS）。</p>
<p>如果未設定原則，就會允許 BitLocker 資料復原代理程式，且不會將復原資訊備份到 AD DS。 MBAM 不需要將復原資訊備份到 AD DS。</p></td>
</tr>
</tbody>
</table>



## 作業系統磁片磁碟機原則定義


本節說明在下列 GPO 節點上找到的 Microsoft BitLocker 管理與監視的作業系統磁片磁碟機原則定義：**電腦**設定 \\ **策略** \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker Management）** \\ **作業系統磁片磁碟機**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">原則名稱</th>
<th align="left">[概覽] 和 [建議的原則] 設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>作業系統磁片磁碟機加密設定</p></td>
<td align="left"><p>建議的設定： <strong> 已啟用</strong></p>
<p>此原則設定可讓您管理作業系統磁片磁碟機是否必須經過加密。</p>
<p>若要獲得較高的安全性，請考慮在 <strong> </strong> 使用 TPM + PIN 保護器啟用 [系統/電源管理/睡眠設定] 中，停用下列原則設定：</p>
<ul>
<li><p>在休眠（電源開啟）時允許待機狀態（S1-S3）</p></li>
<li><p>在睡眠時允許待機狀態（S1-S3）（使用電池）</p></li>
</ul>
<p>如果您執行的是 Microsoft Windows 8 或更新版本，而您想要在沒有 TPM 的電腦上使用 BitLocker，請選取 [ <strong> 允許沒有相容的 tpm 的 bitlocker] </strong> 核取方塊。 在此模式中，啟動需要密碼。 如果您忘記密碼，您必須使用其中一個 BitLocker 復原選項來存取磁片磁碟機。</p>
<p>在有相容的 TPM 的電腦上，啟動時可以使用兩種類型的驗證方法，為加密資料提供額外的保護。 電腦啟動時，只能使用 TPM 進行驗證，或者也可能需要輸入個人識別碼（PIN）。</p>
<p>如果您啟用此原則設定，使用者必須將作業系統磁片磁碟機放在 BitLocker 保護之下，而且磁片磁碟機將會經過加密。</p>
<p>如果您停用此原則，使用者將無法將操作系統磁碟機放在 BitLocker 保護下。 如果您在作業系統磁片磁碟機加密之後套用此原則，磁片磁碟機將會解密。</p>
<p>如果您未設定此原則，則不需要在 BitLocker 保護下放置作業系統磁片磁碟機。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定 TPM 平臺驗證設定檔</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>此原則設定可讓您設定電腦上的 TPM 安全硬體如何保護 BitLocker 加密金鑰。 如果電腦沒有相容的 TPM，或已使用 TPM 保護開啟 BitLocker，此原則設定就不適用。</p>
<p>如果未設定此原則設定，TPM 會使用預設平臺驗證設定檔或由安裝腳本指定的平臺驗證設定檔。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>選擇可如何復原受 BitLocker 保護的操作系統磁碟機</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>設定此原則以啟用 BitLocker 資料復原代理程式，或將 BitLocker 復原資訊儲存至 Active Directory 網域服務（AD DS）。</p>
<p>如果未設定此原則，就可以使用資料復原代理程式，且不會將復原資訊備份到 AD DS。</p>
<p>MBAM 操作不需要將復原資訊備份到 AD DS。</p></td>
</tr>
</tbody>
</table>



## 移除磁片磁碟機原則定義


本節說明在下列 GPO 節點上找到的 Microsoft BitLocker 管理與監視的抽取式磁碟磁碟機原則定義： [**電腦**設定 \\ **策略**] \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker 管理）**  \\  **抽取式磁碟磁碟機**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">原則名稱</th>
<th align="left">[概覽] 和 [建議的原則] 設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在抽取式磁碟磁碟機上控制 BitLocker 的使用</p></td>
<td align="left"><p>建議的設定： <strong> 已啟用</strong></p>
<p>此原則控制如何在可移動資料磁碟機上使用 BitLocker。</p>
<p>啟用 [ <strong> 允許使用者在可移動資料磁碟機上套用 bitlocker 保護 </strong> ] 選項，以允許使用者在可移除的資料磁碟機上執行 bitlocker 設定向導。</p>
<p>啟用 [ <strong> 允許使用者暫停並解密可移動資料磁碟機上的 bitlocker] </strong> 選項，允許使用者從磁片磁碟機中移除 bitlocker 磁片磁碟機加密，或在執行維護時暫停加密。</p>
<p>如果已啟用此原則，且已 <strong> 選取 [允許使用者在可移動資料磁片磁碟機上套用 BitLocker 保護] </strong> 選項，則 MBAM 用戶端會將抽取式磁碟磁碟機的復原資訊儲存至 MBAM 金鑰復原伺服器，並允許使用者在密碼遺失時復原磁片磁碟機。</p></td>
</tr>
<tr class="even">
<td align="left"><p>拒絕寫入存取不受 BitLocker 保護的抽取式磁碟機</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>啟用此原則，只允許對受 BitLocker 保護的磁碟機進行寫入存取。</p>
<p>啟用此原則時，電腦上所有的可移動資料磁碟機都需要加密，才能允許寫入存取。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>允許從舊版 Windows 存取受 BitLocker 保護的抽取式磁碟磁碟機</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>啟用此原則可讓使用 FAT 檔案系統的固定磁片磁碟機解除鎖定，並在執行 Windows Server 2008、Windows Vista、Windows XP （含 SP3）或 Windows XP （含 SP2）的電腦上進行查看。</p>
<p>如果未設定此原則，就可以在執行 Windows Server 2008、Windows Vista、Windows XP （含 SP3）或 Windows XP （含 SP2）的電腦上，解除鎖定以 FAT 檔案系統格式化的可移動資料磁碟機，而且可以查看其內容。 這些作業系統擁有受 BitLocker 保護的磁片磁碟機的唯讀存取權。</p>
<p>當原則停用時，無法在執行 Windows Server 2008、Windows Vista、windows XP 的電腦上，或使用 SP2，在執行 Windows Server、Windows Vista、Windows XP 或 Windows XP 的電腦上，查看以 FAT 檔案系統格式化的抽取式磁碟磁碟機。</p></td>
</tr>
<tr class="even">
<td align="left"><p>針對可移動資料磁碟機設定密碼的使用方式</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>啟用此原則，在可移動資料磁碟機上設定密碼保護。</p>
<p>如果未設定此原則，預設設定就會支援密碼，這不會包含密碼複雜性需求，且只需要八個字元。</p>
<p>若要提高安全性，您可以啟用此原則，並檢查 [ <strong> 可移動資料磁碟機需要密碼] </strong> ，選取 <strong> [需要密碼複雜性] </strong> ，然後設定偏好的 <strong> 最小密碼長度 </strong> 。</p></td>
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


[MBAM 2.0 部署必要條件](mbam-20-deployment-prerequisites-mbam-2.md)









