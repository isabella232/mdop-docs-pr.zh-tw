---
title: 如何使用 DaRT 復原映像來復原本機電腦
description: 如何使用 DaRT 復原映像來復原本機電腦
author: dansimp
ms.assetid: be29b5a8-be08-4cf2-822e-77a51d3f3b65
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c605db895b5ea812d90db51d3c2de9653e2dd2d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810149"
---
# 如何使用 DaRT 復原映像來復原本機電腦


若要使用 Microsoft Diagnostics 和恢復工具組（DaRT）7來復原本機電腦，您必須在遇到需要 DaRT 之問題的使用者電腦上實際出現。 您也可以依照[如何使用 Dart 復原影像復原遠端電腦](how-to-recover-remote-computers-using-the-dart-recovery-image-dart-7.md)的指示，遠端執行 DaRT。

**使用 DaRT 復原本機電腦**

1.  當電腦啟動至 DaRT 復原影像時，會出現 [ **NetStart** ] 對話方塊。 系統會詢問您是否要初始化網路服務。 如果您按一下 **[是]**，系統會假設 DHCP 伺服器出現在網路上，且嘗試從伺服器取得 IP 位址。 如果網路使用靜態 IP 位址而不是 DHCP，您可以稍後在 DaRT 中使用**Tcp/ip 配置**工具來指定靜態 IP 位址。

    若要略過網路初始化程式，請按一下 [**否**]。

2.  在 [網路初始化] 對話方塊中，系統會詢問您是否要重新映射磁片磁碟機盤符。 當您執行 Windows online 時，系統磁碟區通常會對應到磁碟機 C。不過，當您在 [WinRE] 下執行 Windows 離線時，原始的系統磁碟區可能會對應到另一個磁片磁碟機，這可能會造成混淆。 如果您決定重新映射，DaRT 會嘗試對應離線磁碟機盤符，以符合線上磁片磁碟機盤符。 只有在後續的啟動程式中選取了離線作業系統時，才會執行重新映射。

3.  在重新變換對話方塊之後，會出現 [**系統復原選項**] 對話方塊，要求您選取鍵盤配置。 接著，它會顯示系統根目錄、所安裝的作業系統類型，以及分區大小。 如果您沒有看到您的作業系統，且懷疑驅動程式缺乏可能造成失敗，請按一下 [**載入驅動**程式] 載入可疑的驅動程式。 這會提示您插入裝置的安裝媒體及選取驅動程式。 選取您要修復或診斷的安裝，然後按 **[下一步]**。

    **注意**  
    如果 Windows 修復環境（WinRE）偵測到或懷疑 Windows 7 在上次嘗試時無法正常啟動，**啟動修復**可能會開始自動執行。



~~~
If any of the registry hives are corrupted or missing, Registry Editor, and several other DaRT utilities, will have limited functionality. If no operating system is selected, some tools will not be available.

The **System Recovery Options** window appears and lists various recovery tools.
~~~

4. 在 [**系統復原選項**] 視窗中，按一下 [ **Microsoft 診斷與修復工具**組]。

   隨即會開啟 [**診斷與修復工具集**] 視窗。 您現在可以執行在建立 DaRT 復原影像時所包含的任何個別工具或嚮導。

您可以按一下 [**診斷及修復工具集**] 視窗**上的 [** 說明]，開啟用戶端說明檔案，提供執行個別 DaRT 工具所需的詳細指示和資訊。 您也可以按一下 [**診斷及復原工具集**] 視窗上的 [**方案嚮導**]，根據嚮導所提供的簡短訪談，選擇適合情況的最佳工具。

如需任何 DaRT 工具的一般資訊，請參閱[DaRT 7.0 中的工具概覽](overview-of-the-tools-in-dart-70-new-ia.md)。

**在命令提示字元執行 DaRT**

1. 您可以在命令提示字元中，使用下列任何一個參數指定**netstart.exe**命令，以執行 DaRT：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">參數</th>
   <th align="left">描述</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>-網路</p></td>
   <td align="left"><p>初始化網路服務。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>重新裝載</p></td>
   <td align="left"><p>重新映射磁片磁碟機盤符。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>-提示</p></td>
   <td align="left"><p>顯示訊息，要求使用者指定是否要初始化網路並重新映射磁片磁碟機。</p>
   <div class="alert">
   <strong>重要</strong><br/><p>使用者對提示的回應會覆寫網路和重新裝載開關。</p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



2. 您可以自訂 DaRT，讓啟動至 DaRT 的電腦自動開啟用來建立與技術支援人員的遠端連線的**遠端連線**工具。

## 相關主題


[使用 DaRT 7.0 復原電腦](recovering-computers-using-dart-70-dart-7.md)









