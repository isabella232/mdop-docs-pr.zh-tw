---
title: 建立 MED-V 的 Windows 虛擬電腦映像
description: 建立 MED-V 的 Windows 虛擬電腦映像
author: dansimp
ms.assetid: fd7c0b1a-0769-4e7b-ad1a-dad19cca081f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: f947479776e84a4c54edb10d583dd21d7ccf6f43
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800155"
---
# 建立 MED-V 的 Windows 虛擬電腦映像


在您可以將 MED-V 工作區傳送給使用者之前，您必須先準備好虛擬硬碟，以便為 Microsoft 企業版桌面虛擬化（MED-V）2.0 建立 MED-V 工作區安裝程式套件。 若要準備必要的虛擬硬碟，您必須建立包含所需作業系統、更新和軟體的 Windows 虛擬電腦影像，讓您稍後將應用程式和 URL 重新導向資訊部署給使用者。 本節提供有關如何建立虛擬硬碟的指導方針。

若要建立 MED-V 的虛擬影像，您必須遵循下列步驟。

1.  [建立 Windows 虛擬電腦影像](#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc)

2.  [在影像上安裝 Windows XP](#bkmk-installingwindowsxpontovpc)

3.  [在影像上安裝 .NET Framework](#bkmk-installingnet)

4.  [將更新套用至影像](#bkmk-applypatchestovpc)

5.  [安裝整合元件](#bkmk-installintegration)

## <a href="" id="bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc"></a>建立 Windows 虛擬電腦影像


若要建立 Windows 虛擬電腦映射，請參閱 Windows 虛擬電腦檔：

-   [Windows 虛擬 PC 首頁](https://go.microsoft.com/fwlink/?LinkId=148103)（ https://go.microsoft.com/fwlink/?LinkId=148103) 。

-   [Windows 虛擬電腦](https://go.microsoft.com/fwlink/?LinkId=182378)說明（ https://go.microsoft.com/fwlink/?LinkId=182378) 。

或者，如果您已經有想要用來做為虛擬影像基礎的 Windows Imaging （WIM）檔案，您可以將它轉換成您用來建立 MED-V 工作區的 VHD。 如需如何將 WIM 轉換成虛擬硬碟的詳細資訊，請參閱[Windows 7 中的原生 VHD 支援](https://go.microsoft.com/fwlink/?LinkId=195922)（ https://go.microsoft.com/fwlink/?LinkId=195922) 。

**重要** MED-V 只支援每個虛擬機器一個虛擬硬碟，且每個虛擬磁片上只有一個磁碟分割。

 

建立虛擬硬碟之後，請在影像上安裝 Windows XP。

## <a href="" id="bkmk-installingwindowsxpontovpc"></a>在 Windows 虛擬電腦映射上安裝 Windows XP


在建立 MED-V 工作區前，MED-V 需要在 Windows 虛擬電腦映射上安裝 Windows XP SP3。

如需如何安裝 Windows XP 的詳細資訊，請參閱[建立虛擬機器並安裝客體作業系統](https://go.microsoft.com/fwlink/?LinkId=182379)（ https://go.microsoft.com/fwlink/?LinkId=182379) 。

## <a href="" id="bkmk-installingnet"></a>在 Windows 虛擬電腦影像上安裝 .NET Framework 3.5 SP1


您必須將 .NET Framework 3.5 SP1 和更新 KB959209 手動安裝到您準備搭配 MED-V 使用的 Windows 虛擬電腦映射中。 更新[KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) （ https://go.microsoft.com/fwlink/?LinkId=204950) 解決幾個已知的應用程式相容性問題。

## <a href="" id="bkmk-applypatchestovpc"></a>將更新套用至 Windows 虛擬電腦影像


在您的虛擬機器上安裝 Windows XP 之後，請在映射上安裝任何必要的 Windows XP 更新，例如 SP3。 您也可以安裝特定的選擇性更新，以取得較佳的效能。

**重要** MED-V 需要在客體作業系統上執行 Windows XP SP3。

 

**警告** 當您安裝 Windows XP 的更新時，請確定您已在要在 MED-V 工作區中使用的來賓中保留 Internet Explorer 版本。 例如，如果您想要在 MED-V 工作區中執行 Internet Explorer 6，請確認您目前安裝的任何更新不包括 Internet Explorer 7 或 Internet Explorer 8。 此外，建議您設定登錄，以避免自動更新升級 Internet Explorer。

 

### 安裝選用的效能更新

雖然是選擇性的，但我們建議您安裝下列[修補程式 KB972435](https://go.microsoft.com/fwlink/?LinkId=201077)更新（ https://go.microsoft.com/fwlink/?LinkId=201077) 。 此更新會提高終端服務會話中共用資料夾的效能：

**記事** 此更新公開提供。 不過，系統可能會提示您接受 Microsoft 服務的合約。 依照後續網頁上的提示進行，以取得此熱修復程式。

 

### 設定群組原則效能更新

根據預設，群群組原則一次會下載到電腦一個位元組。 當 MED-V 加入網域時，這會造成延遲。 若要提高群組原則的效能，請將下列登錄機碼值設定為 registry：

登錄子機碼： HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon

專案： BufferPolicyReads

類型： DWORD

值：1

## <a href="" id="bkmk-installintegration"></a>安裝整合元件


Windows 虛擬電腦包含整合元件封裝。 這會提供可改善虛擬環境與物理電腦之間互動的功能。 例如，[整合元件套件] 可讓您在主機和來賓電腦之間移動滑鼠。

**重要** MED-V 需要安裝 [整合元件套件]。

 

當您將虛擬影像設定為與 MED-V 搭配使用時，您必須在客體作業系統上手動安裝整合元件套件，以建立可供使用的整合功能。

如需有關如何安裝及使用整合元件套件的詳細資訊，請參閱下列內容：

-   [安裝或升級整合元件套件](https://go.microsoft.com/fwlink/?LinkId=195923)（ https://go.microsoft.com/fwlink/?LinkId=195923) 。

-   [關於整合功能](https://go.microsoft.com/fwlink/?LinkId=195924)（ https://go.microsoft.com/fwlink/?LinkId=195924) 。

### 安裝 RemoteApp 更新

安裝整合元件套件之後，系統會提示您安裝下列更新：「Windows XP SP3 的更新以啟用 RemoteApp」。 這是 MED-V 所需的元件。

**重要** 如果系統未提示您安裝 RemoteApp 更新，您必須手動下載並安裝。 如需有關如何下載此更新的詳細資訊和指示，請參閱[WINDOWS XP SP3 更新，以啟用 RemoteApp](https://go.microsoft.com/fwlink/?LinkId=195925) （ https://go.microsoft.com/fwlink/?LinkId=195925) 。

 

### 啟用遠端桌面

根據預設，在您安裝整合元件套件之後，就會啟用遠端桌面。 如果 MED-V 要運作，請確定已啟用遠端桌面，而且不要發佈任何停用的群組原則。

如需如何啟用遠端桌面的相關資訊，請參閱[啟用或停用遠端桌面](https://go.microsoft.com/fwlink/?LinkId=201162)（ https://go.microsoft.com/fwlink/?LinkId=201162) 。

## 使用 Internet Explorer 管理工具組自訂 Internet Explorer


如有需要，您可以使用 Internet Explorer 管理工具組，在客體作業系統上自訂 Internet Explorer。 如需詳細資訊，請參閱[Internet Explorer 6 管理工具組與部署指南](https://go.microsoft.com/fwlink/?LinkId=200007)（HTTP://go.microsoft.com/fwlink/?LinkId=200007）。

**警告** 您應該考慮在 MED-V 工作區中自訂 Internet Explorer 所帶來的安全性考慮。 如需詳細資訊，請參閱[Med-v 運算的安全性最佳作法](security-best-practices-for-med-v-operations.md)。

 

使用最新的客體作業系統安裝虛擬硬碟之後，您就可以在影像上安裝應用程式。

## 相關主題


[在 Windows 虛擬電腦映像上安裝應用程式](installing-applications-on-a-windows-virtual-pc-image.md)

[設定 MED-V 的 Windows 虛擬電腦映像](configuring-a-windows-virtual-pc-image-for-med-v.md)

 

 





