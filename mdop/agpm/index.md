---
title: 進階群組原則管理
description: 進階群組原則管理
author: dansimp
ms.assetid: 493ca3c3-c3d6-4bb1-9430-dc1e43c86bb0
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/23/2017
ms.openlocfilehash: 457cca9db5d39466691b0bc7c41455910b4483d5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795486"
---
# <span data-ttu-id="01c9a-103">進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="01c9a-103">Advanced Group Policy Management</span></span>


<span data-ttu-id="01c9a-104">Microsoft 高級群組原則管理（AGPM）延伸了群組原則管理主控台（GPMC）的功能，以提供全面的變更控制及針對群組原則物件（Gpo）改進的管理。</span><span class="sxs-lookup"><span data-stu-id="01c9a-104">Microsoft Advanced Group Policy Management (AGPM) extends the capabilities of the Group Policy Management Console (GPMC) to provide comprehensive change control and improved management for Group Policy Objects (GPOs).</span></span> <span data-ttu-id="01c9a-105">在軟體保證的 Microsoft 桌面優化套件（MDOP）中，您可以使用 AGPM。</span><span class="sxs-lookup"><span data-stu-id="01c9a-105">AGPM is available as part of the Microsoft Desktop Optimization Pack (MDOP) for Software Assurance.</span></span>

## <span data-ttu-id="01c9a-106">AGPM 版本資訊</span><span class="sxs-lookup"><span data-stu-id="01c9a-106">AGPM Version Information</span></span>


<span data-ttu-id="01c9a-107">[AGPM 4.0 SP3](agpm-40-sp3-navengl.md)支援 Windows 10，windows server 2019，windows server 2016，windows Server 2012 R2，windows 8.1，windows server 2012，Windows Server 2008 R2，windows 7，windows server 2008，以及 windows Vista （含 SP1）。</span><span class="sxs-lookup"><span data-stu-id="01c9a-107">[AGPM 4.0 SP3](agpm-40-sp3-navengl.md) supports Windows 10, Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows 8.1, Windows Server 2012, Windows Server 2008 R2, Windows 7, Windows Server 2008, and Windows Vista with SP1.</span></span>

<span data-ttu-id="01c9a-108">[AGPM 4.0 SP2](agpm-40-sp2-navengl.md)支援 Windows Server 2012 R2、windows 8.1、windows server 2012、windows Server 2008 R2、windows 7、windows server 2008 及 windows Vista （含 SP1）。</span><span class="sxs-lookup"><span data-stu-id="01c9a-108">[AGPM 4.0 SP2](agpm-40-sp2-navengl.md) supports Windows Server 2012 R2, Windows 8.1, Windows Server 2012, Windows Server 2008 R2, Windows 7, Windows Server 2008, and Windows Vista with SP1.</span></span>

<span data-ttu-id="01c9a-109">[AGPM 4.0 SP1](agpm-40-sp1-navengl.md)支援 windows server 2012、windows Server 2008 R2、windows 7、windows server 2008 及 windows Vista （含 SP1）。</span><span class="sxs-lookup"><span data-stu-id="01c9a-109">[AGPM 4.0 SP1](agpm-40-sp1-navengl.md) supports Windows Server 2012, Windows Server 2008 R2, Windows 7, Windows Server 2008, and Windows Vista with SP1.</span></span>

<span data-ttu-id="01c9a-110">[AGPM 4](agpm-4-navengl.md)支援 windows Server 2008 R2、windows 7、windows Server 2008 及 windows Vista （含 SP1）。</span><span class="sxs-lookup"><span data-stu-id="01c9a-110">[AGPM 4](agpm-4-navengl.md) supports Windows Server 2008 R2, Windows 7, Windows Server 2008, and Windows Vista with SP1.</span></span>

<span data-ttu-id="01c9a-111">[AGPM 3](agpm-3-navengl.md)支援 windows Server 2008 和 windows Vista （含 SP1）。</span><span class="sxs-lookup"><span data-stu-id="01c9a-111">[AGPM 3](agpm-3-navengl.md) supports Windows Server 2008 and Windows Vista with SP1.</span></span>

<span data-ttu-id="01c9a-112">[AGPM 2.5](agpm-25-navengl.md)支援 Windows Vista （32位），沒有 service Pack 和 Windows Server 2003 （32）。</span><span class="sxs-lookup"><span data-stu-id="01c9a-112">[AGPM 2.5](agpm-25-navengl.md) supports Windows Vista (32-bit) with no service pack and Windows Server 2003 (32-bit).</span></span>

## <span data-ttu-id="01c9a-113">附加的 MDOP 產品指南</span><span class="sxs-lookup"><span data-stu-id="01c9a-113">Supplemental MDOP Product Guidance</span></span>


<span data-ttu-id="01c9a-114">除了線上提供的產品檔，在大多數的 MDOP 產品中都提供了補充性產品指示（例如，資訊影片和虛擬實驗）。</span><span class="sxs-lookup"><span data-stu-id="01c9a-114">In addition to the product documentation available online, supplemental product guidance such as informational videos and virtual labs are available for most MDOP products.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="01c9a-115">MDOP 虛擬實驗</span><span class="sxs-lookup"><span data-stu-id="01c9a-115">MDOP Virtual Labs</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="01c9a-116">如需可用的 MDOP 虛擬實驗清單，請移至 <a href="https://go.microsoft.com/fwlink/?LinkId=234276" data-raw-source="[Microsoft Desktop Optimization Pack (MDOP) Virtual Labs](https://go.microsoft.com/fwlink/?LinkId=234276)"> Microsoft 桌面優化套件（MDOP）虛擬實驗室 </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=234276" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=234276"> https://go.microsoft.com/fwlink/?LinkId=234276 </a> ）。</span><span class="sxs-lookup"><span data-stu-id="01c9a-116">For a list of available MDOP virtual labs, go to <a href="https://go.microsoft.com/fwlink/?LinkId=234276" data-raw-source="[Microsoft Desktop Optimization Pack (MDOP) Virtual Labs](https://go.microsoft.com/fwlink/?LinkId=234276)">Microsoft Desktop Optimization Pack (MDOP) Virtual Labs</a> (<a href="https://go.microsoft.com/fwlink/?LinkId=234276" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=234276">https://go.microsoft.com/fwlink/?LinkId=234276</a>).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="01c9a-117">MDOP 技術中心</span><span class="sxs-lookup"><span data-stu-id="01c9a-117">MDOP TechCenter</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="01c9a-118">如需技術白皮書、評估資料、博客及其他 MDOP 資源，請移至 <a href="https://go.microsoft.com/fwlink/?LinkId=225286" data-raw-source="[MDOP TechCenter](https://go.microsoft.com/fwlink/?LinkId=225286)"> MDOP 技術中心 </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=225286" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=225286"> https://go.microsoft.com/fwlink/?LinkId=225286 </a> ）</span><span class="sxs-lookup"><span data-stu-id="01c9a-118">For technical whitepapers, evaluation materials, blogs, and additional MDOP resources, go to <a href="https://go.microsoft.com/fwlink/?LinkId=225286" data-raw-source="[MDOP TechCenter](https://go.microsoft.com/fwlink/?LinkId=225286)">MDOP TechCenter</a> (<a href="https://go.microsoft.com/fwlink/?LinkId=225286" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=225286">https://go.microsoft.com/fwlink/?LinkId=225286</a>)</span></span></p>
<p></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-getmdop"></a><span data-ttu-id="01c9a-119">如何取得 MDOP</span><span class="sxs-lookup"><span data-stu-id="01c9a-119">How to Get MDOP</span></span>


<span data-ttu-id="01c9a-120">MDOP 是一套產品，可協助簡化整個企業的桌面部署、管理和支援。</span><span class="sxs-lookup"><span data-stu-id="01c9a-120">MDOP is a suite of products that can help streamline desktop deployment, management, and support across the enterprise.</span></span> <span data-ttu-id="01c9a-121">MDOP 是提供給軟體保證客戶的附加訂閱。</span><span class="sxs-lookup"><span data-stu-id="01c9a-121">MDOP is available as an additional subscription for Software Assurance customers.</span></span>

<a href="" id="evaluate-mdop"></a><span data-ttu-id="01c9a-122">**評估 MDOP**您也可以依照 MSDN 和 TechNet 協定，將 MDOP 提供給[msdn](https://msdn.microsoft.com/subscriptions/downloads/default.aspx?PV=42:178)和[technet](https://technet.microsoft.com/subscriptions/downloads/default.aspx?PV=42:178)訂閱者，以進行測試和評估。</span><span class="sxs-lookup"><span data-stu-id="01c9a-122">**Evaluate MDOP** MDOP is also available for test and evaluation to [MSDN](https://msdn.microsoft.com/subscriptions/downloads/default.aspx?PV=42:178) and [TechNet](https://technet.microsoft.com/subscriptions/downloads/default.aspx?PV=42:178) subscribers in accordance with MSDN and TechNet agreements.</span></span>

<a href="" id="download-mdop"></a><span data-ttu-id="01c9a-123">**下載 MDOP**MDOP 訂閱者可以在[Microsoft 大量授權網站下載軟體（MVLS）](https://go.microsoft.com/fwlink/?LinkId=166331)。</span><span class="sxs-lookup"><span data-stu-id="01c9a-123">**Download MDOP** MDOP subscribers can download the software at the [Microsoft Volume Licensing website (MVLS)](https://go.microsoft.com/fwlink/?LinkId=166331).</span></span>

<a href="" id="purchase-mdop"></a><span data-ttu-id="01c9a-124">**購買 MDOP**請造訪企業[購買 Windows 企業版授權](https://www.microsoft.com/windows/enterprise/how-to-buy.aspx)網站，瞭解如何為您的企業購買 MDOP。</span><span class="sxs-lookup"><span data-stu-id="01c9a-124">**Purchase MDOP** Visit the enterprise [Purchase Windows Enterprise Licensing](https://www.microsoft.com/windows/enterprise/how-to-buy.aspx) website to find out how to purchase MDOP for your business.</span></span>

 

 





