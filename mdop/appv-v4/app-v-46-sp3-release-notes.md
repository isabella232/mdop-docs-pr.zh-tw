---
title: App-V 4.6 SP3 版本資訊
description: App-V 4.6 SP3 版本資訊
author: dansimp
ms.assetid: 206fadeb-59cc-47b4-836f-191ab1c27ff8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: dd0b82c5e12cbe161066a7f4a4e0932cb92cca42
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802358"
---
# <span data-ttu-id="158a5-103">App-V 4.6 SP3 版本資訊</span><span class="sxs-lookup"><span data-stu-id="158a5-103">App-V 4.6 SP3 Release Notes</span></span>


<span data-ttu-id="158a5-104">若要搜尋這些版本筆記，請按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="158a5-104">To search these Release Notes, press CTRL+F.</span></span>

<span data-ttu-id="158a5-105">安裝 Microsoft Application Virtualization （App-v）管理系統之前，請先閱讀這些版本資訊。</span><span class="sxs-lookup"><span data-stu-id="158a5-105">Read these Release Notes thoroughly before you install the Microsoft Application Virtualization (App-V) Management System.</span></span> <span data-ttu-id="158a5-106">這些版本資訊包含可協助您成功安裝應用程式虛擬化（App-v） 4.6 SP3 的資訊。</span><span class="sxs-lookup"><span data-stu-id="158a5-106">These Release Notes contain information that helps you successfully install Application Virtualization (App-V)4.6 SP3.</span></span> <span data-ttu-id="158a5-107">此檔包含產品檔中不提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="158a5-107">This document contains information that is not available in the product documentation.</span></span> <span data-ttu-id="158a5-108">如果這些版本資訊與其他 App-v 檔之間有差異，最新變更應視為權威性。</span><span class="sxs-lookup"><span data-stu-id="158a5-108">If there is a difference between these Release Notes and other App-V documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="158a5-109">這些版本資訊取代本產品隨附的內容。</span><span class="sxs-lookup"><span data-stu-id="158a5-109">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="158a5-110">防範安全性漏洞與病毒</span><span class="sxs-lookup"><span data-stu-id="158a5-110">Protect Against Security Vulnerabilities and Viruses</span></span>


<span data-ttu-id="158a5-111">若要協助防範安全性漏洞和病毒，請務必為任何要安裝的新軟體安裝最新的可用安全更新。</span><span class="sxs-lookup"><span data-stu-id="158a5-111">To help protect against security vulnerabilities and viruses, it is important to install the latest available security updates for any new software being installed.</span></span> <span data-ttu-id="158a5-112">如需詳細資訊，請參閱[Microsoft 安全性網站](https://go.microsoft.com/fwlink/?LinkId=3482)（ https://go.microsoft.com/fwlink/?LinkId=3482) 。</span><span class="sxs-lookup"><span data-stu-id="158a5-112">For more information, see the [Microsoft Security website](https://go.microsoft.com/fwlink/?LinkId=3482) (https://go.microsoft.com/fwlink/?LinkId=3482).</span></span>

## <span data-ttu-id="158a5-113">Application Virtualization 4.6 SP3 的已知問題</span><span class="sxs-lookup"><span data-stu-id="158a5-113">Known Issues with Application Virtualization4.6 SP3</span></span>


<span data-ttu-id="158a5-114">本節提供有關 Microsoft Application Virtualization （App-v） 4.6 SP3 之問題的最新資訊。</span><span class="sxs-lookup"><span data-stu-id="158a5-114">This section provides the most up-to-date information about issues with Microsoft Application Virtualization (App-V)4.6SP3.</span></span> <span data-ttu-id="158a5-115">這些問題不會出現在產品檔中，某些情況下，可能會矛盾現有的產品檔。</span><span class="sxs-lookup"><span data-stu-id="158a5-115">These issues do not appear in the product documentation and in some cases might contradict existing product documentation.</span></span> <span data-ttu-id="158a5-116">如果可能的話，這些問題將會在稍後的版本中解決。</span><span class="sxs-lookup"><span data-stu-id="158a5-116">When it is possible, these issues will be addressed in later releases.</span></span>

### <span data-ttu-id="158a5-117">無法在虛擬環境中使用網際網路 Explorer11 在 Microsoft Windows 8.1 上開啟超連結</span><span class="sxs-lookup"><span data-stu-id="158a5-117">Unable to open hyperlinks using Internet Explorer11 on Microsoft Windows 8.1 within the Virtual Environment</span></span>

<span data-ttu-id="158a5-118">在使用 Internet Explorer 11 的 Windows 8.1 上，嘗試從虛擬環境中開啟超連結時，將會失敗。</span><span class="sxs-lookup"><span data-stu-id="158a5-118">Attempting to open hyperlinks from within a virtual environment will fail on Windows 8.1 using Internet Explorer 11.</span></span> <span data-ttu-id="158a5-119">這是因為 Internet Explorer 11 現已隨附預設啟用的增強保護模式（EPM），因此這會導致 App-v 無法存取必要的登錄機碼、檔案和通訊埠物件。</span><span class="sxs-lookup"><span data-stu-id="158a5-119">This is because Internet Explorer 11 now ships with the Enhanced Protection Mode (EPM) enabled by default and this causes App-V to be unable to access required registry keys, files and communication port objects.</span></span>

<span data-ttu-id="158a5-120">因應措施：在開啟 App-V 套件前，停用 [網際網路 Explorer11] 中的 EPM。</span><span class="sxs-lookup"><span data-stu-id="158a5-120">WORKAROUND: Disable EPM in Internet Explorer11 before opening an App-V package.</span></span> <span data-ttu-id="158a5-121">這可讓您從虛擬環境中開啟 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="158a5-121">This will allow you to open Internet Explorer from within the virtual environment.</span></span>

## <span data-ttu-id="158a5-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="158a5-122">Related topics</span></span>


[<span data-ttu-id="158a5-123">關於 Microsoft Application Virtualization 4.6 SP3</span><span class="sxs-lookup"><span data-stu-id="158a5-123">About Microsoft Application Virtualization 4.6 SP3</span></span>](about-microsoft-application-virtualization-46-sp3.md)

 

 





