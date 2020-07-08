---
title: 識別 MED-V 工作區的數量和類型
description: 識別 MED-V 工作區的數量和類型
author: dansimp
ms.assetid: 11642253-6b1f-4c4a-a11e-48d8a360e1ea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e0c9ed4b0ce92d0ca752525b847405bbce90a270
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812249"
---
# 識別 MED-V 工作區的數量和類型


MED-V 會建立虛擬環境，以執行需要 Windows XP 的應用程式，或需要與主機電腦上的版本不同的 Internet Explorer 版本。 這個虛擬環境稱為 MED-V 工作區。

根據您的組織在您遷移至 Windows 7 時所面臨的應用程式相容性需求而定，只有特定使用者或部門可能需要 MED-V 工作區。 規劃部署時，您必須判斷企業中所需的 MED-V 工作區數目。 您也必須定義每個 MED-V 工作區的需求。

## 識別 MED-V 工作區的數量與類型


找出您企業中將建立 MED-V 工作區的電腦和群組。 通常，這些使用者需要存取那些無法遷移至 Windows 7 的應用程式。 識別那些無法遷移的應用程式，以及需要 MED-V 工作區來執行這些應用程式的使用者。

您可能也有尚未針對 Windows 7 優化的 intranet 位址。 MED-V 工作區提供 Internet Explorer 瀏覽器，讓使用者可以更好地存取那些尚未準備好用於遷移至 Windows 7 的網址。 當您準備並規劃 MED-V 部署時，您必須先識別並編譯 URL 地址清單，才能從主機電腦上的 Internet Explorer 重新導向到 MED-V 工作區中的 Internet Explorer。

最後，您必須評估磁碟空間需求。 大多數的 MED-V 工作區都是 2 gb 或更大的。 系統上的可用磁碟空間可以快速消耗，視使用者數量和 MED-V 的設定而定。 此外，貴公司的喜好發佈方法也可能需要額外的空間。 一般來說，您應該為 MED-V 工作區釋放至少 10 GB 的磁碟空間，但視影像的大小而定，這會有很大的差異。

### 計算 MED-V 工作區的磁碟空間需求

MED-V 工作區需要記憶體及磁碟空間來自安裝它的主機。 主機上至少需要 2 GB 的磁碟空間。 磁碟空間是可變的，視使用者的 MED-V 工作區中的應用程式數和資料而定。

我們建議在 MED-V 中至少 10 GB 的磁碟空間。 這個數量允許基本的 Windows XP 工作區和一些基本安裝的應用程式和 web 重新導向。 它也會為主機交換磁碟機提供可用的空間。 在基本設定中，MED-V 與單一部署的 MED-V 工作區會使用最大6到 8 GB 的配置。 如果您在 MED-V 工作區包含許多應用程式，或是每個電腦都有一個以上的使用者，您可以使用下列計算來更精確地判斷您的 MED-V 工作區所需的磁碟空間：

*基本 VHD + （每個電腦的使用者 x （差異磁片 + 已儲存狀態））*

若要計算所需的磁碟空間，請判斷下列事項：

-   **基本 VHD 的大小**，即用來建立 med-v 工作區的虛擬硬碟。

    **重要** 請勿針對您的計算使用 medv 檔案大小，因為 medv 檔案已壓縮。

     

-   **每個電腦的使用者**-med-v 為電腦上的每位使用者建立 med-v 工作區。MED-V 工作區會在每個使用者登入時佔用磁碟空間，並建立 MED-V 工作區。

-   **差異磁片的大小**-用於追蹤與基礎 VHD 的差異。 當您將應用程式和軟體更新新增至虛擬硬碟時，此大小會有所不同。 第一次啟動 MED-V 時，會為每個 MED-V 使用者建立差異磁片。

-   **已儲存狀態**檔案的大小-用來維護虛擬機器中的狀態。 一般來說，這只會比虛擬機器的已分配 RAM 稍大一些。 例如，已分配的 1 GB RAM 會建立大約 1081000 KB 的檔案。

下列範例顯示一個根據 MED-V 工作區中的三個使用者（具有 2.6 GB 虛擬硬碟）來進行的計算：

*2.6 gb + （3 x （1.5 gb + 1gb）） = 10.1 gb*

**記事** MED-V 最佳做法是使用實驗式部署來驗證需求，以計算所需的空間。

 

### 找出檔案以判斷檔案大小

下列位置包含電腦和使用者設定的檔案：

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">類型</th>
<th align="left">位置</th>
<th align="left">檔案</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>基本 VHD</p></td>
<td align="left"><p>%ProgramData%\Microsoft\Medv\Workspace</p></td>
<td align="left"><p><em>InternalName </em> （.vhd）-其中 <em> InternalName </em> 是您在 Med-v 工作區包裝程式中選取的虛擬硬碟名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>差異磁片</p></td>
<td align="left"><p>%LocalAppData%\Microsoft\MEDV\v2\Virtual 電腦</p></td>
<td align="left"><p><em>WorkspaceName </em></p></td>
</tr>
<tr class="odd">
<td align="left"><p>已儲存狀態檔案</p></td>
<td align="left"><p>%LocalAppData%\Microsoft\MEDV\v2\Virtual 電腦</p></td>
<td align="left"><p><em>WorkspaceName </em> . vsv</p></td>
</tr>
</tbody>
</table>

 

### 計算共用 MED-V 工作區的磁碟空間需求

如果您是在一部電腦上計算共用的 MED-V 工作區部署，則計算中的每個電腦使用者數永遠都是 "1"，因為 MED-V 只會針對所有使用者設定單一差異磁片。

您可以在%ProgramData%\\Microsoft\\Medv\\AllUsers. 中找到差異磁片與共享 MED-V 工作區的已儲存狀態檔案

## 相關主題


[定義和規劃 MED-V 部署](define-and-plan-your-med-v-deployment.md)

[規劃 MED-V](planning-for-med-v.md)

 

 





