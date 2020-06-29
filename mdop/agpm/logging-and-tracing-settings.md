---
title: 記錄和追蹤設定
description: 記錄和追蹤設定
author: dansimp
ms.assetid: db6b43c7-fdde-4d11-b5ab-a81346e56940
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bef0f8367647aad688c2aec7586ecdaae2e22143
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802677"
---
# <span data-ttu-id="731e8-103">記錄和追蹤設定</span><span class="sxs-lookup"><span data-stu-id="731e8-103">Logging and Tracing Settings</span></span>


<span data-ttu-id="731e8-104">[高級群組原則管理（AGPM）] 的 [管理範本] 設定可讓您集中設定適用于您的 AGPM 服務器和用戶端的記錄和追蹤選項，這些設定會套用至其中的群組原則物件（GPO）。</span><span class="sxs-lookup"><span data-stu-id="731e8-104">The Administrative Template settings for Advanced Group Policy Management (AGPM) enable you to centrally configure logging and tracing options for AGPM Servers and clients to which a Group Policy object (GPO) with these settings is applied.</span></span>

<span data-ttu-id="731e8-105">在群群組原則管理主控台（GPMC）中編輯 GPO 時，在 [**群群組原則物件編輯器**] 中的 [電腦 Configuration\\Administrative Templates\\Windows Components\\AGPM] 下提供下列設定。</span><span class="sxs-lookup"><span data-stu-id="731e8-105">The following setting is available under Computer Configuration\\Administrative Templates\\Windows Components\\AGPM in the **Group Policy Object Editor** when editing a GPO in the Group Policy Management Console (GPMC).</span></span> <span data-ttu-id="731e8-106">如果看不到此路徑，請以滑鼠右鍵按一下 [**管理範本**]，然後新增 [agpm. admx] 或 [agpm .adm] 範本。</span><span class="sxs-lookup"><span data-stu-id="731e8-106">If this path is not visible, right-click **Administrative Templates**, and add the agpm.admx or agpm.adm template.</span></span>

<span data-ttu-id="731e8-107">**追蹤檔案位置**：</span><span class="sxs-lookup"><span data-stu-id="731e8-107">**Trace file locations**:</span></span>

-   <span data-ttu-id="731e8-108">用戶端：%LocalAppData%\\Microsoft\\AGPM\\agpm.log</span><span class="sxs-lookup"><span data-stu-id="731e8-108">Client: %LocalAppData%\\Microsoft\\AGPM\\agpm.log</span></span>

-   <span data-ttu-id="731e8-109">伺服器：%CommonAppData%\\Microsoft\\AGPM\\agpmserv.log</span><span class="sxs-lookup"><span data-stu-id="731e8-109">Server: %CommonAppData%\\Microsoft\\AGPM\\agpmserv.log</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="731e8-110">設定</span><span class="sxs-lookup"><span data-stu-id="731e8-110">Setting</span></span></th>
<th align="left"><span data-ttu-id="731e8-111">效果</span><span class="sxs-lookup"><span data-stu-id="731e8-111">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="731e8-112">AGPM 記錄</span><span class="sxs-lookup"><span data-stu-id="731e8-112">AGPM Logging</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="731e8-113">如果已啟用，此設定會配置是否已開啟追蹤，以及詳細資料的層級。</span><span class="sxs-lookup"><span data-stu-id="731e8-113">If enabled, this setting configures whether tracing is turned on and the level of detail.</span></span> <span data-ttu-id="731e8-114">此設定會影響 AGPM 的用戶端和伺服器元件。</span><span class="sxs-lookup"><span data-stu-id="731e8-114">This setting affects both client and server components of AGPM.</span></span></p>
<p><span data-ttu-id="731e8-115">如果停用或未設定，此設定就不會有任何效果。</span><span class="sxs-lookup"><span data-stu-id="731e8-115">If disabled or not configured, this setting has no effect.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="731e8-116">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="731e8-116">Additional references</span></span>

-   [<span data-ttu-id="731e8-117">系統管理範本設定</span><span class="sxs-lookup"><span data-stu-id="731e8-117">Administrative Template Settings</span></span>](administrative-template-settings.md)

 

 





