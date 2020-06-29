---
title: DaRT 8.0 SP1 版本資訊
description: DaRT 8.0 SP1 版本資訊
author: dansimp
ms.assetid: fa7512d8-fb00-4c27-8f65-c15f3a8ff1cc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a4c49d12fed07f507d2db4d56969d8e7b0559c64
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810755"
---
# DaRT 8.0 SP1 版本資訊


**若要搜尋這些版本筆記，請按 CTRL + F。**

安裝 Microsoft Diagnostics 和復原工具集（DaRT） 8.0 Service Pack 1 （SP1）之前，請仔細閱讀這些版本資訊。

這些版本資訊包含成功安裝診斷和修復工具組 8.0 SP1 所需的資訊。 版本資訊中也包含產品檔中不提供的資訊。 如果這些版本資訊與其他 DaRT 檔之間有差異，最新變更應視為權威性。 這些版本資訊取代本產品隨附的內容。

## 關於產品檔


如需有關 DaRT 檔的詳細資訊，請參閱 Microsoft TechNet 上的[DaRT 首頁](https://go.microsoft.com/fwlink/?LinkID=252096)。

## DaRT 8.0 SP1 的已知問題


### 當您執行 Locksmith 或登錄編輯程式時，系統還原失敗

如果您執行 Locksmith、[登錄編輯程式]，而且可能還有其他工具，系統還原就會失敗。

因應措施 **：** 關閉並重新啟動 DaRT，然後啟動 [系統還原]。

### 啟動並關閉 Locksmith 或電腦管理之後，SFC 掃描無法執行

如果您開始，然後關閉 Locksmith 或電腦管理工具，系統檔案檢查程式將無法執行。

因應措施 **：** 關閉並重新啟動 DaRT，然後啟動 SFC。

### <a href="" id="-------------dart-installer-does-not-fail-when-adk-has-not-been-installed"></a> 尚未安裝 ADK 時，DaRT 安裝程式無法失敗

如果您使用命令列執行 MSI 來安裝 DaRT 8.0 SP1，但尚未安裝 ADK，DaRT 安裝應該會失敗。 目前，DaRT 8.0 SP1 安裝程式會安裝除 DaRT 復原影像以外的所有元件。

因應措施 **：** 所有.

### 在 Locksmith、RegEdit、崩潰分析程式及電腦管理啟動後，無法啟動 Defender

如果您已啟動 Locksmith、RegEdit、故障分析程式及電腦管理，就不會啟動 Defender。

因應措施 **：** 關閉並重新啟動 DaRT，然後啟動 Defender。

### Defender 可能會啟動緩慢

Defender 有時候需要幾分鐘的時間才能啟動。 進度列會指出目前的載入狀態。

因應措施 **：** 所有.

## 版本資訊版權資訊


Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、MicrosoftIntune 和 WindowsPowerShell 是 Microsoft 公司群組的商標。 所有其他商標都是其各自擁有者的財產。



## 相關主題


[關於 DaRT 8.0 SP1](about-dart-80-sp1.md)

 

 





