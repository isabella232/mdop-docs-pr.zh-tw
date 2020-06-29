---
title: 安裝 MBAM 2.5 伺服器軟體
description: 安裝 MBAM 2.5 伺服器軟體
author: dansimp
ms.assetid: b9dbe697-5400-4bac-acfb-ee6dc6586c30
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6612bf52aa53ae693694d7ac02c5cab212d4e24f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809927"
---
# 安裝 MBAM 2.5 伺服器軟體


本主題描述如何使用 Microsoft BitLocker 管理及監視設定向導或使用命令列參數，來安裝 Microsoft BitLocker 管理和監控（MBAM）2.5 伺服器軟體。 針對您正在設定 MBAM 2.5 Server 功能的每個伺服器，重複執行伺服器安裝程式。 完成安裝之後，請參閱設定[MBAM 2.5 伺服器功能](configuring-the-mbam-25-server-features.md)，以取得設定伺服器功能的步驟。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">開始之前</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>查看 MBAM 2.5 規劃資訊</p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</a></p></li>
<li><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 支援的組態</a></p></li>
<li><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)">MBAM 2.5 的概要架構</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>閱讀如何取得記錄檔</p></td>
<td align="left"><p>根據預設，會在本機電腦的% temp% 資料夾中建立記錄檔。 若要將記錄檔寫入特定位置，而不是寫入 <strong> % temp </strong> % 資料夾，請使用 <strong> /log </strong> &lt; <em> location </em> &gt; 引數。</p>
<p>在 [ <strong> </strong> <strong> </strong> <strong> 應用程式和服務記錄 &gt; Microsoft Windows] 下 &gt; </strong> ，可能會在事件檢視器的 [MBAM-設定] 或 MBAM 網頁節點中記錄其他事件。 例如，如果您卸載 MBAM，卸載程式也會在 EventViewer 中卸載 MBAM 設定和 MBAM Web 記錄。</p></td>
</tr>
</tbody>
</table>

 

## 使用 Microsoft BitLocker 管理和監視設定向導來安裝 MBAM 2.5 Server 軟體


使用這些步驟，透過 Microsoft BitLocker 管理和監視設定向導來安裝 MBAM Server 軟體。

**使用嚮導來安裝 MBAM 2.5 Server 軟體**

1.  在您要安裝 MBAM 的伺服器上，執行**MBAMserversetup.exe**以啟動 Microsoft BitLocker 管理及監視設定向導。

2.  在 [**歡迎**] 頁面上，按一下 **[下一步]**。

3.  閱讀並接受 Microsoft 軟體授權協定，然後按一下 **[下一步]** 繼續安裝。

4.  選擇是否要在檢查更新時使用 Microsoft Update，然後按 **[下一步]**。

5.  選擇是否要參與客戶經驗改進計畫，然後按 **[下一步]**。

6.  若要開始安裝，請按一下 [**安裝**]。

7.  若要在 MBAM Server 軟體完成安裝之後設定伺服器功能，請選取 [在**嚮導關閉後執行 MBAM 伺服器設定]** 核取方塊。 或者，您可以在稍後使用伺服器安裝在 [**開始**] 功能表上建立的 [ **MBAM 伺服器**設定] 快捷方式來設定 MBAM。

8.  按一下 **\[完成\]**。

## 使用命令提示字元視窗安裝 MBAM 2.5 Server 軟體


在命令提示字元中，輸入類似下列命令的命令來安裝 MBAM Server 軟體。

``` syntax
MbamServerSetup.exe MBAMServerInstall.log
CEIPENABLED=True OPTIN_FOR_MICROFOST_UPDATES=True INSTALLDIR=c:\mbaminstall
```

下表說明安裝 MBAM 2.5 Server 軟體的命令列參數。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">參數</th>
<th align="left">參數值</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>CEIPENABLED</p></td>
<td align="left"><p>True False</p></td>
<td align="left"><p>True-參與客戶改進體驗計畫，協助 Microsoft 找出要改善哪些 MBAM 功能。</p>
<p>False –不參與客戶改進體驗計畫。</p></td>
</tr>
<tr class="even">
<td align="left"><p>OPTIN_FOR_MICROSOFT_UPDATES</p></td>
<td align="left"><p>True False</p></td>
<td align="left"><p>True-使用 Microsoft Update，讓您的電腦擁有最新的 Windows 和其他 Microsoft 產品，包括 MBAM。</p>
<p>False –不使用 Microsoft Update</p></td>
</tr>
<tr class="odd">
<td align="left"><p>INSTALLDIR</p></td>
<td align="left"><p>&lt;路徑&gt;</p></td>
<td align="left"><p>您想要安裝 MBAM 的位置。</p>
<p>範例：</p>
<p>INSTALLDIR = c:\mbaminstall</p></td>
</tr>
<tr class="even">
<td align="left"><p>FORCE_UNINSTALL</p></td>
<td align="left"><p>True False</p></td>
<td align="left"><p>True-繼續卸載 MBAM 的程式，即使無法移除任何功能也一樣。</p>
<p>False （預設）如果卸載自訂動作無法移除已新增的 MBAM 伺服器功能，則卸載會失敗，而 MBAM 仍會保持安裝狀態。</p>
<p>在這兩個實例中，嘗試卸載 MBAM 期間已成功移除的任何功能都會保持移除。</p></td>
</tr>
</tbody>
</table>

 



## 相關主題


[部署 MBAM 2.5](deploying-mbam-25.md)

[設定 MBAM 2.5 伺服器功能](configuring-the-mbam-25-server-features.md)

 

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





