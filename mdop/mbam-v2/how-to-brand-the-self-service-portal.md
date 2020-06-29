---
title: 如何在自助入口網站設定品牌
description: 如何在自助入口網站設定品牌
author: dansimp
ms.assetid: 3ef9e951-7c42-4f7f-b131-3765d39b3207
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fe4f4efc5852042671711ba5780cc78055957ba8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810982"
---
# 如何在自助入口網站設定品牌


在您安裝 Microsoft BitLocker 管理和監控（MBAM）自助服務入口網站之後，您可以使用公司名稱、說明服務台 URL 及「通知」文字，為自助服務入口網站加上品牌。 您也可以變更 [會話超時] 設定，讓最終使用者的會話在指定的不活動期後到期。

**針對自助服務入口網站設定會話超時與署名**

1.  若要設定使用者會話的超時期間，請啟動**網際網路資訊服務管理員**，或執行**inetmgr.exe**。

2.  流覽至**網站** &gt; **Microsoft BitLocker 管理和監控** &gt; **SelfService** &gt; **ASP.NET** &gt; **會話狀態**，並將 [ **Cookie 設定**] 底下的**超時**值變更為最終使用者的自助服務入口網站會話將到期的分鐘數。 預設值是 5。 若要停用此設定，讓它不會超時，請將此值設定為**0**。

3.  若要設定自助入口網站的署名專案，請啟動 [**網際網路資訊服務管理員**]，或執行**inetmgr.exe**。

4.  流覽至**網站** &gt; **Microsoft BitLocker 管理和監控** &gt; **SelfService** &gt; **應用程式設定**。

5.  在 [**名稱**] 欄中，選取您要變更的專案，然後變更預設值，以反映您想要使用的名稱。 下表列出您可以設定的值。

    **警告**  
    請勿變更 Name （公司名稱）欄中的值，因為這會導致自助服務入口網站停止運作。



~~~
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Name</th>
<th align="left">Default Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>CompanyName*</p></td>
<td align="left"><p>Contoso IT</p></td>
</tr>
<tr class="even">
<td align="left"><p>HelpdeskText*</p></td>
<td align="left"><p>Contact Help Desk or IT Department</p></td>
</tr>
<tr class="odd">
<td align="left"><p>HelpdeskUrl*</p></td>
<td align="left"><p>Http://www.microsoft.com</p></td>
</tr>
<tr class="even">
<td align="left"><p>jQueryPath</p></td>
<td align="left"><p>//ajax.aspnetcdn.com/ajax/jQuery/jquery-1.7.2.min.js</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MicrosoftAjaxPath</p></td>
<td align="left"><p>//ajax.aspnetcdn.com/ajax/3.5/MicrosoftAjax.js</p></td>
</tr>
<tr class="even">
<td align="left"><p>MicrosoftMvcAjaxPath</p></td>
<td align="left"><p>//ajax.aspnetcdn.com/ajax/mvc/2.0/MicrosoftMvcValidation.js</p></td>
</tr>
<tr class="odd">
<td align="left"><p>NoticeTextPath</p></td>
<td align="left"><p>Notice.txt</p>
<div class="alert">
<strong>Note</strong>  
<p>You can edit the Notice text either by using the IIS Manager or by opening and changing the Notice.txt file in the installation directory.</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>
~~~



## 相關主題


[部署 MBAM 2.0 伺服器基礎結構](deploying-the-mbam-20-server-infrastructure-mbam-2.md)









