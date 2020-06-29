---
title: Application Virtualization Client 的疑難排解資訊
description: Application Virtualization Client 的疑難排解資訊
author: dansimp
ms.assetid: 260a8dad-847f-4ec0-b7dd-6e6bc52017ed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c2ab332f5f3b7f8cdc40f6d35e8712d55028a60
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800770"
---
# <span data-ttu-id="4248c-103">Application Virtualization Client 的疑難排解資訊</span><span class="sxs-lookup"><span data-stu-id="4248c-103">Troubleshooting Information for the Application Virtualization Client</span></span>


<span data-ttu-id="4248c-104">本主題包含一些資訊，您可以用來針對應用程式虛擬化（App-v）用戶端的各種問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="4248c-104">This topic includes information that you can use to troubleshoot various issues on the Application Virtualization (App-V) Client.</span></span>

## <span data-ttu-id="4248c-105">發佈更新非常慢</span><span class="sxs-lookup"><span data-stu-id="4248c-105">Publishing Refresh Is Very Slow</span></span>


<span data-ttu-id="4248c-106">如果在特定電腦上發佈重新整理所需的時間比預期更長，且如果用戶端設定為使用**IconSourceRoot**設定，請判斷**IconSourceRoot**是否包含不正確 URL。</span><span class="sxs-lookup"><span data-stu-id="4248c-106">If publishing refresh on a specific computer takes much longer than expected and if the client is configured to use the **IconSourceRoot** setting, determine whether **IconSourceRoot** contains a nonvalid URL.</span></span> <span data-ttu-id="4248c-107">不完整的 URL 會在發佈重新整理時產生很長的延遲。</span><span class="sxs-lookup"><span data-stu-id="4248c-107">A nonvalid URL will cause very long delays during publishing refresh.</span></span>

## <span data-ttu-id="4248c-108">使用者無法連線到伺服器並進入中斷連接的操作模式</span><span class="sxs-lookup"><span data-stu-id="4248c-108">Users Cannot Connect to the Server and Go into Disconnected Operations Mode</span></span>


<span data-ttu-id="4248c-109">當您使用以 RTSPS 通訊協定設定的 App-v 管理伺服器時，如果使用者無法連線並進入中斷連接的操作模式，請判斷在伺服器上使用的憑證是否有效。</span><span class="sxs-lookup"><span data-stu-id="4248c-109">When you are using an App-V Management Server configured with the RTSPS protocol, if the users are unable to connect and they go into disconnected operations mode, determine whether the certificate that is being used on the server is valid.</span></span> <span data-ttu-id="4248c-110">不正確憑證會防止使用者連線，並會導致使用者進入斷開連接的操作模式。</span><span class="sxs-lookup"><span data-stu-id="4248c-110">A nonvalid certificate will prevent users from connecting and will cause them to go into disconnected operations mode.</span></span>

## <a href="" id="users-experience-slow-performance-when-applications-are-not-fully-cached-"></a><span data-ttu-id="4248c-111">當應用程式未完全緩存時，使用者遇到效能降低的問題</span><span class="sxs-lookup"><span data-stu-id="4248c-111">Users Experience Slow Performance When Applications Are Not Fully Cached</span></span>


<span data-ttu-id="4248c-112">當應用程式不完全快取時，使用者在啟動或使用應用程式時，有時候可能會遇到暫時緩慢或斷斷續續的效能。</span><span class="sxs-lookup"><span data-stu-id="4248c-112">When applications are not fully cached, users might occasionally experience temporary slow or intermittent performance when they start or use the application.</span></span> <span data-ttu-id="4248c-113">有幾個可能的原因，例如，當 App-v 用戶端正在自動載入應用程式的程式中，或正在處理不連續的要求時，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="4248c-113">There are several possible reasons this can occur—for example, when the App-V Client is in the process of auto-loading an application or when an Out Of Sequence request is being processed.</span></span> <span data-ttu-id="4248c-114">當應用程式完全緩存時，這些問題就不會再發生。</span><span class="sxs-lookup"><span data-stu-id="4248c-114">When the applications are fully cached, these problems will no longer occur.</span></span>

## <a href="" id="error-displayed-after-an-update-is-removed-"></a><span data-ttu-id="4248c-115">移除更新後顯示錯誤</span><span class="sxs-lookup"><span data-stu-id="4248c-115">Error Displayed After an Update Is Removed</span></span>


<span data-ttu-id="4248c-116">您必須使用正確的 Windows Installer 3.1 命令格式，才能從應用程式 V 用戶端移除更新，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4248c-116">You must use the correct Windows Installer 3.1 command format to remove an update from the App-V Client, as follows:</span></span>

`Msiexec /I {F82584A0-D706-4D2D-9BC1-7E6D8BE3BB0F} MSIPATCHREMOVE={BE3DD018-9A1F-40FD-9538-C0A995CBD254} /qb /l*v "Uninstall.log"`

<span data-ttu-id="4248c-117">使用較舊的命令格式時，會 `msiexec /package <GUID> /uninstall <GUID>` 導致錯誤6003「Application Virtualization 用戶端無法啟動」。</span><span class="sxs-lookup"><span data-stu-id="4248c-117">Using the older command format `msiexec /package <GUID> /uninstall <GUID>` will cause error 6003 "Application Virtualization client could not be started".</span></span>

## <span data-ttu-id="4248c-118">當您嘗試啟動應用程式時，發生錯誤碼 0A-0000E01E</span><span class="sxs-lookup"><span data-stu-id="4248c-118">Error Code 0A-0000E01E Occurs When You Try to Start an Application</span></span>


<span data-ttu-id="4248c-119">錯誤碼 0A-0000E01E 表示順序式應用程式套件可能已損毀。</span><span class="sxs-lookup"><span data-stu-id="4248c-119">Error code 0A-0000E01E indicates that the sequenced application package might be corrupt.</span></span> <span data-ttu-id="4248c-120">解決方案是 resequence 套件。</span><span class="sxs-lookup"><span data-stu-id="4248c-120">The solution is to resequence the package.</span></span>

## <span data-ttu-id="4248c-121">使用者無法存取他們在 Q：磁片磁碟機上建立的檔案</span><span class="sxs-lookup"><span data-stu-id="4248c-121">Users Cannot Access Files They Have Created on the Q: Drive</span></span>


<span data-ttu-id="4248c-122">如果使用者將檔案儲存到**Q：** 磁片磁碟機，他們就無法取得磁片磁碟機的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="4248c-122">If users save files to the **Q:** drive, they cannot retrieve them because they do not have read rights to the drive.</span></span> <span data-ttu-id="4248c-123">使用者不應該將檔案儲存至**Q：** 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="4248c-123">Users should not save files to the **Q:** drive.</span></span>

## <span data-ttu-id="4248c-124">出現1D1 錯誤的使用者</span><span class="sxs-lookup"><span data-stu-id="4248c-124">User Is Prompted with a 1D1 Error</span></span>


<span data-ttu-id="4248c-125">當檔案流式 URL 在開啟的軟體描述項（OSD）檔案中設定不正確時，App-v 用戶端會傳回1d1 錯誤，而不是「找不到檔案」錯誤。</span><span class="sxs-lookup"><span data-stu-id="4248c-125">When the file streaming URL is incorrectly set in the Open Software Descriptor (OSD) file, the App-V Client returns a 1d1 error instead of a “file not found” error.</span></span> <span data-ttu-id="4248c-126">此錯誤表示應用程式啟動失敗，且使用者已強制進入中斷線上作業模式。</span><span class="sxs-lookup"><span data-stu-id="4248c-126">This error indicates that the application start failed and the user has been forced into disconnected operations mode.</span></span> <span data-ttu-id="4248c-127">修正檔案流式處理 URL。</span><span class="sxs-lookup"><span data-stu-id="4248c-127">Correct the file streaming URL.</span></span>

## <span data-ttu-id="4248c-128">與某些應用程式相關聯的不正確圖示</span><span class="sxs-lookup"><span data-stu-id="4248c-128">Incorrect Icons Associated with Some Applications</span></span>


<span data-ttu-id="4248c-129">若要在發佈作業中使用圖示，App-v 用戶端首先會判斷它是否已有圖示的快取複本，方法是在圖示快取中，查看原始來源路徑符合發佈作業所提供之圖示路徑的專案。</span><span class="sxs-lookup"><span data-stu-id="4248c-129">When an icon is to be used in a publishing operation, the App-V Client first determines whether it already has a cached copy of the icon, by looking in the icon cache for an item whose original source path matches the path of the icon given to the publishing operation.</span></span> <span data-ttu-id="4248c-130">如果 App-v 用戶端找到一個相符的專案，則會使用已緩存的圖示;否則，它會將新的圖示下載到快取中。</span><span class="sxs-lookup"><span data-stu-id="4248c-130">If the App-V Client finds a match, it will use the already-cached icon; otherwise, it will download the new icon into the cache.</span></span> <span data-ttu-id="4248c-131">如果圖示的路徑是臨時目錄，或是在新的圖示或套件中重複使用，則在快取中的查閱可能會從先前的操作中挑選錯誤的圖示。</span><span class="sxs-lookup"><span data-stu-id="4248c-131">If the path to the icon is a scratch directory or if it gets reused for new icons or packages, the lookup in the cache might pick the wrong icon from a previous operation.</span></span>

## <span data-ttu-id="4248c-132">啟動應用程式時，系統會提示使用者輸入認證</span><span class="sxs-lookup"><span data-stu-id="4248c-132">Users Are Prompted for Credentials When Starting an Application</span></span>


<span data-ttu-id="4248c-133">如果使用者嘗試啟動的虛擬應用程式是系統管理員限制存取權，使用者可能會收到輸入認證的提示。</span><span class="sxs-lookup"><span data-stu-id="4248c-133">If a user attempts to start a virtual application to which the system administrator has restricted access, the user might be prompted to enter credentials.</span></span> <span data-ttu-id="4248c-134">使用者應該輸入擁有啟動該應用程式許可權的帳戶的使用者名稱和密碼，然後按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="4248c-134">The user should type the user name and password for an account that has permission to launch the application and then press ENTER.</span></span>

## <span data-ttu-id="4248c-135">將 App-v 用戶端升級到版本4.5 之後，發佈更新失敗</span><span class="sxs-lookup"><span data-stu-id="4248c-135">Publishing Refresh Fails After Upgrading the App-V Client to Version 4.5</span></span>


<span data-ttu-id="4248c-136">如果使用者資料目錄之前放在非標準位置（%*AllUsersProfile*%\\Documents\\SoftGrid Client\\Users\\%*username*%），在電腦上沒有系統管理員許可權的使用者將會發現發佈更新在升級 app-v 用戶端後失敗。</span><span class="sxs-lookup"><span data-stu-id="4248c-136">If the user data directory was previously placed in a non-standard location (%*AllUsersProfile*%\\Documents\\SoftGrid Client\\Users\\%*username*%), users who do not have administrator privileges on the computer will find that publishing refresh fails after the App-V Client is upgraded.</span></span> <span data-ttu-id="4248c-137">在升級期間，App-V 用戶端全域資料目錄及其所有子目錄都是以系統管理員的限制存取權進行設定。</span><span class="sxs-lookup"><span data-stu-id="4248c-137">During the upgrade, the App-V Client global data directory and all its subdirectories are configured with restricted access rights for administrators only.</span></span> <span data-ttu-id="4248c-138">您可以在升級前變更使用者資料目錄，讓它不是全域資料目錄的子目錄，來避免這個問題。</span><span class="sxs-lookup"><span data-stu-id="4248c-138">You can avoid this problem by changing the user data directory before upgrading so that it is not a subdirectory of the global data directory.</span></span>

## <span data-ttu-id="4248c-139">安裝失敗後需要重新開機</span><span class="sxs-lookup"><span data-stu-id="4248c-139">Reboot Required After Install Failure</span></span>


<span data-ttu-id="4248c-140">如果用戶端安裝因任何原因而失敗，而且後續嘗試安裝用戶端也失敗，請檢查 Windows 安裝程式記錄檔，看看是否顯示「sftplay 失敗，error = 1072」錯誤。</span><span class="sxs-lookup"><span data-stu-id="4248c-140">If the client install fails for any reason and if subsequent attempts to install the client also fail, check the Windows Installer log to see whether it shows an error “sftplay failed, error=1072”.</span></span> <span data-ttu-id="4248c-141">如果是，請在再次嘗試安裝用戶端之前重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="4248c-141">If so, restart the computer before trying to install the client again.</span></span>

## <span data-ttu-id="4248c-142">修復損毀的虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="4248c-142">Repairing a Corrupted Virtual Application</span></span>


<span data-ttu-id="4248c-143">如果由於任何原因使用 Windows 安裝程式套件（MSI）檔案安裝的虛擬應用程式套件遭到損毀，請重新安裝套件。</span><span class="sxs-lookup"><span data-stu-id="4248c-143">If for any reason a virtual application package installed using a Windows Installer Package (MSI) file becomes corrupted, reinstall the package.</span></span> <span data-ttu-id="4248c-144">Windows Installer 中提供的修復函數將不會更新使用者的磁片量。</span><span class="sxs-lookup"><span data-stu-id="4248c-144">The Repair function available in the Windows Installer will not update the user volumes.</span></span>

## <span data-ttu-id="4248c-145">相關主題</span><span class="sxs-lookup"><span data-stu-id="4248c-145">Related topics</span></span>


[<span data-ttu-id="4248c-146">Application Virtualization Client 參考資料</span><span class="sxs-lookup"><span data-stu-id="4248c-146">Application Virtualization Client Reference</span></span>](application-virtualization-client-reference.md)

 

 





