---
title: 設定環境先決條件
description: 設定環境先決條件
author: dansimp
ms.assetid: 7379e8e5-1cb2-4b8e-8acc-5c04e26f8c91
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8d6fc3b81f6dafbe709dd904b9fba6124d2f6b6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811762"
---
# <span data-ttu-id="eac50-103">設定環境先決條件</span><span class="sxs-lookup"><span data-stu-id="eac50-103">Configure Environment Prerequisites</span></span>


<span data-ttu-id="eac50-104">在您可以部署並執行 Microsoft 企業版桌面虛擬化（MED-V）2.0 之前，您必須確保您的環境符合下列最低先決條件。</span><span class="sxs-lookup"><span data-stu-id="eac50-104">Before you can deploy and run Microsoft Enterprise Desktop Virtualization (MED-V) 2.0, you must ensure that your environment meets the following minimum prerequisites.</span></span>

**<span data-ttu-id="eac50-105">Windows 7</span><span class="sxs-lookup"><span data-stu-id="eac50-105">Windows 7</span></span>**

<span data-ttu-id="eac50-106">MED-V 主機代理程式和 MED-V 工作區包裝程式僅適用于 Windows 7 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="eac50-106">The MED-V Host Agent and the MED-V Workspace Packager are only supported in Windows 7 or newer.</span></span>

**<span data-ttu-id="eac50-107">Windows XP SP3</span><span class="sxs-lookup"><span data-stu-id="eac50-107">Windows XP SP3</span></span>**

<span data-ttu-id="eac50-108">只有在 Windows XP SP3 中才支援 MED-V 來賓代理程式。</span><span class="sxs-lookup"><span data-stu-id="eac50-108">The MED-V Guest Agent is only supported in Windows XP SP3.</span></span>

**<span data-ttu-id="eac50-109">.NET Framework 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="eac50-109">.NET Framework 3.5 SP1</span></span>**

<span data-ttu-id="eac50-110">MED-V 主機和來賓代理與 MED-V 工作區封裝程式需要 Microsoft .NET Framework 3.5 SP1。</span><span class="sxs-lookup"><span data-stu-id="eac50-110">The MED-V Host and Guest agents and the MED-V Workspace Packager require the Microsoft .NET Framework 3.5 SP1.</span></span>

<span data-ttu-id="eac50-111">**重要** 您也必須安裝更新[KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) （ https://go.microsoft.com/fwlink/?LinkId=204950) ，這會解決幾個已知的應用程式相容性問題。</span><span class="sxs-lookup"><span data-stu-id="eac50-111">**Important** You must also install the update [KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) (https://go.microsoft.com/fwlink/?LinkId=204950), which addresses several known application compatibility issues.</span></span>

 

<span data-ttu-id="eac50-112">**記事** 您必須將 .NET Framework 3.5 SP1 和更新 KB959209 手動安裝到您準備搭配 MED-V 使用的 Windows 虛擬電腦映射中。</span><span class="sxs-lookup"><span data-stu-id="eac50-112">**Note** You must manually install the .NET Framework 3.5 SP1 and the update KB959209 into the Windows Virtual PC image that you prepare for use with MED-V.</span></span> <span data-ttu-id="eac50-113">不過，當您在主機電腦上安裝 Windows 7 時，預設會包含 Microsoft .NET Framework 3.5 SP1 和更新。</span><span class="sxs-lookup"><span data-stu-id="eac50-113">However, by default, the Microsoft .NET Framework 3.5 SP1 and the update are included when you install Windows 7 on the host computer.</span></span>

 

**<span data-ttu-id="eac50-114">Active Directory 基礎結構</span><span class="sxs-lookup"><span data-stu-id="eac50-114">An Active Directory Infrastructure</span></span>**

<span data-ttu-id="eac50-115">[群組原則] 可在 Active Directory 環境中提供作業系統、應用程式及使用者設定的集中式管理和配置。</span><span class="sxs-lookup"><span data-stu-id="eac50-115">Group Policy provides the centralized management and configuration of operating systems, applications, and users' settings in an Active Directory environment.</span></span>

## <span data-ttu-id="eac50-116">相關主題</span><span class="sxs-lookup"><span data-stu-id="eac50-116">Related topics</span></span>


[<span data-ttu-id="eac50-117">設定安裝必要條件</span><span class="sxs-lookup"><span data-stu-id="eac50-117">Configure Installation Prerequisites</span></span>](configure-installation-prerequisites.md)

[<span data-ttu-id="eac50-118">高階架構</span><span class="sxs-lookup"><span data-stu-id="eac50-118">High-Level Architecture</span></span>](high-level-architecturemedv2.md)

[<span data-ttu-id="eac50-119">MED-V 2.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="eac50-119">MED-V 2.0 Supported Configurations</span></span>](med-v-20-supported-configurations.md)

 

 





