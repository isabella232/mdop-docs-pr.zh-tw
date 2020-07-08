---
title: 如何使用 DaRT 復原映像來復原遠端電腦
description: 如何使用 DaRT 復原映像來復原遠端電腦
author: dansimp
ms.assetid: 66bc45fb-dc40-4d47-b583-5bb1ff5c97a7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 885ab1d1cf8f51dc4fd4613e41a20a2525ea7d6d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809567"
---
# 如何使用 DaRT 復原映像來復原遠端電腦


Microsoft Diagnostics 與復原工具組（DaRT）7中的遠端連線功能可讓 IT 系統管理員在最終使用者電腦上遠端執行 DaRT 工具。 當使用者（或由支援使用者電腦的技術人員）提供特定資訊之後，IT 系統管理員或技術支援人員就可以控制最終使用者的電腦，並以遠端方式執行必要的 DaRT 工具。

**重要**  
建立遠端連線的兩台電腦必須是相同網路的一部分。



**使用 DaRT 復原遠端電腦**

1.  使用 DaRT 復原影像啟動端使用者電腦。

    您通常會使用下列其中一種方法來引導至 DaRT，以根據您部署 DaRT 復原影像的方式來復原遠端電腦。 如需有關部署 DaRT 復原影像的詳細資訊，請參閱[部署 dart 7.0 恢復影像](deploying-the-dart-70-recovery-image-dart-7.md)。

    -   從問題電腦上的 [恢復] 分區引導至 DaRT。

    -   從網路上的遠端分區引導至 DaRT。

    如需每個方法的優點與缺點的詳細資訊，請參閱[規劃如何儲存和部署 DaRT 7.0 恢復影像](planning-how-to-save-and-deploy-the-dart-70-recovery-image.md)。

    無論您使用何種方法引導至 DaRT，您都必須在 BIOS 中啟用啟動裝置，以找到您要讓使用者使用的引導選項或選項。

    **注意**  
    根據您組織中使用的硬碟、網路介面卡及其他硬體的類型，設定 BIOS 是唯一的。



2.  當電腦啟動至 DaRT 復原影像時，會出現 [ **NetStart** ] 對話方塊。 系統會詢問您是否要初始化網路服務。 如果您按一下 **[是]**，系統會假設 DHCP 伺服器出現在網路上，且嘗試從伺服器取得 IP 位址。 如果網路使用靜態 IP 位址而不是 DHCP，您可以稍後在 DaRT 中使用**Tcp/ip 配置**工具來指定靜態 IP 位址。

    若要略過網路初始化程式，請按一下 [**否**]。

3.  在 [網路初始化] 對話方塊中，系統會詢問您是否要重新映射磁片磁碟機盤符。 當您執行 Windows online 時，系統磁碟區通常會對應到磁碟機 C。不過，當您在 [WinRE] 下執行 Windows 離線時，原始的系統磁碟區可能會對應到另一個磁片磁碟機，這可能會造成混淆。 如果您決定重新映射，DaRT 會嘗試對應離線磁碟機盤符，以符合線上磁片磁碟機盤符。 只有在後續的啟動程式中選取了離線作業系統時，才會執行重新映射。

4.  在重新變換對話方塊之後，會出現 [**系統復原選項**] 對話方塊，要求您選取鍵盤配置。 接著，它會顯示系統根目錄、所安裝的作業系統類型，以及分區大小。 如果您沒有看到您的作業系統，且懷疑驅動程式缺乏可能造成失敗，請按一下 [**載入驅動**程式] 載入可疑的驅動程式。 這會提示您插入裝置的安裝媒體及選取驅動程式。 選取您要修復或診斷的安裝，然後按 **[下一步]**。

    **注意**  
    如果 Windows 修復環境（WinRE）偵測到或懷疑 Windows 7 在上次嘗試時無法正常啟動，**啟動修復**可能會開始自動執行。 如需此情況的相關資訊（包括如何解決），請參閱[DaRT 7.0 疑難排解](troubleshooting-dart-70-new-ia.md)。



~~~
If any of the registry hives are corrupted or missing, Registry Editor, and several other DaRT utilities, will have limited functionality. If no operating system is selected, some tools will not be available.

The **System Recovery Options** window appears and lists various recovery tools.
~~~

5. 在 [**系統復原選項**] 視窗中，選取 [ **Microsoft 診斷與修復工具集**] 以開啟 [**診斷及修復工具集**] 視窗。

6. 在 [**診斷及修復工具**] 視窗中，按一下 [**遠端**連線] 以開啟 [ **DaRT 遠端**連線] 視窗。 如果系統提示您提供支援中心的遠端存取，請按一下 **[確定]**。

   隨即會開啟 [DaRT 遠端連線] 視窗，並顯示票證號碼、IP 位址和埠資訊。

7. 在 [服務台] 代理電腦上，開啟 [ **DaRT 遠端連線檢視器]**。

   按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft DaRT 7**]，然後按一下 [ **DaRT 遠端連線檢視器]**。

8. 在 [ **DaRT 遠端**連線] 視窗中，輸入所需的票證、IP 位址和埠資訊。

   **注意**  
   此資訊是在使用者電腦上建立，且必須由最終使用者提供。 可能有多個 IP 位址可供選擇，視最終使用者電腦上可用的數目而定。



9. 按一下 **\[連線\]**。

IT 系統管理員現在假設您可以控制最終使用者電腦，並可遠端執行 DaRT 工具。

**注意**  
已提供名為 inv32.xml 的檔案，其中包含遠端連線資訊，例如埠號碼和 IP 位址。 根據預設，檔案通常位於%windir%\\system32。



**自訂遠端連線進程**

1. 您可以編輯 winpeshl.ini 檔案，自訂遠端連線進程。 如需如何編輯 winpeshl.ini 檔案的詳細資訊，請參閱[Winpeshl.ini](https://go.microsoft.com/fwlink/?LinkId=219413)檔案。

   指定下列命令和參數，來自訂如何與終端使用者電腦建立遠端連線：

   <table>
   <colgroup>
   <col width="33%" />
   <col width="33%" />
   <col width="33%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">命令</th>
   <th align="left">參數</th>
   <th align="left">描述</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>RemoteRecovery.exe</strong></p></td>
   <td align="left"><p>-nomessage</p></td>
   <td align="left"><p>指定不會顯示確認提示。 <strong>[遠端連線] </strong> 繼續執行，就像最終使用者 &quot; &quot; 對確認提示作出回應時一樣。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>WaitForConnection.exe</strong></p></td>
   <td align="left"><p>無 (none)</p></td>
   <td align="left"><p>防止自訂腳本繼續進行，直到 <strong> 沒有執行任何遠端連線 </strong> ，或是與使用者電腦建立有效的連線。</p>
   <div class="alert">
   <strong>重要</strong><br/><p>這個命令不會提供任何函數（如果它是獨立指定的）。 必須在腳本中指定它才能正常運作。</p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



2. 下列是自訂的 winpeshl.ini 檔案範例，只要嘗試啟動到 DaRT，就可以開啟**遠端**連線工具：

   ```ini
   [LaunchApps]
   "%windir%\system32\netstart.exe -network -remount"
   "cmd /C start %windir%\system32\RemoteRecovery.exe -nomessage"
   "%windir%\system32\WaitForConnection.exe"
   "%SYSTEMDRIVE%\sources\recovery\recenv.exe"
   ```

**在命令提示字元執行遠端連線檢視器**

1.  您可以在命令提示字元上執行**DaRT 遠端連線檢視器**，方法是指定**DartRemoteViewer.exe**命令，並使用下列參數：

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
    <td align="left"><p>-ticket = &lt; <em> ticketnumber</em>&gt;</p></td>
    <td align="left"><p>其中 &lt; <em> ticketnumber </em> &gt; 是由遠端連線產生的票證編號，包括虛線。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>-ipaddress = &lt; <em> ipaddress</em>&gt;</p></td>
    <td align="left"><p>其中， &lt; <em> Ipaddress </em> &gt; 是遠端連線所產生的 IP 位址。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>-port = &lt; <em> 埠</em>&gt;</p></td>
    <td align="left"><p>其中 &lt; <em> port </em> &gt; 是對應至指定 IP 位址的埠。</p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  
The variables for these parameters are created on the end-user computer and must be provided by the end user.
~~~



2. 如果所有三個參數都已指定，且資料有效，則會在程式啟動時立即嘗試連接。 如果有任何參數無效，程式就會啟動，就好像沒有指定參數一樣。

## 相關主題


[使用 DaRT 7.0 復原電腦](recovering-computers-using-dart-70-dart-7.md)









