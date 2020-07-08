---
title: 如何設定自助入口網站品牌形象與工作階段逾時
description: 如何設定自助入口網站品牌形象與工作階段逾時
author: dansimp
ms.assetid: 031eedfc-fade-4d2f-8771-b329e1d38c0d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e222880b2d5557ef15cd7a4efd6421b9972541f4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800117"
---
# 如何設定自助入口網站品牌形象與工作階段逾時


在您設定自助入口網站之後，您可以使用您的公司名稱、說明服務台 URL 和「通知」文字來署名它。 您也可以變更會話超時設定，以讓最終使用者的會話在指定的不活動期後到期。

**注意**  
您也可以使用 [ **Enable-MbamWebApplication** Windows PowerShell Cmdlet] 或 [MBAM 伺服器設定] 嚮導來署名自助入口網站。 如需使用此嚮導的指示，請參閱[如何設定 MBAM 2.5 Web 應用程式](how-to-configure-the-mbam-25-web-applications.md)。



**注意**  
在下列指示中， *SelfService*是自助服務入口網站的預設虛擬目錄名稱。 您在設定自助入口網站時，可能會使用不同的名稱。



**針對自助服務入口網站設定會話超時與署名**

1.  若要設定使用者會話的超時期間，請啟動**網際網路資訊服務管理員**，或執行**inetmgr.exe**。

2.  流覽至**網站** &gt; **Microsoft BitLocker 系統管理和監控** &gt; **SelfService** &gt; **ASP.NET** &gt; **會話狀態**，並將 [ **Cookie 設定**] 底下的**超時**值變更為最終使用者的自助服務入口網站會話到期的分鐘數。 預設值為**5**。 若要停用此設定，讓它不會超時，請將此值設定為**0**。

3.  若要設定自助入口網站的署名專案，請啟動**網際網路資訊服務管理員**或執行**inetmgr.exe**。

4.  流覽至**網站** &gt; **Microsoft BitLocker 管理和監控** &gt; **SelfService** &gt; **應用程式設定**。

5.  在 [ **Name** ] （名稱）欄中，選取您要變更的專案，然後變更預設值以反映您要使用的名稱。 下表列出您可以設定的值。

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
<th align="left">Default value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ClientValidationEnabled</p></td>
<td align="left"><p>true</p></td>
</tr>
<tr class="even">
<td align="left"><p>CompanyName</p></td>
<td align="left"><p>Contoso IT</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DisplayNotice</p></td>
<td align="left"><p>true</p></td>
</tr>
<tr class="even">
<td align="left"><p>HelpdeskText</p></td>
<td align="left"><p>Contact Helpdesk or IT Department</p></td>
</tr>
<tr class="odd">
<td align="left"><p>HelpdeskUrl</p></td>
<td align="left"><p>#</p>
<div class="alert">
<strong>Note</strong>  
<p>In MBAM 2.5 SP1, the HelpdeskUrl default value is empty.</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>jQueryPath</p></td>
<td align="left"><p>[//go.microsoft.com/fwlink/?LinkID=390515](//go.microsoft.com/fwlink/?LinkID=390515)</p>
<div class="alert">
<strong>Note</strong>  
<p>In MBAM 2.5 SP1, this has been changed to a local JavaScript file shipped with the product, located at ~/Scripts/jquery-1.10.2.min.js</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>jQueryValidatePath</p></td>
<td align="left"><p>[//go.microsoft.com/fwlink/?LinkID=390516](//go.microsoft.com/fwlink/?LinkID=390516)</p>
<div class="alert">
<strong>Note</strong>  
<p>In MBAM 2.5 SP1, this has been changed to a local JavaScript file shipped with the product, located at ~/Scripts/jquery.validate.min.js</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>jQueryValidateUnobtrusivePath</p></td>
<td align="left"><p>[//go.microsoft.com/fwlink/?LinkID=390517](//go.microsoft.com/fwlink/?LinkID=390517)</p>
<div class="alert">
<strong>Note</strong>  
<p>In MBAM 2.5 SP1, this has been changed to a local JavaScript file shipped with the product, located at ~/Scripts/jquery.validate.unobtrusive.min.js</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>NoticeTextPath</p></td>
<td align="left"><p>Notice.txt</p>
<div class="alert">
<strong>Note</strong>  
<p>You can edit the notice text either by using the Internet Information Services (IIS) Manager or by opening and changing the Notice.txt file in the installation directory.</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>UnobtrusiveJavaScriptEnabled</p></td>
<td align="left"><p>true</p></td>
</tr>
</tbody>
</table>
~~~





## 相關主題


[為組織自訂自助入口網站](customizing-the-self-service-portal-for-your-organization.md)



## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





