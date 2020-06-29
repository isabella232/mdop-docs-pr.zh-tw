---
title: 如何安裝 Application Virtualization Sequencer
description: 如何安裝 Application Virtualization Sequencer
author: dansimp
ms.assetid: 89cdf60d-18b0-4204-aa9f-b402610f8f0e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 56a6fe03f2149504b6c34c70b2b82ce2ba0b55ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801365"
---
# 如何安裝 Application Virtualization Sequencer


Microsoft Application Virtualization 排序器會監視並記錄應用程式的安裝與設定程式，讓應用程式可以作為虛擬應用程式執行。 您應該在只安裝作業系統的電腦上安裝 Sequencer。 或者，您也可以在執行虛擬環境的電腦（例如 Microsoft Virtual PC）上安裝 Sequencer。 這個方法很實用，因為您可以更輕鬆地維護乾淨的順序環境，讓您可以使用最少的額外設定重複使用。

您必須在所用的電腦上擁有系統管理許可權，才能對應用程式進行排序，且電腦必須不執行任何版本的 Application Virtualization （App-v）用戶端。 使用排序器建立虛擬應用程式是佔用大量資源，所以請務必在符合或超過建議需求的電腦上安裝 Sequencer。 在安全模式中執行 App-v 排序器不受支援。 如需系統需求的詳細資訊，請參閱[應用程式虛擬化系統需求](application-virtualization-system-requirements.md)。

**重要** 當您將應用程式排序之後，您必須在您用來序列化應用程式的電腦上重新安裝作業系統和 Sequencer，才能正確地順序新的應用程式。

 

**若要安裝 Microsoft Application Virtualization 排序器**

1.  將 Microsoft Application Virtualization Sequencer 安裝檔案複製到您要安裝它的電腦上。

2.  若要啟動 Microsoft Application Virtualization Sequencer 安裝精靈，請選取 [ **setup.exe**]。 如果在安裝前沒有偵測到**Microsoft Visual c + + SP1 可再發行套件（x86）** ， **setup.exe**會安裝它。

3.  在 [**歡迎**] 頁面上，按一下 **[下一步]**。

4.  若要接受授權合約條款，請在 [**授權協定**] 頁面上，選取 [**我接受授權合約中的條款**]。 按 **\[下一步\]**。

5.  若要接受預設安裝資料夾，請在 [**目的地資料夾**] 頁面上，按一下 **[下一步]**。 若要指定不同的目的地資料夾，請按一下 [**變更**]，然後指定安裝所用的安裝資料夾。 按 **\[下一步\]**。

6.  在 [**準備好安裝程式**] 頁面上，按一下 [**安裝**]。

7.  在 [ **InstallShield 嚮導已完成]** 頁面上，若要關閉 [安裝精靈] 並開啟排序器，請按一下 **[完成**]。 若要關閉 [安裝精靈] 而不開啟排序器，請取消選取 [**啟動程式**]，然後按一下 **[完成]**。

## 相關主題


[如何升級 Application Virtualization Sequencer](how-to-upgrade-the-application-virtualization-sequencer.md)

[Application Virtualization 部署需求](application-virtualization-deployment-requirements.md)

 

 





