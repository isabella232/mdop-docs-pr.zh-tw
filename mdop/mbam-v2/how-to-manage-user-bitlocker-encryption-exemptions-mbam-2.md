---
title: 如何管理使用者 BitLocker 加密豁免
description: 如何管理使用者 BitLocker 加密豁免
author: dansimp
ms.assetid: 1bfd9d66-6a9a-4d0e-b54a-e5a6627f5ada
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4d5530701fd208d42dc1f6774fac11ee9ca2036b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810935"
---
# 如何管理使用者 BitLocker 加密豁免


如果使用者不需要或想要將其磁碟機加密，Microsoft BitLocker 管理和監控（MBAM）可以用來管理 BitLocker 保護。

若要將使用者從 BitLocker 保護中免除，組織必須建立支援免除的使用者的基礎結構，例如給予使用者使用的連絡人電話號碼、網頁或郵寄地址來要求豁免。 此外，豁免使用者必須新增到專為免除使用者建立之群組原則物件的安全性群組。 當這個安全性群組的成員登入電腦時，使用者的 [群組原則] 設定會顯示使用者已從 BitLocker 保護中免除。 使用者的 [群組原則] 設定會覆寫電腦原則，電腦將保持不受 BitLocker 加密的免除。

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
<td align="left"><p>在電腦上強制執行 BitLocker 保護</p></td>
<td align="left"><p>在電腦上未強制執行 BitLocker 保護</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>使用者豁免</strong></p></td>
<td align="left"><p>在電腦上未強制執行 BitLocker 保護</p></td>
<td align="left"><p>在電腦上未強制執行 BitLocker 保護</p></td>
</tr>
</tbody>
</table>

 

**從 BitLocker 加密免除使用者**

1.  建立將用來從 BitLocker 加密需求管理使用者免除的 ActiveDirectoryDomainServices 安全性群組。

2.  使用 Microsoft BitLocker 管理和監視群群組原則範本建立群組原則物件設定，並將它與您在上一個步驟中建立的 Active Directory 群組建立關聯。 您可以在**UserConfiguration\\Administrative Templates\\Windows COMPONENTS\\MDOP MBAM （BitLocker Management）** 下找到免除使用者的原則設定。

3.  在為 BitLocker 免除的使用者建立安全性群組之後，請將要求豁免的使用者名稱新增到此群組中。 當使用者登入 BitLocker 所控制的電腦時，MBAM 用戶端將會檢查使用者豁免原則設定，並根據使用者是否為 BitLocker 豁免安全性群組的一部分來暫停保護。

    **重要** 在使用使用者例外狀況時，共用電腦案例需要特殊考慮。 如果非豁免使用者登入與豁免使用者共用的電腦，電腦可能會經過加密。

     

**讓使用者從 BitLocker 加密要求免除**

1.  如果您已使用 MBAM 原則範本設定使用者豁免原則，使用者可以透過 MBAM 用戶端要求 BitLocker 保護的免除。

2.  當使用者登入需要加密的電腦時，他們會收到一則通知，告知其電腦即將加密。 他們可以選取 [**要求免除**]，**然後選取 [****開始**] 以接受 BitLocker 加密。

    **記事** 選取 [**要求免除**]：推遲 BitLocker 防護，直到使用者豁免原則中設定的最大時間為止。

     

3.  如果使用者選取 [**要求免除**]，他們會收到通知，告知他們與您組織的 BitLocker 管理群組。 視設定使用者例外原則的設定方式而定，使用者提供下列一或多個連絡人方法：

    -   電話號碼

    -   網頁 URL

    -   郵寄地址

    在收到免除要求之後，MBAM 系統管理員可以決定是否要將使用者新增到 BitLocker 豁免 Active Directory 群組。

    **記事** 使用者提交免除要求之後，MBAM 代理就會將使用者報告為「暫時免除」，然後等待可設定的天數，才能再次檢查電腦的合規性。 如果 MBAM 管理員拒絕免除要求，則會停用 [免除要求] 選項，這會讓使用者無法再次要求例外。

     

## 相關主題


[管理 MBAM 2.0 功能](administering-mbam-20-features-mbam-2.md)

 

 





