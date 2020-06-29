---
title: 疑難排解 Application Virtualization Sequencer 問題
description: 疑難排解 Application Virtualization Sequencer 問題
author: dansimp
ms.assetid: 2712094b-a0bc-4643-aced-5415535f3fec
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa8b84f37217f29ff2c08a2254d7f54ce74348d2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800780"
---
# <span data-ttu-id="33673-103">疑難排解 Application Virtualization Sequencer 問題</span><span class="sxs-lookup"><span data-stu-id="33673-103">Troubleshooting Application Virtualization Sequencer Issues</span></span>


<span data-ttu-id="33673-104">本主題包含一些資訊，您可以用來協助對應用程式虛擬化（App-v）排序器的一般問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="33673-104">This topic includes information that you can use to help troubleshoot general issues on the Application Virtualization (App-V) Sequencer.</span></span>

## <span data-ttu-id="33673-105">使用 App-v 排序器建立 SFTD 檔案時，會意外增加版本號碼</span><span class="sxs-lookup"><span data-stu-id="33673-105">Creating an SFTD File by Using the App-V Sequencer Increases the Version Number Unexpectedly</span></span>


<span data-ttu-id="33673-106">使用命令列來產生新的 sft 檔案。</span><span class="sxs-lookup"><span data-stu-id="33673-106">Use the command line to generate a new .sft file.</span></span> <span data-ttu-id="33673-107">若要使用命令列來建立 sft 檔案，請在命令提示字元中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="33673-107">To create the .sft file by using the command line, enter the following at a command prompt:</span></span>

**<span data-ttu-id="33673-108">mkdiffpkg.exe &lt; 基 sft 檔案名 &gt; &lt; 差異 sft 檔案名&gt;</span><span class="sxs-lookup"><span data-stu-id="33673-108">mkdiffpkg.exe &lt;base SFT file name&gt; &lt;diff SFT file name&gt;</span></span>**

## <a href="" id="file-name-in-osd-file-is-not-correct-after-package-upgrade-"></a><span data-ttu-id="33673-109">在封裝升級後，OSD 檔案中的檔案名不正確</span><span class="sxs-lookup"><span data-stu-id="33673-109">File Name in OSD File Is Not Correct After Package Upgrade</span></span>


<span data-ttu-id="33673-110">當您開啟要升級的套件時，您應該指定根 Q:\\ 磁片磁碟機做為套件的輸出位置。</span><span class="sxs-lookup"><span data-stu-id="33673-110">When you open a package for upgrade, you should specify the root Q:\\ drive as the output location for the package.</span></span> <span data-ttu-id="33673-111">請勿將相關聯的檔案名指定為輸出位置。</span><span class="sxs-lookup"><span data-stu-id="33673-111">Do not specify an associated file name with the output location.</span></span>

## <span data-ttu-id="33673-112">當資料流程傳送至用戶端時，Microsoft Word2003 預設安裝會產生錯誤</span><span class="sxs-lookup"><span data-stu-id="33673-112">Microsoft Word2003 Default Install Results in an Error When Streamed to a Client</span></span>


<span data-ttu-id="33673-113">當您將 Microsoft Word2003 串流到用戶端時，會傳回錯誤，但 Microsoft Word 會繼續執行。</span><span class="sxs-lookup"><span data-stu-id="33673-113">When you stream Microsoft Word2003 to a client, an error is returned, but Microsoft Word continues to run.</span></span>

**<span data-ttu-id="33673-114">解決方案</span><span class="sxs-lookup"><span data-stu-id="33673-114">Solution</span></span>**

<span data-ttu-id="33673-115">Resequence 虛擬應用程式套件，然後選取 [**完整安裝**]。</span><span class="sxs-lookup"><span data-stu-id="33673-115">Resequence the virtual application package and select **Full Install**.</span></span>

## <span data-ttu-id="33673-116">當您建立相依的套件時，無法使用 [活動升級]</span><span class="sxs-lookup"><span data-stu-id="33673-116">Active Upgrade Does Not Work When You Create a Dependent Package</span></span>


<span data-ttu-id="33673-117">當您使用 [作用中升級] 並新增 [登錄] 專案來建立相依的套件時，它看起來會正常運作，但無法使用更新的登錄機碼目。</span><span class="sxs-lookup"><span data-stu-id="33673-117">When you create a dependent package by using active upgrade and add new registry entries, it appears to function correctly, but the updated registry entries are not available.</span></span>

**<span data-ttu-id="33673-118">解決方案</span><span class="sxs-lookup"><span data-stu-id="33673-118">Solution</span></span>**

<span data-ttu-id="33673-119">登錄設定總是與原始版本的套件儲存在一起，所以除非您修復原始套件，否則不會顯示套件更新。</span><span class="sxs-lookup"><span data-stu-id="33673-119">Registry settings are always stored with the original version of the package, so updates to the package will not appear to be available unless you repair the original package.</span></span>

## <span data-ttu-id="33673-120">使用 [屬性] 頁面不會顯示 Microsoft Office2007 檔的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="33673-120">Detailed information is not visible for Microsoft Office2007 documents by using the properties page</span></span>


<span data-ttu-id="33673-121">當您嘗試使用 [屬性] 頁面來查看與 Microsoft Office2007 檔相關聯的詳細資訊時，系統不會顯示詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="33673-121">When you try to view detailed information associated with a Microsoft Office2007 document by using the properties page, the detailed information is not visible.</span></span>

**<span data-ttu-id="33673-122">解決方案</span><span class="sxs-lookup"><span data-stu-id="33673-122">Solution</span></span>**

<span data-ttu-id="33673-123">App-v 不支援這些屬性頁所需的命令介面延伸。</span><span class="sxs-lookup"><span data-stu-id="33673-123">App-V does not support the required shell extensions for these property pages.</span></span>

## <span data-ttu-id="33673-124">當您順序16位的應用程式時，不會捕獲某些登錄機碼</span><span class="sxs-lookup"><span data-stu-id="33673-124">Some registry keys are not captured when you sequence 16-bit applications</span></span>


<span data-ttu-id="33673-125">在 App-V 4.5 中，已從核心模式將登錄掛鉤移至 [使用者模式]。</span><span class="sxs-lookup"><span data-stu-id="33673-125">In App-V 4.5, registry hooking has been moved from kernel mode to user mode.</span></span> <span data-ttu-id="33673-126">如果您想要為使用16位安裝程式的16位應用程式或應用程式排序，您必須先設定 sequencer 電腦，讓該進程在自己的 Windows NT 虛擬 DOS 電腦（NTVDM）複本中執行。</span><span class="sxs-lookup"><span data-stu-id="33673-126">If you want to sequence a 16-bit application or an application that uses a 16-bit installer, you must first configure the sequencer computer so that the process runs in its own copy of the Windows NT Virtual DOS Machine (NTVDM).</span></span>

**<span data-ttu-id="33673-127">解決方案</span><span class="sxs-lookup"><span data-stu-id="33673-127">Solution</span></span>**

<span data-ttu-id="33673-128">在排序應用程式之前，請在先後順序電腦上將下列全域 REGSZ 登錄機碼的值設定為「是」：</span><span class="sxs-lookup"><span data-stu-id="33673-128">Before you sequence the application, set the following global REGSZ registry key value to "yes" on the sequencing computer:</span></span>

<span data-ttu-id="33673-129">HKLM\\SYSTEM\\CurrentControlSet\\Control\\WOW\\DefaultSeparateVDM</span><span class="sxs-lookup"><span data-stu-id="33673-129">HKLM\\SYSTEM\\CurrentControlSet\\Control\\WOW\\DefaultSeparateVDM</span></span>

<span data-ttu-id="33673-130">您必須先重新開機電腦，才會生效。</span><span class="sxs-lookup"><span data-stu-id="33673-130">You must restart the computer before this takes effect.</span></span>

## <span data-ttu-id="33673-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="33673-131">Related topics</span></span>


[<span data-ttu-id="33673-132">Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="33673-132">Application Virtualization Sequencer</span></span>](application-virtualization-sequencer.md)

 

 





