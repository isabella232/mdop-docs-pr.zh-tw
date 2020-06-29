---
title: 改善 APP-V 排序期間的安全性
description: 改善 APP-V 排序期間的安全性
author: dansimp
ms.assetid: f30206dd-5749-4a27-bbaf-61fc21b9c663
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ba97c334c4ac9a928fee3d69c265c12e82e43619
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801003"
---
# <span data-ttu-id="c0491-103">改善 APP-V 排序期間的安全性</span><span class="sxs-lookup"><span data-stu-id="c0491-103">Improving Security During App-V Sequencing</span></span>


<span data-ttu-id="c0491-104">[封裝應用程式以進行排序] 是 App-v 基礎結構中最大的日常作業。</span><span class="sxs-lookup"><span data-stu-id="c0491-104">Packaging applications for sequencing is the largest ongoing task in an App-V infrastructure.</span></span> <span data-ttu-id="c0491-105">由於這項工作正在進行中，因此您應該謹慎地考慮建立排序應用程式時要遵循的原則與程式。</span><span class="sxs-lookup"><span data-stu-id="c0491-105">Because this task is ongoing, you should carefully consider creating policies and procedures to follow when sequencing applications.</span></span> <span data-ttu-id="c0491-106">在 App-v 4.5 中，排序期間，您可以在虛擬化應用程式的檔案資產上捕獲存取控制清單（Acl）。</span><span class="sxs-lookup"><span data-stu-id="c0491-106">In App-V4.5, during sequencing, you can capture Access Control Lists (ACLs) on the file assets of the virtualized application.</span></span>

## <span data-ttu-id="c0491-107">排序器上的病毒掃描</span><span class="sxs-lookup"><span data-stu-id="c0491-107">Virus Scanning on the Sequencer</span></span>


<span data-ttu-id="c0491-108">最好的做法是在先後順序的電腦上安裝掃描軟體，然後掃描電腦以尋找病毒和惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="c0491-108">It is a best practice to install the scanning software on the sequencing computer and then scan the computer for viruses and malware.</span></span> <span data-ttu-id="c0491-109">在順序電腦已掃描且沒有任何病毒或惡意程式碼之後，請先停用排序電腦上的掃描軟體（包括所有防病毒及惡意程式碼偵測軟體），然後再將任何應用程式排序。</span><span class="sxs-lookup"><span data-stu-id="c0491-109">After the sequencing computer is scanned and free of any viruses or malware, disable the scanning software, including all antivirus and malware detection software, on the sequencing computer before sequencing any applications.</span></span> <span data-ttu-id="c0491-110">這會加快順序程式，並防止掃描軟體元件在排序期間偵測並包含在虛擬應用程式套件中。</span><span class="sxs-lookup"><span data-stu-id="c0491-110">This speeds the sequencing process and prevents the scanning software components from being detected during sequencing and included in the virtual application package.</span></span>

## <span data-ttu-id="c0491-111">在檔案上捕獲 Acl （NTFS）</span><span class="sxs-lookup"><span data-stu-id="c0491-111">Capturing ACLs on Files (NTFS)</span></span>


<span data-ttu-id="c0491-112">排序器會捕獲在排序安裝階段監視之檔案的 NTFS 許可權（Acl）。</span><span class="sxs-lookup"><span data-stu-id="c0491-112">The Sequencer captures NTFS permissions (the ACLs) for the files that are monitored during the sequencing installation phase.</span></span> <span data-ttu-id="c0491-113">（在發行 App-V 4.5 之前，Acl 未捕獲為排序程式的一部分）。這項新功能可讓特定的應用程式針對一般需要系統管理許可權的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="c0491-113">(Before the release of App-V4.5, ACLs were not captured as part of the sequencing process.) This new feature enables certain applications to run for users with a low level of permission that would normally require Administrative privileges.</span></span>

<span data-ttu-id="c0491-114">這個功能也可讓排序工程來捕獲廠商所識別的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="c0491-114">This feature also enables the sequencing engineer to capture the security settings identified by the vendor.</span></span> <span data-ttu-id="c0491-115">如果無法套用供應商建議的設定，可能會讓應用程式在使用者受到攻擊或誤用時保持開啟。</span><span class="sxs-lookup"><span data-stu-id="c0491-115">Failing to apply the settings recommended by the vendor could leave the application open to attack or misuse by users.</span></span> <span data-ttu-id="c0491-116">如需有關是否應該使用開啟的 Acl 來部署應用程式的相關資訊，請參閱您的應用程式支援群組或軟體廠商。</span><span class="sxs-lookup"><span data-stu-id="c0491-116">For information about whether or not you should deploy an application with open ACLs, refer to your application support group or the software vendor.</span></span>

<span data-ttu-id="c0491-117">**重要** 雖然排序器會在監視排序的安裝階段時捕獲 NTFS Acl，但不會捕獲登錄的 Acl。</span><span class="sxs-lookup"><span data-stu-id="c0491-117">**Important** Although the sequencer captures the NTFS ACLs while monitoring the installation phase of sequencing, it does not capture the ACLs for the registry.</span></span> <span data-ttu-id="c0491-118">除了服務之外，使用者對虛擬應用程式的所有登錄機碼擁有完全存取權。</span><span class="sxs-lookup"><span data-stu-id="c0491-118">Users have full access to all registry keys for virtual applications except for services.</span></span> <span data-ttu-id="c0491-119">不過，如果使用者修改虛擬應用程式的登錄，該變更會儲存在特定位置（ `uservol_sftfs_v1.pkg` ），而不會影響其他使用者。</span><span class="sxs-lookup"><span data-stu-id="c0491-119">However, if a user modifies the registry of a virtual application, that change is stored in a specific location (`uservol_sftfs_v1.pkg`) and won’t affect other users.</span></span>

 

<span data-ttu-id="c0491-120">在安裝階段中，順序工程師可以視需要修改檔案的預設許可權。</span><span class="sxs-lookup"><span data-stu-id="c0491-120">During the installation phase, a sequencing engineer can modify the default permissions of the files if necessary.</span></span> <span data-ttu-id="c0491-121">排序程式完成之後，但在儲存套件之前，順序工程師可以選擇強制執行在安裝階段捕獲的安全描述項。</span><span class="sxs-lookup"><span data-stu-id="c0491-121">After the sequencing process is complete, but before saving the package, the sequencing engineer can then choose to enforce security descriptors that were captured during the installation phase.</span></span> <span data-ttu-id="c0491-122">如果沒有任何其他解決方案允許應用程式在虛擬化之後正常執行，最佳做法是強制執行安全性描述項。</span><span class="sxs-lookup"><span data-stu-id="c0491-122">It is a best practice to enforce security descriptors if no other solution allows the application to run properly once virtualized.</span></span>

 

 





