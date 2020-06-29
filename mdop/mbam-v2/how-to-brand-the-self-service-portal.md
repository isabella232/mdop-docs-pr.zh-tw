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
# <span data-ttu-id="da34d-103">如何在自助入口網站設定品牌</span><span class="sxs-lookup"><span data-stu-id="da34d-103">How to Brand the Self-Service Portal</span></span>


<span data-ttu-id="da34d-104">在您安裝 Microsoft BitLocker 管理和監控（MBAM）自助服務入口網站之後，您可以使用公司名稱、說明服務台 URL 及「通知」文字，為自助服務入口網站加上品牌。</span><span class="sxs-lookup"><span data-stu-id="da34d-104">After you install the Microsoft BitLocker Administration and Monitoring (MBAM) Self-Service Portal, you can brand the Self-Service Portal with your company name, Help Desk URL, and “notice” text.</span></span> <span data-ttu-id="da34d-105">您也可以變更 [會話超時] 設定，讓最終使用者的會話在指定的不活動期後到期。</span><span class="sxs-lookup"><span data-stu-id="da34d-105">You can also change the Session Timeout setting to make the end user’s session expire after a specified period of inactivity.</span></span>

**<span data-ttu-id="da34d-106">針對自助服務入口網站設定會話超時與署名</span><span class="sxs-lookup"><span data-stu-id="da34d-106">To set the session time-out and branding for the Self-Service Portal</span></span>**

1.  <span data-ttu-id="da34d-107">若要設定使用者會話的超時期間，請啟動**網際網路資訊服務管理員**，或執行**inetmgr.exe**。</span><span class="sxs-lookup"><span data-stu-id="da34d-107">To set the time-out period for the end user’s session, start the **Internet Information Services Manager**, or run **inetmgr.exe**.</span></span>

2.  <span data-ttu-id="da34d-108">流覽至**網站** &gt; **Microsoft BitLocker 管理和監控** &gt; **SelfService** &gt; **ASP.NET** &gt; **會話狀態**，並將 [ **Cookie 設定**] 底下的**超時**值變更為最終使用者的自助服務入口網站會話將到期的分鐘數。</span><span class="sxs-lookup"><span data-stu-id="da34d-108">Browse to **Sites** &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **SelfService** &gt; **ASP.NET** &gt; **Session State**, and change the **Time-out** value under **Cookie Settings** to the number of minutes after which the end user’s Self-Service Portal session will expire.</span></span> <span data-ttu-id="da34d-109">預設值是 5。</span><span class="sxs-lookup"><span data-stu-id="da34d-109">The default is 5.</span></span> <span data-ttu-id="da34d-110">若要停用此設定，讓它不會超時，請將此值設定為**0**。</span><span class="sxs-lookup"><span data-stu-id="da34d-110">To disable the setting so that there is no time-out, set the value to **0**.</span></span>

3.  <span data-ttu-id="da34d-111">若要設定自助入口網站的署名專案，請啟動 [**網際網路資訊服務管理員**]，或執行**inetmgr.exe**。</span><span class="sxs-lookup"><span data-stu-id="da34d-111">To set the branding items for the Self-Service Portal, start the **Internet Information Services Manager**, or run **inetmgr.exe**.</span></span>

4.  <span data-ttu-id="da34d-112">流覽至**網站** &gt; **Microsoft BitLocker 管理和監控** &gt; **SelfService** &gt; **應用程式設定**。</span><span class="sxs-lookup"><span data-stu-id="da34d-112">Browse to **Sites** &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **SelfService** &gt; **Application Settings**.</span></span>

5.  <span data-ttu-id="da34d-113">在 [**名稱**] 欄中，選取您要變更的專案，然後變更預設值，以反映您想要使用的名稱。</span><span class="sxs-lookup"><span data-stu-id="da34d-113">From the **Name** column, select the item that you want to change, and change the default value to reflect the name that you want to use.</span></span> <span data-ttu-id="da34d-114">下表列出您可以設定的值。</span><span class="sxs-lookup"><span data-stu-id="da34d-114">The following table lists the values that you can set.</span></span>

    **<span data-ttu-id="da34d-115">警告</span><span class="sxs-lookup"><span data-stu-id="da34d-115">Caution</span></span>**  
    <span data-ttu-id="da34d-116">請勿變更 Name （公司名稱）欄中的值，因為這會導致自助服務入口網站停止運作。</span><span class="sxs-lookup"><span data-stu-id="da34d-116">Do not change the value in the Name column (CompanyName\*), as it will cause the Self-Service Portal to stop working.</span></span>



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



## <span data-ttu-id="da34d-117">相關主題</span><span class="sxs-lookup"><span data-stu-id="da34d-117">Related topics</span></span>


[<span data-ttu-id="da34d-118">部署 MBAM 2.0 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="da34d-118">Deploying the MBAM 2.0 Server Infrastructure</span></span>](deploying-the-mbam-20-server-infrastructure-mbam-2.md)









