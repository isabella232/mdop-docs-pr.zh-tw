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
# <span data-ttu-id="651dc-103">如何設定自助入口網站品牌形象與工作階段逾時</span><span class="sxs-lookup"><span data-stu-id="651dc-103">How to Set the Self-Service Portal Branding and Session Time-out</span></span>


<span data-ttu-id="651dc-104">在您設定自助入口網站之後，您可以使用您的公司名稱、說明服務台 URL 和「通知」文字來署名它。</span><span class="sxs-lookup"><span data-stu-id="651dc-104">After you configure the Self-Service Portal, you can brand it with your company name, Help Desk URL, and "notice" text.</span></span> <span data-ttu-id="651dc-105">您也可以變更會話超時設定，以讓最終使用者的會話在指定的不活動期後到期。</span><span class="sxs-lookup"><span data-stu-id="651dc-105">You can also change the Session Time-out setting to make the end user’s session expire after a specified period of inactivity.</span></span>

**<span data-ttu-id="651dc-106">注意</span><span class="sxs-lookup"><span data-stu-id="651dc-106">Note</span></span>**  
<span data-ttu-id="651dc-107">您也可以使用 [ **Enable-MbamWebApplication** Windows PowerShell Cmdlet] 或 [MBAM 伺服器設定] 嚮導來署名自助入口網站。</span><span class="sxs-lookup"><span data-stu-id="651dc-107">You can also brand the Self-Service Portal by using the **Enable-MbamWebApplication** Windows PowerShell cmdlet or the MBAM Server Configuration wizard.</span></span> <span data-ttu-id="651dc-108">如需使用此嚮導的指示，請參閱[如何設定 MBAM 2.5 Web 應用程式](how-to-configure-the-mbam-25-web-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="651dc-108">For instructions on using the wizard, see [How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md).</span></span>



**<span data-ttu-id="651dc-109">注意</span><span class="sxs-lookup"><span data-stu-id="651dc-109">Note</span></span>**  
<span data-ttu-id="651dc-110">在下列指示中， *SelfService*是自助服務入口網站的預設虛擬目錄名稱。</span><span class="sxs-lookup"><span data-stu-id="651dc-110">In the following instructions, *SelfService* is the default virtual directory name for the Self-Service Portal.</span></span> <span data-ttu-id="651dc-111">您在設定自助入口網站時，可能會使用不同的名稱。</span><span class="sxs-lookup"><span data-stu-id="651dc-111">You might have used a different name when you configured the Self-Service Portal.</span></span>



**<span data-ttu-id="651dc-112">針對自助服務入口網站設定會話超時與署名</span><span class="sxs-lookup"><span data-stu-id="651dc-112">To set the session time-out and branding for the Self-Service Portal</span></span>**

1.  <span data-ttu-id="651dc-113">若要設定使用者會話的超時期間，請啟動**網際網路資訊服務管理員**，或執行**inetmgr.exe**。</span><span class="sxs-lookup"><span data-stu-id="651dc-113">To set the time-out period for the end user’s session, start the **Internet Information Services Manager**, or run **inetmgr.exe**.</span></span>

2.  <span data-ttu-id="651dc-114">流覽至**網站** &gt; **Microsoft BitLocker 系統管理和監控** &gt; **SelfService** &gt; **ASP.NET** &gt; **會話狀態**，並將 [ **Cookie 設定**] 底下的**超時**值變更為最終使用者的自助服務入口網站會話到期的分鐘數。</span><span class="sxs-lookup"><span data-stu-id="651dc-114">Browse to **Sites** &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **SelfService** &gt; **ASP.NET** &gt; **Session State**, and change the **Time-out** value under **Cookie Settings** to the number of minutes after which the end user’s Self-Service Portal session expires.</span></span> <span data-ttu-id="651dc-115">預設值為**5**。</span><span class="sxs-lookup"><span data-stu-id="651dc-115">The default value is **5**.</span></span> <span data-ttu-id="651dc-116">若要停用此設定，讓它不會超時，請將此值設定為**0**。</span><span class="sxs-lookup"><span data-stu-id="651dc-116">To disable the setting so that there is no time-out, set the value to **0**.</span></span>

3.  <span data-ttu-id="651dc-117">若要設定自助入口網站的署名專案，請啟動**網際網路資訊服務管理員**或執行**inetmgr.exe**。</span><span class="sxs-lookup"><span data-stu-id="651dc-117">To set the branding items for the Self-Service Portal, start the **Internet Information Services Manager** or run **inetmgr.exe**.</span></span>

4.  <span data-ttu-id="651dc-118">流覽至**網站** &gt; **Microsoft BitLocker 管理和監控** &gt; **SelfService** &gt; **應用程式設定**。</span><span class="sxs-lookup"><span data-stu-id="651dc-118">Browse to **Sites** &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **SelfService** &gt; **Application Settings**.</span></span>

5.  <span data-ttu-id="651dc-119">在 [ **Name** ] （名稱）欄中，選取您要變更的專案，然後變更預設值以反映您要使用的名稱。</span><span class="sxs-lookup"><span data-stu-id="651dc-119">In the **Name** column, select the item that you want to change, and change the default value to reflect the name that you want to use.</span></span> <span data-ttu-id="651dc-120">下表列出您可以設定的值。</span><span class="sxs-lookup"><span data-stu-id="651dc-120">The following table lists the values that you can set.</span></span>

    **<span data-ttu-id="651dc-121">警告</span><span class="sxs-lookup"><span data-stu-id="651dc-121">Caution</span></span>**  
    <span data-ttu-id="651dc-122">請勿變更 Name （公司名稱）欄中的值，因為這會導致自助服務入口網站停止運作。</span><span class="sxs-lookup"><span data-stu-id="651dc-122">Do not change the value in the Name column (CompanyName\*), as it will cause Self-Service Portal to stop working.</span></span>



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





## <span data-ttu-id="651dc-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="651dc-123">Related topics</span></span>


[<span data-ttu-id="651dc-124">為組織自訂自助入口網站</span><span class="sxs-lookup"><span data-stu-id="651dc-124">Customizing the Self-Service Portal for Your Organization</span></span>](customizing-the-self-service-portal-for-your-organization.md)



## <span data-ttu-id="651dc-125">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="651dc-125">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="651dc-126">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="651dc-126">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="651dc-127">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="651dc-127">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





