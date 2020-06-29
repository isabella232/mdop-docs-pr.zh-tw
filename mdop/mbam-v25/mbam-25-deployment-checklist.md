---
title: MBAM 2.5 部署檢查清單
description: MBAM 2.5 部署檢查清單
author: dansimp
ms.assetid: 2ba7de17-e3a4-4798-99e0-cd1dc28c5b76
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 11609b3d6d44d62b032e35005e5d967ca6d4e83b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809591"
---
# <span data-ttu-id="69119-103">MBAM 2.5 部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="69119-103">MBAM 2.5 Deployment Checklist</span></span>


<span data-ttu-id="69119-104">您可以使用此檢查清單來協助您在 Microsoft BitLocker 管理和監控（MBAM）部署中使用獨立拓撲。</span><span class="sxs-lookup"><span data-stu-id="69119-104">You can use this checklist to help you during Microsoft BitLocker Administration and Monitoring (MBAM) deployment with a Stand-alone topology.</span></span>

**<span data-ttu-id="69119-105">注意</span><span class="sxs-lookup"><span data-stu-id="69119-105">Note</span></span>**  
<span data-ttu-id="69119-106">此檢查清單概括了在您部署 Microsoft BitLocker 管理和監控功能時，所建議的步驟以及要考慮的高層次專案清單。</span><span class="sxs-lookup"><span data-stu-id="69119-106">This checklist outlines the recommended steps and a high-level list of items to consider when you deploy Microsoft BitLocker Administration and Monitoring features.</span></span> <span data-ttu-id="69119-107">我們建議您將此檢查清單複製到試算表程式中，然後將它自訂為供您使用。</span><span class="sxs-lookup"><span data-stu-id="69119-107">We recommend that you copy this checklist into a spreadsheet program and customize it for your use.</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="69119-108">工作</span><span class="sxs-lookup"><span data-stu-id="69119-108">Task</span></span></th>
<th align="left"><span data-ttu-id="69119-109">參考資料</span><span class="sxs-lookup"><span data-stu-id="69119-109">References</span></span></th>
<th align="left"><span data-ttu-id="69119-110">附註</span><span class="sxs-lookup"><span data-stu-id="69119-110">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="69119-111">複習並完成所有規劃步驟，以準備您的環境以進行 MBAM 部署。</span><span class="sxs-lookup"><span data-stu-id="69119-111">Review and complete all planning steps to prepare your environment for MBAM deployment.</span></span></p></td>
<td align="left"><p><a href="mbam-25-planning-checklist.md" data-raw-source="[MBAM 2.5 Planning Checklist](mbam-25-planning-checklist.md)"><span data-ttu-id="69119-112">MBAM 2.5 規劃檢查清單</span><span class="sxs-lookup"><span data-stu-id="69119-112">MBAM 2.5 Planning Checklist</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="69119-113">查看支援的設定資訊，以確保 MBAM 支援所選取的用戶端和伺服器電腦。</span><span class="sxs-lookup"><span data-stu-id="69119-113">Review the supported configurations information to ensure that MBAM supports the selected client and server computers.</span></span></p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="69119-114">MBAM 2.5 支援的組態</span><span class="sxs-lookup"><span data-stu-id="69119-114">MBAM 2.5 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="69119-115">安裝 MBAM Server 軟體。</span><span class="sxs-lookup"><span data-stu-id="69119-115">Install the MBAM Server software.</span></span></p></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="69119-116">安裝 MBAM 2.5 伺服器軟體</span><span class="sxs-lookup"><span data-stu-id="69119-116">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="69119-117">設定 MBAM 伺服器功能：</span><span class="sxs-lookup"><span data-stu-id="69119-117">Configure the MBAM Server features:</span></span></p>
<ul>
<li><p><span data-ttu-id="69119-118">合規性與審核資料庫與復原資料庫</span><span class="sxs-lookup"><span data-stu-id="69119-118">Compliance and Audit Database and Recovery Database</span></span></p></li>
<li><p><span data-ttu-id="69119-119">報告</span><span class="sxs-lookup"><span data-stu-id="69119-119">Reports</span></span></p></li>
<li><p><span data-ttu-id="69119-120">Web 應用程式</span><span class="sxs-lookup"><span data-stu-id="69119-120">Web applications</span></span></p></li>
<li><p><span data-ttu-id="69119-121">Configuration Manager 整合拓朴（只有當您在此拓朴執行 MBAM 時才需要）</span><span class="sxs-lookup"><span data-stu-id="69119-121">Configuration Manager Integration topology (needed only if you are running MBAM with this topology)</span></span></p></li>
</ul>
<div class="alert">
<strong><span data-ttu-id="69119-122">注意</span><span class="sxs-lookup"><span data-stu-id="69119-122">Note</span></span></strong><br/><p><span data-ttu-id="69119-123">記下您要設定每個功能的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="69119-123">Note the names of the servers on which you configure each feature.</span></span> <span data-ttu-id="69119-124">您將會在整個配置程式中使用此資訊。</span><span class="sxs-lookup"><span data-stu-id="69119-124">You will use this information throughout the configuration process.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="configuring-the-mbam-25-server-features.md" data-raw-source="[Configuring the MBAM 2.5 Server Features](configuring-the-mbam-25-server-features.md)"><span data-ttu-id="69119-125">設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="69119-125">Configuring the MBAM 2.5 Server Features</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="69119-126">驗證 MBAM 設定。</span><span class="sxs-lookup"><span data-stu-id="69119-126">Validate the MBAM configuration.</span></span></p></td>
<td align="left"><p><a href="validating-the-mbam-25-server-feature-configuration.md" data-raw-source="[Validating the MBAM 2.5 Server Feature Configuration](validating-the-mbam-25-server-feature-configuration.md)"><span data-ttu-id="69119-127">驗證 MBAM 2.5 伺服器功能設定</span><span class="sxs-lookup"><span data-stu-id="69119-127">Validating the MBAM 2.5 Server Feature Configuration</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="69119-128">複製 MBAM 群組原則範本，並編輯群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="69119-128">Copy the MBAM Group Policy Template and edit the Group Policy settings.</span></span></p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)"><span data-ttu-id="69119-129">複製 MBAM 2.5 群組原則範本 </a> ，並 <a href="editing-the-mbam-25-group-policy-settings.md" data-raw-source="[Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md)"> 編輯 MBAM 2.5 群組原則設定</span><span class="sxs-lookup"><span data-stu-id="69119-129">Copying the MBAM 2.5 Group Policy Templates</a> and <a href="editing-the-mbam-25-group-policy-settings.md" data-raw-source="[Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md)">Editing the MBAM 2.5 Group Policy Settings</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="69119-130">部署 MBAM 用戶端軟體。</span><span class="sxs-lookup"><span data-stu-id="69119-130">Deploy the MBAM Client software.</span></span></p></td>
<td align="left"><p><a href="deploying-the-mbam-25-client.md" data-raw-source="[Deploying the MBAM 2.5 Client](deploying-the-mbam-25-client.md)"><span data-ttu-id="69119-131">部署 MBAM 2.5 用戶端</span><span class="sxs-lookup"><span data-stu-id="69119-131">Deploying the MBAM 2.5 Client</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>




## <span data-ttu-id="69119-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="69119-132">Related topics</span></span>


[<span data-ttu-id="69119-133">部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="69119-133">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)




## <span data-ttu-id="69119-134">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="69119-134">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="69119-135">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="69119-135">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="69119-136">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="69119-136">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




