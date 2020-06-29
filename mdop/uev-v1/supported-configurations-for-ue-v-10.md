---
title: UE-V 1.0 支援的組態
description: UE-V 1.0 支援的組態
author: dansimp
ms.assetid: d90ab83e-741f-48eb-b1d8-a64cb9259f7a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a84514317de8a4cfd9df9c94a9a130933b00874a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811223"
---
# UE-V 1.0 支援的組態


Microsoft 使用者體驗虛擬化（UE-V）支援下列所述的配置。

**記事** Microsoft 提供目前 service pack 的支援，在某些情況下，也是前面的服務套件。 若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 如需 Microsoft 支援週期原則的詳細資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。

 

## UE-V Agent 與 UE-V 發生器支援的設定


下表列出支援使用者體驗虛擬化發生器和使用者體驗虛擬化代理程式的作業系統。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>作業系統</strong></th>
<th align="left"><strong>版本</strong></th>
<th align="left"><strong>Service pack</strong></th>
<th align="left"><strong>系統架構</strong></th>
<th align="left"><strong>Microsoft .NET Framework</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>旗艦版、企業版或專業版</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
<td align="left"><p>.NET Framework 3.5 SP1</p>
<p>.NET Framework 4 （發生器）</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008R2</p></td>
<td align="left"><p>[標準]、[企業]、[資料中心] 或 [Web 服務器]</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>.NET Framework 3.5 SP1</p>
<p>.NET Framework 4 （發生器）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows8</p></td>
<td align="left"><p>企業版或專業版</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
<td align="left"><p>.NET Framework 4 或 .NET Framework 3.5 SP1 （Agent）</p>
<p>.NET Framework 4 （發生器）</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>標準或資料中心</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>.NET Framework 4 或 .NET Framework 3.5 SP1 （Agent）</p>
<p>.NET Framework 4 （發生器）</p></td>
</tr>
</tbody>
</table>

 

UE-V 沒有特殊的 RAM 需求。

UE-V agent 的安裝需要系統管理許可權，且需要先重新開機電腦，然後才能執行 UE-V agent。

**重要** 您必須停用 Windows 8 中的 [同步處理您的設定] 功能，才能讓 UE-V 能正常運作。 使用 Windows 8 和 UE-V 同步處理設定將會導致無法預測的同步處理行為。

 

### <a href="" id="requirements-for-the-offline-files-feature-"></a>[離線檔案] 功能的需求

UE-V agent 可以同步處理並非一直連線至商業網路的電腦的使用者設定，例如膝上型電腦或位於遠端辦公室的電腦，以及永遠連線至商業網路的電腦（例如託管虛擬桌面介面（VDI）會話的 Windows 伺服器）。

UE-V 預設配置使用 Windows 離線檔案功能來同步處理設定。 [離線檔案] 可確保即使電腦離開商業網路，還是可以使用使用者的設定。 當重建與商業網路的連線時，對設定所做的任何變更都會自動與 [設定] 儲存位置進行同步處理。 [離線檔案] 也可確保使用者的設定適用于使用低速或限制連接的遠端辦公室中的電腦。

若要同步處理偶爾離開商業網路的電腦設定，必須先啟用並啟動 [離線檔案] 功能，然後才能開始進行 UE-V agent 部署。 預設會在 Windows7 上啟用 [離線檔案] 功能。 預設會在 Windows Server2008R2、Windows Server 2012 和 Windows 8 上停用此功能。 如果 [離線檔案] 功能未啟用，則 UE-V 設定同步處理將會失敗。

-   **Windows 7**

    預設會在 Windows 7 上啟用 [離線檔案] 功能。 如有需要，可以在提升許可權的命令提示字元中使用下列命令來啟用離線檔案：

    ``` syntax
    sc config CscService start=auto
    ```

-   **Windows8**

    預設會在 Windows 8 版本上停用 [離線檔案] 功能。 您可以在 Windows 8 上啟用離線檔案，方法是在提升許可權的命令提示字元中使用下列命令：

    ``` syntax
    sc config CscService start=auto
    ```

-   **Windows Server 2008 R2 和 Windows Server 2012**

    Windows Server 2008 R2 或 Windows Server 2012 預設不會安裝 [離線檔案] 功能。 若要啟用 [離線檔案] 功能，必須安裝 [桌面體驗套件]。 此為選用的伺服器元件，其中包含 [離線檔案] 功能。 安裝之後，請在提升許可權的命令提示字元中，以下列命令啟動 [離線檔案] 功能：

    ``` syntax
    sc config csc start= system
    ```

    ``` syntax
    sc config cscservice start= auto
    ```

必須先重新開機電腦，設定才會開始同步處理。

### 同步處理具有永不使用的連線的電腦

當您在一直連線至商業網路的電腦（例如主持 VDI 會話的 Windows Server 電腦）上使用 UE-V 時，應該停用 [離線檔案]。

當 UE-V agent 設定為同步處理設定，而不使用離線檔案時，設定儲存伺服器會視為標準網路共用。 當網路可用時，就會同步處理設定。 在這個設定中，UE-V agent 可以設定為在應用程式設定匯入延遲時發出通知。

如果不使用 [離線檔案] 功能，您必須在進行 UE-V agent 部署之前或期間停用 UE-V 預設行為。 若要停用 UE-V 的離線檔案，請執行下列其中一項操作：

-   在您部署 UE-V agent 之前，請先在 UE-V 群組原則設定中標示 [不要使用離線檔案] 核取方塊。

-   在 UE-V 安裝期間，請 `SyncMethod = None` 在命令提示字元或批次處理檔案中設定 AgentSetup.exe 參數。 如需有關如何部署代理程式的詳細資訊，請參閱[部署 Ue-v agent](deploying-the-ue-v-agent.md)。

如果您在 UE-V 停用 [離線檔案] 設定，而您沒有在安裝時間指定**SyncMethod**參數，ue-v agent 安裝將會失敗。 您也可以使用 PowerShell 或 WMI 停用離線檔案。 如需 WMI 和 PowerShell 命令的詳細資訊，請參閱[使用 PowerShell 和 WMI 管理 ue-v 1.0 Agent 和套件](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md)。

必須先重新開機電腦，設定才會開始同步處理。

### UE-V PowerShell 功能的先決條件

Agent 的 UE-V PowerShell 功能需要啟用 .NET Framework 版本 3.5 SP1，以及 PowerShell 版本2.0 或更高版本。

### UE-V 發生器支援的先決條件

在用來建立自訂設定位置範本的電腦上安裝 UE-V 發生器。 此電腦應該已安裝的應用程式，其設定將會漫遊。 您必須是執行 UE-V 發生器軟體之電腦上系統管理員群組的成員。 此外，UE-V 發生器必須安裝在使用 NTFS 檔案系統的電腦上。 UE-V 發生器軟體需要 .NET Framework 版本4。 如需詳細資訊，請參閱[規劃 ue-v 1.0 的自訂範本部署](planning-for-custom-template-deployment-for-ue-v-10.md)。

## 相關主題


[為 UE-V 1.0 進行規劃](planning-for-ue-v-10.md)

[為 UE-V 準備您的環境](preparing-your-environment-for-ue-v.md)

[部署 UE-V 1.0](deploying-ue-v-10.md)

使用者體驗虛擬化的支援[設定部署 ue-v 1.0 的設定儲存位置](deploying-the-settings-storage-location-for-ue-v-10.md)

[安裝 UE-V 產生器](installing-the-ue-v-generator.md)

[部署 UE-V 代理程式](deploying-the-ue-v-agent.md)

 

 





