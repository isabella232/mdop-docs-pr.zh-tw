---
title: 如何編輯 MBAM 2.0 GPO 設定
description: 如何編輯 MBAM 2.0 GPO 設定
author: dansimp
ms.assetid: f5ffa93d-b4d2-4317-8a1c-7d2be0264fe3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aaf7c7aab4baba66513edbfa2489fbe53c97dda8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810346"
---
# 如何編輯 MBAM 2.0 GPO 設定


若要成功部署 Microsoft BitLocker 管理和監控（MBAM），您必須先決定您要在實施 Microsoft BitLocker 管理和監控時使用的群組原則。 如需其他可用原則的詳細資訊，請參閱[規劃 MBAM 2.0 群組原則需求](planning-for-mbam-20-group-policy-requirements-mbam-2.md)。 在您決定要使用的原則之後，您必須修改一或多個包括 MBAM 原則設定的群組原則物件（GPO）。

您可以使用下列步驟來設定基本的建議 GPO 設定，以讓 MBAM 管理貴組織用戶端電腦的 BitLocker 加密。

**編輯 MBAM 用戶端 GPO 設定**

1.  在已安裝 MBAM 群組原則範本的電腦上，請確定已啟用 MBAM 服務。

2.  在已安裝 MBAM 群組原則範本的電腦上使用群組原則管理主控台（GPMC）或高級群組原則管理（AGPM） MDOP 產品，選取 [電腦設定]，選擇 [**原則**]，按一下 [**系統****管理範本**]，選取 [ **Windows 元件**]，然後按一下 **[MDOP MBAM （BitLocker Management）**]。

3.  編輯在用戶端電腦上啟用 MBAM 用戶端服務所需的群組原則物件設定。 針對後面的資料表中的每個原則，選取 [**原則群組**]，按一下**原則**，然後設定**設定**：

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">原則群組</th>
    <th align="left">原則</th>
    <th align="left">設定</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>用戶端管理</p></td>
    <td align="left"><p>設定 MBAM 服務</p></td>
    <td align="left"><p>啟用。 設定 <strong> MBAM 復原與硬體服務端點 </strong> ，然後 <strong> 選取要儲存的 BitLocker 復原資訊 </strong> 。 設定 <strong> MBAM 合規性服務端點 </strong> ，並在（分鐘）中輸入狀態報表頻率。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>作業系統磁片磁碟機</p></td>
    <td align="left"><p>作業系統磁片磁碟機加密設定</p></td>
    <td align="left"><p>啟用。 <strong>針對作業系統磁片磁碟機設定 [選取保護器] </strong> 。 需要將作業系統磁片磁碟機資料儲存至 MBAMKey 恢復伺服器。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>抽取式磁碟磁碟機</p></td>
    <td align="left"><p>在抽取式磁碟磁碟機上控制 BitLocker 的使用</p></td>
    <td align="left"><p>啟用。 如果 MBAM 會將抽取式磁碟磁碟機資料儲存至 MBAM 金鑰復原伺服器，則為必要。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>固定磁片磁碟機</p></td>
    <td align="left"><p>在固定磁片磁碟機上控制 BitLocker 的使用</p></td>
    <td align="left"><p>啟用。 如果 MBAM 會將固定磁片磁碟機資料儲存至 MBAM 金鑰復原伺服器，則為必要。</p>
    <p>您 <strong> 可以選擇如何復原受 BitLocker 保護的磁碟機 </strong> ，以及 <strong> 允許資料修復代理程式 </strong> 。</p></td>
    </tr>
    </tbody>
    </table>



~~~
**Important**  
Depending on the policies that your organization decides to deploy, you may have to configure additional policies. See [Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md) for Group Policy configuration details for all of the available MBAM GPO policy options.
~~~



## 相關主題


[部署 MBAM 2.0 群組原則物件](deploying-mbam-20-group-policy-objects-mbam-2.md)









