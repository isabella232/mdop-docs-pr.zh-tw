---
title: 規劃使用電子軟體發佈系統部署 App-V 5.1
description: 規劃使用電子軟體發佈系統部署 App-V 5.1
author: dansimp
ms.assetid: c26602c2-5e8d-44e6-90df-adacc593607e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fde3f0ea4f1dec72b97143b4b27dd0b32a503b15
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800334"
---
# <span data-ttu-id="43319-103">規劃使用電子軟體發佈系統部署 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="43319-103">Planning to Deploy App-V 5.1 with an Electronic Software Distribution System</span></span>


<span data-ttu-id="43319-104">如果您使用電子軟體發佈系統來部署 App-v 套件，請參閱下列規劃考慮。</span><span class="sxs-lookup"><span data-stu-id="43319-104">If you are using an electronic software distribution system to deploy App-V packages, review the following planning considerations.</span></span> <span data-ttu-id="43319-105">如需使用 System Center Configuration Manager 來部署 App-v 的相關資訊，請參閱[Configuration Manager 中的應用程式管理簡介](https://go.microsoft.com/fwlink/?LinkId=281816)。</span><span class="sxs-lookup"><span data-stu-id="43319-105">For information about using System Center Configuration Manager to deploy App-V, see [Introduction to Application Management in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=281816).</span></span>

<span data-ttu-id="43319-106">檢查下列元件與架構需求選項，這些選項會在您使用 ESD 部署 App-v 套件時套用：</span><span class="sxs-lookup"><span data-stu-id="43319-106">Review the following component and architecture requirements options that apply when you use an ESD to deploy App-V packages:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="43319-107">部署需求或選項</span><span class="sxs-lookup"><span data-stu-id="43319-107">Deployment requirement or option</span></span></th>
<th align="left"><span data-ttu-id="43319-108">描述</span><span class="sxs-lookup"><span data-stu-id="43319-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="43319-109">App-v 管理伺服器、管理資料庫及發佈伺服器不是必要的。</span><span class="sxs-lookup"><span data-stu-id="43319-109">The App-V Management server, Management database, and Publishing server are not required.</span></span></p></td>
<td align="left"><p><span data-ttu-id="43319-110">這些函數是由已實施的 ESD 解決方案來處理。</span><span class="sxs-lookup"><span data-stu-id="43319-110">These functions are handled by the implemented ESD solution.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="43319-111">您可以將 App-v 報表服務器與報告資料庫與 ESD 並行部署。</span><span class="sxs-lookup"><span data-stu-id="43319-111">You can deploy the App-V Reporting server and Reporting database side by side with the ESD.</span></span></p></td>
<td align="left"><p><span data-ttu-id="43319-112">並行部署可讓您收集資料並產生報告。</span><span class="sxs-lookup"><span data-stu-id="43319-112">The side-by-side deployment lets you to collect data and generate reports.</span></span></p>
<p><span data-ttu-id="43319-113">如果您啟用應用程式 V 用戶端來傳送報告資訊，而您不是使用 App-v 報表服務器，則報告資料會儲存在相關聯的 .xml 檔案中。</span><span class="sxs-lookup"><span data-stu-id="43319-113">If you enable the App-V client to send report information, and you are not using the App-V Reporting server, the reporting data is stored in associated .xml files.</span></span></p></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="43319-114">相關主題</span><span class="sxs-lookup"><span data-stu-id="43319-114">Related topics</span></span>


[<span data-ttu-id="43319-115">規劃部署 App-V</span><span class="sxs-lookup"><span data-stu-id="43319-115">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v51.md)

 

 





