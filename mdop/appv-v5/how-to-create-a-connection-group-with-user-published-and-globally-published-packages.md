---
title: 如何以使用者發佈的套件與全域發佈的套件建立連線群組
description: 如何以使用者發佈的套件與全域發佈的套件建立連線群組
author: dansimp
ms.assetid: 82f7ea7f-7b14-4506-8940-fdcd6c3e117f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: c98981180133881909db17d19cb42771f94bd66a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800572"
---
# 如何以使用者發佈的套件與全域發佈的套件建立連線群組
您可以使用下列其中一種方法，建立包含使用者發佈與全域發佈套件的使用者擁有資格的連接群組：

-   [如何使用 PowerShell Cmdlet 來建立使用者擁有資格的連線群組](#bkmk-posh-userentitled-cg)

-   [如何使用 App-v Server 來建立使用者擁有資格的連線群組](#bkmk-appvserver-userentitled-cg)

**開始之前的須知：**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">不支援的案例和可能的問題</th>
<th align="left">結果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>您不能在全域名為 [連線群組] 中包含使用者發佈的套件。</p></td>
<td align="left"><p>[連接] 群組將會失敗。</p></td>
</tr>
<tr class="even">
<td align="left"><p>如果您要全域發佈套件，然後建立使用者發佈的連線群組（您已將該套件設為非選用），您仍然可以執行 <strong> 取消發佈-AppvClientPackage &lt; 套件 &gt; -global </strong> 以取消發佈套件，即使該套件是在另一個連線群組中使用時也一樣。</p></td>
<td align="left"><p>如果有任何其他的連線群組正在使用該套件，則這些連線群組中的套件將會失敗。</p>
<p>為了避免無意間取消發佈其他連線群組中使用的非選用套件，我們建議您追蹤已使用非選用套件的連線群組。</p></td>
</tr>
</tbody>
</table>

 
<a href="" id="bkmk-posh-userentitled-cg"></a>**如何使用 PowerShell Cmdlet 來建立使用者擁有資格的連線群組**

1.  使用下列命令新增及發佈套件：

    **AppvClientPackage Package1 \ _AppV _file \ _Path**

    **AppvClientPackage Package2 \ _AppV _file \ _Path**

    **Publish-AppvClientPackage-PackageId Package1 \ _ID VersionId Package1 \ _Version 識別碼-全域**

    **Publish-AppvClientPackage-PackageId Package2 \ _ID-VersionIdPackage2 \ _ID**

2.  建立連線群組 XML 檔案。 如需詳細資訊，請參閱[關於連線群組](about-the-connection-group-file.md)檔案。

3.  使用下列命令新增及發佈 [連線] 群組：

    **載入 AppvClientConnectionGroup 連線 _Group \ _XML \ _file \ _Path**

    **Enable-AppvClientConnectionGroup-GroupId CG \ _Group \ _ID VersionId CG \ _Version \ _ID**

<a href="" id="bkmk-appvserver-userentitled-cg"></a>**如何使用 App-v Server 來建立使用者擁有資格的連線群組**

1.  開啟 App-V 5.0 管理主控台。

2.  請依照[如何使用管理主控台](how-to-publish-a-package-by-using-the-management-console-50.md)來將套件發佈至全域及使用者的方式，按照如何發佈套件的指示進行。

3.  依照[如何建立連線群組](how-to-create-a-connection-group.md)以建立連線群組，以及新增使用者發佈及全域發佈的套件中的指示進行。

    您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[管理連線群組](managing-connection-groups.md)

[如何在連線群組中使用選用套件](how-to-use-optional-packages-in-connection-groups.md)

 

 





