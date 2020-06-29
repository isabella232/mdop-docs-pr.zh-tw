---
title: MBAM 2.5 用戶端的必要條件
description: MBAM 2.5 用戶端的必要條件
author: dansimp
ms.assetid: fc230679-9c84-4b99-a77c-bae7e7bf8145
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/23/2017
ms.openlocfilehash: ac5e211e5ea038f47db3d5e68155eb5af38aa231
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812074"
---
# MBAM 2.5 用戶端的必要條件


在最終使用者的電腦上安裝 MBAM 用戶端軟體之前，請確定您的環境和用戶端電腦符合下列先決條件。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必備</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>企業網域必須包含至少一個 Windows Server 2008 （或更新版本）網網域控制站。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>用戶端電腦必須登入企業內部網路。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>僅適用于 Windows 7 用戶端電腦：每個用戶端都必須具有信任的平臺模組（TPM）功能（TPM 1.2 或更新版本）。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>針對 Windows 8.1、Windows 10 RTM 或 Windows 10 版本1511用戶端電腦：如果您希望 MBAM 能夠儲存及管理 TPM 復原金鑰，必須先關閉 TPM 自動供給，然後再將 MBAM 設定為 TPM 擁有者，才能部署 MBAM。</p>
<p>在 MBAM 2.5 SP1 中，您不再需要關閉 TPM 自動供給，但您必須確認已將 TPM 群組原則物件設定為無法將 TPM OwnerAuth 到 Active Directory。</p></td>
<td align="left"><p><a href="mbam-25-security-considerations.md#bkmk-tpm" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md#bkmk-tpm)">MBAM 2.5 安全性考量</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>如果您使用的是 Windows 10 版本1607或更新版本，則只有 Windows 可以取得 TPM 擁有權。 在 addiiton 中，Windows 將不會在預配 TPM 時保留 TPM 擁有者密碼。</p>
<p>在 MBAM 2.5 SP1 中，您必須開啟自動供給。</p>
</p></td>
<td align="left"><p><a href="https://technet.microsoft.com/itpro/windows/keep-secure/change-the-tpm-owner-password" data-raw-source="[TPM owner password](https://technet.microsoft.com/itpro/windows/keep-secure/change-the-tpm-owner-password)"> </a> 如需詳細資訊，請參閱 TPM 擁有者密碼。
</p></td>
</tr>
<tr class="even">
<td align="left"><p>您必須在 BIOS 中開啟 TPM 晶片，然後從作業系統 resettable。</p></td>
<td align="left"><p>如需詳細資訊，請參閱 BIOS 檔。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>電腦的硬碟必須至少有兩個磁碟分割，且必須使用 NTFS 檔案系統來格式化。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>電腦的硬碟必須有與 TPM 相容且在電腦啟動期間支援 USB 裝置的 BIOS。</p></td>
<td align="left"><div class="alert">
<strong>注意</strong><br/><p>確定鍵盤、影片或滑鼠已直接連接，且未透過鍵盤、影片或滑鼠（KVM）開關進行管理。 KVM 切換器可能會干擾電腦偵測硬體實際狀態的能力。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>如果您使用 proxy，必須在系統內容中顯示它。 MBAM 會在系統內容（而非使用者內容）底下執行。</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



**重要**  
如果在沒有 MBAM 的情況下使用 BitLocker，可以安裝 MBAM 並利用現有的 TPM 資訊。




## 相關主題


[MBAM 2.5 支援的組態](mbam-25-supported-configurations.md)

[規劃部署 MBAM 2.5](planning-to-deploy-mbam-25.md)


## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。






