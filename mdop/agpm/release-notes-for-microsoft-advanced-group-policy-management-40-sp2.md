---
title: Microsoft 進階群組原則管理 4.0 SP2 版本資訊
description: Microsoft 進階群組原則管理 4.0 SP2 版本資訊
author: dansimp
ms.assetid: 0593cd11-3308-4942-bf19-8a7bb9447f01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 736eb8d41cbb72b274a2941c60b0357bbc948c9d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802597"
---
# Microsoft 進階群組原則管理 4.0 SP2 版本資訊


若要搜尋這些版本筆記，請按 Ctrl + F。

安裝 Microsoft 高級群組原則管理（AGPM）4.0 服務 Pack2 （SP2）之前，請先閱讀這些版本資訊。 這些版本資訊包含成功安裝 AGPM 4.0 SP2 所需的資訊，且包含產品檔中不提供的資訊。 如果這些版本資訊與其他 AGPM 檔之間有差異，請考慮最新的變更權威性。 這些版本資訊取代本產品隨附的內容。

## AGPM 4.0 SP2 已知問題


本節說明適用于 AGPM 4.0 SP2 的已知問題。

### <a href="" id="control-panel-s--uninstall--tool-may-not-work-when-you-try-to-change-agpm-server-settings"></a>當您嘗試變更 AGPM 服務器設定時，[控制台] 的 [卸載] 工具可能無法運作

當您嘗試變更 AGPM 服務器設定時，在 [控制台] 中用來卸載或變更程式的工具可能無法運作。

因應措施 **：** 在您嘗試使用 [控制台] 變更 AGPM 服務器設定之前，請製作 [AGPM 封存] 資料夾的複本。 然後，您可以使用 Setup.exe 重新安裝 AGPM 服務器，然後選擇您想要的設定參數。

### 報告不會顯示已新增至群組原則物件的連結

[AGPM 設定] 和 [差異] 報告不會顯示已新增至群組原則物件（GPO）的連結。

因應措施 **：** 若要查看報表中的連結，請在 [群組原則管理主控台（GPMC）] 中選取 GPO，然後按一下右窗格中的 [**設定**] 索引標籤。

### 報表不會顯示所有選項屬性設定

[AGPM 設定] 和 [差異] 報告不會顯示在 [群群組原則物件編輯器] 的 [**選擇選項屬性**] 視窗中選取的所有設定。

因應措施 **：** 使用 GPMC 在報表中查看選取的 [**選擇選項] 屬性**設定。

### 報表可能不會顯示某些瀏覽器中的 [顯示] 和 [隱藏] 索引標籤

當您在 Google Chrome 或 Mozilla Firefox 中查看報表時，可能不會顯示 [AGPM 設定] 和 [差異] 報告右側的 [**顯示**及**隱藏**] 索引標籤。

因應措施 **：** 使用 Internet Explorer 瀏覽器來查看報表。

### AGPM 設定和差異報告可能會顯示 GPMC 報告的不同內容

AGPM 設定和差異報告可能不會顯示與 GPMC 中報表相同的內容。

因應措施 **：** 使用 GPMC 來查看 AGPM 報告。

### 如果網網域控制站離線，AGPM 服務就無法啟動

當 AGPM 服務安裝在 Windows®8作業系統或更新版本作業系統的網網域控制站上時，如果網網域控制站處於離線狀態，則服務無法啟動。

因應措施 **：** 在網網域控制站連線之後，手動啟動 AGPM 服務。

### 從 AGPM 4.0 發行加上 hotfix1 升級 AGPM 服務器到 AGPM 4.0 SP2 時會遭到封鎖

如果您嘗試將 AGPM 服務器升級至 AGPM 4.0。 安裝 AGPM 4.0 Server 之後，然後安裝名為 AGPM 4.0 的 AGPM 熱修復程式，在 HTML 報表中報告的差異不正確（請參閱知識庫文章[2643502](https://go.microsoft.com/fwlink/?LinkId=254474)），升級失敗且無法完成。

因應措施 **：** 卸載 AGPM 4.0 伺服器，然後安裝 AGPM 4.0 SP2。

### 報告不會顯示組織單位連結

如果您將不受管理的 GPO 連結至組織單位，然後使用 AGPM 控制該 GPO，則 AGPM 設定和差異報告不會顯示組織單位連結。

因應措施 **：** 在 [**變更設定**] 節點的 [**受控**] 索引標籤上，以滑鼠右鍵按一下該 GPO，按一下 [**設定**]，然後按一下 [ **gpo 連結**] 來查看組織連結。 或者，您可以使用 GPMC 從 [**範圍**] 索引標籤中查看 GPO 的連結。

### 如果您按一下 [變更]、[修復] 或 [移除 AGPM 用戶端] 對話方塊中的 [返回] 按鈕，則 AGPM 會顯示錯誤。

如果您流覽至 [控制台] 中的 [**程式和功能**]，然後選取 [ **Microsoft 高級群組原則管理–用戶端**]，當您按一下 [**修改**]，然後按一下 [**變更]、[修復] 或 [移除 AGPM 用戶端**] 對話方塊中的 [**上一頁**] 按鈕，就會顯示錯誤

因應措施 **：** 按一下 [**取消**] 以清除錯誤，然後再次啟動程式。 按一下 [**修改**] 後，請不要按一下 [**返回**] 按鈕。

### 當核准者部署 GPO 並輸入批註時，無法在 [歷程記錄] 視窗中顯示批註

如果擁有 Editor 角色的使用者提交部署 GPO 的要求，且擁有核准者角色的使用者接著部署該 GPO 並輸入批註，則批註將無法出現在 [歷程**記錄**] 視窗中。

因應措施 **：** 所有.

## 相關主題


[進階群組原則管理](index.md)

[AGPM 4.0 SP2 的新功能](whats-new-in-agpm-40-sp2.md)

 

 





