---
title: 關於使用排序器命令列
description: 關於使用排序器命令列
author: dansimp
ms.assetid: 0fd5f81b-17f9-4065-bce2-8785e8aac7c7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: afb3fb8608c78a3b9237a80529a6c22d792661ba
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802402"
---
# <span data-ttu-id="78428-103">關於使用排序器命令列</span><span class="sxs-lookup"><span data-stu-id="78428-103">About Using the Sequencer Command Line</span></span>


<span data-ttu-id="78428-104">您可以使用命令列來建立已排序的應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="78428-104">You can use the command line to create sequenced application packages.</span></span> <span data-ttu-id="78428-105">使用命令列建立虛擬應用程式在下列案例中很有用：</span><span class="sxs-lookup"><span data-stu-id="78428-105">Using the command line to create virtual applications is useful in the following scenarios:</span></span>

-   <span data-ttu-id="78428-106">您需要建立大量的順序應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="78428-106">You need to create a large number of sequenced application packages.</span></span>

-   <span data-ttu-id="78428-107">您需要定期建立順序應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="78428-107">You need to create a sequenced application package on a recurring basis.</span></span>

<span data-ttu-id="78428-108">**重要** 在命令提示字元進行排序只允許預設排序。</span><span class="sxs-lookup"><span data-stu-id="78428-108">**Important** Sequencing at the command prompt allows for default sequencing only.</span></span> <span data-ttu-id="78428-109">如果您需要變更預設的順序參數，您必須手動修改已排序的應用程式套件，或重新排列應用程式。</span><span class="sxs-lookup"><span data-stu-id="78428-109">If you need to change default sequencing parameters, you must either manually modify a sequenced application package or re-sequence the application.</span></span>

 

<span data-ttu-id="78428-110">您必須使用 [順序] 嚮導來建立對現有順序應用程式套件所做的所有後續修改。</span><span class="sxs-lookup"><span data-stu-id="78428-110">All subsequent modifications to existing sequenced application packages must be made using the sequencing wizard.</span></span>

## <span data-ttu-id="78428-111">必要條件</span><span class="sxs-lookup"><span data-stu-id="78428-111">Prerequisites</span></span>


<span data-ttu-id="78428-112">若要使用命令提示字元對應用程式進行排序，必須符合下列條件：</span><span class="sxs-lookup"><span data-stu-id="78428-112">To sequence an application by using the command prompt, the following conditions must be met:</span></span>

-   <span data-ttu-id="78428-113">要成為已排序的應用程式，不得在安裝程式或 Windows 安裝程式套件外，不需要對其進行變更或因應措施。</span><span class="sxs-lookup"><span data-stu-id="78428-113">The application that is about to be sequenced must not require changes or workarounds made to it outside the installer or Windows Installer package.</span></span>

-   <span data-ttu-id="78428-114">排序前，您必須準備批次檔案清單，以建立已排序的應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="78428-114">Before sequencing, you must prepare a list of batch files for creating the sequenced application packages.</span></span>

-   <span data-ttu-id="78428-115">複查有關命令列參數的詳細資訊，請參閱[命令列參數](command-line-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="78428-115">Review For more information about the command line parameters, see [Command-Line Parameters](command-line-parameters.md).</span></span>

-   <span data-ttu-id="78428-116">使用命令列來查看建立排序的應用程式套件時可能會顯示的錯誤。</span><span class="sxs-lookup"><span data-stu-id="78428-116">Review the errors that might be displayed when creating a sequenced application package by using the command line.</span></span> <span data-ttu-id="78428-117">如需詳細資訊，請參閱錯誤的[命令列錯誤](command-line-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="78428-117">For more information, see these errors, see [Command-Line Errors](command-line-errors.md).</span></span>

## <span data-ttu-id="78428-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="78428-118">Related topics</span></span>


[<span data-ttu-id="78428-119">如何使用命令列管理虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="78428-119">How to Manage Virtual Applications Using the Command Line</span></span>](how-to-manage-virtual-applications-using-the-command-line.md)

 

 





