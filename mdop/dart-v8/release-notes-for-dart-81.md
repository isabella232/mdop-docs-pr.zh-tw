---
title: DaRT 8.1 版本資訊
description: DaRT 8.1 版本資訊
author: dansimp
ms.assetid: 44303107-60f4-485c-848a-7e0529f142d4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d0ba817ddd5bbdefcf7fed833f4c47e7b9d9ce0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810749"
---
# DaRT 8.1 版本資訊


**若要搜尋這些版本筆記，請按 CTRL + F。**

在安裝 Microsoft Diagnostics 與修復工具組（DaRT）8.1 之前，請先閱讀這些版本資訊。

這些版本資訊包含成功安裝診斷和修復工具組8.1 所需的資訊。 版本資訊中也包含產品檔中不提供的資訊。 如果這些版本資訊與其他 DaRT 檔之間有差異，最新變更應視為權威性。 這些版本資訊取代本產品隨附的內容。

## DaRT 8.1 的已知問題


### Disk 指揮無法在 Windows 8.1 的物理分區中修復損壞的主要開機記錄

在 Windows 8.1 中，[還原主要開機記錄（MBR）] 或 [GUID 分區表（GPT）] 選項在 [磁片] 中無法修復物理分區中損毀的主要開機記錄，因此無法啟動用戶端電腦。

因應措施 **：** 啟動**啟動修復**，按一下 [**疑難排解**]，按一下 [**高級選項**]，然後按一下 [**開始修復**]。

### 針對同一磁片磁碟機進行的磁片擦除多個實例會導致除最後一個實例以外的所有實例報告失敗

如果您啟動磁片擦除的多個實例，然後嘗試使用兩個不同的磁片擦放實例來拭除同一磁片磁碟機，除了最後一個以外的所有實例，都無法擦除磁片磁碟機。

因應措施 **：** 所有.

### 磁片擦除可能無法清除具有快閃記憶體之固態磁片磁碟機上的所有資料

如果您在具有快閃記憶體的固態磁片磁碟機（SSD）上使用 [磁片擦除] 來清除資料，則所有資料都可能無法清除。 之所以會發生這個問題，是因為 SSD 固件在執行磁片擦除時控制寫入的物理位置。

因應措施 **：** 所有.

### 當您執行 [Locksmith] 嚮導或 [登錄編輯程式] 時，系統還原失敗

如果您執行的是 [Locksmith] 嚮導、[登錄編輯程式]，而且可能還有其他工具，系統還原就會失敗。

因應措施 **：** 關閉並重新啟動 DaRT，然後啟動 [系統還原]。

### 啟動及關閉 Locksmith 嚮導或電腦管理之後，系統檔案檢查（SFC）掃描無法執行

如果您在 [電腦管理] 中開始然後關閉 [Locksmith 嚮導] 或 [工具]，系統檔案檢查程式將無法執行。

因應措施 **：** 關閉並重新啟動 DaRT，然後啟動 [系統檔案檢查程式]。

### <a href="" id="-------------dart-installer-does-not-fail-when-the-windows-assessment-and-deployment-kit-is-not-installed"></a> 在未安裝 Windows 評估與部署套件時，DaRT 安裝程式無法失敗

如果您在安裝 DaRT 8.1 時使用命令列來執行 Windows 安裝程式（.msi），而且尚未安裝 Windows 評估與部署套件（WindowsADK），DaRT 安裝應該會失敗。 目前，DaRT 8.1 安裝程式會安裝 DaRT 恢復影像以外的所有元件。

因應措施 **：** 所有.

### Windows Defender 無法在 Locksmith 嚮導、[登錄編輯程式]、[崩潰] 分析程式及電腦管理啟動後啟動

如果您已經啟動 Locksmith 嚮導、[登錄編輯程式]、[崩潰分析程式] 和 [電腦管理]，Windows Defender 就不會啟動。

因應措施 **：** 關閉並重新啟動 DaRT，然後啟動 Windows Defender。

### Windows Defender 啟動速度可能很慢

Windows Defender 有時候會需要幾分鐘的時間才能啟動。 進度列會指出目前的載入狀態。

因應措施 **：** 所有.

## 相關主題


[關於 DaRT 8.1](about-dart-81.md)

 

 





