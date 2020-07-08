---
title: 為 UE-V 準備您的環境
description: 為 UE-V 準備您的環境
author: dansimp
ms.assetid: c93d3b33-e032-451a-9e1b-8534e1625396
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8f806f3c326bad5204a7f1ee69e11b61177e3cce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810682"
---
# 為 UE-V 準備您的環境


Microsoft 使用者體驗虛擬化（UE-V）使用設定儲存位置在電腦之間漫遊設定。 [設定] 儲存位置是檔案共用，應該在 UE-V Agent 部署期間進行設定。 它必須定義為 [設定儲存位置] 或 [作為 Active Directory 主目錄]。 此外，系統管理員還應該將時間伺服器設定為支援一致的同步處理。 若要為 UE-V 準備您的環境，請考慮下列事項：

-   [Ue-v 設定儲存空間](#bkmk-uevsettingsstorage)：

    -   [定義設定儲存位置](#bkmk-definingsettingsstoragelocation)

    -   [使用 Active Directory 主目錄與 UE-V](#bkmk-usingactivedirectoryhomedirectory)

-   [同步處理 UE-V 設定同步處理電腦的時鐘](#bkmk-synchronizecomputerclocks)

-   [效能與容量規劃](#bkmk-performancecapacityplanning)

如需作業系統和電腦需求的詳細資訊，請參閱[ue-v 1.0 支援的](supported-configurations-for-ue-v-10.md)設定。

## <a href="" id="bkmk-uevsettingsstorage"></a>UE-V 設定儲存空間


您可以在下列其中一種設定中定義 [使用者體驗虛擬化設定] 儲存空間： [設定儲存位置] 或 [Active Directory 主目錄]。

### <a href="" id="bkmk-definingsettingsstoragelocation"></a>定義設定儲存位置

UE-V 設定儲存位置是一個可由 UE-V 使用者存取的標準網路共用。 您必須先建立根目錄，才能定義設定儲存位置。 將在共用上儲存設定的使用者，必須擁有儲存位置的讀/寫許可權。 UE-V Agent 將在這個根目錄下建立使用者專用的資料夾。 設定儲存位置是透過設定**SettingsStoragePath**配置選項來定義。 此選項可以使用下列方式進行設定：

-   透過命令列參數或在批次腳本中安裝 UE-V agent 期間。

-   使用 [群組原則]。

-   安裝之後，請使用 PowerShell 或 WMI。

路徑必須位於伺服器和共用的通用命名慣例（UNC）路徑中。 例如， **\\\\server\\settingsshare\\**。 這個設定選項支援使用變數來啟用特定的漫遊案例。

您可以將 `%username%` 變數與伺服器的 UNC 路徑搭配使用並共用。 這將在使用者登入的所有電腦或會話上提供相同的設定體驗。 在下列情況下，請考慮進行這項設定：

1.  企業中的使用者有多個相似設定的物理電腦，且每個使用者的設定在所有電腦上都應該是相同的。

2.  企業中的使用者使用虛擬桌面基礎結構（VDI）池，這些設定應該在每個使用者的 VDI 會話中保留。

3.  企業中的使用者有一部物理電腦，另外也使用 VDI。 無論是使用物理電腦或 VDI 會話，每個使用者的設定體驗都應該是一樣的。

4.  有多個企業電腦是由多個使用者使用。 每個使用者的設定體驗在所有電腦上應該都是相同的。

您可以將 **%username%\\%computername%** 變數與伺服器的 UNC 路徑搭配使用，然後共用。 這將會保留每個電腦的設定體驗。 在下列情況下，請考慮進行這項設定：

1.  企業中的使用者有多個物理電腦，而且您想要保留每個電腦的設定體驗。

2.  企業電腦是由多個使用者使用。 針對使用者登入的每一台電腦，都應該保留設定體驗。

UE-V agent 會根據 UE-V `SettingsStoragePath` 設定及定義的變數，動態建立使用者專用的設定儲存路徑。

UE-V agent 會動態建立一個 `SettingsPackages` 在每個使用者特定儲存位置中指定的隱藏系統資料夾。 UE-V agent 會讀取並將設定寫入此位置，如已註冊的 UE-V 設定位置範本所定義。

如果使用者的一組受管理電腦的設定儲存位置相同，適用的 UE-V 設定是由「上次寫入 wins」規則所決定。 在一部電腦上執行的代理程式會讀取並寫入到 [設定] 位置，而不受在其他電腦上執行的代理程式的影響。 [上次寫入的設定] 和 [值] 是下一個代理程式從 [設定] 儲存位置讀取時所套用的設定。 如需詳細資訊，請參閱[部署 ue-v 1.0 的設定儲存位置](deploying-the-settings-storage-location-for-ue-v-10.md)。

### <a href="" id="bkmk-usingactivedirectoryhomedirectory"></a>在 UE-V 使用 Active Directory 主目錄

如果在部署代理時沒有為 UE-V 設定設定儲存位置，則會使用使用者的 Active Directory （AD）主目錄來儲存設定位置套件。 UE-V agent 會在每個使用者的廣告主目錄根目錄下，動態建立 [設定儲存空間] 資料夾。 如果沒有另行定義設定儲存位置（SettingsStoragePath），則代理程式只會使用 Active Directory 主目錄。

## <a href="" id="bkmk-synchronizecomputerclocks"></a>同步處理 UE-V 設定同步處理電腦的時鐘


執行 UE-V agent 以進行同步處理設定的電腦，必須使用時間伺服器。 時間戳記是用來判斷是否需要從 [設定] 儲存位置同步處理設定。 如果電腦時鐘不准確，較舊的設定會覆寫較新的設定，或者新設定可能不會儲存到設定儲存位置。 使用時間伺服器可讓 UE-V 維持一致的設定體驗。

## <a href="" id="bkmk-performancecapacityplanning"></a>效能與容量規劃


UE-V 的容量需求可透過使用標準磁片容量和網路狀況監視來決定。 UE-V 使用伺服器訊息區塊（SMB）共用來儲存設定套件。 [設定] 套件的大小會根據特定應用程式的設定資訊而有所不同。 雖然大部分的設定套件都很小，但同步處理可能較大的檔案（例如桌面影像），可能會導致效能較差，特別是在較慢的網路上。 若要最大限度地減少網路延遲的問題，您應該在使用者電腦所在的同一個本機網路上建立設定儲存位置。

根據預設，如果網路速度緩慢或設定套件較大，UE-V 同步處理會在2秒後超時。 您可以使用群組原則設定超時。 如需如何設定超時的詳細資訊，請參閱[使用群組原則物件設定 ue-v](configuring-ue-v-with-group-policy-objects.md)。

## 相關主題


[Microsoft User Experience Virtualization (UE-V) 1.0](index.md)

[為 UE-V 1.0 進行規劃](planning-for-ue-v-10.md)

[UE-V 1.0 支援的組態](supported-configurations-for-ue-v-10.md)

 

 





