---
title: 維護 App-V 5.0
description: 維護 App-V 5.0
author: dansimp
ms.assetid: 66851ec3-c674-493b-ad6d-db8fcbf1956c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3445bfe00ba7703a66fa3da2f9d7089990dd3854
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800388"
---
# <span data-ttu-id="31b0b-103">維護 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="31b0b-103">Maintaining App-V 5.0</span></span>


<span data-ttu-id="31b0b-104">完成所有必要的規劃，然後部署 App-V 5.0 之後，您就可以使用下列資訊來維護 App-v 5.0 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="31b0b-104">After you have completed all the necessary planning, and then deployment of App-V 5.0, you can use the following information to maintain the App-V 5.0 infrastructure.</span></span>

## <a href="" id="move-the-app-v-5-0-server-"></a><span data-ttu-id="31b0b-105">移動 app-v 5.0 Server</span><span class="sxs-lookup"><span data-stu-id="31b0b-105">Move the App-V 5.0 Server</span></span>


<span data-ttu-id="31b0b-106">App-V 5.0 伺服器會連接到 App-v 5.0 資料庫。</span><span class="sxs-lookup"><span data-stu-id="31b0b-106">The App-V 5.0 server connects to the App-V 5.0 database.</span></span> <span data-ttu-id="31b0b-107">因此，您可以將管理元件安裝到網路上的任何電腦，然後將它連線到 App-v 5.0 資料庫。</span><span class="sxs-lookup"><span data-stu-id="31b0b-107">Therefore you can install the management component to any computer on the network and then connect it to the App-V 5.0 database.</span></span>

[<span data-ttu-id="31b0b-108">如何將 App-V 伺服器移動到另一部電腦</span><span class="sxs-lookup"><span data-stu-id="31b0b-108">How to Move the App-V Server to Another Computer</span></span>](how-to-move-the-app-v-server-to-another-computer.md)

## <a href="" id="determine-if-an-app-v-5-0-application-is-running-virtualized-"></a><span data-ttu-id="31b0b-109">判斷 App-V 5.0 應用程式是否正在執行虛擬化</span><span class="sxs-lookup"><span data-stu-id="31b0b-109">Determine if an App-V 5.0 Application is Running Virtualized</span></span>


<span data-ttu-id="31b0b-110">想要判斷應用程式是否正在使用 App-v 5.0 或更新版本進行虛擬化的獨立軟體廠商（ISV），應該在預設命名空間中開啟稱為\*\*AppVVirtual 的 &lt; &gt; \*\*命名物件。</span><span class="sxs-lookup"><span data-stu-id="31b0b-110">Independent software vendors (ISV) who want to determine if an application is running virtualized with App-V 5.0 or above, should open a named object called **AppVVirtual-&lt;PID&gt;** in the default namespace.</span></span> <span data-ttu-id="31b0b-111">例如，Windows API **GetCurrentProcessId （）** 可以用來取得目前進程的識別碼（例如4052），然後，如果可以使用**OpenEvent （）** 在預設命名空間中成功開啟名為**AppVVirtual-4052**的命名事件物件，則表示該應用程式是虛擬的。</span><span class="sxs-lookup"><span data-stu-id="31b0b-111">For example, Windows API **GetCurrentProcessId()** can be used to obtain the current process's ID, for example 4052, and then if a named Event object called **AppVVirtual-4052** can be successfully opened using **OpenEvent()** in the default namespace for read access, then the application is virtual.</span></span> <span data-ttu-id="31b0b-112">如果**OpenEvent （）** 通話失敗，應用程式就不是虛擬的。</span><span class="sxs-lookup"><span data-stu-id="31b0b-112">If the **OpenEvent()** call fails, the application is not virtual.</span></span>

<span data-ttu-id="31b0b-113">此外，如果 ISV 想要明確地虛擬化或不虛擬化對特定 API 的使用 App-v 5.0 和更新版本的呼叫，可以使用 AppEntSubsystems32.dll 模組中實現的**VirtualizeCurrentThread （）** 和**CurrentThreadIsVirtualized （）** 函數。</span><span class="sxs-lookup"><span data-stu-id="31b0b-113">Additionally, ISV’s who want to explicitly virtualize or not virtualize calls on specific API’s with App-V 5.0 and above, can use the **VirtualizeCurrentThread()** and **CurrentThreadIsVirtualized()** functions implemented in the AppEntSubsystems32.dll module.</span></span> <span data-ttu-id="31b0b-114">這些都提供一種在下游元件上進行的提示，應不要將呼叫虛擬化。</span><span class="sxs-lookup"><span data-stu-id="31b0b-114">These provide a way of hinting at a downstream component that the call should or should not be virtualized.</span></span>






## <span data-ttu-id="31b0b-115">維護 App 的其他資源-V 5。0</span><span class="sxs-lookup"><span data-stu-id="31b0b-115">Other resources for maintaining App-V 5.0</span></span>


[<span data-ttu-id="31b0b-116">App-V 5.0 作業</span><span class="sxs-lookup"><span data-stu-id="31b0b-116">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





