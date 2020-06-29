---
title: 用戶端事件記錄檔
description: 用戶端事件記錄檔
author: dansimp
ms.assetid: d5c2f270-db6a-45f1-8557-8c6fb28fd568
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7324d07bf018944fcbe24168bba2e9abea9cea41
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810407"
---
# 用戶端事件記錄檔

MBAM 用戶端事件記錄位於 [事件檢視器]-[應用程式和服務記錄]-Microsoft – Windows – MBAM-操作路徑中。
下表包含可在 MBAM 用戶端上發生的事件 Id。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">事件識別碼</th>
<th align="left">通道</th>
<th align="left">事件符號</th>
<th align="left">訊息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>sr-1</p></td>
<td align="left"><p>操作</p></td>
<td align="left"><p>VolumeEnactmentSuccessful</p></td>
<td align="left"><p>已成功套用 MBAM 原則。</p></td>
</tr>
<tr class="even">
<td align="left"><p>pplx-2</p></td>
<td align="left"><p>系統管理員</p></td>
<td align="left"><p>VolumeEnactmentFailed</p></td>
<td align="left"><p>套用 MBAM 原則時發生錯誤。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>3</p></td>
<td align="left"><p>操作</p></td>
<td align="left"><p>TransferStatusDataSuccessful</p></td>
<td align="left"><p>已成功傳送加密狀態資料。</p></td>
</tr>
<tr class="even">
<td align="left"><p>4</p></td>
<td align="left"><p>系統管理員</p></td>
<td align="left"><p>TransferStatusDataFailed</p></td>
<td align="left"><p>傳送加密狀態資料時發生錯誤。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>型</p></td>
<td align="left"><p>系統管理員</p></td>
<td align="left"><p>SystemVolumeNotFound</p></td>
<td align="left"><p>系統磁碟區遺失。 需要 SystemVolume 以加密作業系統磁片磁碟機。</p></td>
</tr>
<tr class="even">
<td align="left"><p>9</p></td>
<td align="left"><p>系統管理員</p></td>
<td align="left"><p>TPMNotFound</p></td>
<td align="left"><p>TPM 硬體遺失。 需要 TPM 來加密作業系統磁片磁碟機與任何 TPM 保護器。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>第</p></td>
<td align="left"><p>系統管理員</p></td>
<td align="left"><p>MachineHWExempted</p></td>
<td align="left"><p>電腦已免除加密。 電腦的硬體狀態：已免除</p></td>
</tr>
<tr class="even">
<td align="left"><p>11</p></td>
<td align="left"><p>系統管理員</p></td>
<td align="left"><p>MachineHWUnknown</p></td>
<td align="left"><p>電腦已免除加密。 電腦的硬體狀態：未知</p></td>
</tr>
<tr class="odd">
<td align="left"><p>之間</p></td>
<td align="left"><p>系統管理員</p></td>
<td align="left"><p>HWCheckFailed</p></td>
<td align="left"><p>硬體免除檢查失敗。</p></td>
</tr>
<tr class="even">
<td align="left"><p>合</p></td>
<td align="left"><p>系統管理員</p></td>
<td align="left"><p>UserIsExempted</p></td>
<td align="left"><p>使用者不受加密。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>4</p></td>
<td align="left"><p>系統管理員</p></td>
<td align="left"><p>UserIsWaiting</p></td>
<td align="left"><p>使用者要求例外。</p></td>
</tr>
<tr class="even">
<td align="left"><p>工資</p></td>
<td align="left"><p>系統管理員</p></td>
<td align="left"><p>UserExemptionCheckFailed</p></td>
<td align="left"><p>使用者豁免檢查失敗。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>位</p></td>
<td align="left"><p>系統管理員</p></td>
<td align="left"><p>UserPostponed</p></td>
<td align="left"><p>使用者已延遲加密處理常式。</p></td>
</tr>
<tr class="even">
<td align="left"><p>11x17</p></td>
<td align="left"><p>系統管理員</p></td>
<td align="left"><p>TPMInitializationFailed</p></td>
<td align="left"><p>TPM 初始化失敗。 使用者拒絕 BIOS 變更。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>滿</p></td>
<td align="left"><p>系統管理員</p></td>
<td align="left"><p>CoreServiceDown</p></td>
<td align="left"><p>無法連線至 MBAM 復原與硬體服務。</p></td>
</tr>
<tr class="even">
<td align="left"><p>合</p></td>
<td align="left"><p>操作</p></td>
<td align="left"><p>CoreServiceUp</p></td>
<td align="left"><p>已成功連線至 MBAM 復原與硬體服務。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>20</p></td>
<td align="left"><p>系統管理員</p></td>
<td align="left"><p>PolicyMismatch</p></td>
<td align="left"><p>MBAM 原則發生衝突或已損毀。</p></td>
</tr>
<tr class="even">
<td align="left"><p>日前</p></td>
<td align="left"><p>系統管理員</p></td>
<td align="left"><p>ConflictingOSVolumePolicies</p></td>
<td align="left"><p>偵測到 OS 大量加密原則發生衝突。 檢查與操作系統磁碟機保護器相關的 BitLocker 與 MBAM 原則。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>22</p></td>
<td align="left"><p>系統管理員</p></td>
<td align="left"><p>ConflictingFDDVolumePolicies</p></td>
<td align="left"><p>偵測到固定資料磁片磁碟機的大量加密原則衝突。 檢查與 FDD 磁碟機保護器相關的 BitLocker 與 MBAM 原則。</p></td>
</tr>
<tr class="even">
<td align="left"><p>27</p></td>
<td align="left"><p>系統管理員</p></td>
<td align="left"><p>EncryptionFailedNoDra</p></td>
<td align="left"><p>加密時發生錯誤。 在適用于 Windows 8.1 電腦的 FIPS 模式中，需要有資料復原代理程式（DRA）保護器。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>28</p></td>
<td align="left"><p>操作</p></td>
<td align="left"><p>TpmOwnerAuthEscrowed</p></td>
<td align="left"><p>TPM OwnerAuth 已 escrowed。</p></td>
</tr>
<tr class="even">
<td align="left"><p>5</p></td>
<td align="left"><p>操作</p></td>
<td align="left"><p>RecoveryKeyEscrowed</p></td>
<td align="left"><p>已 escrowed 該卷的 BitLocker 復原金鑰。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>為期</p></td>
<td align="left"><p>操作</p></td>
<td align="left"><p>RecoveryKeyReset</p></td>
<td align="left"><p>已更新此卷的 BitLocker 復原金鑰。</p></td>
</tr>
<tr class="even">
<td align="left"><p>31</p></td>
<td align="left"><p>操作</p></td>
<td align="left"><p>EnforcePolicyDateSet</p></td>
<td align="left"><p>已 <em> &lt; &gt; </em> 為此卷設定強制原則日期、日期</p></td>
</tr>
<tr class="odd">
<td align="left"><p>32</p></td>
<td align="left"><p>操作</p></td>
<td align="left"><p>EnforcePolicyDateCleared</p></td>
<td align="left"><p>已 <em> &lt; &gt; </em> 清除該卷的 [強制原則日期]、[日期]。</p></td>
</tr>
<tr class="even">
<td align="left"><p>33</p></td>
<td align="left"><p>操作</p></td>
<td align="left"><p>TpmLockOutResetSucceeded</p></td>
<td align="left"><p>已成功重設 TPM 封鎖。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>34</p></td>
<td align="left"><p>系統管理員</p></td>
<td align="left"><p>TpmLockOutResetFailed</p></td>
<td align="left"><p>無法重設 TPM 封鎖。</p></td>
</tr>
<tr class="even">
<td align="left"><p>35</p></td>
<td align="left"><p>操作</p></td>
<td align="left"><p>TpmOwnerAuthRetrievalSucceeded</p></td>
<td align="left"><p>已成功從 MBAM 服務中檢索到 TPM OwnerAuth。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>36</p></td>
<td align="left"><p>系統管理員</p></td>
<td align="left"><p>TpmOwnerAuthRetrievalFailed</p></td>
<td align="left"><p>無法從 MBAM services 中取得 TPM OwnerAuth。</p></td>
</tr>
<tr class="even">
<td align="left"><p>37</p></td>
<td align="left"><p>系統管理員</p></td>
<td align="left"><p>WmiProviderDllSearchPathUpdateFailed</p></td>
<td align="left"><p>無法更新 WMI 提供者的 DLL 搜尋路徑。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>38</p></td>
<td align="left"><p>系統管理員</p></td>
<td align="left"><p>TimedOutWaitingForWmiProvider</p></td>
<td align="left"><p>代理程式停止-等待 MBAM WMI 提供者實例超時。</p></td>
</tr>
<tr class="even">
<td align="left"><p>39</p></td>
<td align="left"><p>操作</p></td>
<td align="left"><p>RemovableDriveMounted</p></td>
<td align="left"><p>已裝入抽取式磁碟磁碟機。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>40</p></td>
<td align="left"><p>操作</p></td>
<td align="left"><p>RemovableDriveDismounted</p></td>
<td align="left"><p>抽取式磁碟磁碟機已卸載。</p></td>
</tr>
<tr class="even">
<td align="left"><p>41</p></td>
<td align="left"><p>操作</p></td>
<td align="left"><p>FailedToEnactEndpointUnreachable</p></td>
<td align="left"><p>無法連線至 MBAM 復原與硬體服務，無法成功將 MBAM 原則套用到該卷。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>42</p></td>
<td align="left"><p>操作</p></td>
<td align="left"><p>FailedToEnactLockedVolume</p></td>
<td align="left"><p>已鎖定的磁片狀態會使 MBAM 原則無法順利套用到該卷。</p></td>
</tr>
<tr class="even">
<td align="left"><p>43</p></td>
<td align="left"><p>操作</p></td>
<td align="left"><p>TransferStatusDataFailedEndpointUnreachable</p></td>
<td align="left"><p>無法連線至 MBAM 合規性與狀態服務，因此無法傳輸加密狀態資料。</p></td>
</tr>
</tbody>
</table>

 


## 相關主題
[MBAM 2.5 技術參考資料](technical-reference-for-mbam-25.md)

[伺服器事件記錄檔](server-event-logs.md)

 


## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





