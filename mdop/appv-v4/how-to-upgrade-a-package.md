---
title: 如何升級封裝
description: 如何升級封裝
author: dansimp
ms.assetid: 831c7556-6f6c-4b3a-aefb-26889094dc1a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0a9b3eca2c996337d79e551784818a421f495316
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801042"
---
# <span data-ttu-id="6c48a-103">如何升級封裝</span><span class="sxs-lookup"><span data-stu-id="6c48a-103">How to Upgrade a Package</span></span>


<span data-ttu-id="6c48a-104">自動升級的程式與在應用程式虛擬化伺服器管理主控台中新增套件版本的程式相同。</span><span class="sxs-lookup"><span data-stu-id="6c48a-104">The process for an automatic upgrade is the same as for adding a package version in the Application Virtualization Server Management Console.</span></span> <span data-ttu-id="6c48a-105">當您在現有的套件中 resequence 應用程式時，會執行自動升級。</span><span class="sxs-lookup"><span data-stu-id="6c48a-105">An automatic upgrade is performed when you resequence the application in an existing package.</span></span> <span data-ttu-id="6c48a-106">接著，您可以將這個新版本新增到您的伺服器以進行流式處理。</span><span class="sxs-lookup"><span data-stu-id="6c48a-106">Then you can add this new version to your servers for streaming.</span></span>

<span data-ttu-id="6c48a-107">當您使用新版本升級套件時，您可以將現有版本保留不動，或將它刪除，只保留最新版本。</span><span class="sxs-lookup"><span data-stu-id="6c48a-107">When you upgrade a package with a new version, you can leave the existing version in place or delete it and leave only the newest one.</span></span> <span data-ttu-id="6c48a-108">您可能會想要保留舊版本，以便與舊版檔相容，或讓您在將新版本提供給所有使用者之前先進行測試。</span><span class="sxs-lookup"><span data-stu-id="6c48a-108">You might want to leave the old version in place for compatibility with legacy documents or so that you can test the new version before making it available to all users.</span></span>

**<span data-ttu-id="6c48a-109">自動升級套件</span><span class="sxs-lookup"><span data-stu-id="6c48a-109">To upgrade a package automatically</span></span>**

1.  <span data-ttu-id="6c48a-110">將新的 SFT 檔案複製到 Application Virtualization 伺服器的 [內容] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="6c48a-110">Copy the new SFT file to the Application Virtualization Server's content folder.</span></span>

    <span data-ttu-id="6c48a-111">**記事** 如果 resequencing 未新增已變更開啟軟體描述項（OSD）、圖示（.ICO）或 Sequencer 專案（SPRJ）檔案的功能，您就不需要複製這些檔案。</span><span class="sxs-lookup"><span data-stu-id="6c48a-111">**Note** If resequencing did not add features that changed the Open Software Descriptor (OSD), icon (ICO), or Sequencer Project (SPRJ) files, you do not need to copy those.</span></span> <span data-ttu-id="6c48a-112">如果您想要所有這些檔案都顯示相同的日期，您可以包含這些檔案。</span><span class="sxs-lookup"><span data-stu-id="6c48a-112">You can include these files if you want all these files to display the same date.</span></span>

     

2.  <span data-ttu-id="6c48a-113">在應用程式虛擬化伺服器管理主控台的左窗格中，展開 [**套件**]。</span><span class="sxs-lookup"><span data-stu-id="6c48a-113">In left pane of the Application Virtualization Server Management Console, expand **Packages**.</span></span>

3.  <span data-ttu-id="6c48a-114">以滑鼠右鍵按一下您要升級的套件，然後選取 [**新增版本**]。</span><span class="sxs-lookup"><span data-stu-id="6c48a-114">Right-click the package you want to upgrade, and select **Add Version**.</span></span>

4.  <span data-ttu-id="6c48a-115">在 [**新增套件版本**] 對話方塊中，流覽或輸入新應用程式版本在 [檔案] 欄位的**完整路徑**中的完整路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="6c48a-115">In the **Add Package Version** dialog box, browse for or type the full path name for the new application version in the **Full Path for the file** field.</span></span> <span data-ttu-id="6c48a-116">這必須是 SFT 檔案。</span><span class="sxs-lookup"><span data-stu-id="6c48a-116">This must be an SFT file.</span></span>

5.  <span data-ttu-id="6c48a-117">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="6c48a-117">Click **Next**.</span></span>

6.  <span data-ttu-id="6c48a-118">[**摘要**] 對話方塊會顯示檔案位置，並提示您在其中複製檔案（如果您尚未這麼做）。</span><span class="sxs-lookup"><span data-stu-id="6c48a-118">The **Summary** dialog box shows the file location and prompts you to copy the file there if you have not already done so.</span></span> <span data-ttu-id="6c48a-119">驗證資訊之後，按一下 **[完成]** 。</span><span class="sxs-lookup"><span data-stu-id="6c48a-119">Click **Finish** after you have verified the information.</span></span>

    <span data-ttu-id="6c48a-120">新版本現在已完成，且準備好進行資料流程。</span><span class="sxs-lookup"><span data-stu-id="6c48a-120">The new version is now complete and ready to stream.</span></span>

## <span data-ttu-id="6c48a-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="6c48a-121">Related topics</span></span>


[<span data-ttu-id="6c48a-122">如何在伺服器管理主控台中管理封裝</span><span class="sxs-lookup"><span data-stu-id="6c48a-122">How to Manage Packages in the Server Management Console</span></span>](how-to-manage-packages-in-the-server-management-console.md)

 

 





