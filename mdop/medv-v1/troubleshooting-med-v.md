---
title: 疑難排解 MED-V
description: 疑難排解 MED-V
author: dansimp
ms.assetid: f43dae36-6485-4e06-9c66-0a646e27079d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 38d13be699a92368ff258026acd8e0d5f0e28cd6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811409"
---
# 疑難排解 MED-V


本節提供的資訊可協助針對 Microsoft 企業版桌面虛擬化（MED-V）的一般問題進行疑難排解。

## 變更主機解析度，然後最大化 MED-V 工作區，使桌面看起來像是黑色


在完整的桌面圖案中工作時，如果您變更主機解析度，然後最大化 MED-V 工作區視窗，則桌面會出現黑色，而 MED-V 工作區可能不會回應。

### 解決方案

停止並啟動 MED-V 工作區。

## 在已停用網路介面卡的情況下啟動 MED-V 工作區，然後再啟用配接器並不會還原網路連線


如果您在 bridge 模式中設定 MED-V 工作區，然後在已停用網路介面卡的情況下啟動 MED-V 工作區，則如果稍後啟用該配接器，則無法還原透過該配接器的網路連線。

### 解決方案

停止並啟動 MED-V 工作區。

## 每個電腦只有一個 Windows 使用者可以使用影像


MED-V 工作區圖像只能由下載或匯入影像的 Windows 使用者使用。 只有在擁有下載的影像所在資料夾許可權的系統管理員，才可以使用此使用者。

### 解決方案

在影像存放區上手動變更存取控制清單（ACL）。

## 在已啟用使用者許可權的情況下，使用 Configuration Manager 安裝 MED-V-V 時，卸載失敗


如果 MED-V 是使用 Microsoft System Center Configuration Manager 安裝，且套件的 [執行] 模式設定為 [使用者權利]，則卸載失敗，並顯示錯誤訊息，指出只有系統管理使用者可以卸載 MED-V。

### 解決方案

為 MED-V 建立 Configuration Manager 套件時，請將 [執行模式] 設定為 [系統管理許可權]。

## 當您使用公司部署系統安裝 MED-V-V 時，安裝會設定為在安裝之後執行用戶端，而您無法執行用戶端


如果 MED-V 是使用公司部署系統來安裝，且安裝套件是設定為在安裝之後執行 MED-V 用戶端，則在用戶端以 system 帳戶執行之後，您就無法看到用戶端正在執行（在通知區域中除外），而且您無法與其互動。

### 解決方案

當您使用公司部署系統安裝 MED-V 時，請使用*START \ _MEDV = 0* .msi 參數。

## MED-V 測試影像無法啟動


如果 MED-V 測試影像無法啟動，它將不會復原，而且所有未來的啟動都會失敗，並出現「GINA 無法載入」錯誤訊息。

### 解決方案

刪除現有的測試影像，然後重新建立。

## 在嘗試使用錯誤的認證加入網域之後，該影像在加入網域時永遠不會成功


如果加入網域構造區塊（這是虛擬電腦的第一次設定腳本的一部分）發生配置錯誤，則在嘗試加入網域時，會導致 MED-V 工作區失敗。 修復配置錯誤之後，MED-V 工作區中包含的影像將無法加入網域。

### 解決方案

如果已部署影像，請重新發佈影像。 如果影像是測試影像，請重新建立影像。

## MED-V 不支援多個監視器


MED-V 不支援在多台監視器上顯示已發佈的應用程式。 已發佈的應用程式和其他用戶端視窗可能會顯示在錯誤的螢幕上，有時在畫面斷開連接之後，MED-V 會嘗試將畫面移至顯示器，讓連接的顯示器顯示為空白。

### 解決方案

中斷其他螢幕，然後重新開機用戶端。

## 如果主機在 MED-V 工作區啟動期間當機當機，則 MED-V 工作區可能無法啟動


如果主機在 MED-V 工作區啟動程式中當機，且出現錯誤訊息，指出「根項目遺失」，則 MED-V 工作區可能會將資料新增至空白的虛擬機器設定（VMC）檔案，這會導致啟動程式失敗。

### 解決方案

使用基底影像的 VMC 檔案取代空白的 VMC 檔案。

## 鍵盤在已發佈的應用程式視窗中沒有回應


在 MED-V 工作區中，如果您在已發佈的應用程式成為焦點時按下 Windows 標誌鍵，就不會再在已發佈的應用程式視窗中回應鍵盤。

### 解決方案

在已發佈的應用程式成為焦點時，按下 Windows 標誌鍵。

## 網域 MED-V-V 工作區無法更新網域認證


在網域環境中使用持久的 MED-V 工作區時，如果您變更網域密碼，MED-V 用戶端就不會更新 MED-V 工作區網域認證。 當已發佈的應用程式嘗試存取網路資源時，您會收到錯誤訊息，通知您認證已過期。

### 解決方案

重新開機 MED-V 工作區作業系統。

## 最大化已發佈的應用程式視窗封面主機工作列


如果您將已發佈的應用程式視窗最大化至全螢幕，可能會覆蓋主機工作列。

### 解決方案

執行下列其中一項：

最小化已發佈的應用程式視窗，以取得通知區域的存取權，並重新啟動 MED-V 工作區。

將已發佈的應用程式視窗最小化，然後將視窗還原至它的最大化狀態。

## 在 MED-V Server Configuration Manager 中新增使用者或群組無法運作


當您在 [**選取使用者或群組**] 對話方塊中新增使用者或群組時，選取的使用者或群組不會新增至 med-v Server 設定管理員的存取控制清單中。

### 解決方案

使用 [**輸入使用者或組名**] 對話方塊新增使用者或群組。 如需詳細資訊，請參閱[如何安裝和設定 Med-v 伺服器元件](how-to-install-and-configure-the-med-v-server-component.md#bkmk-configuringpermissions)。

## 在已安裝 Windows 7 版 Windows Virtual PC 的電腦上，MED-V 無法運作


MED-V 需要 Windows Virtual PC2007。 Windows 虛擬電腦的 Windows7 和 Virtual PC2007 SP1 無法安裝在同一部電腦上。

### 解決方案

在安裝 Virtual PC2007 SP1 和 MED-V 之前，請先卸載 Windows7 的虛擬電腦。

## <a href="" id="med-v-does-not-support-virtual-pc-and-windows-xp-mode-images-"></a>MED-V 不支援虛擬電腦和 WindowsXP 模式影像


MED-V 1.0 SP1 不支援由 Windows Virtual PC 為 Windows7 建立的影像。 如果使用 Windows7 影像的虛擬 PC，則在啟動期間用戶端將會失敗。

### 解決方案

使用 Virtual PC2007 SP1 建立 MED-V 影像。

## Windows 防火牆會封鎖 Virtual PC2007 SP1 網路活動


根據預設，Windows 防火牆會封鎖 Virtual PC2007 SP1 網路活動，當 Virtual PC2007 SP1 在用戶端電腦上啟動時，會出現防火牆訊息，攔截其啟動順序及所有網路存取。

### 解決方案

在最終使用者使用 MED-V 之前，先使用 [群組原則] 來更新防火牆例外狀況。

## 當您升級用戶端時，會出現錯誤訊息


當您將用戶端從 MED-V 1.0 升級到 MED-V 1.0 SP1 時，可能會出現一則訊息，通知您沒有定義 MED-V 工作區。

### 解決方案

關閉用戶端並重新啟動。

## 相關主題


[MED-V 1.0 版本資訊](med-v-10-release-notesmedv-10.md)

[MED-V 1.0 SP1 和 SP2 版本資訊](med-v-10-sp1-and-sp2-release-notesmedv-10-sp1.md)

 

 





