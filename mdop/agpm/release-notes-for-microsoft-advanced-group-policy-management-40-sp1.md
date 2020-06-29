---
title: Microsoft 進階群組原則管理 4.0 SP1 版本資訊
description: Microsoft 進階群組原則管理 4.0 SP1 版本資訊
author: dansimp
ms.assetid: 91835bf8-e53c-4202-986e-8d37050d1267
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ff9ce0405df766aef9b30e67d07ceb579c4fa89f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801854"
---
# Microsoft 進階群組原則管理 4.0 SP1 版本資訊


若要搜尋這些版本筆記，請按 Ctrl + F。

安裝 Microsoft 高級群組原則管理（AGPM） 4.0 SP1 之前，請先閱讀這些版本資訊。 這些版本資訊包含成功安裝 AGPM 4.0 SP1 所需的資訊，且包含產品檔中無法提供的資訊。 如果這些版本資訊與其他 AGPM 檔之間有差異，最新變更應該視為權威性。 這些版本資訊取代本產品隨附的內容。

## AGPM 4.0 SP1 已知問題


本節包含適用于 AGPM 4.0 SP1 的版本資訊。

### <a href="" id="control-panel-s--uninstall--tool-may-not-work-when-you-try-to-change-agpm-server-settings"></a>當您嘗試變更 AGPM 服務器設定時，[控制台] 的 [卸載] 工具可能無法運作

[控制台] 中的工具可讓您卸載或變更程式在您嘗試變更 AGPM 服務器設定時可能無法運作。

因應措施：在您嘗試使用 [控制台] 變更 AGPM 服務器設定之前，請製作 [AGPM 封存] 資料夾的複本。 然後，您可以使用 Setup.exe 重新安裝 AGPM 服務器，然後選擇您想要的設定參數。

### 報告不會顯示已新增至群組原則物件的連結

[AGPM 設定] 和 [差異] 報告不會顯示已新增至群組原則物件（GPO）的連結。

因應措施：若要在報表中查看連結，請在 [群組原則管理主控台（GPMC）] 中選取 GPO，然後按一下右窗格中的 [**設定**] 索引標籤。

### <a href="" id="reports-do-not-display-all--choice-options-properties--settings"></a>報告不會顯示所有「選擇選項屬性」設定

[AGPM 設定] 和 [差異] 報告不會顯示在 [群群組原則物件編輯器] 的 [選擇選項屬性] 視窗中選取的所有設定。

因應措施：使用 GPMC 在報表中查看選取的 [選擇選項] 屬性設定。

### 報表不會顯示某些瀏覽器中的 [顯示] 和 [隱藏] 索引標籤

當您在 Google Chrome 或 Mozilla Firefox 中查看報表時，[顯示] 和 [隱藏] 索引標籤會顯示在 [AGPM 設定] 和 [差異] 報告的右側。

解決方法：使用 Internet Explorer 來查看報表。

### AGPM 設定和差異報告可能會顯示 GPMC 報告的不同內容

在群組原則管理主控台（GPMC）中，AGPM 設定和差異報告可能不會顯示與報告相同的內容。

解決方法：使用 GPMC 來查看 AGPM 報告。

### 如果網網域控制站沒有線上，則 AGPM 服務無法啟動

當 AGPM 服務安裝在 Windows 8 上的網網域控制站上時，如果網網域控制站沒有線上，該服務就不會啟動。

因應措施：在網網域控制站處於線上狀態之後，手動啟動 AGPM 服務。

### 將 AGPM 服務器升級至 AGPM 4.0 SP1 時，當您從 AGPM 4.0 發行加上此熱修復程式後，就會遭到封鎖

如果您嘗試將 AGPM 服務器升級至 AGPM 4.0。 SP1 安裝 AGPM 4.0 之後，接著安裝 AGPM 修復程式（請參閱知識庫文章[2643502](https://go.microsoft.com/fwlink/?LinkId=254474)），升級失敗且無法完成。

解決方法：卸載 AGPM 4.0 伺服器，然後安裝 AGPM 4.0 SP1。

### 報告不會顯示組織單位連結

如果您將不受管理的 GPO 連結至組織單位，然後使用 AGPM 控制該 GPO，則 AGPM 設定和差異報告不會顯示組織單位連結。

因應措施：從 [**變更設定**] 節點的 [**受控**] 索引標籤上，以滑鼠右鍵按一下該 GPO，然後按一下 [**設定**]，再按一下 [ **gpo 連結**] 來查看組織連結。 或者，您可以使用 GPMC 從 [**範圍**] 索引標籤中查看 GPO 的連結。

## 相關主題


[進階群組原則管理](index.md)

[AGPM 4.0 SP1 的新功能](whats-new-in-agpm-40-sp1.md)

 

 





