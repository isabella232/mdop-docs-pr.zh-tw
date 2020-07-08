---
title: MED-V 2.0 端對端操作案例
description: MED-V 2.0 端對端操作案例
author: dansimp
ms.assetid: 1d87f5f3-9fc5-4731-8bd1-c155714f34ee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 90a7c2135ad27040ed87dac980b67321eb771574
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811594"
---
# MED-V 2.0 端對端操作案例


此範例案例 Microsoft 企業桌面虛擬化（MED-V）2.0 可協助您使用多個案例端對端部署和管理 MED-V。 您可以將這個範例案例想像成案例研究，協助將個別案例和程式放在內容中。

本節提供在企業中建立、部署及管理 MED-V 工作區作為端對端方案的基本資訊與指示。

## MED-V 運算逐步方案


您在 MED-V 作業案例中遵循的逐步程式會包括下列專案：

-   [建立適用于 med-v 的 Windows 虛擬電腦影像](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc)，看看如何建立和設定 Med-v 的 WINDOWS 虛擬電腦影像。 您必須先準備一個虛擬硬碟（VHD），才能將 MED-V 工作區傳送給使用者，然後才能為 MED-V 建立 MED-V 工作區安裝程式套件。

-   [建立適用于 med-v 的 Windows 虛擬電腦影像](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installingwindowsxpontovpc)，看看如何在您的 WINDOWS 虛擬電腦影像上安裝 WINDOWS XP SP3 作業系統。 在建立 MED-V 工作區前，MED-V 需要在 Windows 虛擬電腦映射上安裝 Windows XP SP3。

-   [建立適用于 med-v 的 Windows 虛擬電腦映射](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installingnet)：如何將 .net FRAMEWORK 3.5 SP1 及更新 KB959209 手動安裝到您準備搭配 med-v 使用的 WINDOWS 虛擬電腦影像中。 MED-V 需要 .NET Framework 3.5 SP1，而更新[KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) （ https://go.microsoft.com/fwlink/?LinkId=204950) 解決數個已知的應用程式相容性問題。

-   [建立適用于 med-v 的 Windows 虛擬電腦影像](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-applypatchestovpc)，瞭解如何使用最新的軟體更新及其他需要或重要的修補程式（對於執行 med-v）來更新您的 Windows XP 映射。

-   [建立適用于 med-v 的 Windows 虛擬電腦影像](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installintegration)查看如何在您的 Windows XP 映射中安裝整合元件套件。 它們提供可改善虛擬環境與物理電腦之間互動的功能。

-   [在 Windows 虛擬電腦影像上安裝應用程式](installing-applications-on-a-windows-virtual-pc-image.md)，可瞭解如何在您的 Windows XP 映射上安裝特定類型的軟體，這些軟體在您執行 med-v （例如電子軟體發佈系統和防毒軟體）時很有説明。

-   [針對 med-v 設定 Windows VIRTUAL 電腦映射](configuring-a-windows-virtual-pc-image-for-med-v.md)，討論如何使用 Sysprep 來設定影像，以確保它已可搭配 med-v 使用。 然後，就會使用準備的 MED-V 影像來建立 MED-V 工作區套件。

-   [建立 Med-v 工作區套件](create-a-med-v-workspace-package.md)審查如何建立您在整個企業中部署的 med-v 工作區套件。 您可以部署 MED-V 工作區套件，在最終使用者的電腦上安裝 MED-V 工作區。 MED-V 工作區是一種 Windows XP 桌上型電腦環境，使用者可在此環境中與 MED-V 提供的虛擬機器進行互動。

-   [測試 Med-v 工作區套件](testing-the-med-v-workspace-package.md)討論如何建立測試環境，您可以在其中測試 med-v 工作區套件的功能，例如第一次設定設定和應用程式發佈。 完成您的 MED-V 工作區套件測試並確認它已正常運作之後，您就可以將它部署在整個企業中。

-   [部署 Med-v 工作區套件](deploying-the-med-v-workspace-package.md)討論如何使用電子軟體發佈系統或 Windows 7 影像來部署 med-v 工作區。 或者，如果您想要的話，此區段也會說明如何手動部署 MED-V 工作區。

-   [監視 med-v-v 工作區](monitor-med-v-workspaces.md)會檢查如何監視 med-v 工作區的部署，以判斷第一次安裝程式是否已順利完成。 監控第一次設定的成功與否，是因為 MED-V 在第一次成功完成之前並不是使用中的狀態。 本節也說明您可以設定您的環境來偵測那些可能會影響 MED-V 的網路變更。

-   [管理 Med-v 工作區應用程式](manage-med-v-workspace-applications.md)查看如何在已部署的 med-v 工作區上安裝及移除或發佈及取消發佈應用程式。 本節也說明如何在 MED-V 工作區中手動更新軟體，以及如何管理自動更新。 MED-V 工作區是包含獨立作業系統的虛擬機器，其自動軟體更新程式必須與企業中的物理電腦完全管理。

-   [管理 MED-V URL](manage-med-v-url-redirection.md)重新導向查看如何在已部署的 med-v 工作區上新增和移除網址重新導向設定。 您可以透過登錄來新增或移除 URL 重新導向資訊，或重建 MED-V 工作區。 您也可以在 MED-V 工作區包裝程式上使用此嚮導來管理 web 位址重新導向。

-   [管理 Med-v 工作區設定](manage-med-v-workspace-settings.md)瞭解如何使用 Med-v-v 工作區包裝程式來查看及編輯 med-v 設定設定。 本節列出所有可設定的 MED-V 登錄機碼，並包含每個的「類型」、「預設」和「描述」。 本節也包含如何在 MED-V 工作區中管理印表機的相關資訊。 在 MED-V 2.0 中，印表機重新導向可以讓使用者在 MED-V 虛擬機器與主機電腦之間保持一致的列印體驗。

## 相關主題


[適用於 MED-V 的操作](operations-for-med-v.md)

[MED-V 2.0 端對端規劃案例](end-to-end-planning-scenario-for-med-v-20.md)

[MED-V 2.0 端對端部署案例](end-to-end-deployment-scenario-for-med-v-20.md)

 

 





