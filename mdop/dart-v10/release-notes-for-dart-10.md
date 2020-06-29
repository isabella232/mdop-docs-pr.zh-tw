---
title: DaRT 10 版本資訊
description: DaRT 10 版本資訊
author: dansimp
ms.assetid: eb996980-f9c4-42cb-bde9-6b3d4b82b58c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 12ae5865538155f3c9ecf8b5f23b0d9e23232833
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809663"
---
# DaRT 10 版本資訊


**若要搜尋這些版本筆記，請按 CTRL + F。**

在安裝 Microsoft Diagnostics 與修復工具集（DaRT）10之前，請先閱讀這些版本資訊。

這些版本資訊包含成功安裝診斷和修復工具組10所需的資訊。 版本資訊中也包含產品檔中不提供的資訊。 如果這些版本資訊與其他 DaRT 檔之間有差異，最新變更應視為權威性。 這些版本資訊取代本產品隨附的內容。

## DaRT 10 的已知問題


### Disk 指揮無法在 Windows 10 的物理分區中修復損壞的主要開機記錄

在 Windows 10 中，[還原主要開機記錄（MBR）] 或 [GUID 分區表（GPT）] 選項在 [磁片] 選項中無法修復物理分區中損壞的主開機記錄，因此無法啟動用戶端電腦。

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

如果您使用命令列來執行 DaRT 10 （.msi），而且尚未安裝 Windows 評估與部署套件（WindowsADK），DaRT 安裝應該會失敗。 目前，DaRT 10 安裝程式會安裝 DaRT 復原影像以外的所有元件。

因應措施 **：** 所有.

## 相關主題


[關於 DaRT 10](about-dart-10.md)

 

 





