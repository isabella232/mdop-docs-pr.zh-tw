---
title: 如何匯入應用程式
description: 如何匯入應用程式
author: dansimp
ms.assetid: ab40acad-1025-478d-8e13-0e1ff1bd37e4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7d9cd6d065ca28b5d856acdae7d10a1280105e9d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801402"
---
# 如何匯入應用程式


通常，您必須匯入應用程式，才能從應用程式虛擬化管理伺服器對流進行資料流程。 您也可以手動新增應用程式，但您必須提供應用程式的確切詳細資訊來執行此操作。 如需詳細資訊，請參閱[如何手動新增應用程式](how-to-manually-add-an-application.md)。

**記事** 若要匯入應用程式，您必須擁有其已排序的開啟軟體描述項（OSD）檔案或其 Sequencer 專案（SPRJ）檔案（在伺服器上可用）。

 

匯入應用程式時，您應該確認伺服器已在 [**系統選項**] 對話方塊的 [**一般**] 索引標籤上，將 [**預設內容路徑**] 欄位中的值設定為（可透過以滑鼠右鍵按一下 App-v Server 主控台中的 [**應用程式虛擬化系統**] 節點）。 預設的內容路徑值定義了要匯入應用程式的位置，以及在匯入程式期間，此值用於修改 SFT 檔案的 OSD 檔案中定義的路徑，以及圖示快速鍵。 在 OSD 檔案中，SFT 檔案的路徑是在 CODEBASE HREF 專案中指定，而圖示的路徑是在快速鍵專案中指定。

在匯入程式中，在 OSD 檔案中，在這兩個路徑中指定的埠（如果有的話）會以預設內容路徑中的值取代。 下表提供匯入路徑會受到影響的範例。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">預設內容路徑</th>
<th align="left">OSD 檔案基本代碼 HREF</th>
<th align="left">結果值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\server\content &lt; /p&gt;</td>
<td align="left"><p><a href="http://WebServer/myFolder/package.sft" data-raw-source="http://WebServer/myFolder/package.sft">http://WebServer/myFolder/package.sft</a></p></td>
<td align="left"><p>\server\content\myFolder\package.sft</p></td>
</tr>
</tbody>
</table>

 

**匯入應用程式**

1.  以滑鼠右鍵按一下左窗格中的 [**應用程式**] 節點，然後選擇 [匯**入應用程式**]。

2.  在 [**開啟**舊檔] 對話方塊中，流覽至應用程式的 SPRJ 或 OSD 檔案。 醒目提示檔案，然後按一下 [**開啟**]。

3.  在 [**新增應用程式] 嚮導**中，請確定已針對您要進行串流的應用程式選取 [**已啟用**] 核取方塊。 您也可以在其中輸入描述並確認伺服器與檔路徑。 此外，如果您已設定授權和伺服器群組，您可以選取這些使用者。

4.  按 **\[下一步\]**。

5.  在 [**已發佈的快速鍵**] 畫面上，選取您想要在用戶端電腦上顯示應用程式快捷方式的位置方塊。

6.  按 **\[下一步\]**。

7.  在 [檔案**關聯**] 畫面中，您可以在此應用程式中新增新的檔案關聯。 若要這樣做，請按一下 [**新增**]，輸入副檔名（不含前一個點），輸入描述，然後按一下 **[確定]**。

    **記事** 使用 Sequencer 4.0 排序的應用程式會在您匯入或透過管理主控台建立檔案時填入 [檔案**關聯**] 對話方塊。 先前的 Sequencer 版本套件的應用程式不會。

     

8.  按 **\[下一步\]**。

9.  在 [**存取許可權**] 畫面中，按一下 [**新增**]。

10. 完成 [**選取群組**] 對話方塊。 完成後，請按一下 **[確定]**。

11. 按 **\[下一步\]**。

12. 在 [**摘要**] 畫面上，您可以查看 [匯入] 設定。 按一下 **[完成]**，或按一下 [**上一步**] 來變更匯入，或按一下 [**取消**] 以取消匯入。

## 相關主題


[如何在伺服器管理主控台中管理應用程式群組](how-to-manage-application-groups-in-the-server-management-console.md)

[如何在伺服器管理主控台中管理應用程式](how-to-manage-applications-in-the-server-management-console.md)

[如何手動新增應用程式](how-to-manually-add-an-application.md)

 

 





