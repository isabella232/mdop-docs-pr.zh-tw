---
title: 如何將伺服器設定成受信任可以委派
description: 如何將伺服器設定成受信任可以委派
author: dansimp
ms.assetid: d8d11588-17c0-4bcb-a7e6-86b5e4ba7e1c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7164b3046671853216b870d68e651fed4fd84695
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801541"
---
# 如何將伺服器設定成受信任可以委派


當您安裝 Microsoft Application Virtualization （App-v）管理伺服器軟體時，您可以選擇使用分散式系統架構來安裝它。 如果您在不同的電腦上安裝主控台、管理 Web 服務和資料庫，您必須將網際網路資訊服務（IIS）伺服器設定為信任委派。 這是必要的，因為管理 Web 服務會使用使用主機的 App-v 管理員認證，嘗試連線到 App-v 資料存放區。 安裝資料存放區的資料庫伺服器不會接受來自 IIS 伺服器的系統管理員認證，除非已將 IIS 伺服器設定為信任委派，且管理 Web 服務將無法連線到 App-v 資料儲存區。

**記事** 如果您在單一伺服器上安裝 App-v Management Server 軟體，並將資料存放區放在另一個伺服器上，則有一個情況是您仍必須將伺服器設定為信任委派，即使管理 Web 服務與管理主控台位於相同的伺服器上也一樣。 如果您需要使用 [**使用替代認證**] 選項連線到主控台中的管理 Web 服務，就會發生這種情況。

 

您可以使用的委派類型，取決於您在 Active Directory 網域服務（新增）基礎結構中設定的網域功能層級。 下表列出可針對 App-v 的每個網域功能層級設定的委派類型。 表格後面的詳細指示。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">網域功能層級</th>
<th align="left">提供委派層次</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows 2000 原生</p></td>
<td align="left"><ul>
<li><p>無委派（預設）</p></li>
<li><p>無限制委派</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2003、Windows Server 2008 或 Windows Server 2008 R2</p></td>
<td align="left"><ul>
<li><p>無委派（預設）</p></li>
<li><p>無限制的委派¹</p></li>
<li><p>受限制的委派（使用 Kerberos 專用通訊協定）</p></li>
<li><p>受限制的委派（使用任何驗證通訊協定）¹</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

¹不要使用。

## 若要在網域功能層級為 Windows 2000 原生時設定無限制的委派


在您的 Web 服務器網域的網網域控制站上，完成下列步驟。

****

1.  按一下 [**開始**]、[系統**管理工具**]，然後按一下 [ **Active Directory 使用者和電腦**]。

2.  展開 [網域]，然後展開 [電腦] 資料夾。

3.  在右窗格中，以滑鼠右鍵按一下網頁伺服器的電腦名稱稱，然後按一下 [**屬性**]。

4.  在 [**一般**] 索引標籤上，確認已選取 [**信任電腦以進行委派**] 核取方塊。

5.  按一下 \[確定\] ****。

## 若要在網域功能層級為 Windows Server 2003、Windows Server 2008 或 Windows Server 2008 R2 時設定無限制的委派


在您的 Web 服務器網域的網網域控制站上，完成下列步驟。

****

1.  按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **Active Directory 使用者和電腦**]。

2.  展開 [網域]，然後展開 [電腦] 資料夾。

3.  在右窗格中，以滑鼠右鍵按一下網頁伺服器的電腦名稱稱，選取 [**屬性**]，然後按一下 [**委派**] 索引標籤。

4.  按一下以選取 **[信任此電腦以委派給任何服務（僅限 Kerberos）**]。

5.  按一下 \[確定\] ****。

## 若要在網域功能層級為 Windows Server 2003、Windows Server 2008 或 Windows Server 2008 R2 時設定受限制的委派


在您的 Web 服務器網域的網網域控制站上，完成下列步驟。

****

1.  按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **Active Directory 使用者和電腦**]。

2.  展開 [網域]，然後展開 [電腦] 資料夾。

3.  在右窗格中，以滑鼠右鍵按一下網頁伺服器的電腦名稱稱，選取 [**屬性**]，然後按一下 [**委派**] 索引標籤。

4.  按一下以選取 [**信任此電腦只委派指定的服務**]。

5.  確定已選取 [**僅使用 Kerberos** ]，然後按一下 **[確定]**。

6.  按一下 [**新增**] 按鈕。 在 [**新增服務**] 對話方塊中，按一下 [**使用者或電腦**]，然後流覽至或輸入含有 app-v 資料存放區之 Microsoft SQL server 的名稱，然後從 IIS 接收使用者認證。 按一下 \[確定\] ****。

7.  在 [**可用的服務**] 清單中，選取列出埠號碼的 MSSQLSvc 服務，Microsoft SQL Server 會接受該埠編號（預設埠為1433）。 按一下 \[確定\] ****。

### 針對受限制委派設定 IIS 7 的其他步驟

如果您在 IIS 7 伺服器上執行管理 Web 服務，您必須完成下列步驟，才能將 IIS 7 *useAppPoolCredentials*變數設定為 True。

1.  開啟提升許可權的命令提示字元視窗。 若要開啟提升許可權的命令提示字元視窗，請按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**附件**]，以滑鼠右鍵按一下**命令提示**字元，然後按一下 [**以系統管理員**身分

2.  流覽至%windir%\\system32\\inetsrv。

3.  輸入**appcmd.exe 設定 config-section： system.webserver/security/authentication/windowsAuthentication-useAppPoolCredentials： true**，然後按 enter。

 

 





