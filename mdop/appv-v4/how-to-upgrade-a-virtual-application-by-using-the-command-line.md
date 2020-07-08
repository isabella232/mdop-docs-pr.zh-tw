---
title: 如何使用命令列升級虛擬應用程式
description: 如何使用命令列升級虛擬應用程式
author: dansimp
ms.assetid: 83c97767-6ea1-42aa-b411-ccc9fa61cf81
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8612deb31a1692dd85cfee88ca4b18cbc5ac2ab2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801026"
---
# 如何使用命令列升級虛擬應用程式


使用下列程式，使用命令列來升級虛擬應用程式。

**若要升級虛擬應用程式**

1.  在執行應用程式虛擬化（App-v） Sequencer 的電腦上，若要開啟命令提示字元，請選取 [**開始**]、[**執行**]，然後輸入**cmd**。 按一下 \[確定\] ****。

2.  在命令提示字元中，指定安裝 App-v 排序器的位置。 例如，在命令提示字元中，您可以輸入下列內容： **cd C:\\program files Files\\Microsoft Application Virtualization 排序**器。

3.  在命令提示字元中，輸入下列命令，並使用您的值取代引號中的文字：

    `SFTSequencer /UPGRADE:"pathtosourceSPRJ" /INSTALLPACKAGE:"pathtoUpgradeInstaller" /DECODEPATH:"pathtodecodefolder" /OUTPUTFILE:"pathtodestinationSPRJ"`

    **注意**  
    您可以根據您所升級之應用程式的複雜性，使用命令列來指定其他參數。 如需可與 App-v 排序器搭配使用的完整參數清單，請參閱[Sequencer 命令列參數](sequencer-command-line-parameters.md)。



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
<td align="left"><p><em>pathtosourceSPRJ</em></p></td>
<td align="left"><p>Specifies the directory location of the virtual application to be upgraded.</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>pathtoUpgradeInstaller</em></p></td>
<td align="left"><p>Specifies the Windows Installer or a batch file that will be used to install an upgrade to the application.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>pathtodecodefolder</em></p></td>
<td align="left"><p>Specify the directory in which to unpack the SFT file.</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>pathtodestinationSPRJ</em></p></td>
<td align="left"><p>Specifies the path and file name of the SPRJ file that will be created.</p></td>
</tr>
</tbody>
</table>
~~~



4. 按**enter**。

## 相關主題


[如何使用 App-v 排序器建立或升級虛擬應用程式](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)

[排序器命令列錯誤碼](sequencer-command-line-error-codes.md)

[排序器命令列參數](sequencer-command-line-parameters.md)









