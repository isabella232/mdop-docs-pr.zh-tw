---
title: 如何新增封裝版本
description: 如何新增封裝版本
author: dansimp
ms.assetid: dbb829c1-e5cb-4a2f-bc17-9a9bb50c671c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a60252e8b43af61ad548df30a93d8fbc9bae0cb7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808733"
---
# <span data-ttu-id="e8bd0-103">如何新增封裝版本</span><span class="sxs-lookup"><span data-stu-id="e8bd0-103">How to Add a Package Version</span></span>


<span data-ttu-id="e8bd0-104">在應用程式虛擬化伺服器管理主控台中，當您 resequence 套件時，可以使用下列程式，將新版本新增到您的伺服器以進行流式處理。</span><span class="sxs-lookup"><span data-stu-id="e8bd0-104">In the Application Virtualization Server Management Console, when you resequence a package, you can use the following procedure to add the new version to your servers for streaming.</span></span>

<span data-ttu-id="e8bd0-105">**記事** 當您使用新版本升級套件時，您可以將現有版本保留不動，或將它刪除，只保留最新版本。</span><span class="sxs-lookup"><span data-stu-id="e8bd0-105">**Note** When you upgrade a package with a new version, you can leave the existing version in place or delete it and leave only the newest one.</span></span> <span data-ttu-id="e8bd0-106">您可能會想要保留舊版本，以便與舊版檔相容，或讓您在將新版本提供給所有使用者之前先進行測試。</span><span class="sxs-lookup"><span data-stu-id="e8bd0-106">You might want to leave the old version in place for compatibility with legacy documents or so that you can test the new version before making it available to all users.</span></span>

 

**<span data-ttu-id="e8bd0-107">新增套件版本</span><span class="sxs-lookup"><span data-stu-id="e8bd0-107">To add a package version</span></span>**

1.  <span data-ttu-id="e8bd0-108">將新的 SFT 檔案複製到應用程式伺服器的 [內容] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="e8bd0-108">Copy the new SFT file to the application server's content folder.</span></span> <span data-ttu-id="e8bd0-109">如果 resequencing 未將變更新增到開啟的軟體描述項（OSD）、圖示（.ICO）或 Sequencer 專案（SPRJ）檔案，您就不需要複製這些檔案。</span><span class="sxs-lookup"><span data-stu-id="e8bd0-109">If resequencing did not add changes to the Open Software Descriptor (OSD), icon (ICO), or Sequencer Project (SPRJ) files, you do not need to copy those.</span></span> <span data-ttu-id="e8bd0-110">如果您想要所有檔案都顯示相同的日期，您可以包含這些檔案。</span><span class="sxs-lookup"><span data-stu-id="e8bd0-110">You can include those files if you want all the files to display the same date.</span></span>

2.  <span data-ttu-id="e8bd0-111">在應用程式虛擬化伺服器管理主控台的左窗格中，展開 [**套件**] 節點。</span><span class="sxs-lookup"><span data-stu-id="e8bd0-111">In left pane of the Application Virtualization Server Management Console, expand the **Packages** node.</span></span>

3.  <span data-ttu-id="e8bd0-112">以滑鼠右鍵按一下您要升級的套件，然後選擇 [**新增版本**]。</span><span class="sxs-lookup"><span data-stu-id="e8bd0-112">Right-click the package you want to upgrade, and choose **Add Version**.</span></span>

4.  <span data-ttu-id="e8bd0-113">在 [**新增套件版本**] 對話方塊中，流覽或輸入新應用程式檔案的路徑名稱（位於 [**套件檔案的完整路徑**] 欄位中）。</span><span class="sxs-lookup"><span data-stu-id="e8bd0-113">In the **Add Package Version** dialog box, browse for or type the path name for the new application file in the **Full path for package file** field.</span></span> <span data-ttu-id="e8bd0-114">這必須是 SFT 檔案。</span><span class="sxs-lookup"><span data-stu-id="e8bd0-114">This must be an SFT file.</span></span>

5.  <span data-ttu-id="e8bd0-115">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="e8bd0-115">Click **Next**.</span></span>

6.  <span data-ttu-id="e8bd0-116">[**摘要**] 對話方塊會顯示檔案位置，並提示您在其中複製檔案（如果您尚未這麼做）。</span><span class="sxs-lookup"><span data-stu-id="e8bd0-116">The **Summary** dialog box shows the file location and prompts you to copy the file there if you have not already done so.</span></span> <span data-ttu-id="e8bd0-117">驗證資訊之後，按一下 **[完成]** 。</span><span class="sxs-lookup"><span data-stu-id="e8bd0-117">Click **Finish** after you have verified the information.</span></span>

    <span data-ttu-id="e8bd0-118">新版本現在已完成，且準備好進行資料流程。</span><span class="sxs-lookup"><span data-stu-id="e8bd0-118">The new version is now complete and ready to stream.</span></span>

## <span data-ttu-id="e8bd0-119">相關主題</span><span class="sxs-lookup"><span data-stu-id="e8bd0-119">Related topics</span></span>


[<span data-ttu-id="e8bd0-120">如何刪除封裝</span><span class="sxs-lookup"><span data-stu-id="e8bd0-120">How to Delete a Package</span></span>](how-to-delete-a-packageserver.md)

[<span data-ttu-id="e8bd0-121">如何在伺服器管理主控台中管理封裝</span><span class="sxs-lookup"><span data-stu-id="e8bd0-121">How to Manage Packages in the Server Management Console</span></span>](how-to-manage-packages-in-the-server-management-console.md)

 

 





