---
title: 關於連線群組虛擬環境
description: 關於連線群組虛擬環境
author: dansimp
ms.assetid: 535fa640-cbd9-425e-8437-94650a70c264
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2bd93c9e7acbf7bbf3f9da506d5d95b8df09e1f1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800711"
---
# 關於連線群組虛擬環境


**本主題內容如下：**

-   [如何決定封裝優先順序](#bkmk-pkg-priority-deter)

-   [將相同的套件路徑合併成連接群組中的一個虛擬目錄](#bkmk-merged-root-ve-exp)

## <a href="" id="bkmk-pkg-priority-deter"></a>如何決定封裝優先順序


虛擬環境及其目前狀態會與連線群組相關聯，而不會與個別套件建立關聯。 如果從連線群組中移除 App-v 套件，則在連線群組中存在的狀態將不會與套件一起遷移。

如果同一個套件是兩個不同連線群組的一部分，您必須指出應該使用哪個連線群組 App。 例如，您可能會在連線群組中有兩個套件，每個套件都定義相同的登錄 DWORD 值。

所使用的連線群組是依據套件在**AppConnectionGroup** XML 檔中出現的順序所決定：

-   第一個套件的優先順序最高。

-   第二個套件的優先順序最高。

請考慮下列範例區段：

```xml
<appv:Packages><appv:PackagePackageId="A8731008-4523-4713-83A4-CD1363907160"VersionId="E889951B-7F30-418B-A69C-B37283BC0DB9"/><appv:PackagePackageId="1DC709C8-309F-4AB4-BD47-F75926D04276"VersionId="01F1943B-C778-40AD-BFAD-AC34A695DF3C"/><appv:PackagePackageId="04220DCA-EE77-42BE-A9F5-96FD8E8593F2"VersionId="E15EFFE9-043D-4C01-BC52-AD2BD1E8BAFA"/></appv:Packages>
```

假設在第一個和第三個套件中定義了相同的 DWORD 值 ABC （HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region），例如：

-   套件1（A8731008-4523-4713-83A4-CD1363907160）： HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region = 5

-   套件3（04220DCA-EE77-42BE-A9F5-96FD8E8593F2）： HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region = 10

由於套件1會先出現，所以 AppConnectionGroup 的虛擬環境會將單一 DWORD 值為5（HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region = 5）。 這表示套件1、套件2和套件3中的虛擬應用程式在查詢 HKEY \ _LOCAL 時，會看到值 5 _MACHINE \\software\\contoso\\finapp\\region。

其他虛擬環境資源的解決方式類似，但一般情況下，會發生衝突。

## <a href="" id="bkmk-merged-root-ve-exp"></a>將相同的套件路徑合併成連接群組中的一個虛擬目錄


如果連線群組中有兩個以上的套件包含完全相同的目錄路徑，則會將這些路徑合併到連線群組虛擬環境內的單一虛擬目錄中。 這種路徑合併可讓一個套件中的應用程式存取不同套件中的檔案。

當您從連線群組中移除套件時，已移除套件中的應用程式將無法再存取連線群組中其餘套件中的檔案。

App V 在連線群組中尋找檔案名稱的順序，是由在連線群組資訊清單檔案中所列的 app-v 套件順序來指定。

下列範例顯示 [**封裝 a** ] 與 [**封裝 B**] 的 [連線] 群組中的檔案名查閱順序與關聯性。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">封裝 A</th>
<th align="left">套件 B</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>C:\Windows\System32</p></td>
<td align="left"><p>C:\Windows\System32</p></td>
</tr>
<tr class="even">
<td align="left"><p>C:\AppTest</p></td>
<td align="left"><p>C:\AppTest</p></td>
</tr>
</tbody>
</table>

 

在上述範例中，當虛擬化的應用程式嘗試尋找特定檔案時，會先搜尋封裝 A，以取得相符的檔案路徑。 如果找不到相符路徑，則會使用下列對應規則搜尋封裝 B：

-   如果在兩個應用程式套件的同一個虛擬資料夾階層中都存在名為**test.txt**的檔案，則會使用第一個相符的檔案。

-   如果一個名為**bar.txt**的檔案存在於一個應用程式套件的虛擬資料夾階層中，而不在另一個，則會使用第一個相符的檔案。






## 相關主題


[管理連線群組](managing-connection-groups.md)

 

 





