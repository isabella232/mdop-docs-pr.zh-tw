---
title: App-V 4.6 SP1 版本資訊
description: App-V 4.6 SP1 版本資訊
author: dansimp
ms.assetid: aeb6784a-864a-4f4e-976b-40c34dcfd8d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7081aaf4a04d52bf288d7a76b4a488e2b200c3d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802377"
---
# App-V 4.6 SP1 版本資訊


若要搜尋這些版本筆記，請按 CTRL + F。

**重要** 安裝 Microsoft Application Virtualization （App-v）管理系統之前，請先閱讀這些版本資訊。 這些版本資訊包含的資訊可協助您成功安裝應用程式虛擬化（App-v） 4.6 SP1。 此檔包含產品檔中不提供的資訊。 如果這些版本資訊與其他 App-v 檔之間有差異，最新變更應視為權威性。

 

## 防範安全性漏洞與病毒


若要協助防範安全性漏洞和病毒，請務必為任何要安裝的新軟體安裝最新的可用安全更新。 如需詳細資訊，請參閱[Microsoft 安全性網站](https://go.microsoft.com/fwlink/?LinkId=3482)（ https://go.microsoft.com/fwlink/?LinkId=3482) 。

## 應用程式虛擬化 4.6 SP1 的已知問題


本節提供關於 Microsoft 應用程式虛擬化（App-v） 4.6 SP1 問題的最新資訊。 這些問題不會出現在產品檔中，某些情況下，可能會矛盾現有的產品檔。 如果可能的話，這些問題將會在稍後的版本中解決。

### 如果 SPRT 的路徑不是以正斜線（/）結尾，就會遺失

當專案範本中 HREF 中的路徑不是以正斜杠（）結尾時 **/** ，產生的 HREF 不包含路徑。 當使用者手動處理**sprt**檔案時，就會發生這種情況。 如果您使用 sequencer，它會永遠在路徑後面加上斜線（ **/** ）。

因應措施請確認 HREF 有結尾的正斜杠（ **/** ）。

### 使用者資料夾名稱不會對應到套件名稱

包含 user 和 global installer.pkg 檔案的資料夾不會再包含套件名稱。 之前，App-v 用戶端會使用 [套件根資料夾8.3 簡稱] 作為資料夾名稱的一部分。 這可讓您輕鬆識別它。 當您使用 App-v 4.6 SP1 排序器時，套件根資料夾8.3 的短名稱現在就是隨機字串。 這會讓您難以在執行 App-v 用戶端的電腦上，找出包含套件**installer.pkg**檔案的資料夾。

因應措施請使用下列其中一種方法，更輕鬆地辨識這些套件資料夾：

1.  當您使用排序器建立套件時，請為主要應用程式資料夾指定遵循8.3 命名慣例的資料夾名稱。 然後，此名稱就會用來做為使用者資料夾名稱的一部分，就像在 App-v 4.6 中的情況。

2.  Sprj 檔案現在包含一個標記，以顯示用作使用者資料夾名稱開頭的字串。 您可以使用**PACKAGEROOTFOLDER**元素的**SHORTNAME**元素來判斷名稱。

### 在超過64個處理器的電腦上執行 App-v 4.6 SP1

當您在已安裝超過64個處理器的電腦上執行 App-v 4.6 SP1 時，App-v 用戶端會失敗。

因應措施無。 不支援此設定。 您必須執行 App-v 4.6 SP1on 少於64個處理器的電腦。

### 未在使用 Microsoft Update 的所有地區設定中提供 Application Virtualization 4.6 SP1 更新

當您使用 Microsoft Update 時，App-v 4.6 SP1 的更新不適用於下列語言地區設定：

-   哈薩克文

-   印度文

-   塞爾維亞文-西瑞爾文

因應措施如果您使用的是 Microsoft Windows Server Update Services （WSUS），請使用英文版的更新，或從 Microsoft 更新目錄下載更新。

### 展開父套件後，您無法使用並列元件順序排列外掛程式

當您使用 [**工具**] 展開父項套件時，會將 [  /  **封裝到本機系統**] 的 [應用程式-V] 排序器視窗中的 [封裝到本機系統]，而且您會傳回安裝錯誤。 例如：

-   **HRESULT 0x80073712**

當 sequencer 將並列元件寫入到註冊表，但不清除下列登錄機碼的值時，就會造成這種情況：

HKEY \ _LOCAL \ _MACHINE \\COMPONENTS\\StoreDirty

解決方法在執行排序器的電腦上展開上層套件後，您必須刪除下列登錄機碼的值：

HKEY \ _LOCAL \ _MACHINE \\COMPONENTS\\StoreDirty

刪除值後，請依序排列外掛程式。

### 版本資訊版權資訊

本檔是以「原樣」提供。 此檔中所表示的資訊和視圖（例如 URL 和其他網際網路網站參考）可能會變更，恕不另行通知。 您會承擔使用它的風險。

本文中描述的一些範例只提供給說明，且是虛構的。 沒有任何實際的關聯或連線是有意或無意的。

本文件不為您提供對任何 Microsoft 產品中的任何智慧財產的法定權利。 您可以複製本文件供內部參照之用。 您可以針對內部、參考目的來修改這份檔。



Microsoft、Active Directory、ActiveSync、ActiveX、Excel、SQL Server、Windows、Windows PowerShell、Windows Server 和 Windows Vista 是 Microsoft 公司群組的商標。

所有其他商標都是其各自擁有者的財產。

 

 





