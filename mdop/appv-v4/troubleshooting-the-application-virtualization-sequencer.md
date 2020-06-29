---
title: 疑難排解 Application Virtualization Sequencer
description: 疑難排解 Application Virtualization Sequencer
author: dansimp
ms.assetid: 12ea8367-0b84-44e1-a885-e0539486556b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 60c47b853c74d90afc21e9ca172c0eec2a2c7a0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800768"
---
# <span data-ttu-id="d8048-103">疑難排解 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="d8048-103">Troubleshooting the Application Virtualization Sequencer</span></span>


<span data-ttu-id="d8048-104">本主題包含一些資訊，您可以用來協助對應用程式虛擬化（App-v）排序器的一般問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="d8048-104">This topic includes information that you can use to help troubleshoot general issues on the Application Virtualization (App-V) Sequencer.</span></span>

## <span data-ttu-id="d8048-105">使用 App-v 排序器建立 SFTD 檔案時，會意外增加版本號碼</span><span class="sxs-lookup"><span data-stu-id="d8048-105">Creating an SFTD File by Using the App-V Sequencer Increases the Version Number Unexpectedly</span></span>


<span data-ttu-id="d8048-106">與 SFTD 檔案相關聯的版本號碼會意外增加。</span><span class="sxs-lookup"><span data-stu-id="d8048-106">The version number associated with an SFTD file increases unexpectedly.</span></span>

**<span data-ttu-id="d8048-107">解決方案</span><span class="sxs-lookup"><span data-stu-id="d8048-107">Solution</span></span>**

<span data-ttu-id="d8048-108">使用命令列來產生新的 sft 檔案。</span><span class="sxs-lookup"><span data-stu-id="d8048-108">Use the command line to generate a new .sft file.</span></span> <span data-ttu-id="d8048-109">若要使用命令列來建立 sft 檔案，請在命令提示字元中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="d8048-109">To create the .sft file by using the command line, enter the following at a command prompt:</span></span>

**<span data-ttu-id="d8048-110">mkdiffpkg.exe &lt; 基 sft 檔案名 &gt; &lt; 差異 sft 檔案名&gt;</span><span class="sxs-lookup"><span data-stu-id="d8048-110">mkdiffpkg.exe &lt;base SFT file name&gt; &lt;diff SFT file name&gt;</span></span>**

## <a href="" id="file-name-in-osd-file-is-not-correct-after-package-upgrade-"></a><span data-ttu-id="d8048-111">在封裝升級後，OSD 檔案中的檔案名不正確</span><span class="sxs-lookup"><span data-stu-id="d8048-111">File Name in OSD File Is Not Correct After Package Upgrade</span></span>


<span data-ttu-id="d8048-112">在您升級現有的套件後，檔案名不正確。</span><span class="sxs-lookup"><span data-stu-id="d8048-112">After you upgrade an existing package, the file name is not correct.</span></span>

**<span data-ttu-id="d8048-113">解決方案</span><span class="sxs-lookup"><span data-stu-id="d8048-113">Solution</span></span>**

<span data-ttu-id="d8048-114">當您開啟要升級的套件時，您應該指定根 Q:\\ 磁片磁碟機做為套件的輸出位置。</span><span class="sxs-lookup"><span data-stu-id="d8048-114">When you open a package for upgrade, you should specify the root Q:\\ drive as the output location for the package.</span></span> <span data-ttu-id="d8048-115">請勿將相關聯的檔案名指定為輸出位置。</span><span class="sxs-lookup"><span data-stu-id="d8048-115">Do not specify an associated file name with the output location.</span></span>

## <span data-ttu-id="d8048-116">當資料流程傳送至用戶端時，Microsoft Word2003 預設安裝會產生錯誤</span><span class="sxs-lookup"><span data-stu-id="d8048-116">Microsoft Word2003 Default Install Results in an Error When Streamed to a Client</span></span>


<span data-ttu-id="d8048-117">當您將 Microsoft Word2003 串流到用戶端時，會傳回錯誤，但 Microsoft Word 會繼續執行。</span><span class="sxs-lookup"><span data-stu-id="d8048-117">When you stream Microsoft Word2003 to a client, an error is returned but Microsoft Word continues to run.</span></span>

**<span data-ttu-id="d8048-118">解決方案</span><span class="sxs-lookup"><span data-stu-id="d8048-118">Solution</span></span>**

<span data-ttu-id="d8048-119">Resequence 虛擬應用程式套件，然後選取 [**完整安裝**]。</span><span class="sxs-lookup"><span data-stu-id="d8048-119">Resequence the virtual application package, and select **Full Install**.</span></span>

## <span data-ttu-id="d8048-120">建立相依套件時，套件升級無法運作</span><span class="sxs-lookup"><span data-stu-id="d8048-120">Package Upgrade Does Not Work When You Create a Dependent Package</span></span>


<span data-ttu-id="d8048-121">當您使用套件升級建立相依套件並新增登錄專案時，它看起來會正常運作，但無法使用更新的登錄專案。</span><span class="sxs-lookup"><span data-stu-id="d8048-121">When you create a dependent package by using package upgrade and add new registry entries, it appears to function correctly but the updated registry entries are not available.</span></span>

**<span data-ttu-id="d8048-122">解決方案</span><span class="sxs-lookup"><span data-stu-id="d8048-122">Solution</span></span>**

<span data-ttu-id="d8048-123">登錄設定總是與原始版本的套件儲存在一起，所以除非您修復原始套件，否則不會顯示套件更新。</span><span class="sxs-lookup"><span data-stu-id="d8048-123">Registry settings are always stored with the original version of the package, so updates to the package will not appear to be available unless you repair the original package.</span></span>

## <span data-ttu-id="d8048-124">嘗試順序的錯誤。NET 2。0</span><span class="sxs-lookup"><span data-stu-id="d8048-124">Error When Trying to Sequence .NET2.0</span></span>


<span data-ttu-id="d8048-125">當您對需要的套件進行排序時。NET 2.0，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="d8048-125">When you sequence a package that requires .NET2.0, you get an error.</span></span>

**<span data-ttu-id="d8048-126">解決方案</span><span class="sxs-lookup"><span data-stu-id="d8048-126">Solution</span></span>**

<span data-ttu-id="d8048-127">需要的排序套件順序。不支援 NET 2.0。</span><span class="sxs-lookup"><span data-stu-id="d8048-127">Sequencing packages that require .NET2.0 is not supported.</span></span>

## <span data-ttu-id="d8048-128">相關主題</span><span class="sxs-lookup"><span data-stu-id="d8048-128">Related topics</span></span>


[<span data-ttu-id="d8048-129">Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="d8048-129">Application Virtualization Sequencer</span></span>](application-virtualization-sequencer.md)

 

 





