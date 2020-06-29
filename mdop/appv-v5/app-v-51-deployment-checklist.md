---
title: App-V 5.1 部署檢查清單
description: App-V 5.1 部署檢查清單
author: dansimp
ms.assetid: 44bed85a-e4f5-49d7-a308-a2b681f76372
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0864335e505996a3ea379b09de6a1aaa7fbe1676
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800677"
---
# <span data-ttu-id="63731-103">App-V 5.1 部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="63731-103">App-V 5.1 Deployment Checklist</span></span>


<span data-ttu-id="63731-104">此檢查清單可用來協助您在 Microsoft 應用程式虛擬化（App-v）5.1 部署期間使用。</span><span class="sxs-lookup"><span data-stu-id="63731-104">This checklist can be used to help you during Microsoft Application Virtualization (App-V) 5.1 deployment.</span></span>

**<span data-ttu-id="63731-105">注意</span><span class="sxs-lookup"><span data-stu-id="63731-105">Note</span></span>**  
<span data-ttu-id="63731-106">此檢查清單概述在部署 App-v 5.1 功能時，所建議的步驟和要考慮的高層次專案清單。</span><span class="sxs-lookup"><span data-stu-id="63731-106">This checklist outlines the recommended steps and a high-level list of items to consider when deploying App-V 5.1 features.</span></span> <span data-ttu-id="63731-107">建議您將此檢查清單複製到試算表程式中，然後將它自訂為供您使用。</span><span class="sxs-lookup"><span data-stu-id="63731-107">It is recommended that you copy this checklist into a spreadsheet program and customize it for your use.</span></span>



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
<th align="left"><span data-ttu-id="63731-108">工作</span><span class="sxs-lookup"><span data-stu-id="63731-108">Task</span></span></th>
<th align="left"><span data-ttu-id="63731-109">參考資料</span><span class="sxs-lookup"><span data-stu-id="63731-109">References</span></span></th>
<th align="left"><span data-ttu-id="63731-110">附註</span><span class="sxs-lookup"><span data-stu-id="63731-110">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="63731-111">完成規劃階段，以準備 App-v 5.1 部署的計算環境。</span><span class="sxs-lookup"><span data-stu-id="63731-111">Complete the planning phase to prepare the computing environment for App-V 5.1 deployment.</span></span></p></td>
<td align="left"><p><a href="app-v-51-planning-checklist.md" data-raw-source="[App-V 5.1 Planning Checklist](app-v-51-planning-checklist.md)"><span data-ttu-id="63731-112">App-V 5.1 規劃檢查清單</span><span class="sxs-lookup"><span data-stu-id="63731-112">App-V 5.1 Planning Checklist</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="63731-113">查看 App-v 5.1 支援的設定資訊，確認已選取的用戶端和伺服器電腦支援 App-v 5.1 功能安裝。</span><span class="sxs-lookup"><span data-stu-id="63731-113">Review the App-V 5.1 supported configurations information to make sure selected client and server computers are supported for App-V 5.1 feature installation.</span></span></p></td>
<td align="left"><p><a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)"><span data-ttu-id="63731-114">App-V 5.1 支援的組態</span><span class="sxs-lookup"><span data-stu-id="63731-114">App-V 5.1 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="63731-115">執行 App-v 5.1 安裝程式，為您的環境部署必要的 App-V 5.1 功能。</span><span class="sxs-lookup"><span data-stu-id="63731-115">Run App-V 5.1 Setup to deploy the required App-V 5.1 features for your environment.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="63731-116">注意</span><span class="sxs-lookup"><span data-stu-id="63731-116">Note</span></span></strong><br/><p><span data-ttu-id="63731-117">追蹤在安裝期間建立的伺服器名稱與相關聯的 URL。</span><span class="sxs-lookup"><span data-stu-id="63731-117">Keep track of the names of the servers and associated URL’s created during installation.</span></span> <span data-ttu-id="63731-118">此資訊將會在整個安裝過程中使用。</span><span class="sxs-lookup"><span data-stu-id="63731-118">This information will be used throughout the installation process.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p></p>
<ul>
<li><p><a href="how-to-install-the-sequencer-51beta-gb18030.md" data-raw-source="[How to Install the Sequencer](how-to-install-the-sequencer-51beta-gb18030.md)"><span data-ttu-id="63731-119">如何安裝 Sequencer</span><span class="sxs-lookup"><span data-stu-id="63731-119">How to Install the Sequencer</span></span></a></p></li>
<li><p><a href="how-to-deploy-the-app-v-client-51gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-51gb18030.md)"><span data-ttu-id="63731-120">如何部署 App-V 用戶端</span><span class="sxs-lookup"><span data-stu-id="63731-120">How to Deploy the App-V Client</span></span></a></p></li>
<li><p><a href="how-to-deploy-the-app-v-51-server.md" data-raw-source="[How to Deploy the App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md)"><span data-ttu-id="63731-121">如何部署 App-V 5.1 Server</span><span class="sxs-lookup"><span data-stu-id="63731-121">How to Deploy the App-V 5.1 Server</span></span></a></p></li>
</ul></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>








## <span data-ttu-id="63731-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="63731-122">Related topics</span></span>


[<span data-ttu-id="63731-123">部署 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="63731-123">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)









