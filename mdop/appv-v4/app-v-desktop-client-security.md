---
title: App-V Desktop Client 安全性
description: App-V Desktop Client 安全性
author: dansimp
ms.assetid: 216b9c16-7bb4-4f94-b9d8-810501285008
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 26add6f855780113613cf1591c41722643954477
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809284"
---
# <span data-ttu-id="613ab-103">App-V Desktop Client 安全性</span><span class="sxs-lookup"><span data-stu-id="613ab-103">App-V Desktop Client Security</span></span>


<span data-ttu-id="613ab-104">App-v Desktop 用戶端提供了許多舊版產品無法使用的安全性增強功能。</span><span class="sxs-lookup"><span data-stu-id="613ab-104">The App-V Desktop Client provides many security enhancements that were not available in previous versions of the product.</span></span> <span data-ttu-id="613ab-105">這些變更預設會提供較高的安全性等級，以及設定用戶端設定的設定。</span><span class="sxs-lookup"><span data-stu-id="613ab-105">These changes provide higher levels of security by default and through configuration of the client settings.</span></span>

<span data-ttu-id="613ab-106">**記事** 當您在電腦上安裝 app-v Desktop 用戶端時，軟體會預設為最安全的設定。</span><span class="sxs-lookup"><span data-stu-id="613ab-106">**Note** When you install the App-V Desktop Client on a computer, the software defaults to the most secure settings.</span></span> <span data-ttu-id="613ab-107">不過，當您升級時，用戶端的先前設定就會繼續。</span><span class="sxs-lookup"><span data-stu-id="613ab-107">However, when upgrading, the previous settings of the client persist.</span></span>

 

<span data-ttu-id="613ab-108">根據預設，App-v Desktop 用戶端只會設定為允許非系統管理使用者執行發佈更新與資料流程應用程式所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="613ab-108">By default, the App-V Desktop Client is configured only with the permissions required to allow a non-administrative user to perform a publishing refresh and stream applications.</span></span> <span data-ttu-id="613ab-109">在 App-v Desktop 用戶端中提供的其他安全性增強功能包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="613ab-109">Additional security enhancements provided in the App-V Desktop Client include the following:</span></span>

-   <span data-ttu-id="613ab-110">根據預設，只允許發佈重新整理程式來更新 OSD 快取。</span><span class="sxs-lookup"><span data-stu-id="613ab-110">By default, an OSD cache update is allowed only by the publishing refresh process.</span></span>

-   <span data-ttu-id="613ab-111">`sftlog.txt`只有對用戶端有本機管理存取權的帳戶才能存取 () 的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="613ab-111">The log file (`sftlog.txt`) is accessible only by accounts with local administrative access to the client.</span></span>

-   <span data-ttu-id="613ab-112">記錄檔現在有最大大小。</span><span class="sxs-lookup"><span data-stu-id="613ab-112">The log file now has a maximum size.</span></span>

-   <span data-ttu-id="613ab-113">記錄檔案是透過 [封存設定] 進行管理。</span><span class="sxs-lookup"><span data-stu-id="613ab-113">The log files are managed through archive settings.</span></span>

-   <span data-ttu-id="613ab-114">現在已執行系統事件記錄。</span><span class="sxs-lookup"><span data-stu-id="613ab-114">System Event logging is now performed.</span></span>

## <span data-ttu-id="613ab-115">權限</span><span class="sxs-lookup"><span data-stu-id="613ab-115">Permissions</span></span>


<span data-ttu-id="613ab-116">安裝桌面用戶端之後，您可以透過 MMC 或使用 Microsoft 所提供的 ADM 範本，在個別用戶端上設定其他安全性設定。</span><span class="sxs-lookup"><span data-stu-id="613ab-116">After you install the Desktop Client, you can configure other security settings through the MMC, or on an individual client by using the registry or the ADM Template provided by Microsoft.</span></span> <span data-ttu-id="613ab-117">App-v Desktop 用戶端具有您可以設定的許可權，以限制非系統管理員使用者存取桌面用戶端的所有功能。</span><span class="sxs-lookup"><span data-stu-id="613ab-117">The App-V Desktop Client has permissions that you can set to restrict non-administrative users from accessing all the features of the Desktop Client.</span></span> <span data-ttu-id="613ab-118">如需許可權的完整清單，請參閱 App-v 用戶端說明檔案或 App-v 操作指南。</span><span class="sxs-lookup"><span data-stu-id="613ab-118">For a full list of permissions, please see the App-V Client Help file or App-V Operations Guide.</span></span>

<span data-ttu-id="613ab-119">**重要** 請謹慎考慮變更許可權的後果，特別是在多位使用者所共用的系統上（例如終端伺服器）。</span><span class="sxs-lookup"><span data-stu-id="613ab-119">**Important** Carefully consider the consequences of changing access rights, especially on systems that are shared by multiple users, such as Terminal Servers.</span></span>

 

<span data-ttu-id="613ab-120">**記事** 如果環境中的使用者擁有其電腦的本機系統管理員許可權，則會略過許可權。</span><span class="sxs-lookup"><span data-stu-id="613ab-120">**Note** If users in the environment have local administrator privileges for their computers, the permissions are ignored.</span></span>

 

### <span data-ttu-id="613ab-121">ADM 範本</span><span class="sxs-lookup"><span data-stu-id="613ab-121">ADM Template</span></span>

<span data-ttu-id="613ab-122">Microsoft Application Virtualization (App-v) 引入 ADM 範本，您可以用來透過群組原則設定最常見的用戶端設定。</span><span class="sxs-lookup"><span data-stu-id="613ab-122">Microsoft Application Virtualization (App-V) introduces an ADM Template that you can use to configure the most common client settings through Group Policies.</span></span> <span data-ttu-id="613ab-123">此範本可讓系統管理員透過集中式管理模型來實施及變更許多用戶端設定。</span><span class="sxs-lookup"><span data-stu-id="613ab-123">This template enables administrators to implement and change many of the client settings through a centralized administration model.</span></span> <span data-ttu-id="613ab-124">ADM 範本中提供的部分設定為安全性設定。</span><span class="sxs-lookup"><span data-stu-id="613ab-124">Some of the settings available in the ADM Template are security settings.</span></span>

<span data-ttu-id="613ab-125">**重要** 使用 ADM 範本時，請記住設定是群組原則喜好設定，而不是完全管理的群組原則。</span><span class="sxs-lookup"><span data-stu-id="613ab-125">**Important** When using the ADM Template, remember that the settings are Group Policy preference settings and not fully managed Group Policies.</span></span>

 

<span data-ttu-id="613ab-126">如需 ADM 範本的完整描述、特定設定，以及在您的環境中成功部署用戶端的指導方針，請參閱 App V ADM 範本白皮書 [https://go.microsoft.com/fwlink/LinkId=122063](https://go.microsoft.com/fwlink/?LinkId=122063) 。</span><span class="sxs-lookup"><span data-stu-id="613ab-126">For a full description of the ADM Template, the specific settings, and guidance to successfully deploy clients in your environment, see the App-V ADM Template white paper at [https://go.microsoft.com/fwlink/LinkId=122063](https://go.microsoft.com/fwlink/?LinkId=122063).</span></span>

## <span data-ttu-id="613ab-127">移除 OSD 檔案類型關聯</span><span class="sxs-lookup"><span data-stu-id="613ab-127">Removing OSD File Type Associations</span></span>


<span data-ttu-id="613ab-128">如果您的組織不需要使用者直接從 OSD 檔案開啟應用程式，您可以移除用戶端上的檔案類型關聯，以加強安全性。</span><span class="sxs-lookup"><span data-stu-id="613ab-128">If your organization does not require users to open applications directly from an OSD file, you can enhance security by removing the file type associations on the client.</span></span> <span data-ttu-id="613ab-129">`HKEY_CURRENT_USERS`使用 [登錄編輯程式] 移除 OSD 的按鍵 `Softgird.osd.file` 。</span><span class="sxs-lookup"><span data-stu-id="613ab-129">Remove the `HKEY_CURRENT_USERS` keys for OSD and `Softgird.osd.file` by using the registry editor.</span></span> <span data-ttu-id="613ab-130">您可以將此程式置於登入腳本或安裝後腳本中，以自動化這些變更。</span><span class="sxs-lookup"><span data-stu-id="613ab-130">You can put this process into a logon script or into a post-installation script to automate these changes.</span></span>

 

 





