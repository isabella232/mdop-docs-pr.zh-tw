---
title: 使用自訂 UE-V 範本與 UE-V 產生器
description: 使用自訂 UE-V 範本與 UE-V 產生器
author: dansimp
ms.assetid: 7bb2583a-b032-4800-9bf9-eb33528e1d0d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: db5387254842bfdcf3898089bc12a8e929e3813a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810280"
---
# <span data-ttu-id="308f6-103">使用自訂 UE-V 範本與 UE-V 產生器</span><span class="sxs-lookup"><span data-stu-id="308f6-103">Working with Custom UE-V Templates and the UE-V Generator</span></span>


<span data-ttu-id="308f6-104">為了在使用者電腦之間漫遊應用程式，Microsoft 使用者體驗虛擬化（UE-V）使用*設定位置範本*。</span><span class="sxs-lookup"><span data-stu-id="308f6-104">In order to roam applications between user computers, Microsoft User Experience Virtualization (UE-V) uses *settings location templates*.</span></span> <span data-ttu-id="308f6-105">某些設定位置範本包含在使用者體驗虛擬化中。</span><span class="sxs-lookup"><span data-stu-id="308f6-105">Some settings location templates are included with User Experience Virtualization.</span></span> <span data-ttu-id="308f6-106">您也可以使用 UE-V 發生器建立、編輯或驗證自訂設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="308f6-106">You can also create, edit, or validate custom settings location templates with the UE-V Generator.</span></span>

<span data-ttu-id="308f6-107">UE-V 發生器會監視應用程式，以探索和捕獲應用程式儲存其設定的位置。</span><span class="sxs-lookup"><span data-stu-id="308f6-107">The UE-V Generator monitors an application to discover and capture the locations where the application stores its settings.</span></span> <span data-ttu-id="308f6-108">所監視的應用程式必須是傳統的應用程式。</span><span class="sxs-lookup"><span data-stu-id="308f6-108">The application being monitored must be a traditional application.</span></span> <span data-ttu-id="308f6-109">UE-V 發生器無法為下列應用程式類型建立設定位置範本：</span><span class="sxs-lookup"><span data-stu-id="308f6-109">The UE-V Generator cannot create a settings location template for the following application types:</span></span>

-   <span data-ttu-id="308f6-110">虛擬化應用程式</span><span class="sxs-lookup"><span data-stu-id="308f6-110">Virtualized applications</span></span>

-   <span data-ttu-id="308f6-111">透過終端服務提供的應用程式</span><span class="sxs-lookup"><span data-stu-id="308f6-111">Application offered through terminal services</span></span>

-   <span data-ttu-id="308f6-112">JAVA 應用程式</span><span class="sxs-lookup"><span data-stu-id="308f6-112">Java applications</span></span>

-   <span data-ttu-id="308f6-113">Windows 8 應用程式</span><span class="sxs-lookup"><span data-stu-id="308f6-113">Windows 8 applications</span></span>

## <span data-ttu-id="308f6-114">使用 UE-V 產生器建立 UE-V 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="308f6-114">Create UE-V Settings Location Templates with the UE-V Generator</span></span>


<span data-ttu-id="308f6-115">如何使用 UE-V 發生器來建立設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="308f6-115">How to use the UE-V Generator to create settings location templates.</span></span>

[<span data-ttu-id="308f6-116">使用 UE-V 產生器建立 UE-V 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="308f6-116">Create UE-V Settings Location Templates with the UE-V Generator</span></span>](create-ue-v-settings-location-templates-with-the-ue-v-generator.md)

## <span data-ttu-id="308f6-117">使用 UE-V 產生器編輯 UE-V 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="308f6-117">Edit UE-V Settings Location Templates with the UE-V Generator</span></span>


<span data-ttu-id="308f6-118">如何使用 UE-V 發生器編輯設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="308f6-118">How to use the UE-V Generator to edit settings location templates.</span></span>

[<span data-ttu-id="308f6-119">使用 UE-V 產生器編輯 UE-V 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="308f6-119">Edit UE-V Settings Location Templates with the UE-V Generator</span></span>](edit-ue-v-settings-location-templates-with-the-ue-v-generator.md)

## <span data-ttu-id="308f6-120">使用 UE-V 產生器驗證 UE-V 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="308f6-120">Validate UE-V Settings Location Templates with UE-V Generator</span></span>


<span data-ttu-id="308f6-121">如何使用 UE-V 發生器來驗證在 UE-V 發生器之外修改的設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="308f6-121">How to use the UE-V Generator to validate settings location templates modified outside the UE-V Generator.</span></span>

[<span data-ttu-id="308f6-122">使用 UE-V 產生器驗證 UE-V 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="308f6-122">Validate UE-V Settings Location Templates with UE-V Generator</span></span>](validate-ue-v-settings-location-templates-with-ue-v-generator.md)

## <a href="" id="bkmk-standardnonstandardsettingslocations"></a><span data-ttu-id="308f6-123">標準和非標準的設定位置</span><span class="sxs-lookup"><span data-stu-id="308f6-123">Standard and Nonstandard settings locations</span></span>


<span data-ttu-id="308f6-124">UE-V 發生器可協助您找出應用程式用來儲存設定資訊之設定檔和登錄設定的位置。</span><span class="sxs-lookup"><span data-stu-id="308f6-124">The UE-V Generator helps you identify where applications look for settings files and registry settings that applications use to store settings information.</span></span> <span data-ttu-id="308f6-125">您可以使用 UE-V 發生器來開啟應用程式，以在標準位置中捕捉設定。</span><span class="sxs-lookup"><span data-stu-id="308f6-125">You can use the UE-V Generator to open the application as part of the discovery process to capture settings in standard locations.</span></span> <span data-ttu-id="308f6-126">標準位置包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="308f6-126">Standard locations include the following:</span></span>

-   <span data-ttu-id="308f6-127">[**註冊表設定**]-[HKEY \] 下的 [註冊表位置] **_CURRENT \ _USER**</span><span class="sxs-lookup"><span data-stu-id="308f6-127">**Registry Settings** – Registry locations under **HKEY\_CURRENT\_USER**</span></span>

-   <span data-ttu-id="308f6-128">**應用程式設定**檔案–儲存在 \\**使用者**\\ [使用者名稱 \] 中的檔案檔案**AppData**  \\  **漫遊**</span><span class="sxs-lookup"><span data-stu-id="308f6-128">**Application Settings Files** – Files stored under \\ **Users** \\ \[User name\] \\ **AppData** \\ **Roaming**</span></span>

<span data-ttu-id="308f6-129">UE-V 發生器不包括通常儲存應用程式軟體檔案的位置，在使用者電腦或環境之間無法順利漫遊。</span><span class="sxs-lookup"><span data-stu-id="308f6-129">The UE-V Generator excludes locations which commonly store application software files do not roam well between user computers or environments.</span></span> <span data-ttu-id="308f6-130">UE-V 發生器會將這些位置排除在一起。</span><span class="sxs-lookup"><span data-stu-id="308f6-130">The UE-V Generator excludes these locations.</span></span> <span data-ttu-id="308f6-131">[排除的位置] 如下所示：</span><span class="sxs-lookup"><span data-stu-id="308f6-131">Excluded locations are as follows:</span></span>

-   <span data-ttu-id="308f6-132">HKEY \ _CURRENT \ _USER 登錄的使用者無法寫入值的登錄機碼和檔案</span><span class="sxs-lookup"><span data-stu-id="308f6-132">HKEY\_CURRENT\_USER registry keys and files to which the logged-on user cannot write values</span></span>

-   <span data-ttu-id="308f6-133">HKEY \ _CURRENT \ _USER 與 Windows 作業系統核心功能相關聯的登錄機碼和檔案</span><span class="sxs-lookup"><span data-stu-id="308f6-133">HKEY\_CURRENT\_USER registry keys and files that are associated with the core functionality of the Windows operating system</span></span>

-   <span data-ttu-id="308f6-134">位於 HKEY \ _LOCAL \ _MACHINE hive 中的所有登錄機碼（需要系統管理員許可權，而且可能需要 UAC 協定才能設定）</span><span class="sxs-lookup"><span data-stu-id="308f6-134">All registry keys that are located in the HKEY\_LOCAL\_MACHINE hive (Requires Administrator rights and might require UAC agreement to set)</span></span>

-   <span data-ttu-id="308f6-135">位於 [程式檔案] 目錄中的檔案（需要系統管理員許可權，而且可能需要 UAC 協定才能設定）</span><span class="sxs-lookup"><span data-stu-id="308f6-135">Files that are located in Program Files directories (Requires Administrator rights and might require UAC agreement to set)</span></span>

-   <span data-ttu-id="308f6-136">檔案位於使用者 \\ [使用者名稱 \] \] \\ AppData \\ LocalLow</span><span class="sxs-lookup"><span data-stu-id="308f6-136">Files located in Users \\ \[User name\] \\ AppData \\ LocalLow</span></span>

-   <span data-ttu-id="308f6-137">位於% systemroot% 中的 Windows 作業系統檔案（需要系統管理員許可權，而且可能需要 UAC 協定才能設定）</span><span class="sxs-lookup"><span data-stu-id="308f6-137">Windows operating system files that are located in %systemroot% (Requires Administrator rights and might require UAC agreement to set)</span></span>

<span data-ttu-id="308f6-138">如果您需要儲存在這些位置的登錄機碼和檔案，才能漫遊應用程式設定，您可以在建立範本時，將排除的位置手動新增到 [設定位置] 範本。</span><span class="sxs-lookup"><span data-stu-id="308f6-138">If registry keys and files stored in these locations are required in order to roam application settings, you can manually add the excluded locations to the settings location template during the template creation process.</span></span>

## <span data-ttu-id="308f6-139">此產品的其他資源</span><span class="sxs-lookup"><span data-stu-id="308f6-139">Other resources for this product</span></span>


[<span data-ttu-id="308f6-140">UE-V 1.0 作業</span><span class="sxs-lookup"><span data-stu-id="308f6-140">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

[<span data-ttu-id="308f6-141">管理 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="308f6-141">Administering UE-V 1.0</span></span>](administering-ue-v-10.md)

 

 





