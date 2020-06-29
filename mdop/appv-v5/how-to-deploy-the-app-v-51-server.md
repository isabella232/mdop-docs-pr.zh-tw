---
title: 如何部署 App-V 5.1 Server
description: 如何部署 App-V 5.1 Server
author: dansimp
ms.assetid: 4729beda-b98f-481b-ae74-ad71c59b1d69
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4a367be7db4cea1835124657dbdfa3375474228e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800517"
---
# 如何部署 App-V 5.1 Server


使用下列程式來安裝 Microsoft Application Virtualization （App-v） 5.1 server。 如需有關部署 App-v 5.1 Server 的資訊，請參閱[關於 app-v 5.1](about-app-v-51.md#bkmk-migrate-to-51)。

**開始之前：**

-   確定您已安裝必備軟體。 請參閱[App-V 5.1 先決條件](app-v-51-prerequisites.md)。

-   請參閱[應用程式 V 5.1 安全性考慮](app-v-51-security-considerations.md)的伺服器區段。

-   指定將託管每個元件的埠。

-   新增防火牆規則，以允許傳入要求存取指定的埠。

-   如果您使用 SQL 腳本（而不是 Windows 安裝程式）來設定管理資料庫或報表資料庫，您必須先執行 SQL 腳本，然後才能安裝管理伺服器或報表伺服器。 瞭解[如何使用 SQL 腳本部署 App-v 資料庫](how-to-deploy-the-app-v-databases-by-using-sql-scripts51.md)。

**若要安裝應用程式-V 5.1 伺服器**

1. 將 App-v 5.1 server 安裝檔案複製到您要安裝它的電腦上。

2. 以管理員身分按一下並執行**appv\_server\_setup.exe** ，然後按一下 [**安裝**]，啟動 App V 5.1 伺服器的安裝。

3. 查看並接受授權條款，並選擇是否要啟用 Microsoft 更新。

4. 在 [**功能選取**] 頁面上，選取 [下列所有元件]。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">元件</th>
   <th align="left">說明</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>管理伺服器</p></td>
   <td align="left"><p>提供 App-v 基礎結構的整體管理功能。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>管理資料庫</p></td>
   <td align="left"><p>協助 App-v 管理的資料庫 predeployments。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>發佈伺服器</p></td>
   <td align="left"><p>提供虛擬應用程式的託管與流式處理功能。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>報表伺服器</p></td>
   <td align="left"><p>提供 App-v 5.1 reporting services。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>報表資料庫</p></td>
   <td align="left"><p>協助 App-v 報告的資料庫 predeployments。</p></td>
   </tr>
   </tbody>
   </table>

     

5. 在 [**安裝位置**] 頁面上，接受要安裝所選元件的預設位置，或在 [**安裝位置**] 行上輸入新路徑來變更位置。

6. 在初始 [**建立新的管理資料庫**] 頁面上，選取下列適當的選項，以設定**Microsoft SQL Server 實例**與**管理伺服器資料庫**。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">方法</th>
   <th align="left">您需要執行的動作</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>您使用的是自訂的 Microsoft SQL Server 實例。</p></td>
   <td align="left"><p>選取 <strong> [使用自訂實例] </strong> ，然後輸入實例的名稱。</p>
   <p>使用格式 <strong> INSTANCENAME </strong> 。 假設的安裝位置是本機電腦。</p>
   <p>不支援：使用格式 <strong> ServerName </strong> &lt; 強 &gt; 實例的伺服器名稱 </strong> 。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>您使用的是自訂資料庫名稱。</p></td>
   <td align="left"><p>選取 <strong> [自訂設定] </strong> ，然後輸入資料庫的名稱。</p>
   <p>資料庫名稱必須是唯一的，否則安裝將會失敗。</p></td>
   </tr>
   </tbody>
   </table>

     

7. 在 [**設定**] 頁面上，接受 [**使用此本機電腦**的預設值]。

   **注意**  
   如果您要並排安裝管理伺服器與管理資料庫，此頁面上的某些選項將無法使用。 在這種情況下，預設會選取適當的選項，且無法變更。

     

8. 在初始 [**建立新的報表資料庫**] 頁面上，選取以下適當的選項，以設定**Microsoft SQL Server 實例**與**報表伺服器資料庫**。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">方法</th>
   <th align="left">您需要執行的動作</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>您使用的是自訂的 Microsoft SQL Server 實例。</p></td>
   <td align="left"><p>選取 <strong> [使用自訂實例] </strong> ，然後輸入實例的名稱。</p>
   <p>使用格式 <strong> INSTANCENAME </strong> 。 假設的安裝位置是本機電腦。</p>
   <p>不支援：使用格式 <strong> ServerName </strong> &lt; 強 &gt; 實例的伺服器名稱 </strong> 。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>您使用的是自訂資料庫名稱。</p></td>
   <td align="left"><p>選取 <strong> [自訂設定] </strong> ，然後輸入資料庫的名稱。</p>
   <p>資料庫名稱必須是唯一的，否則安裝將會失敗。</p></td>
   </tr>
   </tbody>
   </table>

     

9. 在 [**設定**] 頁面上，接受預設值： [**使用此本機電腦**]。

   **注意**  
   如果您要並排安裝管理伺服器與管理資料庫，此頁面上的某些選項將無法使用。 在這種情況下，預設會選取適當的選項，且無法變更。

     

10. 在 [**設定**（管理伺服器配置）] 頁面上，指定以下專案：

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">要設定的專案</th>
    <th align="left">描述與範例</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>輸入擁有足夠許可權的 AD 群組，以管理 App-v 環境。</p></td>
    <td align="left"><p>範例： MyDomain\MyUser</p>
    <p>安裝之後，您可以使用管理主控台新增其他使用者或群組。 不過，不支援全域安全性群組和 Active Directory 網域服務（AD DS）通訊群組。 您必須使用「 <strong> 網域本機」 </strong> 或「通用」 <strong> </strong> 群組才能執行此動作。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>網站名稱 </strong> ：指定將用來執行發佈服務的自訂名稱。</p></td>
    <td align="left"><p>如果您沒有自訂名稱，請不要進行任何變更。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>埠系結 </strong> ：指定將由 app-v 使用的唯一端口號碼。</p></td>
    <td align="left"><p>範例： <strong> 12345</strong></p>
    <p>確定指定的埠未由其他網站使用。</p></td>
    </tr>
    </tbody>
    </table>

     

11. 在 [**設定****發佈伺服器**設定] 頁面上，指定以下專案：

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">要設定的專案</th>
    <th align="left">描述與範例</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>指定管理服務的 URL。</p></td>
    <td align="left"><p>範例<a href="http://localhost:12345" data-raw-source="http://localhost:12345">http://localhost:12345</a></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>網站名稱 </strong> ：指定將用來執行發佈服務的自訂名稱。</p></td>
    <td align="left"><p>如果您沒有自訂名稱，請不要進行任何變更。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>埠系結 </strong> ：指定將由 app-v 使用的唯一端口號碼。</p></td>
    <td align="left"><p>範例：54321</p>
    <p>確定指定的埠未由其他網站使用。</p></td>
    </tr>
    </tbody>
    </table>

     

12. 在 [**報表伺服器**] 頁面上，指定下列內容：

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">要設定的專案</th>
    <th align="left">描述與範例</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>網站名稱 </strong> ：指定將用來執行報表服務的自訂名稱。</p></td>
    <td align="left"><p>如果您沒有自訂名稱，請不要進行任何變更。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>埠系結 </strong> ：指定將由 app-v 使用的唯一端口號碼。</p></td>
    <td align="left"><p>範例：55555</p>
    <p>確定指定的埠未由其他網站使用。</p></td>
    </tr>
    </tbody>
    </table>

     

13. 若要開始安裝，請在 [**就緒**] 頁面上按一下 [**安裝**]，然後按一下 [**完成**] 頁面上的 [**關閉**]。

14. 若要確認安裝程式已順利完成，請開啟網頁瀏覽器，然後輸入下列 URL：

    **HTTP:// &lt;管理伺服器電腦名稱稱 &gt; ： &lt; 管理服務埠編號 &gt; /Console.html**。

    範例： **http://localhost:12345/console.html** 。 如果安裝成功，則會顯示 App-v 管理主控台，沒有任何錯誤。

    您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[部署 App-V 5.1](deploying-app-v-51.md)

[如何在與管理和報告服務不同的電腦上安裝管理和報告資料庫](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services51.md)

[如何在遠端電腦上安裝發佈伺服器](how-to-install-the-publishing-server-on-a-remote-computer51.md)

[如何使用指令碼來部署 App-V 5.1 伺服器](how-to-deploy-the-app-v-51-server-using-a-script.md)

 

 





