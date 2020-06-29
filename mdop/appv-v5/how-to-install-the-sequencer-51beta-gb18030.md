---
title: 如何安裝 Sequencer
description: 如何安裝 Sequencer
author: dansimp
ms.assetid: 5e8f1696-9bc0-4f44-8cb7-b809b2daae10
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b72330718a14cb8ffb0e582c946ff1e70539036c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800475"
---
# 如何安裝 Sequencer


使用下列程式來安裝 Microsoft Application Virtualization （App-v） 5.1 sequencer。 執行 sequencer 的電腦必須不執行 App-v 5.1 用戶端的任何版本。

不支援升級 App-v 排序器的前一個安裝。

**重要** 如需 sequencer 需求的完整清單，請參閱[app-v 5.1 先決條件](app-v-51-prerequisites.md)和[app-v 5.1 支援](app-v-51-supported-configurations.md)的設定的排序器區段。

 

您也可以使用命令列來安裝 App-v 5.1 排序器。 下列清單會顯示使用命令列和**appv\_sequencer\_setup.exe**安裝排序器選項的相關資訊：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">命令</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>/INSTALLDIR</p></td>
<td align="left"><p>指定安裝目錄。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/CEIPOPTIN</p></td>
<td align="left"><p>可參與 Microsoft 客戶經驗改進計畫。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/Log</p></td>
<td align="left"><p>指定安裝記錄的儲存位置，預設位置是 <strong> % Temp% </strong> 。 例如， <strong> C：\登入 </strong> 記錄。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/q</p></td>
<td align="left"><p>指定安靜或無提示的安裝。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/Uninstall</p></td>
<td align="left"><p>指定移除排序器。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/ACCEPTEULA</p></td>
<td align="left"><p>接受授權合約。 這對於無操作安裝是必要的。 範例用法： <strong> /ACCEPTEULA </strong> 或 <strong> /ACCEPTEULA = 1 </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/LAYOUT</p></td>
<td align="left"><p>指定相關聯的版面配置動作。 它也會將 Windows Installer （.msi）及腳本檔案解壓縮至資料夾，但不安裝 App-v 5.1。 不需要任何值。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/LAYOUTDIR</p></td>
<td align="left"><p>指定版面配置目錄。 需要字串值。 範例用法： <strong> /LAYOUTDIR = "C:\Application Virtualization 用戶端" </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/? 或/h 或/help</p></td>
<td align="left"><p>顯示相關的說明。</p></td>
</tr>
</tbody>
</table>

 

**安裝 App-v 5.1 排序器**

1.  將 App-v 5.1 sequencer 安裝檔案複製到安裝該檔案的電腦上。 按兩下**appv\_sequencer\_setup.exe**然後按一下 [**安裝**]。

2.  在 [**軟體授權條款**] 頁面上，您應該查看授權條款。 若要接受授權條款，請選取 **[我接受授權條款]。** 按 **\[下一步\]**。

3.  在 [**使用 Microsoft update]，協助保護您的電腦安全性且最新的**頁面，若要啟用 microsoft 更新，請選取 **[在我檢查更新時使用 microsoft Update （建議）]。** 若要從執行中停用 Microsoft 更新，請選取 [**我不想使用 Microsoft Update**]。 按 **\[下一步\]**。

4.  在 [**客戶經驗改進計畫**] 頁面上，若要參與程式，請選取 [**加入客戶經驗改進計畫**]。 這可讓您收集有關如何使用 App-v 5.1 的資訊。 如果您不想參與程式，請選取 [**我現在不想加入計畫**]。 按一下 **\[安裝\]**。

5.  若要開啟排序器，請按一下 [**開始**]，然後按一下 [ **Microsoft Application Virtualization 排序**器]。

**若要排查 App-v 5.1 sequencer 的安裝問題**

-   如需有關 sequencer 安裝的詳細資訊，您可以在 **% temp%** 資料夾中查看錯誤記錄。 若要查看記錄檔，請按一下 [**開始**]，輸入 **% temp%**，然後尋找**appv\_ 記錄**。

    您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[規劃部署 App-V](planning-to-deploy-app-v51.md)

 

 





