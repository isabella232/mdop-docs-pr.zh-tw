---
title: SFTMIME 命令參考
description: SFTMIME 命令參考
author: dansimp
ms.assetid: a4a69228-9dd3-4623-b773-899d03c0cf10
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 47aac9110febaf3f349461d74fef840326b1c6e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800801"
---
# <span data-ttu-id="f582e-103">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="f582e-103">SFTMIME Command Reference</span></span>


<span data-ttu-id="f582e-104">SFTMIME 是應用程式虛擬化（App-v）所使用的命令列介面，可讓您管理許多用戶端設定詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f582e-104">SFTMIME is a command-line interface used by Application Virtualization (App-V) that enables you to manage many client configuration details.</span></span> <span data-ttu-id="f582e-105">本節包含所有命令及其參數，以及每個命令的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="f582e-105">This section contains all the commands and their parameters, with a brief description of each.</span></span>

**<span data-ttu-id="f582e-106">重要</span><span class="sxs-lookup"><span data-stu-id="f582e-106">Important</span></span>**  
-   <span data-ttu-id="f582e-107">所有反斜線字元都必須使用前面的反斜線來轉義，否則路徑將無法正確分析。</span><span class="sxs-lookup"><span data-stu-id="f582e-107">All backslash characters must be escaped using a preceding backslash, or the path will not be parsed correctly.</span></span>

-   <span data-ttu-id="f582e-108">如果您使用呼叫程式來調用**CreateProcess**的 SFTMIME，您必須確定第一個參數是 sftmime.exe 的路徑。</span><span class="sxs-lookup"><span data-stu-id="f582e-108">If you are using a calling program to invoke SFTMIME with **CreateProcess**, you must ensure that the first parameter is the path to sftmime.exe.</span></span>

-   <span data-ttu-id="f582e-109">SFTMIME**查詢 OBJ**命令的輸出無法輸送至**findstr**命令，以搜尋字串。</span><span class="sxs-lookup"><span data-stu-id="f582e-109">The output of the SFTMIME **QUERY OBJ** command cannot be piped to the **findstr** command to search for a string.</span></span>

-   <span data-ttu-id="f582e-110">使用**全域**開關需要本機系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="f582e-110">Use of the **GLOBAL** switch requires local administrator rights.</span></span>

-   <span data-ttu-id="f582e-111">使用短路徑和相對路徑可能會導致意外的結果，且應避免發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="f582e-111">Use of short paths and relative paths can lead to unexpected results and should be avoided.</span></span> <span data-ttu-id="f582e-112">永遠使用完整路徑。</span><span class="sxs-lookup"><span data-stu-id="f582e-112">Always use full paths.</span></span>

 

## <span data-ttu-id="f582e-113">本節內容</span><span class="sxs-lookup"><span data-stu-id="f582e-113">In This Section</span></span>


[<span data-ttu-id="f582e-114">ADD APP</span><span class="sxs-lookup"><span data-stu-id="f582e-114">ADD APP</span></span>](add-app.md)

[<span data-ttu-id="f582e-115">ADD PACKAGE</span><span class="sxs-lookup"><span data-stu-id="f582e-115">ADD PACKAGE</span></span>](add-package.md)

[<span data-ttu-id="f582e-116">ADD SERVER</span><span class="sxs-lookup"><span data-stu-id="f582e-116">ADD SERVER</span></span>](add-server.md)

[<span data-ttu-id="f582e-117">ADD TYPE</span><span class="sxs-lookup"><span data-stu-id="f582e-117">ADD TYPE</span></span>](add-type.md)

[<span data-ttu-id="f582e-118">CLEAR APP</span><span class="sxs-lookup"><span data-stu-id="f582e-118">CLEAR APP</span></span>](clear-app.md)

[<span data-ttu-id="f582e-119">CLEAR OBJ</span><span class="sxs-lookup"><span data-stu-id="f582e-119">CLEAR OBJ</span></span>](clear-obj.md)

[<span data-ttu-id="f582e-120">CONFIGURE APP</span><span class="sxs-lookup"><span data-stu-id="f582e-120">CONFIGURE APP</span></span>](configure-app.md)

[<span data-ttu-id="f582e-121">CONFIGURE PACKAGE</span><span class="sxs-lookup"><span data-stu-id="f582e-121">CONFIGURE PACKAGE</span></span>](configure-package.md)

[<span data-ttu-id="f582e-122">CONFIGURE SERVER</span><span class="sxs-lookup"><span data-stu-id="f582e-122">CONFIGURE SERVER</span></span>](configure-server.md)

[<span data-ttu-id="f582e-123">CONFIGURE TYPE</span><span class="sxs-lookup"><span data-stu-id="f582e-123">CONFIGURE TYPE</span></span>](configure-type.md)

[<span data-ttu-id="f582e-124">DELETE APP</span><span class="sxs-lookup"><span data-stu-id="f582e-124">DELETE APP</span></span>](delete-app.md)

[<span data-ttu-id="f582e-125">DELETE OBJ</span><span class="sxs-lookup"><span data-stu-id="f582e-125">DELETE OBJ</span></span>](delete-obj.md)

[<span data-ttu-id="f582e-126">DELETE PACKAGE</span><span class="sxs-lookup"><span data-stu-id="f582e-126">DELETE PACKAGE</span></span>](delete-package.md)

[<span data-ttu-id="f582e-127">DELETE SERVER</span><span class="sxs-lookup"><span data-stu-id="f582e-127">DELETE SERVER</span></span>](delete-server.md)

[<span data-ttu-id="f582e-128">DELETE TYPE</span><span class="sxs-lookup"><span data-stu-id="f582e-128">DELETE TYPE</span></span>](delete-type.md)

[<span data-ttu-id="f582e-129">HELP</span><span class="sxs-lookup"><span data-stu-id="f582e-129">HELP</span></span>](help.md)

[<span data-ttu-id="f582e-130">LOAD APP</span><span class="sxs-lookup"><span data-stu-id="f582e-130">LOAD APP</span></span>](load-app.md)

[<span data-ttu-id="f582e-131">LOAD PACKAGE</span><span class="sxs-lookup"><span data-stu-id="f582e-131">LOAD PACKAGE</span></span>](load-package.md)

[<span data-ttu-id="f582e-132">LOCK APP</span><span class="sxs-lookup"><span data-stu-id="f582e-132">LOCK APP</span></span>](lock-app.md)

[<span data-ttu-id="f582e-133">PUBLISH APP</span><span class="sxs-lookup"><span data-stu-id="f582e-133">PUBLISH APP</span></span>](publish-app.md)

[<span data-ttu-id="f582e-134">PUBLISH PACKAGE</span><span class="sxs-lookup"><span data-stu-id="f582e-134">PUBLISH PACKAGE</span></span>](publish-package.md)

[<span data-ttu-id="f582e-135">QUERY OBJ</span><span class="sxs-lookup"><span data-stu-id="f582e-135">QUERY OBJ</span></span>](query-obj.md)

[<span data-ttu-id="f582e-136">REFRESH SERVER</span><span class="sxs-lookup"><span data-stu-id="f582e-136">REFRESH SERVER</span></span>](refresh-server.md)

[<span data-ttu-id="f582e-137">REPAIR APP</span><span class="sxs-lookup"><span data-stu-id="f582e-137">REPAIR APP</span></span>](repair-app.md)

[<span data-ttu-id="f582e-138">UNLOAD APP</span><span class="sxs-lookup"><span data-stu-id="f582e-138">UNLOAD APP</span></span>](unload-app.md)

[<span data-ttu-id="f582e-139">UNLOAD PACKAGE</span><span class="sxs-lookup"><span data-stu-id="f582e-139">UNLOAD PACKAGE</span></span>](unload-package.md)

[<span data-ttu-id="f582e-140">UNLOCK APP</span><span class="sxs-lookup"><span data-stu-id="f582e-140">UNLOCK APP</span></span>](unlock-app.md)

[<span data-ttu-id="f582e-141">UNPUBLISH PACKAGE</span><span class="sxs-lookup"><span data-stu-id="f582e-141">UNPUBLISH PACKAGE</span></span>](unpublish-package.md)

 

 





