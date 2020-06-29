---
title: 如何設定用戶端記錄檔
description: 如何設定用戶端記錄檔
author: dansimp
ms.assetid: dd79f8ce-61e2-4dc8-af03-2a353554a1b2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 729089d683c5d102eb7eb45314583023d3362639
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801561"
---
# 如何設定用戶端記錄檔


您可以使用下列程式來設定應用程式虛擬化（App-v）用戶端記錄檔。

**變更記錄檔的位置**

-   編輯下列登錄機碼值，以指定記錄檔的新路徑。 變更這個值之後，您必須重新開機**sftlist**服務。 您也可以在安裝後以互動方式變更這個位置。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogFileName

**變更記錄報告層級**

-   根據預設，寫入記錄的訊息類型包括嚴重等級4（資訊）或更高的所有事件。 嚴重度等級會儲存在下列金鑰值中。 將此金鑰值設為5，即可啟用詳細記錄。 在疑難排解期間，只要使用詳細記錄，就會產生大量的訊息，並導致記錄快速填入。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogMinSeverity

**變更記錄大小**

-   在應用程式虛擬化（App-v）4.5 中，記錄大小由下列登錄機碼值所控制。 此值預設為256MB，會定義在重設前，該記錄可能會增長的最大大小（以 MB 為單位）。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogMaxSize

    **小心** 此登錄機碼的值必須設定為大於零的值，才能確保記錄檔已重設。

     

**變更備份份數**

-   當記錄檔案達到最大大小時，當下次寫入記錄時，就會強制執行重設。 [重設] 會建立新的記錄檔案，而舊的檔案會重新命名為 [備份]。 下列登錄設定會控制當檔案重設時所保留的記錄檔備份複本數。 預設值為4。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogRolloverCount

    備份記錄檔案名的格式為： **sftlog\_YYYYMMDD\_hhmmss-uuu.txt** ，且以通用協調時間（UTC）為基礎，以重設時間為基礎。 下表列出建立檔案名及其描述時所使用的符號。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">符號</th>
    <th align="left">描述</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>年</p></td>
    <td align="left"><p>4位數年份</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>年</p></td>
    <td align="left"><p>2位數的月份（01-12）</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>DD</p></td>
    <td align="left"><p>月份中的第幾天（01到31）</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>hh</p></td>
    <td align="left"><p>小時（00–23）</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>年</p></td>
    <td align="left"><p>分鐘（00–59）</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>ss</p></td>
    <td align="left"><p>秒（00–59）</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>uuu</p></td>
    <td align="left"><p>毫秒（000至999）</p></td>
    </tr>
    </tbody>
    </table>

     

## 相關主題


[如何使用命令列設定 App-V 用戶端登錄設定](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





