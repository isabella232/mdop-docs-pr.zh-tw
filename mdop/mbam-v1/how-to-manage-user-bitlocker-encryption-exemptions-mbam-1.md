---
title: 如何管理使用者 BitLocker 加密豁免
description: 如何管理使用者 BitLocker 加密豁免
author: dansimp
ms.assetid: 48d69721-504f-4524-8a04-b9ce213ac9b4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8c3d70558a65c3288174413d6c36cc9c77bc9eaa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800225"
---
# 如何管理使用者 BitLocker 加密豁免


Microsoft BitLocker 管理和監控（MBAM）可透過 exempting 不需要或不想要磁片磁碟機加密的使用者來管理 BitLocker 保護。

若要將使用者從 BitLocker 保護中免除，組織必須先建立一個支援此類免除的基礎結構。 支援基礎結構可能包含連絡人電話號碼、網頁或郵寄地址來要求豁免。 此外，任何免除使用者也必須新增到專為免除的使用者所建立之群群組原則的安全性群組中。 當此安全性群組的成員登入電腦時，使用者群組原則會顯示使用者已從 BitLocker 保護中免除。 使用者原則會覆寫電腦原則，電腦將保持不受 BitLocker 加密的免除。

**記事** 如果電腦已受 BitLocker 保護，使用者豁免原則就不會有任何作用。

 

下表顯示如何根據免除的設定來套用 BitLocker 保護。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">使用者狀態</th>
<th align="left">未免除的電腦</th>
<th align="left">電腦豁免</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>使用者不受豁免</strong></p></td>
<td align="left"><p>在電腦上強制執行 BitLocker 保護。</p></td>
<td align="left"><p>在電腦上未強制執行 BitLocker 保護。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>使用者豁免</strong></p></td>
<td align="left"><p>在電腦上未強制執行 BitLocker 保護。</p></td>
<td align="left"><p>在電腦上未強制執行 BitLocker 保護。</p></td>
</tr>
</tbody>
</table>

 

**從 BitLocker 加密免除使用者**

1.  建立將用來從 BitLocker 加密管理使用者免除的 ActiveDirectoryDomainServices 安全性群組。

2.  使用 MBAM 群組原則範本來建立群組原則物件設定。 將群組原則物件與您在上一個步驟中建立的 Active Directory 群組建立關聯。 如需讓使用者從 BitLocker 加密中要求豁免所需原則設定的詳細資訊，請參閱[規劃 MBAM 1.0 群組原則需求](planning-for-mbam-10-group-policy-requirements.md)中的 [設定使用者豁免原則] 區段。

3.  在為 BitLocker 免除的使用者建立安全性群組之後，請將要求豁免的使用者名稱新增到此群組中。 當使用者登入由 BitLocker 控制的電腦時，MBAM 用戶端會檢查使用者豁免原則設定，並根據使用者是否為 BitLocker 豁免安全性群組的一部分來暫停保護。

    **記事** 共用電腦案例需要關於使用者例外的特殊考慮。 如果非豁免使用者登入與豁免使用者共用的電腦，電腦可能會經過加密。

     

**讓使用者從 BitLocker 加密要求豁免**

1.  在您以 usingwith MBAM 原則範本設定使用者豁免原則之後，使用者就可以透過 MBAM 用戶端要求 BitLocker 保護的例外情況。

2.  當使用者登入 MBAM 硬體相容性清單中標示為**相容**的電腦時，系統會向使用者顯示電腦即將加密的通知。 使用者可以選取 [**要求免除**]，**然後選取 [****開始**] 以接受 BitLocker 加密。

    **記事** 選取 [**要求免除**] 會延遲 BitLocker 防護，直到使用者豁免原則中設定的最大時間為止。

     

3.  當使用者選取 [**要求豁免**] 時，系統會通知使用者與組織的 BitLocker 管理群組。 視設定使用者例外原則的設定方式而定，使用者提供下列一或多個連絡人方法：

    -   電話號碼

    -   網頁 URL

    -   郵寄地址

    在提交要求之後，MBAM 管理員可以決定是否適當地將使用者新增至 BitLocker 免除 Active Directory 群組。

    **記事** 當使用者免除原則的延遲時間限制已過期之後，使用者就不會看到要求免除加密原則的選項。 此時，使用者必須直接與 MBAM 管理員聯繫，才能從 BitLocker 保護接收例外。

     

## 相關主題


[管理 MBAM 1.0 功能](administering-mbam-10-features.md)

 

 





