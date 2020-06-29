---
title: 部署適用於 UE-V 1.0 的 UE-V 設定位置範本
description: 部署適用於 UE-V 1.0 的 UE-V 設定位置範本
author: dansimp
ms.assetid: 7e0cc553-14f7-40fa-828a-281c8d2d1934
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b276fb9d6c0b3749f9818483869dfe98bbc147c7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812165"
---
# 部署適用於 UE-V 1.0 的 UE-V 設定位置範本


Microsoft 使用者體驗虛擬化（UE-V）使用設定位置範本（XML 檔案），定義使用者體驗虛擬化所捕獲並套用的設定。 UE-V 包含一組標準範本，以及一個工具（即 UE-V 發生器），可讓您建立自訂設定位置範本。 在您建立設定位置範本之後，您應該對其進行測試，以確保應用程式設定能在測試環境中正確漫遊。 然後，您就可以將設定位置範本安全地部署到企業中的電腦上。

您可以使用企業軟體發佈（ESD）、群組原則喜好設定或設定 UE-V 設定範本目錄來部署設定位置範本。 使用 ESD 或群組原則部署的範本，必須透過 UE-V WMI 或 PowerShell 註冊。 儲存在設定範本目錄位置的範本會自動由 UE-V agent 進行註冊。

## 使用設定範本目錄路徑部署設定位置範本


UE-V 設定位置範本目錄路徑可以使用下列方法來定義：群組原則、代理安裝命令列參數、WMI 或 PowerShell。 在定義範本目錄路徑之後，UE-V agent 就會從這個位置檢索新的或更新的範本。 UE-V agent 每天都會檢查這個位置，然後根據在這個資料夾中找到的範本，更新其同步處理行為。 在此資料夾中新增或更新的範本，自上次檢查之後，由 UE-V agent 註冊。 UE-V agent 也會登出已從該資料夾移除的範本。 範本是由任務排程器每日登錄並取消註冊一次。

**若要使用設定範本目錄路徑來部署 UE-V 設定位置範本**

1.  流覽至定義為 [設定] 範本目錄的網路共用資料夾。

2.  在設定範本目錄中新增、移除或更新設定位置範本，以反映 UE-V 電腦的所需 UE-V agent 範本配置。

3.  電腦上的範本會根據設定範本目錄的變更，每日更新一次。

4.  開啟提升許可權的命令提示字元，然後流覽到 **% program files%\\Microsoft 使用者體驗虛擬化 \\ agent \\ &lt; x86 &gt; 或 x64 **，然後執行**ApplySettingsTemplateCatalog.exe** ，在執行 ue-v agent 的電腦上手動更新範本。

## 相關主題


[Microsoft User Experience Virtualization (UE-V) 1.0](index.md)

[部署 UE-V 1.0](deploying-ue-v-10.md)

[規劃要與 UE-V 1.0 同步處理的應用程式](planning-which-applications-to-synchronize-with-ue-v-10.md)

 

 





