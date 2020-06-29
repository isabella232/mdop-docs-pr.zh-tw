---
title: 部署 DaRT 7.0 到系統管理員電腦
description: 部署 DaRT 7.0 到系統管理員電腦
author: dansimp
ms.assetid: 8baf26aa-b168-463c-810f-a165918b9d9f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 96eda08e28b915e30d88aa57cb19562958848cf4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800156"
---
# <span data-ttu-id="6cb05-103">部署 DaRT 7.0 到系統管理員電腦</span><span class="sxs-lookup"><span data-stu-id="6cb05-103">Deploying DaRT 7.0 to Administrator Computers</span></span>


<span data-ttu-id="6cb05-104">開始部署 Microsoft Diagnostics 和恢復工具集（DaRT）7之前，請先審查您的環境需求。</span><span class="sxs-lookup"><span data-stu-id="6cb05-104">Before you begin the deployment of Microsoft Diagnostics and Recovery Toolset (DaRT)7, review the requirements for your environment.</span></span> <span data-ttu-id="6cb05-105">這包括安裝 DaRT 的硬體需求。</span><span class="sxs-lookup"><span data-stu-id="6cb05-105">This includes the hardware requirements for installing DaRT.</span></span> <span data-ttu-id="6cb05-106">如需有關 DaRT 硬體和軟體需求的詳細資訊，請參閱[dart 7.0 支援](dart-70-supported-configurations-dart-7.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="6cb05-106">For more information about DaRT hardware and software requirements, see [DaRT 7.0 Supported Configurations](dart-70-supported-configurations-dart-7.md).</span></span>

<span data-ttu-id="6cb05-107">本節中的主題可用來協助您根據您的環境和部署策略，在企業中部署 DaRT。</span><span class="sxs-lookup"><span data-stu-id="6cb05-107">The topics in this section can be used to help you deploy DaRT in your enterprise based on your environment and deployment strategy.</span></span>

## <span data-ttu-id="6cb05-108">將 DaRT 7.0 部署到系統管理員電腦</span><span class="sxs-lookup"><span data-stu-id="6cb05-108">Deploy DaRT 7.0 to administrator computers</span></span>


<span data-ttu-id="6cb05-109">您可以使用 DaRT 的 Windows Installer 檔案，在您要用來建立 DaRT 復原影像的電腦上安裝 DaRT，然後針對最終使用者電腦進行疑難排解及修正。</span><span class="sxs-lookup"><span data-stu-id="6cb05-109">You can use the Windows Installer file for DaRT to install DaRT on a computer that you will use to first create the DaRT recovery image and then troubleshoot and fix end-user computers.</span></span> <span data-ttu-id="6cb05-110">通常，在整個組織中，您可能只會在系統管理員電腦上安裝您要建立 DaRT 復原影像所需的 DaRT 功能。</span><span class="sxs-lookup"><span data-stu-id="6cb05-110">Frequently, across an organization, you might install on the administrator computer only the DaRT functionality that you need to create a DaRT recovery image.</span></span> <span data-ttu-id="6cb05-111">然後，在技術支援人員的電腦上，您可能只安裝必須用來排查問題電腦的 DaRT 功能，例如 DaRT 遠端連線檢視器和損毀分析程式。</span><span class="sxs-lookup"><span data-stu-id="6cb05-111">Then, on a helpdesk administrator’s computer, you might install only the DaRT functionality that you must have to troubleshoot a problem computer, such as the DaRT Remote Connection Viewer and the Crash Analyzer.</span></span>

<span data-ttu-id="6cb05-112">除了手動執行 Windows 安裝程式檔案以安裝 DaRT 之外，您也可以在命令提示字元中安裝 DaRT，以支援企業軟體部署系統（例如 SystemCenterConfigurationManager2012）。</span><span class="sxs-lookup"><span data-stu-id="6cb05-112">In addition to manually running the Windows Installer file to install DaRT, you can also install DaRT at the command prompt to support enterprise software deployment systems such as SystemCenterConfigurationManager2012.</span></span>

[<span data-ttu-id="6cb05-113">如何部署 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="6cb05-113">How to Deploy DaRT 7.0</span></span>](how-to-deploy-dart-70.md)

## <span data-ttu-id="6cb05-114">變更、修復或移除 DaRT 7。0</span><span class="sxs-lookup"><span data-stu-id="6cb05-114">Change, repair, or remove DaRT 7.0</span></span>


<span data-ttu-id="6cb05-115">若要變更、修復或移除 DaRT 安裝，請按兩下 DaRT 安裝檔案，然後按一下對應至您要執行之動作的按鈕，或透過 Windows [控制台] 進行。</span><span class="sxs-lookup"><span data-stu-id="6cb05-115">You can change, repair, or remove the DaRT installation by double-clicking the DaRT installation file and then clicking the button that corresponds to the action that you want to perform or through the Windows Control Panel.</span></span>

[<span data-ttu-id="6cb05-116">如何變更、修復或移除 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="6cb05-116">How to Change, Repair, or Remove DaRT 7.0</span></span>](how-to-change-repair-or-remove-dart-70.md)

## <span data-ttu-id="6cb05-117">將 DaRT 7.0 部署到系統管理員電腦的其他資源</span><span class="sxs-lookup"><span data-stu-id="6cb05-117">Other resources for Deploying the DaRT 7.0 to Administrator Computers</span></span>


-   [<span data-ttu-id="6cb05-118">部署 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="6cb05-118">Deploying DaRT 7.0</span></span>](deploying-dart-70-new-ia.md)

 

 





