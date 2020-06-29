---
title: 如何使用電子軟體發佈來部署 App-V 5.1 封裝
description: 如何使用電子軟體發佈來部署 App-V 5.1 封裝
author: dansimp
ms.assetid: e1957a5a-1f18-42da-b2c1-a5ae5a4cca7a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a9ed5fbb264f8fb9676d7fa18fe4de8019ea8e79
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800530"
---
# 如何使用電子軟體發佈來部署 App-V 5.1 封裝


您可以使用電子軟體發佈（ESD）系統，將 App-v 5.1 虛擬應用程式部署到 App-v 用戶端。 如需詳細資訊，請參閱您使用的 ESD 提供的說明文件。

如需元件需求，以及使用 ESD 來部署 app-v 套件的選項，請參閱[規劃以使用電子軟體發佈系統部署 app-v 5.1](planning-to-deploy-app-v-51-with-an-electronic-software-distribution-system.md)。

使用下列其中一種方法，將套件發佈至有 ESD 的 App-v 用戶端電腦：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>協力廠商 ESD 提供的功能</p></td>
<td align="left"><p>使用協力廠商 ESD 中的功能。</p></td>
</tr>
<tr class="even">
<td align="left"><p>獨立 Windows 安裝程式</p></td>
<td align="left"><p>在目標用戶端電腦上，使用您最初為應用程式排序時所建立的關聯 Windows 安裝程式（.msi）檔案，在目標用戶端電腦上安裝應用程式。 Windows Installer 檔案包含相關聯的 App-v 5.1 套件檔案資訊，用於設定套件，並將所需的套件檔案複製到用戶端。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>PowerShell</p></td>
<td align="left"><p>使用 PowerShell Cmdlet 來部署虛擬化的應用程式。 如需有關使用 PowerShell 與 App-v 5.1 的詳細資訊，請參閱 <a href="administering-app-v-51-by-using-powershell.md" data-raw-source="[Administering App-V 5.1 by Using PowerShell](administering-app-v-51-by-using-powershell.md)"> 使用 powershell 管理 app-v 5.1 </a> 。</p></td>
</tr>
</tbody>
</table>

 

**使用 ESD 部署 app-v 5.1 套件**

1.  在您的環境中的電腦上安裝 app-v 5.1 排序器。 如需安裝排序器的詳細資訊，請參閱[如何安裝排序](how-to-install-the-sequencer-51beta-gb18030.md)器。

2.  使用 App-v 5.1 Sequencer 來建立虛擬應用程式。 如需建立虛擬應用程式的相關資訊，請參閱[建立及管理 app-v 5.1 虛擬化應用程式](creating-and-managing-app-v-51-virtualized-applications.md)。

3.  建立虛擬應用程式之後，請使用您的 ESD 方案部署套件。

    如果您使用的是 System Center Configuration Manager，請先查看[Configuration Manager 中的應用程式管理簡介](https://go.microsoft.com/fwlink/?LinkId=281816)，以取得使用 app-v 5.1 和 System Center2012 Configuration Manager 的相關資訊。

    您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[App-V 5.1 作業](operations-for-app-v-51.md)

 

 





