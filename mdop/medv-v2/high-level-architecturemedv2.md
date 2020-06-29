---
title: 高階架構
description: 高階架構
author: dansimp
ms.assetid: a00edb9f-207b-4f32-9e8f-522ea2739d2f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a5db4a56b2abfb0df19b0d6d86f4bf88380c2bf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812267"
---
# <span data-ttu-id="102e2-103">高階架構</span><span class="sxs-lookup"><span data-stu-id="102e2-103">High-Level Architecture</span></span>


<span data-ttu-id="102e2-104">本節說明 Microsoft 企業桌面虛擬化（MED-V）2.0 的高層次系統架構和元件設計。</span><span class="sxs-lookup"><span data-stu-id="102e2-104">This section describes the high-level system architecture and component design of Microsoft Enterprise Desktop Virtualization (MED-V) 2.0.</span></span>

## <span data-ttu-id="102e2-105">系統架構</span><span class="sxs-lookup"><span data-stu-id="102e2-105">System Architecture</span></span>


<span data-ttu-id="102e2-106">MED-V 可增強 Windows 虛擬電腦，在一個裝置上執行兩個作業系統、新增虛擬影像傳遞、群組原則的資源調配，以及集中式管理。</span><span class="sxs-lookup"><span data-stu-id="102e2-106">MED-V enhances Windows Virtual PC to run two operating systems on one device, adding virtual image delivery, Group Policy-based provisioning, and centralized management.</span></span> <span data-ttu-id="102e2-107">透過使用 MED-V，您可以在任何執行 Windows 7 專業版、企業版或 Windows 7 旗艦版的 Windows 桌上型電腦上，輕鬆地設定、部署及管理企業 Windows 虛擬電腦影像。</span><span class="sxs-lookup"><span data-stu-id="102e2-107">By using MED-V, you can easily configure, deploy, and manage corporate Windows Virtual PC images on any Windows-based desktop running Windows 7 Professional, Enterprise, or Windows 7 Ultimate.</span></span> <span data-ttu-id="102e2-108">MED-V 方案包含下列元件：</span><span class="sxs-lookup"><span data-stu-id="102e2-108">The MED-V solution includes the following components:</span></span>

<a href="" id="---------------med-v-host"></a> **<span data-ttu-id="102e2-109">MED-V 主機</span><span class="sxs-lookup"><span data-stu-id="102e2-109">MED-V Host</span></span>**  
<span data-ttu-id="102e2-110">Windows 7 環境，其中包含 MED-V 主機代理程式、電子軟體發佈（ESD）系統、註冊表管理系統和 MED-V 來賓。</span><span class="sxs-lookup"><span data-stu-id="102e2-110">A Windows 7 environment that includes a MED-V Host Agent, an electronic software distribution (ESD) system, a registry management system, and a MED-V guest.</span></span> <span data-ttu-id="102e2-111">MED-V 主機會與 MED-V 來賓互動，讓您可以處理某些設定函數和系統資訊。</span><span class="sxs-lookup"><span data-stu-id="102e2-111">The MED-V host interacts with the MED-V guest so that certain setup functions and system information can be processed.</span></span>

<a href="" id="-------------------med-v-host-agent"></a> **<span data-ttu-id="102e2-112">MED-V 主機代理程式</span><span class="sxs-lookup"><span data-stu-id="102e2-112">MED-V Host Agent</span></span>**  
<span data-ttu-id="102e2-113">MED-V 主機中包含的 MED-V 軟體，提供與 MED-V 來賓進行通訊的通道。</span><span class="sxs-lookup"><span data-stu-id="102e2-113">The MED-V software contained in the MED-V host that provides a channel to communicate with the MED-V guest.</span></span> <span data-ttu-id="102e2-114">它也提供第一次設定和應用程式發佈等功能。</span><span class="sxs-lookup"><span data-stu-id="102e2-114">It also provides functionality such as first time setup and application publishing.</span></span>

<span data-ttu-id="102e2-115">**記事** 已安裝 MED-V 和其必要元件之後，必須設定 MED-V-V。</span><span class="sxs-lookup"><span data-stu-id="102e2-115">**Note** After MED-V and its required components are installed MED-V must be configured.</span></span> <span data-ttu-id="102e2-116">MED-V 的設定稱為第一次設定。</span><span class="sxs-lookup"><span data-stu-id="102e2-116">The configuration of MED-V is referred to as first time setup.</span></span>

 

<a href="" id="esd-system"></a>**<span data-ttu-id="102e2-117">ESD 系統</span><span class="sxs-lookup"><span data-stu-id="102e2-117">ESD System</span></span>**  
<span data-ttu-id="102e2-118">您的現有軟體發佈方法，可讓您部署並安裝 MED-V 所建立的 MED-V 工作區套件檔案。</span><span class="sxs-lookup"><span data-stu-id="102e2-118">Your existing software distribution method that lets you deploy and install the MED-V workspace package files that MED-V creates.</span></span>

<a href="" id="registry-management-system"></a>**<span data-ttu-id="102e2-119">註冊管理系統</span><span class="sxs-lookup"><span data-stu-id="102e2-119">Registry Management System</span></span>**  
<span data-ttu-id="102e2-120">您現有的管理群組原則設定和喜好設定的方法。</span><span class="sxs-lookup"><span data-stu-id="102e2-120">Your existing method of managing Group Policy settings and preferences.</span></span>

<a href="" id="windows-virtual-pc-image"></a>**<span data-ttu-id="102e2-121">Windows 虛擬電腦影像</span><span class="sxs-lookup"><span data-stu-id="102e2-121">Windows Virtual PC Image</span></span>**  
<span data-ttu-id="102e2-122">系統管理員定義的虛擬機器，內含下列元件：</span><span class="sxs-lookup"><span data-stu-id="102e2-122">An administrator-defined virtual machine that contains the following components:</span></span>

<a href="" id="corporate-operating-system"></a>**<span data-ttu-id="102e2-123">公司作業系統</span><span class="sxs-lookup"><span data-stu-id="102e2-123">Corporate Operating System</span></span>**  
<span data-ttu-id="102e2-124">您的標準公司作業系統。</span><span class="sxs-lookup"><span data-stu-id="102e2-124">Your standard corporate operating system.</span></span>

<a href="" id="management-and-security-tools"></a>**<span data-ttu-id="102e2-125">管理和安全性工具</span><span class="sxs-lookup"><span data-stu-id="102e2-125">Management and Security Tools</span></span>**  
<span data-ttu-id="102e2-126">您的標準管理和安全性工具，例如防防毒保護。</span><span class="sxs-lookup"><span data-stu-id="102e2-126">Your standard management and security tools, such as virus protection.</span></span>

<a href="" id="-----------------------med-v-guest"></a> **<span data-ttu-id="102e2-127">MED-V 來賓</span><span class="sxs-lookup"><span data-stu-id="102e2-127">MED-V Guest</span></span>**  
<span data-ttu-id="102e2-128">Windows XP SP3 環境，是在 Windows 7 上執行的 windows 虛擬電腦（包含下列元件）的一部分：</span><span class="sxs-lookup"><span data-stu-id="102e2-128">A Windows XP SP3 environment, as part of a Windows Virtual PC running on Windows 7 that contains the following components:</span></span>

<a href="" id="---------------------------med-v-guest-agent"></a> **<span data-ttu-id="102e2-129">MED-V 來賓代理程式</span><span class="sxs-lookup"><span data-stu-id="102e2-129">MED-V Guest Agent</span></span>**  
<span data-ttu-id="102e2-130">MED-V 來賓中包含的 MED-V 軟體，提供與 MED-V 主機進行通訊的通道。</span><span class="sxs-lookup"><span data-stu-id="102e2-130">The MED-V software contained in the MED-V guest that provides a channel to communicate with the MED-V host.</span></span> <span data-ttu-id="102e2-131">它也支援 MED-V 主機代理程式，其中包含執行第一次設定等函數。</span><span class="sxs-lookup"><span data-stu-id="102e2-131">It also supports the MED-V Host Agent with functions like performing first time setup.</span></span>

<span data-ttu-id="102e2-132">**記事** MED-V 來賓代理程式會在第一次設定期間自動安裝。</span><span class="sxs-lookup"><span data-stu-id="102e2-132">**Note** The MED-V Guest Agent is installed automatically during first time setup.</span></span>

 

<a href="" id="esd-client"></a>**<span data-ttu-id="102e2-133">ESD 用戶端</span><span class="sxs-lookup"><span data-stu-id="102e2-133">ESD Client</span></span>**  
<span data-ttu-id="102e2-134">ESD 系統的選擇性元件，可將軟體套件及報告狀態安裝至 ESD 系統。</span><span class="sxs-lookup"><span data-stu-id="102e2-134">An optional part of your ESD system that installs software packages and reports status to the ESD system.</span></span>

## <span data-ttu-id="102e2-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="102e2-135">Related topics</span></span>


[<span data-ttu-id="102e2-136">規劃應用程式作業系統相容性</span><span class="sxs-lookup"><span data-stu-id="102e2-136">Planning for Application Operating System Compatibility</span></span>](planning-for-application-operating-system-compatibility.md)

[<span data-ttu-id="102e2-137">準備 MED-V 的部署環境</span><span class="sxs-lookup"><span data-stu-id="102e2-137">Prepare the Deployment Environment for MED-V</span></span>](prepare-the-deployment-environment-for-med-v.md)

 

 





