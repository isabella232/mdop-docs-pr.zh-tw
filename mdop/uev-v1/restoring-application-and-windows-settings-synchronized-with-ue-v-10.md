---
title: 還原與 UE-V 1.0 同步的應用程式和 Windows 設定
description: 還原與 UE-V 1.0 同步的應用程式和 Windows 設定
author: dansimp
ms.assetid: 254a16b1-f186-44a4-8e22-49a4ee87c734
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 31ae83e0a44f98b66a9930f8c5db2231992a4700
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800078"
---
# 還原與 UE-V 1.0 同步的應用程式和 Windows 設定


Microsoft 使用者體驗虛擬化（UE-V）的 WMI 和 PowerShell 功能可讓您還原設定套件。 WMI 和 PowerShell 命令可讓您將應用程式和 Windows 設定還原為在安裝 UE-V Agent 之後第一次啟動應用程式時電腦上的設定值。 此還原動作是在每個應用程式或 Windows 設定基礎上執行。 下次執行應用程式時，或當使用者登入作業系統時，就會還原這些設定。

**使用 PowerShell 還原應用程式設定和 Windows 設定**

1.  開啟 [Windows PowerShell] 視窗。 若要匯入 Microsoft UE-V PowerShell 模組，請輸入下列命令：

    ``` syntax
    Import-module UEV
    ```

2.  輸入下列 PowerShell Cmdlet 來還原應用程式設定和 Windows 設定。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>PowerShell Cmdlet</strong></th>
    <th align="left"><strong>描述</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Restore-UevUserSetting</p></td>
    <td align="left"><p>還原應用程式的使用者設定或還原一組 Windows 設定</p></td>
    </tr>
    </tbody>
    </table>

     

**使用 WMI 來還原應用程式設定和 Windows 設定**

1.  開啟 PowerShell 視窗。

2.  輸入下列 WMI 命令來還原應用程式設定和 Windows 設定。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>WMI 命令</strong></th>
    <th align="left"><strong>描述</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>WmiMethod-命名空間 root\Microsoft\UEV-Class UserSettings-Name RestoreByTemplateId-ArgumentList &lt; template_ID&gt;</p></td>
    <td align="left"><p>還原應用程式的使用者設定或還原一組 Windows 設定</p></td>
    </tr>
    </tbody>
    </table>

     

## 相關主題


[管理 UE-V 1.0](administering-ue-v-10.md)

[UE-V 1.0 作業](operations-for-ue-v-10.md)

 

 





