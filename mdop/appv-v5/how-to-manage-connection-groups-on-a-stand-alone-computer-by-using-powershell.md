---
title: 如何使用 PowerShell 來管理獨立電腦上的連線群組
description: 如何使用 PowerShell 來管理獨立電腦上的連線群組
author: dansimp
ms.assetid: b73ae74d-8a6f-4bb3-b1f2-0067c7bd5212
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 32dd4f9c5ad1ba4ae9e25246d5ec52a6363ef303
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800465"
---
# 如何使用 PowerShell 來管理獨立電腦上的連線群組


App-v 連線群組可讓您在單一虛擬環境中，以一組已定義套件的形式來執行所有虛擬應用程式。 例如，您可以使用個別的套件，將應用程式及其外掛程式虛擬化，但在單一連線群組中一起執行。

連線群組 XML 檔案會定義在您已安裝 App-v 用戶端的電腦上執行的連線群組。 如需連線群組 XML 檔案及其設定方式的相關資訊，請參閱[關於連線群組](about-the-connection-group-file.md)檔案。

本主題說明下列程式：

-   [在連線群組中新增併發布 App-v 套件](#bkmk-add-pub-pkgs-in-cg)

-   [在 App-V 用戶端上新增並啟用 [連線] 群組](#bkmk-add-enable-cg-on-clt)

-   [啟用或停用特定使用者的連線群組](#bkmk-enable-cg-for-user-poshtopic)

-   [僅允許系統管理員啟用連線群組](#bkmk-admin-only-posh-topic-cg)

<a href="" id="bkmk-add-pub-pkgs-in-cg"></a>**在連線群組中新增併發布 App-v 套件**

1.  若要在執行 App-v 用戶端的電腦上新增併發布 App-v 5.0 套件，請輸入下列命令：

    AppvClientPackage – path c:\\tmpstore\\quartfin.appv |發佈-AppvClientPackage

2.  針對連接群組中的每個套件，重複執行此程式的**步驟 1** 。

<a href="" id="bkmk-add-enable-cg-on-clt"></a>**在 App-V 用戶端上新增並啟用 [連線] 群組**

1.  輸入下列命令以新增 [連線] 群組：

    AppvClientConnectionGroup – path c:\\tmpstore\\financ.xml

2.  輸入下列命令以啟用 [連接] 群組：

    Enable-AppvClientConnectionGroup – name "財務應用程式"

    當成員套件中的任何虛擬應用程式都在目的電腦上執行時，它們會在連線到連線群組的虛擬環境中執行，並將提供給連線群組中其他套件中的所有虛擬應用程式。

<a href="" id="bkmk-enable-cg-for-user-poshtopic"></a>**啟用或停用特定使用者的連線群組**

1.  查看參數描述與需求：

    -   此參數可讓系統管理員啟用或停用特定使用者的連線群組。

    -   您必須使用 App-v 5.0 SP2 修補程式套件5或更新版本，才能使用這個參數。

    -   您可以從使用者或系統管理員會話執行此 Cmdlet。

    -   您必須以管理認證登入，才能使用此參數。

    -   最終使用者必須登入。

    -   您必須提供最終使用者的安全識別碼（SID）。

2.  使用下列 Cmdlet，並新增選擇性 **– UserSID**參數，其中 **-UserSID**代表最終使用者的安全性識別碼（SID）：

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">Cmdlet</th>
    <th align="left">範例</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Enable-AppVClientConnectionGroup</p></td>
    <td align="left"><p>Enable-AppVClientConnectionGroup "ConnectionGroupA"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Disable-AppVClientConnectionGroup</p></td>
    <td align="left"><p>Disable-AppVClientConnectionGroup "ConnectionGroupA"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</p></td>
    </tr>
    </tbody>
    </table>

<a href="" id="bkmk-admin-only-posh-topic-cg"></a>**僅允許系統管理員啟用連線群組**

1.  請參閱使用此 Cmdlet 的描述與需求：

    -   使用這個 Cmdlet 和參數設定 App-v 用戶端，只允許系統管理員（而非最終使用者）啟用或停用連線群組。

    -   您必須至少使用 App-v 5.0 SP3，才能使用此 Cmdlet。

2.  執行下列 Cmdlet 和參數：

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">Cmdlet</th>
    <th align="left">參數和值</th>
    <th align="left">範例</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Set-AppvClientConfiguration</p></td>
    <td align="left"><p>–RequirePublishAsAdmin</p>
    <ul>
    <li><p>0-False</p></li>
    <li><p>1-True</p></li>
    </ul></td>
    <td align="left"><p>Set-AppvClientConfiguration – RequirePublishAsAdmin1</p></td>
    </tr>
    </tbody>
    </table>

    您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[App-V 5.0 作業](operations-for-app-v-50.md)

[使用 PowerShell 管理 App-V](administering-app-v-by-using-powershell.md)

 

 





