---
title: 如何上傳 MED-V 映像至伺服器
description: 如何上傳 MED-V 映像至伺服器
author: dansimp
ms.assetid: 0e70dfdf-3e3a-4860-970c-535806caa907
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6703eb24bc3542c280af41988a257a2f14643645
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811313"
---
# 如何上傳 MED-V 映像至伺服器


測試完 MED-V 圖像之後，就可以將它打包，然後上傳到伺服器。 如需有關配置影像 Web 發佈伺服器的資訊，請參閱[如何設定影像 Web 發佈伺服器](how-to-configure-the-image-web-distribution-server.md)。

將 MED-V 影像打包並上傳到伺服器之後，就可以使用企業軟體發行中心將它發佈給使用者，或使用部署套件來供使用者下載。 如需使用企業軟體發行中心進行部署的詳細資訊，請參閱[使用企業軟體發佈系統部署 Med-v 工作區](deploying-a-med-v-workspace-using-an-enterprise-software-distribution-system.md)。 如需使用套件進行部署的相關資訊，請參閱[使用部署套件部署 Med-v 工作區](deploying-a-med-v-workspace-using-a-deployment-package.md)。

**注意**  
在上傳影像之前，請確認未在瀏覽器設定中定義網頁 proxy，且目前未執行 Windows Update。



**將 MED-V 影像上傳到伺服器**

1.  在 [**本機打包影像**] 窗格中，選取您建立的影像。

2.  按一下 **[上傳**]。

    圖像會上傳到伺服器。 這可能需要花費相當長的時間。

    伺服器上的影像是由下表所列的屬性所定義。

**在伺服器屬性上打包的影像**

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

[如何封裝 MED-V 映像](how-to-pack-a-med-v-image.md)









