---
title: 如何使用 SQL 指令碼部署 App-V 資料庫
description: 如何使用 SQL 指令碼部署 App-V 資料庫
author: dansimp
ms.assetid: 23637936-475f-4ca5-adde-76bb27d2372b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 511d1020571eead25af9e9591fe1834a9f97f068
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800512"
---
# 如何使用 SQL 指令碼部署 App-V 資料庫


使用下列指示來使用 SQL 腳本（而不是 Windows 安裝程式）來執行下列作業：

-   安裝 App-v 5.0 資料庫

-   將5.0 資料庫升級為較新的版本

**如何使用 SQL 腳本來安裝 App-v 資料庫**

1. 在您安裝資料庫腳本之前，請先查看並保留 App-v 授權條款的複本。 透過執行資料庫腳本，您即已同意授權條款。 如果您不接受，請不要使用這個軟體。

2. 將**appv\_server\_setup.exe**從 app-v 版本媒體複製到臨時位置。

3. 從命令提示字元執行**appv\_server\_setup.exe** ，並指定解壓縮資料庫腳本的臨時位置。

   範例： appv\_server\_setup.exe/layout c:\\ &lt; 臨時位置路徑&gt;

4. 流覽至您建立的臨時位置，開啟 [提取的**DatabaseScripts** ] 資料夾，然後查看適當的 Readme.txt 檔案以取得相關指示：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">資料庫</th>
   <th align="left">要使用 Readme.txt 檔案的位置</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>管理資料庫</p></td>
   <td align="left"><p>ManagementDatabase 子資料夾</p>
   <div class="alert">
   <strong>重要</strong><br/><p>如果您要升級到或安裝應用程式-V 5.0 SP3 管理資料庫，請參閱 <a href="https://support.microsoft.com/kb/3031340" data-raw-source="[SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail](https://support.microsoft.com/kb/3031340)"> 安裝或升級 app-v 5.0 Sp3 管理伺服器資料庫的 SQL 腳本失敗 </a> 。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p>報表資料庫</p></td>
   <td align="left"><p>ReportingDatabase 子資料夾</p></td>
   </tr>
   </tbody>
   </table>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 相關主題


[部署 App-V 5.0 伺服器](deploying-the-app-v-50-server.md)

[如何部署 App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)









