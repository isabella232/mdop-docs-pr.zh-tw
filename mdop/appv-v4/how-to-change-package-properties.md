---
title: 如何變更封裝內容
description: 如何變更封裝內容
author: dansimp
ms.assetid: 6050916a-d4fe-4dac-8f2a-47308dbbf481
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d2427a2651f3941f967c171ae7854facc62b4aa9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801658"
---
# <span data-ttu-id="13945-103">如何變更封裝內容</span><span class="sxs-lookup"><span data-stu-id="13945-103">How to Change Package Properties</span></span>


<span data-ttu-id="13945-104">您可以使用下列程式來修改應用程式虛擬化套件名稱及其相關的批註。</span><span class="sxs-lookup"><span data-stu-id="13945-104">You can use the following procedures to modify an Application Virtualization package name and its associated comments.</span></span>

<span data-ttu-id="13945-105">如果這是您第一次建立套件，您也可以變更順序參數區塊大小，決定順序式應用程式套件如何從應用程式虛擬化伺服器傳送到應用程式虛擬化桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="13945-105">If this is the first time the package has been created, you can also change the sequencing parameter block size, which determines how a sequenced application package is streamed from an Application Virtualization Server to an Application Virtualization Desktop Client.</span></span>

<span data-ttu-id="13945-106">**記事** 選取區塊大小時，請考慮 SFT 檔案和網路頻寬的大小。</span><span class="sxs-lookup"><span data-stu-id="13945-106">**Note** When selecting a block size, consider the size of the SFT file and your network bandwidth.</span></span> <span data-ttu-id="13945-107">區塊大小較小的檔案需要花較長的時間，才能在網路上傳輸，但頻寬較少。</span><span class="sxs-lookup"><span data-stu-id="13945-107">A file with a smaller block size takes longer to stream over the network, but it is less bandwidth intensive.</span></span> <span data-ttu-id="13945-108">區塊大小較大的檔案速度可能較快，但使用的網路頻寬更多。</span><span class="sxs-lookup"><span data-stu-id="13945-108">Files with larger block sizes might stream faster, but they use more network bandwidth.</span></span> <span data-ttu-id="13945-109">透過實驗，您可以探索您網路上的資料流程應用程式的最佳區塊大小。</span><span class="sxs-lookup"><span data-stu-id="13945-109">Through experimentation, you can discover the optimum block size for streaming applications on your network.</span></span>

 

<span data-ttu-id="13945-110">[**屬性**] 索引標籤上的 [套件屬性] 的剩餘部分會自動產生，且無法在此索引標籤上修改。</span><span class="sxs-lookup"><span data-stu-id="13945-110">The remainder of the package properties on the **Properties** tab is automatically generated and cannot be modified on this tab.</span></span>

**<span data-ttu-id="13945-111">變更套件名稱或批註</span><span class="sxs-lookup"><span data-stu-id="13945-111">To change the package name or comments</span></span>**

1.  <span data-ttu-id="13945-112">按一下 [**屬性**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="13945-112">Click the **Properties** tab.</span></span>

2.  <span data-ttu-id="13945-113">在 [**套件名稱**] 文字方塊中，輸入或編輯套件所使用的單一名稱，其中可以包含多個應用程式。</span><span class="sxs-lookup"><span data-stu-id="13945-113">In the **Package Name** text box, enter or edit the single name used for the package, which can contain multiple applications.</span></span>

3.  <span data-ttu-id="13945-114">在 [**批註**] 文字方塊中，選擇性地輸入或編輯任何批註。</span><span class="sxs-lookup"><span data-stu-id="13945-114">In the **Comments** text box, optionally enter or edit any comments.</span></span> <span data-ttu-id="13945-115">建議的最佳做法是提供有關封裝及排序的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="13945-115">The suggested best practice is to provide detail information about the package and sequencing.</span></span>

4.  <span data-ttu-id="13945-116">從 [**檔案**] 功能表中，選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="13945-116">From the **File** menu, select **Save**.</span></span>

**<span data-ttu-id="13945-117">變更組塊大小</span><span class="sxs-lookup"><span data-stu-id="13945-117">To change the block size</span></span>**

1.  <span data-ttu-id="13945-118">按一下 [**屬性**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="13945-118">Click the **Properties** tab.</span></span>

2.  <span data-ttu-id="13945-119">在 [**區塊大小**] 下拉式清單中，選取 [ **4 kb**]、[ **16 KB**]、[ **32 KB**] 或 [ **64 kb**]。</span><span class="sxs-lookup"><span data-stu-id="13945-119">On the **Block Size** drop-down list, select **4 KB**, **16 KB**, **32 KB**, or **64 KB**.</span></span>

3.  <span data-ttu-id="13945-120">從 [**檔案**] 功能表中，選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="13945-120">From the **File** menu, select **Save**.</span></span>

## <span data-ttu-id="13945-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="13945-121">Related topics</span></span>


[<span data-ttu-id="13945-122">關於內容索引標籤</span><span class="sxs-lookup"><span data-stu-id="13945-122">About the Properties Tab</span></span>](about-the-properties-tab.md)

[<span data-ttu-id="13945-123">排序器主控台</span><span class="sxs-lookup"><span data-stu-id="13945-123">Sequencer Console</span></span>](sequencer-console.md)

 

 





