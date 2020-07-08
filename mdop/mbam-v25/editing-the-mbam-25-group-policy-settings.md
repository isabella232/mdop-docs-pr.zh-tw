---
title: 編輯 MBAM 2.5 群組原則設定
description: 編輯 MBAM 2.5 群組原則設定
author: dansimp
ms.assetid: a50b6b0c-6818-4419-8447-d0520a533dba
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0f6d180cba6dc721ff7de1607d57f90184303d88
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800133"
---
# 編輯 MBAM 2.5 群組原則設定


若要成功部署 Microsoft BitLocker 管理和監控（MBAM），您必須：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">工作</th>
<th align="left">詳細資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>複製 MBAM 2.5 群組原則範本。</p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)">複製 MBAM 2.5 群組原則範本</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>決定您想要在 MBAM 實施中使用哪一個群組原則物件（Gpo）。 根據貴組織的需求，您可能必須設定其他群組原則設定。</p></td>
<td align="left"><p><a href="planning-for-mbam-25-group-policy-requirements.md" data-raw-source="[Planning for MBAM 2.5 Group Policy Requirements](planning-for-mbam-25-group-policy-requirements.md)">規劃 MBAM 2.5 群組原則需求 </a> -包含 gpo 的描述</p></td>
</tr>
<tr class="odd">
<td align="left"><p>為您的組織設定群組原則設定。</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

**重要** 請勿變更**BitLocker 磁片磁碟機加密**節點中的群組原則設定，否則 MBAM 將無法正常運作。 當您在**MDOP MBAM （BitLocker 管理）** 節點中設定群組原則設定時，MBAM 會自動為您設定**BitLocker 磁片磁碟機加密**設定。

 

**編輯 MBAM 用戶端群組原則設定**

1.  在已安裝 MBAM 群組原則範本的電腦上，請確定已啟用 MBAM 服務。

2.  在已安裝 MBAM 群組原則範本的電腦上使用 [群組原則管理主控台（GPMC）] 或 [Microsoft 高級群組原則管理 MDOP] 產品，選取 [**電腦**設定 &gt; **原則**] &gt; **管理範本** &gt; **Windows 元件** &gt; **MDOP MBAM （BitLocker 管理）**。

3.  編輯在用戶端電腦上啟用 MBAM 用戶端服務所需的群組原則設定。 針對下表中的每個原則，選取 [**原則群組**]，按一下您想要的**原則**，然後設定設定。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">原則群組</th>
    <th align="left">原則</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>用戶端管理</p></td>
    <td align="left"><p>設定 MBAM 服務</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>作業系統磁片磁碟機</p></td>
    <td align="left"><p>作業系統磁片磁碟機加密設定</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>抽取式磁碟磁碟機</p></td>
    <td align="left"><p>在抽取式磁碟磁碟機上控制 BitLocker 的使用</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>固定磁片磁碟機</p></td>
    <td align="left"><p>在固定磁片磁碟機上控制 BitLocker 的使用</p></td>
    </tr>
    </tbody>
    </table>

     

## 相關主題


[MBAM 2.5 群組原則需求規劃](planning-for-mbam-25-group-policy-requirements.md)

[複製 MBAM 2.5 群組原則範本](copying-the-mbam-25-group-policy-templates.md)

 
## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
 





