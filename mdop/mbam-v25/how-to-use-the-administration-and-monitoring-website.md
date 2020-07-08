---
title: 如何使用 Administration and Monitoring Website
description: 如何使用 Administration and Monitoring Website
author: dansimp
ms.assetid: bb96a4e8-d4f4-4e6f-b7db-82d96998bfa6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9b9597e29a5a7a6236cb351d8d6d1f682edce3cf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800245"
---
# 如何使用 Administration and Monitoring Website


管理和監控網站（也稱為說明服務台）是 BitLocker 磁碟機加密的管理介面。 您可以使用網站來查看報告、復原使用者的磁片磁碟機，以及管理使用者的 TPMs，如下列各節所述。

**記事** 如果您是在獨立拓撲中使用 MBAM，您可以從 [管理] 和 [監視] 網站上查看所有報表。 如果您使用的是 Configuration Manager 整合拓朴，您可以在 Configuration Manager 中查看所有報表，除了復原審核報告之外，您還會從管理和監控網站繼續進行查看。 如需有關報告的詳細資訊，請參閱[使用 MBAM 2.5 監視及報告 BitLocker 合規性](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)。

 

## 使用管理和監控網站所需的角色


若要存取 [管理] 和 [監視] 網站的特定區域，您必須具備下列其中一項角色，即您在 Active Directory 中建立的群組。 您可以為這些群組使用任何名稱。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">帳戶</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM 高級支援人員的使用者</p></td>
<td align="left"><p>提供管理和監控網站所有區域的存取權。 擁有此角色的使用者在協助使用者復原其磁碟機時，只會輸入復原金鑰，而不是使用者的網域和使用者名稱。 如果使用者是 MBAM [支援人員] 群組和 MBAM [高級服務台使用者] 群組的成員，MBAM [高級支援人員] 群組許可權會覆寫 MBAM 的 [支援人員] 群組許可權。</p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 支援人員的使用者</p></td>
<td align="left"><p>提供存取管理和監控網站的 [管理 TPM] 和 [磁碟機恢復] 區域。 擁有此角色的人員在使用任一區域時，都必須填入所有欄位，包括使用者的網域和帳戶名稱。</p>
<p>如果使用者是 MBAM [支援人員] 群組和 MBAM [高級服務台使用者] 群組的成員，MBAM [高級支援人員] 群組許可權會覆寫 MBAM 的 [支援人員] 群組許可權。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 報表使用者</p></td>
<td align="left"><p>提供 <strong> </strong> 管理和監控網站 [報告] 區域中報告的存取權。</p></td>
</tr>
</tbody>
</table>

 

## 您可以在 [管理及監視] 網站上執行的工作


下表摘要列出您可以在 [管理] 和 [監視] 網站上執行的工作，並提供每個任務詳細資訊的連結。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">工作</th>
<th align="left">您可在其中存取任務的網站區域</th>
<th align="left">描述</th>
<th align="left">其他資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>檢視報告</p></td>
<td align="left"><p>報告</p></td>
<td align="left"><p>可讓您執行報告，以監控 BitLocker 使用量、合規性及金鑰復原活動。 報告提供有關企業合規性、個別電腦，以及特定電腦要求復原金鑰或 TPM OwnerAuth 套件的相關資料。</p></td>
<td align="left"><p><a href="viewing-mbam-25-reports-for-the-stand-alone-topology.md" data-raw-source="[Viewing MBAM 2.5 Reports for the Stand-alone Topology](viewing-mbam-25-reports-for-the-stand-alone-topology.md)">檢視獨立拓撲的 MBAM 2.5 報告</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>判斷遺失或被盜電腦的 BitLocker 加密狀態</p></td>
<td align="left"><p>報告</p></td>
<td align="left"><p>判斷電腦遺失或被盜時，是否已加密卷。</p></td>
<td align="left"><p><a href="how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-25.md" data-raw-source="[How to Determine BitLocker Encryption State of Lost Computers](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-25.md)">如何判斷遺失的電腦之 BitLocker 加密狀態</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>復原遺失的磁片磁碟機</p></td>
<td align="left"><p>磁片磁碟機恢復</p></td>
<td align="left"><p>復原下列磁片磁碟機：</p>
<ul>
<li><p>在復原模式中</p></li>
<li><p>已移動</p></li>
<li><p>已損毀</p></li>
</ul></td>
<td align="left"><ul>
<li><p><a href="how-to-recover-a-drive-in-recovery-mode-mbam-25.md" data-raw-source="[How to Recover a Drive in Recovery Mode](how-to-recover-a-drive-in-recovery-mode-mbam-25.md)">如何修復處於修復模式的磁碟機</a></p></li>
<li><p><a href="how-to-recover-a-moved-drive-mbam-25.md" data-raw-source="[How to Recover a Moved Drive](how-to-recover-a-moved-drive-mbam-25.md)">如何修復已移動的磁碟機</a></p></li>
<li><p><a href="how-to-recover-a-corrupted-drive-mbam-25.md" data-raw-source="[How to Recover a Corrupted Drive](how-to-recover-a-corrupted-drive-mbam-25.md)">如何修復損毀的磁碟機</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>重設 TPM 封鎖</p></td>
<td align="left"><p>管理 TPM</p></td>
<td align="left"><p>提供存取 MBAM 用戶端所收集的 TPM 資料的許可權。 在 TPM 封鎖中，請使用 [管理] 和 [監視] 網站來取得解鎖 TPM 所需的密碼檔。</p></td>
<td align="left"><p><a href="how-to-reset-a-tpm-lockout-mbam-25.md" data-raw-source="[How to Reset a TPM Lockout](how-to-reset-a-tpm-lockout-mbam-25.md)">如何重設 TPM 鎖定</a></p></td>
</tr>
</tbody>
</table>

 


## 相關主題


[使用 MBAM 2.5 執行 BitLocker 管理](performing-bitlocker-management-with-mbam-25.md)

 

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





