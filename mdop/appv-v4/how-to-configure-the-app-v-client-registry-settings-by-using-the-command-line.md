---
title: 如何使用命令列設定 App-V 用戶端登錄設定
description: 如何使用命令列設定 App-V 用戶端登錄設定
author: dansimp
ms.assetid: 3e3d873f-13d2-402f-97b4-f62d0c399171
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c424f39c8209ca641f6073838ebcb8726acc9e25
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801601"
---
# <span data-ttu-id="605ff-103">如何使用命令列設定 App-V 用戶端登錄設定</span><span class="sxs-lookup"><span data-stu-id="605ff-103">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>


<span data-ttu-id="605ff-104">使用命令列在安裝期間部署並設定應用程式虛擬化（App-v）用戶端之後，可能需要變更一或多個用戶端設定。</span><span class="sxs-lookup"><span data-stu-id="605ff-104">After the Application Virtualization (App-V) Client has been deployed and configured during the installation by using the command line, it might be necessary to change one or more client configuration settings.</span></span> <span data-ttu-id="605ff-105">如此一來，您可以使用下列其中一種方法編輯適當的登錄機碼來完成：</span><span class="sxs-lookup"><span data-stu-id="605ff-105">This is accomplished by editing the appropriate registry keys, using one of the following methods:</span></span>

-   <span data-ttu-id="605ff-106">直接使用登錄編輯程式</span><span class="sxs-lookup"><span data-stu-id="605ff-106">Using the Registry Editor directly</span></span>

-   <span data-ttu-id="605ff-107">使用 .reg 檔案</span><span class="sxs-lookup"><span data-stu-id="605ff-107">Using a .reg file</span></span>

-   <span data-ttu-id="605ff-108">使用「VBScript」或「Windows PowerShell」等指令碼語言</span><span class="sxs-lookup"><span data-stu-id="605ff-108">Using a scripting language such as VBScript or Windows PowerShell</span></span>

<span data-ttu-id="605ff-109">您也可以使用 [ADM] 範本。</span><span class="sxs-lookup"><span data-stu-id="605ff-109">There is also an ADM template that you can use.</span></span> <span data-ttu-id="605ff-110">如需 ADM 範本的詳細資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkId=121835> 。</span><span class="sxs-lookup"><span data-stu-id="605ff-110">For more information about the ADM template, see <https://go.microsoft.com/fwlink/?LinkId=121835>.</span></span>

<span data-ttu-id="605ff-111">**小心** 當您編輯登錄時請小心，因為錯誤可能會使電腦處於無法使用的狀態。</span><span class="sxs-lookup"><span data-stu-id="605ff-111">**Caution** Use care when you edit the registry because errors can leave the computer in an unusable state.</span></span> <span data-ttu-id="605ff-112">請務必遵循與編輯註冊表有關的標準商務慣例。</span><span class="sxs-lookup"><span data-stu-id="605ff-112">Be sure to follow your standard business practices that relate to registry edits.</span></span> <span data-ttu-id="605ff-113">在部署到生產電腦之前，請先在測試環境中徹底測試所有提議的變更。</span><span class="sxs-lookup"><span data-stu-id="605ff-113">Thoroughly test all proposed changes in a test environment before you deploy them to production computers.</span></span>

 

## <span data-ttu-id="605ff-114">本節內容</span><span class="sxs-lookup"><span data-stu-id="605ff-114">In This Section</span></span>


<span data-ttu-id="605ff-115">**重要** 在64位電腦上，下列各節中所述的金鑰和值將會位於 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\Client。</span><span class="sxs-lookup"><span data-stu-id="605ff-115">**Important** On a 64-bit computer, the keys and values described in the following sections will be under HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\Client.</span></span>

 

<a href="" id="how-to-reset-the-filesystem-cache"></a>[<span data-ttu-id="605ff-116">如何重設 FileSystem 快取</span><span class="sxs-lookup"><span data-stu-id="605ff-116">How to Reset the FileSystem Cache</span></span>](how-to-reset-the-filesystem-cache.md)  
<span data-ttu-id="605ff-117">提供重設 FileSystem 快取所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="605ff-117">Provides the information that is required to reset the FileSystem cache.</span></span>

<a href="" id="how-to-change-the-size-of-the-filesystem-cache"></a>[<span data-ttu-id="605ff-118">如何變更 FileSystem 快取的大小</span><span class="sxs-lookup"><span data-stu-id="605ff-118">How to Change the Size of the FileSystem Cache</span></span>](how-to-change-the-size-of-the-filesystem-cache.md)  
<span data-ttu-id="605ff-119">說明如何變更快取的大小。</span><span class="sxs-lookup"><span data-stu-id="605ff-119">Explains how you can change the size of the cache.</span></span>

<a href="" id="how-to-use-the-cache-space-management-feature"></a>[<span data-ttu-id="605ff-120">如何使用快取空間管理功能</span><span class="sxs-lookup"><span data-stu-id="605ff-120">How to Use the Cache Space Management Feature</span></span>](how-to-use-the-cache-space-management-feature.md)  
<span data-ttu-id="605ff-121">說明如何設定快取空間管理功能。</span><span class="sxs-lookup"><span data-stu-id="605ff-121">Describes how you can configure the cache space management feature.</span></span>

<a href="" id="how-to-configure-the-client-log-file"></a>[<span data-ttu-id="605ff-122">如何設定用戶端記錄檔</span><span class="sxs-lookup"><span data-stu-id="605ff-122">How to Configure the Client Log File</span></span>](how-to-configure-the-client-log-file.md)  
<span data-ttu-id="605ff-123">描述控制用戶端記錄檔的各種登錄專案值，以及您可以如何變更它們。</span><span class="sxs-lookup"><span data-stu-id="605ff-123">Describes the various registry key values that control the client log file and how you can change them.</span></span>

<a href="" id="how-to-configure-user-permissions"></a>[<span data-ttu-id="605ff-124">如何設定使用者權限</span><span class="sxs-lookup"><span data-stu-id="605ff-124">How to Configure User Permissions</span></span>](how-to-configure-user-permissions.md)  
<span data-ttu-id="605ff-125">識別控制使用者許可權的登錄機碼，並提供如何變更某些許可權的範例。</span><span class="sxs-lookup"><span data-stu-id="605ff-125">Identifies the registry key that controls the user permissions and gives examples of how you can change some permissions.</span></span>

<a href="" id="how-to-configure-the-client-for-application-package-retrieval"></a>[<span data-ttu-id="605ff-126">如何設定應用程式封裝擷取的用戶端</span><span class="sxs-lookup"><span data-stu-id="605ff-126">How to Configure the Client for Application Package Retrieval</span></span>](how-to-configure-the-client-for-application-package-retrieval.md)  
<span data-ttu-id="605ff-127">說明如何將用戶端設定為從不同來源中檢索套件內容、圖示及檔案類型關聯，並提供幾個正確路徑格式的範例。</span><span class="sxs-lookup"><span data-stu-id="605ff-127">Explains how to configure the client to retrieve package content, icons, and file type associations from different sources, and provides several examples of the correct path format.</span></span>

<a href="" id="how-to-configure-the-client-for-disconnected-operation-mode"></a>[<span data-ttu-id="605ff-128">如何設定中斷連線的操作模式的用戶端</span><span class="sxs-lookup"><span data-stu-id="605ff-128">How to Configure the Client for Disconnected Operation Mode</span></span>](how-to-configure-the-client-for-disconnected-operation-mode.md)  
<span data-ttu-id="605ff-129">提供有關如何設定與中斷式作業模式相關聯之各種設定的資訊。</span><span class="sxs-lookup"><span data-stu-id="605ff-129">Provides information about how to configure the various settings associated with disconnected operations mode.</span></span>

<a href="" id="how-to-configure-shortcut-and-file-type-association-behavior"></a>[<span data-ttu-id="605ff-130">如何設定捷徑和檔案類型關聯行為</span><span class="sxs-lookup"><span data-stu-id="605ff-130">How to Configure Shortcut and File Type Association Behavior</span></span>](how-to-configure-shortcut-and-file-type-association-behavior-46-only.md)  
<span data-ttu-id="605ff-131">描述在 App-v 用戶端中控制快速鍵與檔案類型關聯的登錄項值，並提供如何進行設定的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="605ff-131">Describes the registry key values that control shortcuts and file type associations in the App-V client, and provides details on how to configure them.</span></span>

## <span data-ttu-id="605ff-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="605ff-132">Related topics</span></span>


[<span data-ttu-id="605ff-133">Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="605ff-133">Application Virtualization Client</span></span>](application-virtualization-client.md)

 

 





