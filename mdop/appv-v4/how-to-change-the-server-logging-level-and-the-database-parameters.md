---
title: 如何變更伺服器登入層級和資料庫參數
description: 如何變更伺服器登入層級和資料庫參數
author: dansimp
ms.assetid: e3ebaee5-6c4c-4aa8-9766-c5aeb00f477a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bb35ac09c5e23f4847662171b68284f868e66dee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801654"
---
# 如何變更伺服器登入層級和資料庫參數


您可以使用下列程式來變更應用程式虛擬化伺服器管理主控台的記錄層級和資料庫記錄參數。

提供下列記錄層級：

-   僅交易

-   致命錯誤

-   錯誤

-   警告/錯誤

-   資訊/警告/錯誤

-   冗長

**記事** 由於您使用**詳細**模式時所產生的記錄檔案大小，因此建議您不要使用此記錄集等級設定來執行生產伺服器。

 

資料庫記錄參數決定了資料庫驅動程式類型、存取認證及記錄資料庫的位置。

**若要變更管理伺服器的記錄層級**

1.  按一下 [**伺服器群組**] 節點，以顯示 [伺服器群組]。

2.  以滑鼠右鍵按一下 [伺服器] 群組，然後選取 [**屬性**]。

3.  在 [**屬性**] 對話方塊中，選取 [**記錄**] 索引標籤。

4.  在 [**伺服器群組屬性**] 對話方塊中，選取伺服器，然後按一下 [**編輯**]。

5.  在 [**新增/編輯記錄模組**] 對話方塊中，從 [**事件種類**] 下拉式清單中選取記錄層級。

6.  按一下 \[確定\] ****。

7.  在 [**伺服器群組屬性**] 對話方塊中，按一下 **[確定] 或 [套用]** 。 **Apply**

**變更流式處理伺服器的記錄層級**

1.  編輯下列登錄機碼值，以變更記錄層級：

    -   HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\DistributionServer\\LogLevel

2.  選取下列其中一個值來設定記錄層級。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">值</th>
    <th align="left">記錄層級</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>0</p></td>
    <td align="left"><p>僅交易</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>sr-1</p></td>
    <td align="left"><p>致命錯誤</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>pplx-2</p></td>
    <td align="left"><p>錯誤</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>3</p></td>
    <td align="left"><p>警告/錯誤</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>4</p></td>
    <td align="left"><p>資訊/警告/錯誤</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>500</p></td>
    <td align="left"><p>冗長</p></td>
    </tr>
    </tbody>
    </table>

     

**變更資料庫記錄參數**

1.  按一下 [**伺服器群組**] 節點，以顯示 [伺服器群組]。

2.  以滑鼠右鍵按一下 [伺服器] 群組，然後選取 [**屬性**]。

3.  在 [**屬性**] 對話方塊中，選取 [**記錄**] 索引標籤。

4.  在 [**伺服器群組屬性**] 對話方塊中，選取伺服器，然後按一下 [**編輯**]。

5.  在 [**新增/編輯記錄模組**] 對話方塊中，從 [**資料庫驅動程式**] 下拉式清單中選取資料庫驅動程式。

6.  輸入**DNS 主機名稱**。

7.  按一下 [**動態判斷埠**] 核取方塊，或在 [**埠**] 欄位中輸入埠號碼。

8.  在對應欄位中輸入**服務名稱**。

9.  按一下 \[確定\] ****。

10. 在 [**伺服器群組屬性**] 對話方塊中，按一下 **[確定] 或 [套用]** 。 **Apply**

## 相關主題


[如何在伺服器管理主控台中自訂 Application Virtualization 系統](how-to-customize-an-application-virtualization-system-in-the-server-management-console.md)

 

 





