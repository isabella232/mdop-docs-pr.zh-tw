---
title: 如何設定映像預先設置
description: 如何設定映像預先設置
author: dansimp
ms.assetid: 92781b5a-208f-45a4-a078-ee90cf9efd9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 38ddb7a69845aa4dbcb9cbd16b84dedc04438732
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811738"
---
# <span data-ttu-id="e47e8-103">如何設定映像預先設置</span><span class="sxs-lookup"><span data-stu-id="e47e8-103">How to Configure Image Pre-staging</span></span>


<span data-ttu-id="e47e8-104">**記事** 影像預暫存只適用于初始影像下載。</span><span class="sxs-lookup"><span data-stu-id="e47e8-104">**Note** Image pre-staging is useful only for the initial image download.</span></span> <span data-ttu-id="e47e8-105">影像更新不支援此功能。</span><span class="sxs-lookup"><span data-stu-id="e47e8-105">It is not supported for image update.</span></span>

 

## <span data-ttu-id="e47e8-106">如何設定映像預先設置</span><span class="sxs-lookup"><span data-stu-id="e47e8-106">How to Configure Image Pre-staging</span></span>


**<span data-ttu-id="e47e8-107">若要設定影像預暫存</span><span class="sxs-lookup"><span data-stu-id="e47e8-107">To configure image pre-staging</span></span>**

1.  <span data-ttu-id="e47e8-108">在用戶端電腦上的 [影像存放區目錄] 底下，建立預先暫存映射的資料夾，並將其命名為*Med-v 影像*。</span><span class="sxs-lookup"><span data-stu-id="e47e8-108">On the client computer, under the image store directory, create a folder for the pre-staging image, and name it *MED-V Images*.</span></span>

    <span data-ttu-id="e47e8-109">**記事** 這個資料夾必須稱為*Med-v 影像*。</span><span class="sxs-lookup"><span data-stu-id="e47e8-109">**Note** This folder must be called *MED-V Images*.</span></span>

     

2.  <span data-ttu-id="e47e8-110">在 MED-V 影像資料夾中，建立子資料夾，並將其命名為*PrestagedImages*。</span><span class="sxs-lookup"><span data-stu-id="e47e8-110">Inside the MED-V Images folder, create a subfolder and name it *PrestagedImages*.</span></span>

    <span data-ttu-id="e47e8-111">**記事** 此資料夾必須呼叫*PrestagedImages*。</span><span class="sxs-lookup"><span data-stu-id="e47e8-111">**Note** This folder must be called *PrestagedImages*.</span></span>

     

3.  <span data-ttu-id="e47e8-112">若要將存取控制清單（ACL）安全性套用至*Med-v 圖像*資料夾，請設定下列 ACL：</span><span class="sxs-lookup"><span data-stu-id="e47e8-112">To apply Access Control Lists (ACL) security to the *MED-V Images* folder, set the following ACL:</span></span>

    **<span data-ttu-id="e47e8-113">NT AUTHORITY\\Authenticated 使用者：（OI）（CI）（特殊存取權）</span><span class="sxs-lookup"><span data-stu-id="e47e8-113">NT AUTHORITY\\Authenticated Users:(OI)(CI)(special access:)</span></span>**

                                             **READ\_CONTROL**

                                    **SYNCHRONIZE**

                                    **FILE\_GENERIC\_READ**

                                    **FILE\_READ\_DATA**

    **                                 <span data-ttu-id="e47e8-114">檔案 \ _APPEND \ _DATA</span><span class="sxs-lookup"><span data-stu-id="e47e8-114">FILE\_APPEND\_DATA</span></span>**

                                    **FILE\_READ\_EA**

                                    **FILE\_READ\_ATTRIBUTES**

    **<span data-ttu-id="e47e8-115">NT AUTHORITY\\SYSTEM：（OI）（CI） F</span><span class="sxs-lookup"><span data-stu-id="e47e8-115">NT AUTHORITY\\SYSTEM:(OI)(CI)F</span></span>**

    **<span data-ttu-id="e47e8-116">BUILTIN\\Administrators：（OI）（CI） F</span><span class="sxs-lookup"><span data-stu-id="e47e8-116">BUILTIN\\Administrators:(OI)(CI)F</span></span>**

    <span data-ttu-id="e47e8-117">**記事** 建議將 ACL 安全性套用至*Med-v 影像*資料夾。</span><span class="sxs-lookup"><span data-stu-id="e47e8-117">**Note** It is recommended to apply ACL security to the *MED-V Images* folder.</span></span>

     

4.  <span data-ttu-id="e47e8-118">若要將 ACL 安全性套用至*PrestagedImages*資料夾，請設定下列 ACL：</span><span class="sxs-lookup"><span data-stu-id="e47e8-118">To apply ACL security to the *PrestagedImages* folder, set the following ACL:</span></span>

    **<span data-ttu-id="e47e8-119">NT AUTHORITY\\Authenticated 使用者：（OI）（CI）（特殊存取權）</span><span class="sxs-lookup"><span data-stu-id="e47e8-119">NT AUTHORITY\\Authenticated Users:(OI)(CI)(special access:)</span></span>**

    **<span data-ttu-id="e47e8-120">READ \ _CONTROL</span><span class="sxs-lookup"><span data-stu-id="e47e8-120">READ\_CONTROL</span></span>**

    **<span data-ttu-id="e47e8-121">試</span><span class="sxs-lookup"><span data-stu-id="e47e8-121">SYNCHRONIZE</span></span>**

    **<span data-ttu-id="e47e8-122">檔案 \ _GENERIC \ _READ</span><span class="sxs-lookup"><span data-stu-id="e47e8-122">FILE\_GENERIC\_READ</span></span>**

    **<span data-ttu-id="e47e8-123">檔案 \ _READ \ _DATA</span><span class="sxs-lookup"><span data-stu-id="e47e8-123">FILE\_READ\_DATA</span></span>**

    **<span data-ttu-id="e47e8-124">檔案 \ _READ \ _EA</span><span class="sxs-lookup"><span data-stu-id="e47e8-124">FILE\_READ\_EA</span></span>**

    **<span data-ttu-id="e47e8-125">檔案 \ _READ \ _ATTRIBUTES</span><span class="sxs-lookup"><span data-stu-id="e47e8-125">FILE\_READ\_ATTRIBUTES</span></span>**

    **<span data-ttu-id="e47e8-126">NT AUTHORITY\\SYSTEM：（OI）（CI） F</span><span class="sxs-lookup"><span data-stu-id="e47e8-126">NT AUTHORITY\\SYSTEM:(OI)(CI)F</span></span>**

    **<span data-ttu-id="e47e8-127">BUILTIN\\Administrators：（OI）（CI） F</span><span class="sxs-lookup"><span data-stu-id="e47e8-127">BUILTIN\\Administrators:(OI)(CI)F</span></span>**

    <span data-ttu-id="e47e8-128">**記事** 建議將 ACL 安全性套用至*PrestagedImages*資料夾。</span><span class="sxs-lookup"><span data-stu-id="e47e8-128">**Note** It is recommended to apply ACL security to the *PrestagedImages* folder.</span></span>

     

5.  <span data-ttu-id="e47e8-129">將圖像檔案（CKM 和索引檔案）推入 [ *PrestagedImages* ] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="e47e8-129">Push the image files (CKM and INDEX files) to the *PrestagedImages* folder.</span></span>

    <span data-ttu-id="e47e8-130">**記事** 在圖像檔案推到前階段資料夾之後，建議您執行資料完整性檢查，並將檔案標示為唯讀。</span><span class="sxs-lookup"><span data-stu-id="e47e8-130">**Note** After the image files have been pushed to the pre-stage folder, it is recommended to run a data integrity check and to mark the files as read-only.</span></span>

     

6.  <span data-ttu-id="e47e8-131">在 MED-V 用戶端安裝中包含下列參數： *Client.MSI VMSFOLDER = "C:\\MED-V 影像"*。</span><span class="sxs-lookup"><span data-stu-id="e47e8-131">Include the following parameter in the MED-V client installation: *Client.MSI VMSFOLDER=”C:\\MED-V Images”*.</span></span>

## <span data-ttu-id="e47e8-132">如何更新前階段位置</span><span class="sxs-lookup"><span data-stu-id="e47e8-132">How to Update the Pre-stage Location</span></span>


**<span data-ttu-id="e47e8-133">更新前階段位置</span><span class="sxs-lookup"><span data-stu-id="e47e8-133">To update the pre-stage location</span></span>**

1.  <span data-ttu-id="e47e8-134">登錄機碼（ *PrestagedImagesPath*）指向預設的影像位置。</span><span class="sxs-lookup"><span data-stu-id="e47e8-134">The registry key, *PrestagedImagesPath*, points to the default image location.</span></span> <span data-ttu-id="e47e8-135">它位於下列目錄中：</span><span class="sxs-lookup"><span data-stu-id="e47e8-135">It is located in the following directory:</span></span>

    -   <span data-ttu-id="e47e8-136">在 x86</span><span class="sxs-lookup"><span data-stu-id="e47e8-136">On an x86 -</span></span> `KEY_LOCAL_MACHINE\SOFTWARE\Kidaro`

    -   <span data-ttu-id="e47e8-137">在 x64</span><span class="sxs-lookup"><span data-stu-id="e47e8-137">On an x64 -</span></span> `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432node`

2.  <span data-ttu-id="e47e8-138">如果圖像位於不同的位置，請變更路徑。</span><span class="sxs-lookup"><span data-stu-id="e47e8-138">If the image is in a different location, change the path.</span></span>

 

 





