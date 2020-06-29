---
title: 如何變更伺服器快取大小
description: 如何變更伺服器快取大小
author: dansimp
ms.assetid: 24e63744-21c3-458e-b137-9592f4fe785c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 92e56a8a28f7a00d71805b497f9e404cca65919d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801653"
---
# <span data-ttu-id="f7635-103">如何變更伺服器快取大小</span><span class="sxs-lookup"><span data-stu-id="f7635-103">How to Change the Server Cache Size</span></span>


<span data-ttu-id="f7635-104">您可以使用下列程式，直接從應用程式虛擬化伺服器管理主控台變更任何伺服器的快取大小。</span><span class="sxs-lookup"><span data-stu-id="f7635-104">You can use the following procedure to change the cache size for any server directly from the Application Virtualization Server Management Console.</span></span>

<span data-ttu-id="f7635-105">**記事** 雖然您可以變更快取大小，除非您的設定明確要求您變更大小，否則建議您將快取大小保持為預設值。</span><span class="sxs-lookup"><span data-stu-id="f7635-105">**Note** Although you can change the cache size, unless your configuration specifically requires you to change the size, it is recommended that you leave the cache size set to the default values.</span></span>

 

**<span data-ttu-id="f7635-106">變更伺服器快取大小</span><span class="sxs-lookup"><span data-stu-id="f7635-106">To change the server cache size</span></span>**

1.  <span data-ttu-id="f7635-107">按一下左窗格中的 [**伺服器群組**] 節點，展開伺服器群組清單。</span><span class="sxs-lookup"><span data-stu-id="f7635-107">Click the **Server Groups** node in the left pane to expand the list of server groups.</span></span>

2.  <span data-ttu-id="f7635-108">在 [**結果**] 窗格中，按兩下所需的伺服器群組，以顯示群組中的伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="f7635-108">In the **Results** pane, double-click the desired server group to display the list of servers in the group.</span></span>

3.  <span data-ttu-id="f7635-109">在 [**結果**] 窗格中，以滑鼠右鍵按一下所需的伺服器，然後選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="f7635-109">In the **Results** pane, right-click the desired server and select **Properties**.</span></span>

4.  <span data-ttu-id="f7635-110">選取 [**高級**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="f7635-110">Select the **Advanced** tab.</span></span>

5.  <span data-ttu-id="f7635-111">在伺服器快取的 [**最大記憶體配置**] 欄位中輸入一個值，然後在 [**警告記憶體分派**] 欄位中輸入閾值警告層級的值。</span><span class="sxs-lookup"><span data-stu-id="f7635-111">Enter a value in the **Maximum Memory Allocation** field for the server cache, and enter a value for the threshold warning level in the **Warn Memory Allocation** field.</span></span>

6.  <span data-ttu-id="f7635-112">在 [**最大區塊大小**] 欄位中輸入值。</span><span class="sxs-lookup"><span data-stu-id="f7635-112">Enter a value in the **Maximum Block Size** field.</span></span> <span data-ttu-id="f7635-113">這個數位必須大於或等於將從伺服器傳送資料流程的最大套件區塊大小。</span><span class="sxs-lookup"><span data-stu-id="f7635-113">This number must be greater than or equal to the maximum block size of the largest package that will be streamed from the server.</span></span>

7.  <span data-ttu-id="f7635-114">按一下 **\[確定\]**。</span><span class="sxs-lookup"><span data-stu-id="f7635-114">Click **OK**.</span></span>

## <span data-ttu-id="f7635-115">相關主題</span><span class="sxs-lookup"><span data-stu-id="f7635-115">Related topics</span></span>


[<span data-ttu-id="f7635-116">如何變更伺服器連結埠</span><span class="sxs-lookup"><span data-stu-id="f7635-116">How to Change the Server Port</span></span>](how-to-change-the-server-port.md)

[<span data-ttu-id="f7635-117">如何在伺服器管理主控台中管理伺服器</span><span class="sxs-lookup"><span data-stu-id="f7635-117">How to Manage Servers in the Server Management Console</span></span>](how-to-manage-servers-in-the-server-management-console.md)

 

 





