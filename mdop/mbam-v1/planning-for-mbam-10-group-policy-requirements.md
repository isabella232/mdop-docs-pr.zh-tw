---
title: MBAM 1.0 群組原則需求規劃
description: MBAM 1.0 群組原則需求規劃
author: dansimp
ms.assetid: 0fc9c509-7850-4a8e-bb82-b949025bcb02
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f5061748107dc1d00baa41188b8cf240ec187317
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800093"
---
# MBAM 1.0 群組原則需求規劃


Microsoft BitLocker 管理與監控（MBAM）用戶端管理需要套用自訂群組策略設定。 本主題說明當您使用 MBAM 管理企業中的 BitLocker 磁碟機加密時，群組原則物件（GPO）可用的原則選項。

**重要**  
MBAM 不會使用 Windows BitLocker 磁片磁碟機加密的預設 GPO 設定。 如果預設設定為啟用，可能會造成衝突行為。 若要啟用 MBAM 來管理 BitLocker，您必須在安裝 MBAM 群群組原則範本之後定義 GPO 原則設定。



在您安裝 MBAM 群組原則範本之後，您可以查看及修改可讓 MBAM 管理企業 BitLocker 加密的可用自訂 MBAM GPO 原則策略設定。 MBAM 群組原則範本必須安裝在能夠執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM） MDOP 技術的電腦上。 接著，若要編輯適用的 GPO，請開啟 GPMC 或 AGPM，然後流覽至下列 GPO 節點： [**電腦設定] 系統** \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker Management）**。

MDOP MBAM （BitLocker 管理） GPO 節點分別包含四個全域原則設定和四個子 GPO 設定節點。 四個 GPO 全域原則設定為：用戶端管理、固定磁片磁碟機、作業系統磁片磁碟機及抽取式磁碟磁碟機。 下列各節提供原則定義及建議的原則設定，以協助您規劃 MBAM GPO 原則設定需求。

**注意**  
如需設定最小建議的 GPO 設定以啟用 MBAM 管理 BitLocker 加密的詳細資訊，請參閱[如何編輯 MBAM 1.0 GPO 設定](how-to-edit-mbam-10-gpo-settings.md)。



## 全域原則定義


本節說明可在下列 GPO 節點上找到的 MBAM 全域原則定義： [電腦設定]**系統** \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker Management）**。

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


本節說明 MBAM 的用戶端管理原則定義，可在下列 GPO 節點找到： [**電腦設定] 系統** \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker Management）**  \\  **用戶端管理**。

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
<li><p><strong>MBAM [恢復與硬體服務] 端點 </strong> 。 這是您必須設定以啟用 MBAM 用戶端 BitLocker 加密管理的第一個策略設定。 針對此設定，請輸入與下列範例類似的端點位置： <strong> HTTP:// </strong><em> &lt; MBAM 管理及監視伺服器名稱 &gt; </em><strong> ： </strong><em> &lt; 埠該 web 服務已系結至 &gt; </em><strong> /MBAMRecoveryAndHardwareService/CoreService.svc </strong> 。</p></li>
<li><p><strong>選取要儲存的 BitLocker 復原資訊 </strong> 。 此原則設定可讓您設定金鑰復原服務來備份 BitLocker 恢復資訊。 它也可讓您設定用於收集合規性和審核報告的狀態報表服務。 原則提供一種系統管理方法，可復原由 BitLocker 加密的資料，以協助防止因缺少重要資訊而造成資料遺失。 狀態報表和金鑰復原活動將會自動傳送到已設定的報表伺服器位置。</p>
<p>如果您未設定或停用此原則設定，就不會儲存金鑰復原資訊，且狀態報表和金鑰復原活動將不會報告給伺服器。 當此設定設定為 [復原 <strong> 密碼及金鑰套件] 時，系統會自動將復原 </strong> 密碼及金鑰套件備份到已設定的金鑰復原伺服器位置。</p></li>
<li><p><strong>輸入用戶端檢查狀態頻率（分鐘） </strong> 。 此原則設定會管理用戶端檢查 BitLocker 保護原則的頻率，以及用戶端電腦上的狀態。 此原則也會管理將用戶端合規性狀態儲存到伺服器的頻率。 用戶端會檢查用戶端電腦上的 BitLocker 保護原則和狀態，同時也會以設定的頻率來備份用戶端復原金鑰。</p>
<p>根據公司所建立的需求來設定此頻率，以查看電腦合規性狀態的頻率，以及備份用戶端復原金鑰的頻率。</p></li>
<li><p><strong>MBAM 狀態報表服務端點 </strong> 。 這是您必須設定以啟用 MBAM 用戶端 BitLocker 加密管理的第二個原則設定。 針對此設定，請使用下列範例輸入端點位置： <strong> HTTP:// </strong><em> &lt; MBAM 管理和監視伺服器名稱 &gt; </em><strong> ： </strong><em> &lt; 埠該 web 服務已系結至 &gt; </em><strong> /MBAMComplianceStatusService/StatusReportingService。 svc </strong> 。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>允許硬體相容性檢查</p></td>
<td align="left"><p>建議的設定： <strong> 已啟用</strong></p>
<p>此原則設定可讓您在 MBAM 用戶端電腦的磁片磁碟機上啟用 BitLocker 保護之前，管理硬體相容性驗證。</p>
<p>如果您的企業的電腦硬體或電腦不支援信任的平臺模組（TPM），您就應該啟用此原則選項。 如果下列其中一個準則為 true，請啟用硬體相容性驗證，以確保 MBAM 僅適用于支援 BitLocker 的電腦模型。 如果貴組織中的所有電腦都支援 BitLocker，您就不需要部署硬體相容性，而且您可以將此原則設定為 [ <strong> 未設定] </strong> 。</p>
<p>如果您啟用此原則設定，在策略在電腦磁碟機上啟用 BitLocker 保護前，每24小時都會驗證一次電腦的硬體相容性清單。</p>
<div class="alert">
<strong>注意</strong><br/><p>在啟用此原則設定之前，請確認您已 <strong> </strong> 在 [ <strong> 設定 MBAM 服務原則] 選項中設定了 [MBAM 復原與硬體服務端點] 設定 </strong> 。</p>
</div>
<div>

</div>
<p>如果您停用或不設定此原則設定，就不會針對硬體相容性清單驗證電腦模型。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>設定使用者豁免原則</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>此原則設定可讓您設定網站位址、電子郵件地址或電話號碼，這將會指示使用者從 BitLocker 加密要求例外。</p>
<p>如果您啟用此原則設定並提供網站位址、電子郵件地址或電話號碼，使用者將會看到一個對話方塊，其中顯示如何針對 BitLocker 保護申請免除的相關指示。 如需如何為使用者啟用 BitLocker 加密免除的詳細資訊，請參閱 <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md)"> 如何管理使用者 Bitlocker 加密免除 </a> 。</p>
<p>如果您停用或不設定此原則設定，就不會向使用者顯示如何申請免除申請的指示。</p>
<div class="alert">
<strong>注意</strong><br/><p>使用者豁免是針對每個使用者管理，而不是針對每個電腦。 如果有多個使用者登入同一部電腦，而一位使用者並未免除，電腦將會經過加密。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## 固定的磁片磁碟機原則定義


本節說明 MBAM 的固定磁片磁碟機原則定義，可在下列 GPO 節點找到： [電腦設定]**系統** \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker Management）** 已  \\  **固定的磁片磁碟機**。

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
<td align="left"><p>建議 <strong> </strong> 的設定： [啟用]，然後選取 [ <strong> 啟用自動解鎖固定資料磁碟機] </strong> 核取方塊（如果需要加密作業系統卷）。</p>
<p>此原則設定可讓您管理是否要加密固定的磁片磁碟機。</p>
<p>當您啟用此原則時，請勿停 <strong> 用設定固定資料磁碟機的密碼使用 </strong> 原則。</p>
<p>如果 <strong> 已選取 [啟用自動解鎖固定資料磁碟機] </strong> 核取方塊，則必須加密作業系統量。</p>
<p>如果您啟用此原則設定，使用者必須將所有固定磁片放在 BitLocker 保護之下，這將會加密磁片磁碟機。</p>
<p>如果您未設定此原則，或如果您停用此原則，使用者就不需要將固定磁片放在 BitLocker 保護下。</p>
<p>如果您停用這項原則，MBAM agent 會解密任何已加密的固定磁片磁碟機。</p>
<p>如果不需要加密作業系統卷，請清除 [ <strong> 啟用自動解鎖固定資料磁碟機] </strong> 核取方塊。</p></td>
</tr>
<tr class="even">
<td align="left"><p>拒絕 [寫入] 許可權給不受 BitLocker 保護的固定磁片磁碟機</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>此原則設定決定電腦上固定磁片磁碟機是否需要 BitLocker 保護，才能讓它們能寫入。 當您開啟 BitLocker 時，就會套用此原則設定。</p>
<p>如果未設定原則，電腦上所有的固定磁片磁碟機都會以讀/寫許可權掛載。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>允許從較舊版本的 Windows 存取受 BitLocker 保護的固定磁片磁碟機</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>在執行 Windows Server 2008、Windows Vista、windows XP （含 SP3）或 Windows XP （含 SP2）的電腦上，啟用此原則來解除鎖定並查看以檔案配置資料表（FAT）檔案系統格式化的固定磁片磁碟機。</p>
<p>這些作業系統對受 BitLocker 保護的磁片磁碟機擁有唯讀許可權。</p>
<p>當原則停用時，使用 FAT 檔案系統格式化的固定磁片磁碟機將無法解除鎖定，而且無法在執行 Windows Server 2008、Windows Vista、Windows XP （含 SP3）的電腦上，或使用 SP2 的 Windows XP 中查看其內容。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定在固定磁片磁碟機使用密碼</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>啟用此原則，在固定磁片磁碟機上設定密碼保護。</p>
<p>如果未設定原則，預設設定就會支援密碼，這不會包含密碼複雜性需求，且只需要八個字元。</p>
<p>若要獲得較高的安全性，請啟用此原則，並選取 [ <strong> 需要密碼才能修正資料磁碟機] </strong> ，選取 <strong> [需要密碼複雜性] </strong> ，然後設定所需的 <strong> 最小密碼長度 </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>選擇如何復原受 BitLocker 保護的固定磁片磁碟機</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>設定此原則以啟用 BitLocker 資料復原代理程式，或將 BitLocker 復原資訊儲存至 Active Directory 網域服務（AD DS）。</p>
<p>如果未設定此原則，就會允許 BitLocker 資料復原代理程式，且不會將復原資訊備份到 AD DS。 MBAM 不需要將復原資訊備份到 AD DS。</p></td>
</tr>
</tbody>
</table>



## 作業系統磁片磁碟機原則定義


本節說明 MBAM 的作業系統磁片磁碟機原則定義，可在下列 GPO 節點找到： [電腦設定]**系統** \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker 管理）**  \\  **作業系統磁片磁碟機**。

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
<p>此原則設定決定作業系統磁片磁碟機是否會經過加密。</p>
<p>設定此原則以執行下列動作：</p>
<ul>
<li><p>針對作業系統磁片磁碟機強制執行 BitLocker 保護。</p></li>
<li><p>設定 PIN 使用量，以使用受信任的平臺模組（TPM） PIN 來保護作業系統。</p></li>
<li><p>設定增強的啟動 Pin，以允許字元（例如大寫、小寫字母和數位）。 MBAM 不支援使用符號和空格來增強 Pin，即使 BitLocker 支援符號和空格也一樣。</p></li>
</ul>
<p>如果您啟用此原則設定，就必須由使用者使用 BitLocker 來保護作業系統磁片磁碟機。</p>
<p>如果您未設定或停用此設定，則不需要使用者使用 BitLocker 來保護作業系統磁片磁碟機。</p>
<p>如果您停用這個原則，MBAM 代理程式會解密作業系統的磁片卷（如果它是加密的）。</p>
<p>啟用此原則設定時，系統會要求使用者使用 BitLocker 保護來保護作業系統，而且磁片磁碟機已加密。 根據您的加密需求，您可以選取作業系統磁片磁碟機的保護方法。</p>
<p>如需較高的安全性需求，請使用 TPM + PIN、允許增強的 Pin，並將最小 PIN 長度設定為八個字元。</p>
<p>使用 TPM + PIN 保護器啟用此原則時，您可以考慮停用 [ <strong> 系統 </strong>  /  <strong> 電源管理 </strong>  /  <strong> 睡眠設定 </strong> ] 底下的下列原則：</p>
<ul>
<li><p>在休眠（電源開啟）時允許待機狀態（S1-S3）</p></li>
<li><p>在睡眠時允許待機狀態（S1-S3）（使用電池）</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>設定 TPM 平臺驗證設定檔</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>此原則設定可讓您設定電腦上的 TPM 安全硬體如何保護 BitLocker 加密金鑰。 如果電腦沒有相容的 TPM，或者 BitLocker 已啟用 TPM 保護，則此原則設定不適用。</p>
<p>如果未設定此原則，TPM 會使用預設平臺驗證設定檔或由安裝腳本指定的平臺驗證設定檔。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>選擇如何復原受 BitLocker 保護的作業系統磁片磁碟機</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>設定此原則以啟用 BitLocker 資料復原代理程式，或將 BitLocker 復原資訊儲存至 Active Directory 網域服務（AD DS）。</p>
<p>如果未設定此原則，就可以使用資料復原代理程式，且不會將復原資訊備份到 AD DS。</p>
<p>MBAM 操作不需要將復原資訊備份到 AD DS。</p></td>
</tr>
</tbody>
</table>



## 移除磁片磁碟機原則定義


本節說明 MBAM 的抽取式磁碟磁碟機原則定義，可在下列 GPO 節點找到： [**電腦設定] 系統** \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker 管理）**  \\  **抽取式磁碟磁碟機**。

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
<td align="left"><p>控制抽取式磁碟磁碟機上的 BitLocker 使用</p></td>
<td align="left"><p>建議的設定： <strong> 已啟用</strong></p>
<p>此原則控制如何在可移動資料磁碟機上使用 BitLocker。</p>
<p>啟用 [ <strong> 允許使用者在可移動資料磁碟機上套用 bitlocker 保護 </strong> ] 選項，以允許使用者在可移除的資料磁碟機上執行 bitlocker 設定向導。</p>
<p>啟用 [ <strong> 允許使用者暫停並解密可移動資料磁碟機上的 bitlocker] </strong> 選項，允許使用者從磁片磁碟機中移除 bitlocker 磁片磁碟機加密，或在執行維護時暫停加密。</p>
<p>如果已啟用此原則，且已 <strong> 選取 [允許使用者在可移動資料磁片磁碟機上套用 BitLocker 保護] </strong> 選項，則 MBAM 用戶端會將抽取式磁碟磁碟機的復原資訊儲存至 MBAM 金鑰復原伺服器，並允許使用者在密碼遺失時復原磁片磁碟機。</p></td>
</tr>
<tr class="even">
<td align="left"><p>拒絕不受 BitLocker 保護的抽取式磁碟磁碟機的 [寫入] 許可權</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>啟用此原則以允許只寫許可權使用受 BitLocker 保護的磁片磁碟機。</p>
<p>啟用此原則時，電腦上所有的可移動資料磁碟機都需要加密，才能允許寫入權限。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>允許從舊版 Windows 存取受 BitLocker 保護的抽取式磁碟磁碟機</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>在執行 Windows Server 2008、Windows Vista、windows XP （含 SP3）或 Windows XP （含 SP2）的電腦上，啟用此原則來解除鎖定並查看格式化為（FAT）檔案系統的固定磁片磁碟機。</p>
<p>這些作業系統對受 BitLocker 保護的磁片磁碟機擁有唯讀許可權。</p>
<p>當原則停用時，無法在執行 Windows Server 2008、Windows Vista、windows XP 的電腦上，或使用 SP2，在執行 Windows Server、Windows Vista、Windows XP 或 Windows XP 的電腦上，查看以 FAT 檔案系統格式化的抽取式磁碟磁碟機。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定可移除資料磁碟機的密碼使用方式</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>啟用此原則，在可移動資料磁碟機上設定密碼保護。</p>
<p>如果未設定此原則，預設設定就會支援密碼，這不會包含密碼複雜性需求，而且只需要八個字元。</p>
<p>若要提高安全性，您可以啟用此原則，然後選取 [ <strong> 移除資料磁碟機需要密碼] </strong> ，選取 <strong> [需要密碼複雜性] </strong> ，然後設定首選的 <strong> 最小密碼長度 </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>選擇可如何復原受 BitLocker 保護的抽取式磁碟磁碟機</p></td>
<td align="left"><p>建議的配置： <strong> 未設定</strong></p>
<p>您可以設定此原則來啟用 BitLocker 資料復原代理程式，或將 BitLocker 復原資訊儲存至 Active Directory 網域服務（AD DS）。</p>
<p>如果原則設定為 [ <strong> 未設定] </strong> ，則允許資料復原代理程式，且不會將復原資訊備份到 AD DS。</p>
<p>MBAM 操作不需要將復原資訊備份到 AD DS。</p></td>
</tr>
</tbody>
</table>



## 相關主題


[MBAM 1.0 的環境準備](preparing-your-environment-for-mbam-10.md)









