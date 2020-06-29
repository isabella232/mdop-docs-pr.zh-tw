---
title: 關於共用封裝加速器頁面
description: 關於共用封裝加速器頁面
author: dansimp
ms.assetid: 9630cde0-e2c3-476f-8fa1-58b3c9f7d3f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 34fe55d910a7532f011b239ff5b8162aa9240f32
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802438"
---
# <span data-ttu-id="130bd-103">關於共用封裝加速器頁面</span><span class="sxs-lookup"><span data-stu-id="130bd-103">About Sharing Package Accelerators Page</span></span>


<span data-ttu-id="130bd-104">下列資訊提供如何共用套件加速器的最佳做法資訊。</span><span class="sxs-lookup"><span data-stu-id="130bd-104">This following information provides best practice information about how to share Package Accelerators.</span></span> <span data-ttu-id="130bd-105">如果您打算共用套件加速器檔案，諸如電腦名稱稱、使用者帳戶資訊等資訊，以及有關轉換中所包含之應用程式的相關資訊，都可能包含在封裝加速器檔案中。</span><span class="sxs-lookup"><span data-stu-id="130bd-105">If you plan to share Package Accelerators files, information such as computer names, user account information, and information about applications included in the transforms might be included in the Package Accelerators file.</span></span> <span data-ttu-id="130bd-106">您應該檢查與虛擬應用程式套件相關聯的任何設定或設定檔，以確保應用程式不包含任何個人資訊。此頁面包含下列元素。</span><span class="sxs-lookup"><span data-stu-id="130bd-106">You should review any settings or configuration files associated with the virtual application package to ensure the applications do not contain any personal information.This page contains the following elements.</span></span>

-   <span data-ttu-id="130bd-107">[使用者**名稱**]。</span><span class="sxs-lookup"><span data-stu-id="130bd-107">**Username**.</span></span> <span data-ttu-id="130bd-108">當您登入執行 Microsoft App-v 排序器的電腦時，您應該使用一般的使用者帳戶，例如內建的**系統管理員**帳戶。</span><span class="sxs-lookup"><span data-stu-id="130bd-108">When you log on to the computer running the Microsoft App-V Sequencer, you should use a generic user account, such as the built-in **administrator** account.</span></span> <span data-ttu-id="130bd-109">您不應該使用以現有的使用者名稱為基礎的帳戶。</span><span class="sxs-lookup"><span data-stu-id="130bd-109">You should not use an account that is based on an existing user name.</span></span>

-   <span data-ttu-id="130bd-110">[**電腦名稱稱**]。</span><span class="sxs-lookup"><span data-stu-id="130bd-110">**Computer Name**.</span></span> <span data-ttu-id="130bd-111">指定執行排序器之電腦的一般、非識別名稱。</span><span class="sxs-lookup"><span data-stu-id="130bd-111">Specify a general, non-identifying name of the computer running the Sequencer.</span></span>

-   <span data-ttu-id="130bd-112">**伺服器 URL**。</span><span class="sxs-lookup"><span data-stu-id="130bd-112">**Server URL**.</span></span> <span data-ttu-id="130bd-113">在 App-v 排序器主控台的 [**部署**] 索引標籤上，使用伺服器 URL 設定資訊的預設設定。</span><span class="sxs-lookup"><span data-stu-id="130bd-113">In the App-V Sequencer console, on the **Deployment** tab, use the default settings for the server URL configuration information.</span></span>

-   <span data-ttu-id="130bd-114">**應用程式**。</span><span class="sxs-lookup"><span data-stu-id="130bd-114">**Applications**.</span></span> <span data-ttu-id="130bd-115">如果您不想在建立套件加速器時共用執行 Sequencer 之電腦上所安裝的應用程式清單，您必須刪除**appv\_manifest.xml**檔案。</span><span class="sxs-lookup"><span data-stu-id="130bd-115">If you do not want to share the list of applications that were installed on the computer running the Sequencer when you created the Package Accelerator, you must delete the **appv\_manifest.xml** file.</span></span> <span data-ttu-id="130bd-116">此檔案位於虛擬應用程式套件的套件根目錄中。</span><span class="sxs-lookup"><span data-stu-id="130bd-116">This file is located in the package root directory of the virtual application package.</span></span>

## <span data-ttu-id="130bd-117">相關主題</span><span class="sxs-lookup"><span data-stu-id="130bd-117">Related topics</span></span>


[<span data-ttu-id="130bd-118">建立封裝加速器精靈 (AppV 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="130bd-118">Create Package Accelerator Wizard (AppV 4.6 SP1)</span></span>](create-package-accelerator-wizard--appv-46-sp1-.md)

[<span data-ttu-id="130bd-119">關於 App-V 封裝加速器 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="130bd-119">About App-V Package Accelerators (App-V 4.6 SP1)</span></span>](about-app-v-package-accelerators--app-v-46-sp1-.md)

 

 





