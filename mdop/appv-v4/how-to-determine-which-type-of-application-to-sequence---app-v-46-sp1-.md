---
title: 如何判斷要順序的應用程式類型（App-v 4.6 SP1）
description: 如何判斷要順序的應用程式類型（App-v 4.6 SP1）
author: dansimp
ms.assetid: 936abee2-98f1-45fb-9f0d-786e1d7464b1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 001f6afa36ca28eb1b8e0cc2ccc161cef4194d24
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801437"
---
# <span data-ttu-id="98786-103">如何判斷要順序的應用程式類型（App-v 4.6 SP1）</span><span class="sxs-lookup"><span data-stu-id="98786-103">How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)</span></span>


<span data-ttu-id="98786-104">您可以使用 Microsoft Application Virtualization （App-v） Sequencer 來排列三種基本類型的應用程式。</span><span class="sxs-lookup"><span data-stu-id="98786-104">You can sequence three basic types of applications by using Microsoft Application Virtualization (App-V) Sequencer.</span></span>

## <span data-ttu-id="98786-105">若要判斷要排序的應用程式類型</span><span class="sxs-lookup"><span data-stu-id="98786-105">To determine which type of application to sequence</span></span>


<span data-ttu-id="98786-106">使用下表來判斷您應該序列化的應用程式類型，並取得如何為應用程式排序的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="98786-106">Use the following table to determine which type of application you should sequence and to obtain more information about how to sequence the application.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="98786-107">應用程式類型</span><span class="sxs-lookup"><span data-stu-id="98786-107">Application Type</span></span></th>
<th align="left"><span data-ttu-id="98786-108">描述</span><span class="sxs-lookup"><span data-stu-id="98786-108">Description</span></span></th>
<th align="left"><span data-ttu-id="98786-109">其他資訊</span><span class="sxs-lookup"><span data-stu-id="98786-109">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98786-110">Standard</span><span class="sxs-lookup"><span data-stu-id="98786-110">Standard</span></span></p></td>
<td align="left"><p><span data-ttu-id="98786-111">選取此選項以建立包含應用程式或應用程式套件的套件。</span><span class="sxs-lookup"><span data-stu-id="98786-111">Select this option to create a package that contains an application or a suite of applications.</span></span> <span data-ttu-id="98786-112">您應該針對您打算順序的大部分應用程式選取此選項。</span><span class="sxs-lookup"><span data-stu-id="98786-112">You should select this option for most applications that you plan to sequence.</span></span></p></td>
<td align="left"><p><a href="how-to-sequence-a-new-standard-application--app-v-46-sp1-.md" data-raw-source="[How to Sequence a New Standard Application (App-V 4.6 SP1)](how-to-sequence-a-new-standard-application--app-v-46-sp1-.md)"><span data-ttu-id="98786-113">如何排序新的標準應用程式 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="98786-113">How to Sequence a New Standard Application (App-V 4.6 SP1)</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98786-114">附加元件或外掛程式</span><span class="sxs-lookup"><span data-stu-id="98786-114">Add-on or Plug-in</span></span></p></td>
<td align="left"><p><span data-ttu-id="98786-115">選取此選項以建立可擴展標準應用程式功能的套件，例如 Microsoft Excel 的外掛程式。</span><span class="sxs-lookup"><span data-stu-id="98786-115">Select this option to create a package that extends the functionality of a standard application, for example, a plug-in for Microsoft Excel.</span></span> <span data-ttu-id="98786-116">此外，您也可以使用本機安裝應用程式的外掛程式，或是使用動態套件組合連結的其他套件。</span><span class="sxs-lookup"><span data-stu-id="98786-116">Additionally, you can use plug-ins for natively installed applications, or another package that is linked by using Dynamic Suite Composition.</span></span> <span data-ttu-id="98786-117">如需有關動態套件組合的詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)"> 如何使用動態套件組合 </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804"> https://go.microsoft.com/fwlink/?LinkId=203804 </a> ）。</span><span class="sxs-lookup"><span data-stu-id="98786-117">For more information about Dynamic Suite Composition, see <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)">How To Use Dynamic Suite Composition</a> (<a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804">https://go.microsoft.com/fwlink/?LinkId=203804</a>).</span></span></p></td>
<td align="left"><p><a href="how-to-sequence-a-new-add-on-or-plug-in-application--app-v-46-sp1-.md" data-raw-source="[How to Sequence a New Add-on or Plug-in Application (App-V 4.6 SP1)](how-to-sequence-a-new-add-on-or-plug-in-application--app-v-46-sp1-.md)"><span data-ttu-id="98786-118">如何排序新附加元件或外掛應用程式 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="98786-118">How to Sequence a New Add-on or Plug-in Application (App-V 4.6 SP1)</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98786-119">中介軟體</span><span class="sxs-lookup"><span data-stu-id="98786-119">Middleware</span></span></p></td>
<td align="left"><p><span data-ttu-id="98786-120">選取此選項以建立標準應用程式所需的套件，例如 Microsoft .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="98786-120">Select this option to create a package that is required by a standard application, for example, the Microsoft .NET Framework.</span></span> <span data-ttu-id="98786-121">中介軟體套件是使用動態套件組合來連結到其他套件。</span><span class="sxs-lookup"><span data-stu-id="98786-121">Middleware packages are used for linking to other packages by using Dynamic Suite Composition.</span></span> <span data-ttu-id="98786-122">如需有關動態套件組合的詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)"> 如何使用動態套件組合 </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804"> https://go.microsoft.com/fwlink/?LinkId=203804 </a> ）。</span><span class="sxs-lookup"><span data-stu-id="98786-122">For more information about Dynamic Suite Composition, see <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)">How To Use Dynamic Suite Composition</a> (<a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804">https://go.microsoft.com/fwlink/?LinkId=203804</a>).</span></span></p></td>
<td align="left"><p><a href="how-to-sequence-a-new-middleware-application--app-v-46-sp1-.md" data-raw-source="[How to Sequence a New Middleware Application (App-V 4.6 SP1)](how-to-sequence-a-new-middleware-application--app-v-46-sp1-.md)"><span data-ttu-id="98786-123">如何排序新的中介軟體應用程式 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="98786-123">How to Sequence a New Middleware Application (App-V 4.6 SP1)</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="98786-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="98786-124">Related topics</span></span>


[<span data-ttu-id="98786-125">Application Virtualization Sequencer 的工作 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="98786-125">Tasks for the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

 

 





