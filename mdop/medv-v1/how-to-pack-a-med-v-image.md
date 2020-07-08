---
title: 如何封裝 MED-V 映像
description: 如何封裝 MED-V 映像
author: dansimp
ms.assetid: e1ce2307-0f1b-4bf8-b146-e4012dc138d2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0a330b8feca922239691bed083767c3acc57105d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810700"
---
# 如何封裝 MED-V 映像


必須先將 MED-V 影像打包，然後才能將它新增到部署套件或上傳到伺服器。

**建立打包的 MED-V 影像**

1.  按一下 [**影像**管理] 按鈕。

2.  在 [**影像**] 模組中，按一下 [**本機打包影像**] 窗格中的 [**新增**]。

3.  在 [**打包影像建立**] 對話方塊中，執行下列其中一項動作來選取虛擬機器影像：

    -   在 [**基底圖像**檔案] 欄位中，輸入為 med-v 準備的 MICROSOFT Virtual 電腦影像準備的目錄完整路徑。

    -   按一下 **[流覽**]，流覽至準備 Med-v-V 的 MICROSOFT Virtual 電腦影像所在的目錄。

4.  您可以執行下列其中一項動作，以指定新影像的名稱：

    -   在 [**影像名稱**] 欄位中，輸入想要的名稱。

        **注意**  
        下列字元不能包含在影像名稱中： space " &lt; &gt; |\\ / : \* ?



~~~
    A new packed image will be created.

-   From the drop-down list, select an existing name.

    A new version of the existing image will be created.
~~~

5. 按一下 \[確定\] ****。

   您的主機電腦上會建立新的 MED-V 封裝影像，其屬性在下表中定義。

**注意**  
在**本機打包的影像**和**伺服器窗格上打包的影像**中，每個影像的最新版本都會顯示為父節點。 按一下父節點，以查看所有其他現有的圖像版本。



**本機打包的影像屬性**

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
<td align="left"><p>在管理員建立影像時所定義之打包影像的名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>版本</p></td>
<td align="left"><p>所顯示影像的版本。</p>
<div class="alert">
<strong>注意</strong><br/><p>除非刪除，否則所有先前的版本都會保留。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>檔案大小（壓縮）</p></td>
<td align="left"><p>影像的實際壓縮大小。</p></td>
</tr>
<tr class="even">
<td align="left"><p>影像大小（未壓縮）</p></td>
<td align="left"><p>影像的實際未壓縮大小。</p></td>
</tr>
</tbody>
</table>



## 相關主題


[如何安裝 MED-V 用戶端及 MED-V 管理主控台](how-to-install-med-v-client-and-med-v-management-console.md)

[使用 MED-V 管理主控台使用者介面](using-the-med-v-management-console-user-interface.md)

[建立 MED-V 的虛擬電腦映像](creating-a-virtual-pc-image-for-med-v.md)









