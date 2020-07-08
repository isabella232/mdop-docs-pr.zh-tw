---
title: 如何建立和測試 MED-V 映像
description: 如何建立和測試 MED-V 映像
author: dansimp
ms.assetid: 40e4aba6-12cb-4794-967d-2c09dc20d808
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9f7989871a695b09c987124ab02c0143082148f3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812117"
---
# 如何建立和測試 MED-V 映像


MED-V 系統管理員會建立 MED-V 影像，讓它可以上傳，與 MED-V 工作區建立關聯，然後透過網路發佈至用戶端、新增至 MED-V 套件，或使用協力廠商系統下載到用戶端。 建議您先建立測試影像，並在 MED-V 用戶端上進行測試，然後再進行部署。

建立 MED-V 影像時，會透過下列階段進行：

1.  **本機測試影像**：可在本機測試的基本影像。

2.  **本機封裝影像**：在測試影像之後，影像會封裝為在測試之前存在的影像。 在測試期間進行的變更不會包含在打包的影像中。

3.  **在伺服器上封裝影像**：打包的影像會上傳到伺服器。

## 如何建立 MED-V 測試圖像


**若要建立新的 MED-V 測試影像**

1.  按一下 [**影像**管理] 按鈕。

    [**影像**] 模組隨即出現。

    -   [**影像**] 模組由下列窗格組成：

        -   **本機測試影像**-本機解包圖像。

        -   **本機打包的影像**-在本機電腦上的所有打包影像。

        -   **在伺服器上打包的影像**：已打包並上傳到伺服器的所有影像。

    -   在**本機打包的影像**和**伺服器窗格上打包的影像**中，每個影像的最新版本都會顯示為父節點。 按一下父節點，以查看所有其他現有的圖像版本。

2.  在 [**本機測試影像**] 窗格中，按一下 [**新增**]。

3.  在 [**測試影像建立**] 對話方塊中，執行下列其中一項動作，選取您要設定為 med-v 測試影像的虛擬機器影像：

    -   在 [**基底圖像**檔案] 欄位中，輸入為 med-v 準備的 MICROSOFT Virtual 電腦影像準備的目錄完整路徑。

    -   按一下 **[流覽**]，流覽至準備 Med-v-V 的 MICROSOFT Virtual 電腦影像所在的目錄。

4.  在 [**影像名稱**] 欄位中，輸入或選取想要的名稱。

    **記事** 下列字元不能包含在影像名稱中： space " &lt; &gt; |\\ / : \* ?

     

5.  按一下 \[確定\] ****。

    您的主機電腦上會建立新的 MED-V 測試影像，其屬性在下表中定義。

    如需有關設定 MED-V 工作區圖像的詳細資訊，請參閱設定[Med-v 工作區原則](configuring-med-v-workspace-policies.md)。

**本機測試影像屬性**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">屬性</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>圖像名稱</p></td>
<td align="left"><p>在管理員建立影像時所定義之測試映射的名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>影像路徑</p></td>
<td align="left"><p>測試影像的本機路徑。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>新建</p></td>
<td align="left"><p>已建立測試影像的日期。</p></td>
</tr>
</tbody>
</table>

 

## 如何從 MED-V 用戶端測試 MED-V 影像


建立 MED-V 測試圖像之後，請使用下列程式在本機測試影像。

**測試 MED-V 影像**

1.  按一下 [**原則**管理] 按鈕。

2.  在**原則**模組中，執行下列動作，將 med-v 測試影像指派給 med-v 工作區：

    1.  按一下 [**虛擬機器**] 索引標籤。

    2.  在 [**指派的影像**] 欄位中，選取您所建立的 med-v 測試影像。 如果您的測試影像不在清單中，請**按一下 [** 重新整理]。

    3.  按一下工具列上的 [**儲存變更**]。

3.  設定要測試的任何其他 MED-V 工作區設定。 如需詳細資訊，請參閱設定[Med-v 工作區原則](configuring-med-v-workspace-policies.md)。

4.  啟動 MED-V-V 用戶端。

5.  在 [**確認執行測試**確認] 方塊中，按一下 [**使用測試影像**]。

6.  測試 MED-V 工作區測試影像。

    如需啟動和執行 MED-V 用戶端的相關資訊，請參閱[Med-v 用戶端作業](med-v-client-operations.md)。

**記事** 測試影像時，請不要開啟 VPC 並變更影像。

 

**記事** 測試影像時，不會將變更儲存至會話之間的影像;相反地，這些檔案是儲存在個別的臨時檔案中。 這是為了確保影像在生產環境中打包並執行時，它是原始的乾淨影像。

 

## 相關主題


[建立 MED-V 的虛擬電腦映像](creating-a-virtual-pc-image-for-med-v.md)

[建立 MED-V 工作區](creating-a-med-v-workspacemedv-10-sp1.md)

[設定 MED-V 工作區原則](configuring-med-v-workspace-policies.md)

[MED-V 用戶端操作](med-v-client-operations.md)

 

 





