---
title: 如何使用命令列來排列新應用程式的順序
description: 如何使用命令列來排列新應用程式的順序
author: dansimp
ms.assetid: de72912b-d9e7-45b5-a601-12528f1a4cac
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2dd638a7e4765cedbf1d8050626fb8cc54b2ce8b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801113"
---
# 如何使用命令列來排列新應用程式的順序


您可以使用命令列來排序新的應用程式。 當您必須建立大量的虛擬應用程式，或需要定期建立順序化的應用程式時，使用命令列很有用。

**重要**  
[命令列順序] 只允許預設排序。 如果您需要變更您要排序之應用程式的預設安裝設定，您必須手動修改虛擬應用程式，或使用應用程式虛擬化（App-v） Sequencer 來更新虛擬應用程式。 如需使用 App-v 排序器更新虛擬應用程式的詳細資訊，請參閱[如何升級現有的虛擬應用程式](how-to-upgrade-an-existing-virtual-application.md)。



使用下列程式，使用命令列來建立虛擬應用程式。

**使用命令列來排序應用程式**

1.  在執行 App-v 排序器的電腦上，選取 [**開始**]、[**執行**]，然後輸入**cmd**來開啟命令提示字元。 按一下 \[確定\] ****。

2.  使用命令提示字元指定 App V 排序器的安裝位置。 例如，在命令提示字元中，您可以輸入下列內容： **cd C:\\program files Files\\Microsoft Application Virtualization 排序**器。

3.  在命令提示字元中，輸入下列命令，並使用您的值取代引號中的文字：

    `SFTSequencer /INSTALLPACKAGE:"pathtoMSI" /INSTALLPATH:"pathtopackageroot" /OUTPUTFILE:"pathtodestinationSPRJ"`

    **注意**  
    您可以使用命令列來指定其他參數，這取決於您所排序的應用程式的複雜性。 如需可與 App-v 排序器搭配使用的完整參數清單，請參閱[Application Virtualization Sequencer 命令列](application-virtualization-sequencer-command-line.md)。



~~~
Use the value descriptions in the following table to help you determine the actual text you will use in the preceding command.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Value</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><em>pathtoMSI</em></p></td>
<td align="left"><p>Specifies the Windows Installer or a batch file that will be used to install an application so that it can be sequenced.</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>pathtopackageroot</em></p></td>
<td align="left"><p>Specifies the package root directory.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>pathtodestinationSPRJ</em></p></td>
<td align="left"><p>Specifies the path and file name of the SPRJ file that will be created.</p></td>
</tr>
</tbody>
</table>
~~~



4. 按**enter**。

## 相關主題


[如何使用命令列管理虛擬應用程式](how-to-manage-virtual-applications-using-the-command-line.md)









