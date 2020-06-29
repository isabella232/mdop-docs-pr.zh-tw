---
title: 設定安裝必要條件
description: 設定安裝必要條件
author: dansimp
ms.assetid: ff9cf28a-3eac-4b6c-8ce9-bfc202f57947
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 6cd9379804c45a2025064a6eecf363c010980369
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802165"
---
# <span data-ttu-id="935e7-103">設定安裝必要條件</span><span class="sxs-lookup"><span data-stu-id="935e7-103">Configure Installation Prerequisites</span></span>


<span data-ttu-id="935e7-104">下列指示是安裝及使用 Microsoft 企業版桌面虛擬化（MED-V）2.0 的先決條件：</span><span class="sxs-lookup"><span data-stu-id="935e7-104">The following instructions are prerequisites for installing and using Microsoft Enterprise Desktop Virtualization (MED-V) 2.0:</span></span>

[<span data-ttu-id="935e7-105">Windows 虛擬電腦</span><span class="sxs-lookup"><span data-stu-id="935e7-105">Windows Virtual PC</span></span>](#bkmk-howtoinstallandconfiguremicrosoftvirtualpc7)

[<span data-ttu-id="935e7-106">Windows 虛擬電腦更新</span><span class="sxs-lookup"><span data-stu-id="935e7-106">Windows Virtual PC Update</span></span>](#bkmk-howtoinstallandconfiguremicrosoftvirtualpc7update)

[<span data-ttu-id="935e7-107">防病毒/備份軟體設定</span><span class="sxs-lookup"><span data-stu-id="935e7-107">Antivirus/Backup Software Configuration</span></span>](#bkmk-antivirusbackupsoftwareconfiguration)

## <a href="" id="bkmk-howtoinstallandconfiguremicrosoftvirtualpc7"></a><span data-ttu-id="935e7-108">如何安裝和設定 Windows 虛擬電腦</span><span class="sxs-lookup"><span data-stu-id="935e7-108">How to Install and Configure Windows Virtual PC</span></span>


<span data-ttu-id="935e7-109">**重要** 如果主機電腦上已存在 Windows 版 Virtual PC，您必須先將其卸載，才能安裝 Windows 虛擬電腦。</span><span class="sxs-lookup"><span data-stu-id="935e7-109">**Important** If a version of Virtual PC for Windows already exists on the host computer, you must uninstall it before you install Windows Virtual PC.</span></span>

 

**<span data-ttu-id="935e7-110">若要安裝 Windows Virtual 電腦</span><span class="sxs-lookup"><span data-stu-id="935e7-110">To install Windows Virtual PC</span></span>**

1.  <span data-ttu-id="935e7-111">從 Microsoft 下載中心下載[Windows 虛擬電腦](https://go.microsoft.com/fwlink/?LinkId=195918)（ https://go.microsoft.com/fwlink/?LinkId=195918) 。</span><span class="sxs-lookup"><span data-stu-id="935e7-111">Download [Windows Virtual PC](https://go.microsoft.com/fwlink/?LinkId=195918) from the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=195918).</span></span>

2.  <span data-ttu-id="935e7-112">在主機電腦上執行安裝檔，然後依照嚮導中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="935e7-112">Run the installation file on the host computer, and follow the steps in the wizard.</span></span>

<span data-ttu-id="935e7-113">**重要** Windows 虛擬電腦包含整合元件套件，提供可改善虛擬環境與物理電腦之間互動的功能。</span><span class="sxs-lookup"><span data-stu-id="935e7-113">**Important** Windows Virtual PC includes the Integration Components package, which provides features that improve the interaction between the virtual environment and the physical computer.</span></span> <span data-ttu-id="935e7-114">例如，它可讓您在主機和來賓電腦之間移動滑鼠。</span><span class="sxs-lookup"><span data-stu-id="935e7-114">For example, it lets your mouse move between the host and the guest computers.</span></span> <span data-ttu-id="935e7-115">MED-V 需要安裝 [整合元件套件]。</span><span class="sxs-lookup"><span data-stu-id="935e7-115">MED-V requires the installation of the Integration Components package.</span></span>

 

## <a href="" id="bkmk-howtoinstallandconfiguremicrosoftvirtualpc7update"></a><span data-ttu-id="935e7-116">如何安裝和設定 Windows 虛擬電腦更新</span><span class="sxs-lookup"><span data-stu-id="935e7-116">How to Install and Configure the Windows Virtual PC Update</span></span>


<span data-ttu-id="935e7-117">與文章 KB977206 相關聯的 Microsoft 更新會針對沒有硬體協助虛擬化（HAV）技術的電腦啟用 Windows XP 模式。</span><span class="sxs-lookup"><span data-stu-id="935e7-117">The Microsoft update associated with article KB977206 enables Windows XP Mode for computers without hardware-assisted virtualization (HAV) technology.</span></span> <span data-ttu-id="935e7-118">我們建議您安裝此更新，因為如果客體作業系統中的整合元件套件與主機電腦上安裝的 Windows Virtual 電腦版本不相符，部分整合功能可能無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="935e7-118">We recommended that you install this update because some integration features might not work correctly if the Integration Components package in the guest operating system do not match the version of Windows Virtual PC that is installed on the host computer.</span></span>

<span data-ttu-id="935e7-119">**重要** 當您在執行 Windows 7 的主機電腦上安裝 MED-V-V （Service Pack 1）時，您不需要安裝此更新。</span><span class="sxs-lookup"><span data-stu-id="935e7-119">**Important** You do not have to install this update when you are installing MED-V on host computers that are running Windows 7 with Service Pack 1.</span></span>

 

<span data-ttu-id="935e7-120">**秘訣** 除了這裡列出的更新之外，我們建議您查看所有可用的 Windows 虛擬電腦更新，並針對您的環境套用適當或必要的更新。</span><span class="sxs-lookup"><span data-stu-id="935e7-120">**Tip** In addition to the update listed here, we recommend that you review all available Windows Virtual PC updates and apply those updates that are appropriate or necessary for your environment.</span></span>

 

**<span data-ttu-id="935e7-121">若要安裝 Windows Virtual 電腦更新</span><span class="sxs-lookup"><span data-stu-id="935e7-121">To install the Windows Virtual PC Update</span></span>**

1.  <span data-ttu-id="935e7-122">從 Microsoft 下載中心下載所需的 Windows Virtual PC 更新。</span><span class="sxs-lookup"><span data-stu-id="935e7-122">Download the required Windows Virtual PC update from the Microsoft Download Center.</span></span>

    <span data-ttu-id="935e7-123">[32 位更新](https://go.microsoft.com/fwlink/?LinkId=195919)（ https://go.microsoft.com/fwlink/?LinkId=195919) 。</span><span class="sxs-lookup"><span data-stu-id="935e7-123">[32-bit Update](https://go.microsoft.com/fwlink/?LinkId=195919) (https://go.microsoft.com/fwlink/?LinkId=195919).</span></span>

    <span data-ttu-id="935e7-124">[64 位更新](https://go.microsoft.com/fwlink/?LinkId=195920)（ https://go.microsoft.com/fwlink/?LinkId=195920) 。</span><span class="sxs-lookup"><span data-stu-id="935e7-124">[64-bit Update](https://go.microsoft.com/fwlink/?LinkId=195920) (https://go.microsoft.com/fwlink/?LinkId=195920).</span></span>

2.  <span data-ttu-id="935e7-125">在主機電腦上以提升模式執行安裝檔案，然後依照嚮導中的步驟執行。</span><span class="sxs-lookup"><span data-stu-id="935e7-125">Run the installation file on the host computer in elevated mode, and follow the steps in the wizard.</span></span>

    <span data-ttu-id="935e7-126">如需適用于 Windows Virtual 電腦之修復程式套件的詳細資訊，請參閱[文章 977206](https://go.microsoft.com/fwlink/?LinkId=195921) （ https://go.microsoft.com/fwlink/?LinkId=195921) 。</span><span class="sxs-lookup"><span data-stu-id="935e7-126">For more information about the hotfix package for Windows Virtual PC, see [article 977206](https://go.microsoft.com/fwlink/?LinkId=195921) (https://go.microsoft.com/fwlink/?LinkId=195921).</span></span>

## <a href="" id="bkmk-antivirusbackupsoftwareconfiguration"></a><span data-ttu-id="935e7-127">如何設定防毒軟體/備份軟體</span><span class="sxs-lookup"><span data-stu-id="935e7-127">How to Configure Antivirus/Backup Software</span></span>


<span data-ttu-id="935e7-128">為了防止防病毒活動影響虛擬桌面電腦的效能，我們建議您將下列虛擬機器檔案類型排除在主機電腦上執行的任何防毒軟體或備份程式中：</span><span class="sxs-lookup"><span data-stu-id="935e7-128">To prevent antivirus activity from affecting the performance of the virtual desktop, we recommend, where you can, to exclude the following virtual machine file types from any antivirus or backup process that is running on the host computer:</span></span>

-   <span data-ttu-id="935e7-129">\*.VMC</span><span class="sxs-lookup"><span data-stu-id="935e7-129">\*.VMC</span></span>

-   <span data-ttu-id="935e7-130">\*.VUD</span><span class="sxs-lookup"><span data-stu-id="935e7-130">\*.VUD</span></span>

-   <span data-ttu-id="935e7-131">\*.VSV</span><span class="sxs-lookup"><span data-stu-id="935e7-131">\*.VSV</span></span>

-   <span data-ttu-id="935e7-132">\*.VHD</span><span class="sxs-lookup"><span data-stu-id="935e7-132">\*.VHD</span></span>

## <span data-ttu-id="935e7-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="935e7-133">Related topics</span></span>


[<span data-ttu-id="935e7-134">設定環境先決條件</span><span class="sxs-lookup"><span data-stu-id="935e7-134">Configure Environment Prerequisites</span></span>](configure-environment-prerequisites.md)

[<span data-ttu-id="935e7-135">高階架構</span><span class="sxs-lookup"><span data-stu-id="935e7-135">High-Level Architecture</span></span>](high-level-architecturemedv2.md)

[<span data-ttu-id="935e7-136">MED-V 2.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="935e7-136">MED-V 2.0 Supported Configurations</span></span>](med-v-20-supported-configurations.md)

 

 





