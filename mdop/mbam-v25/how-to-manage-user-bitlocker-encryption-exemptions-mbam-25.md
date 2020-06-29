---
title: 如何管理使用者 BitLocker 加密豁免
description: 如何管理使用者 BitLocker 加密豁免
author: dansimp
ms.assetid: f582ab82-5bb5-4cd3-ad7c-483240533cf9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c4224a0fb6d905c2362659efe7cf05e16756f7c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811967"
---
# 如何管理使用者 BitLocker 加密豁免


Microsoft BitLocker 管理和監控（MBAM）可讓您從 BitLocker 磁片磁碟機加密需求中免除使用者。

若要將使用者從 BitLocker 保護中免除，您必須：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">工作</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>建立基礎結構以支援免除的使用者。</p></td>
<td align="left"><p>此基礎結構的範例包括提供使用者的電話號碼、網頁或郵寄地址，讓他們可以用來要求豁免。</p></td>
</tr>
<tr class="even">
<td align="left"><p>針對專門針對免除的使用者設定的群組原則物件，將免除的使用者新增到安全性群組。</p></td>
<td align="left"><p>當這個安全性群組的成員登入電腦時，使用者的群組原則設定會從 BitLocker 保護 exempts 使用者。 使用者的 [群組原則] 設定會覆寫電腦原則，電腦將保持不受 BitLocker 加密的免除。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果電腦已受 BitLocker 保護且已免除使用者，MBAM 不會制定加密原則。 不過，如果不是由加密原則免除的另一個使用者登入電腦，就會進行加密。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



下列步驟說明當使用者從 MBAM 用戶端或您組織所使用的任何程式來要求 BitLocker 磁碟機加密免除程式的例外情況時，會發生什麼情況。 您必須設定 MBAM 組原則設定，以允許使用者從 BitLocker 磁片磁碟機加密要求免除。

1.  當使用者登入需要加密的電腦時，會收到其電腦即將加密的通知。 您可以選取 [**延遲**]，選取 [**要求免除**]，然後選取 [**開始加密**] 來接受 BitLocker 加密。

    **注意**  
    選取 [**要求免除**]：推遲 BitLocker 防護，直到使用者豁免原則中設定的最大時間為止。



2.  如果使用者選取 [**要求免除**]，他們會收到通知，告知他們與組織的 BitLocker 管理群組。 視設定**使用者例外原則**的設定方式而定，使用者提供下列一或多個連絡人方法：

    -   電話號碼

    -   網頁 URL

    -   郵寄地址

3.  在收到免除要求之後，MBAM 系統管理員會決定是否要將使用者新增到 BitLocker 免除 Active Directory 網域服務（AD DS）群組。

4.  在最終使用者提交免除要求之後，MBAM 用戶端會將使用者報告為「暫時免除」。 用戶端接著會等到指定的天數（IT 系統管理員設定的天數），才能再次檢查電腦的相容性。 如果 MBAM 管理員拒絕免除要求，則會停用 [免除要求] 選項，這會防止使用者再次要求例外。

Microsoft BitLocker 管理和監控（MBAM）可讓您從 BitLocker 磁片磁碟機加密需求中免除使用者。

若要將使用者從 BitLocker 保護中免除，您必須：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">工作</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>建立基礎結構以支援免除的使用者。</p></td>
<td align="left"><p>此基礎結構的範例包括提供使用者的電話號碼、網頁或郵寄地址，讓他們可以用來要求豁免。</p></td>
</tr>
<tr class="even">
<td align="left"><p>針對專門針對免除的使用者設定的群組原則物件，將免除的使用者新增到安全性群組。</p></td>
<td align="left"><p>當這個安全性群組的成員登入電腦時，使用者的群組原則設定會從 BitLocker 保護 exempts 使用者。 使用者的 [群組原則] 設定會覆寫電腦原則，電腦將保持不受 BitLocker 加密的免除。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果電腦已受 BitLocker 保護，使用者豁免原則就不會有任何作用。 此外，如果其他使用者登入的電腦未從加密原則中免除，就會進行加密。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



下列步驟說明當使用者從 MBAM 用戶端或您組織所使用的任何程式來要求 BitLocker 磁碟機加密免除程式的例外情況時，會發生什麼情況。 您必須設定 MBAM 組原則設定，以允許使用者從 BitLocker 磁片磁碟機加密要求免除。

1.  當使用者登入需要加密的電腦時，會收到其電腦即將加密的通知。 您可以選取 [**延遲**]，選取 [**要求免除**]，然後選取 [**開始加密**] 來接受 BitLocker 加密。

    **注意**  
    選取 [**要求免除**]：推遲 BitLocker 防護，直到使用者豁免原則中設定的最大時間為止。



2.  如果使用者選取 [**要求免除**]，他們會收到通知，告知他們與組織的 BitLocker 管理群組。 視設定**使用者例外原則**的設定方式而定，使用者提供下列一或多個連絡人方法：

    -   電話號碼

    -   網頁 URL

    -   郵寄地址

3.  在收到免除要求之後，MBAM 系統管理員會決定是否要將使用者新增到 BitLocker 免除 Active Directory 網域服務（AD DS）群組。

4.  在最終使用者提交免除要求之後，MBAM 用戶端會將使用者報告為「暫時免除」。 用戶端接著會等到指定的天數（IT 系統管理員設定的天數），才能再次檢查電腦的相容性。 如果 MBAM 管理員拒絕免除要求，則會停用 [免除要求] 選項，這會防止使用者再次要求例外。

**從 BitLocker 磁碟機加密免除使用者**

1.  建立將用來從 BitLocker 加密需求管理使用者免除的 AD DS 安全性群組。

2.  使用 Microsoft BitLocker 管理和監視群群組原則範本來建立群組原則物件。

3.  將 [群組原則] 物件與您在上一個步驟中建立的 AD DS 群組建立關聯。 免除使用者的原則設定是位於： UserConfiguration 系統**UserConfiguration** &gt; **管理範本** &gt; **Windows 元件** &gt; **MDOP MBAM （BitLocker Management）**。

4.  針對您針對 BitLocker 免除的使用者所建立的安全性群組，請新增要求豁免之使用者的名稱。

    當使用者登入由 BitLocker 控制的電腦時，MBAM 用戶端會檢查使用者豁免原則設定。 如果電腦已加密，就不會暫停 BitLocker 保護。 如果電腦未加密，MBAM 不會提示使用者進行加密。

    **重要**  
    如果您使用的是 BitLocker 使用者免除，共用電腦案例需要特殊考慮。 如果非豁免使用者登入與豁免使用者共用的電腦，電腦可能會經過加密。




## 相關主題


[管理 MBAM 2.5 功能](administering-mbam-25-features.md)

[MBAM 2.5 群組原則需求規劃](planning-for-mbam-25-group-policy-requirements.md)




## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




