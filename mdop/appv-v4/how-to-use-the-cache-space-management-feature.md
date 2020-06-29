---
title: 如何使用快取空間管理功能
description: 如何使用快取空間管理功能
author: dansimp
ms.assetid: 60965660-c015-46a8-88ac-54cbc050fe33
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fcb9cc4bc076e1acf52fb1c03797384c45b82f7b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801013"
---
# <span data-ttu-id="c575b-103">如何使用快取空間管理功能</span><span class="sxs-lookup"><span data-stu-id="c575b-103">How to Use the Cache Space Management Feature</span></span>


<span data-ttu-id="c575b-104">FileSystem 快取空間管理功能使用最新使用的（LRU）演算法，且預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="c575b-104">The FileSystem cache space management feature uses a Least Recently Used (LRU) algorithm and is enabled by default.</span></span> <span data-ttu-id="c575b-105">如果新套件所需的空間超過快取中的可用空間，應用程式虛擬化（App-v）用戶端會使用這項功能來判斷它可以從快取中刪除的現有套件（如果有的話），為新套件騰出空間。</span><span class="sxs-lookup"><span data-stu-id="c575b-105">If the space that is required for a new package would exceed the available free space in the cache, the Application Virtualization (App-V) Client uses this feature to determine which, if any, existing packages it can delete from the cache to make room for the new package.</span></span> <span data-ttu-id="c575b-106">用戶端會刪除最舊的最近存取日期的套件（如果它比 MinPkgAge 註冊表值中指定的值還舊）。</span><span class="sxs-lookup"><span data-stu-id="c575b-106">The client deletes the package with the oldest last-accessed date if it is older than the value specified in the MinPkgAge registry value.</span></span> <span data-ttu-id="c575b-107">使用 [FileSystem 快取空間管理] 功能也可協助避免較低的快取空間問題。</span><span class="sxs-lookup"><span data-stu-id="c575b-107">Use of the FileSystem cache space management feature can also help to avoid low cache space problems.</span></span>

<span data-ttu-id="c575b-108">如有需要，則會刪除一個以上的套件。</span><span class="sxs-lookup"><span data-stu-id="c575b-108">More than one package is deleted if necessary.</span></span> <span data-ttu-id="c575b-109">鎖定的套件不會被刪除。</span><span class="sxs-lookup"><span data-stu-id="c575b-109">Packages that are locked are not deleted.</span></span>

<span data-ttu-id="c575b-110">**記事** 若要確保快取已為所有已部署套件指派足夠的空間，請使用設定用戶端時使用的 [**可用磁碟空間閾值**] 設定，讓快取視需要增加。</span><span class="sxs-lookup"><span data-stu-id="c575b-110">**Note** To ensure that the cache has sufficient space allocated for all packages that might be deployed, use the **Use free disk space threshold** setting when you configure the client so that the cache can grow as needed.</span></span> <span data-ttu-id="c575b-111">或者，您可以在安裝期間預先決定需要多少磁碟空間，並在安裝時設定快取大小。</span><span class="sxs-lookup"><span data-stu-id="c575b-111">Alternatively, determine in advance how much disk space will be needed for the App-V cache, and at installation time, set the cache size accordingly.</span></span>

 

<span data-ttu-id="c575b-112">[快取空間管理] 功能是由 UnloadLeastRecentlyUsed 登錄值所控制。</span><span class="sxs-lookup"><span data-stu-id="c575b-112">The cache space management feature is controlled by the UnloadLeastRecentlyUsed registry value.</span></span> <span data-ttu-id="c575b-113">如果值為1，則會啟用此功能，而值0（零）則會停用它。</span><span class="sxs-lookup"><span data-stu-id="c575b-113">A value of 1 enables the feature, and a value of 0 (zero) disables it.</span></span>

**<span data-ttu-id="c575b-114">啟用或停用緩衝空間管理功能</span><span class="sxs-lookup"><span data-stu-id="c575b-114">To enable or disable the cache space management feature</span></span>**

-   <span data-ttu-id="c575b-115">將下列登錄值設定為1，以啟用 LRU 演算法。</span><span class="sxs-lookup"><span data-stu-id="c575b-115">Set the following registry value to 1 to enable the LRU algorithm.</span></span> <span data-ttu-id="c575b-116">將它設定為0（零）以停用此功能。</span><span class="sxs-lookup"><span data-stu-id="c575b-116">Set it to 0 (zero) to disable the feature.</span></span>

    <span data-ttu-id="c575b-117">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\UnloadLeastRecentlyUsed</span><span class="sxs-lookup"><span data-stu-id="c575b-117">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\UnloadLeastRecentlyUsed</span></span>

**<span data-ttu-id="c575b-118">控制可放棄哪些套件</span><span class="sxs-lookup"><span data-stu-id="c575b-118">To control which packages can be discarded</span></span>**

-   <span data-ttu-id="c575b-119">若要判斷何時可以選取要捨棄的套件，請將下列登錄值設為等於自上次存取套件後所要經過的最小天數。</span><span class="sxs-lookup"><span data-stu-id="c575b-119">To determine when the package can be selected for discard, set the following registry value to equal the minimum number of days you want to elapse since the package was last accessed.</span></span> <span data-ttu-id="c575b-120">您最近使用的套件將不會遭到捨棄。</span><span class="sxs-lookup"><span data-stu-id="c575b-120">Packages that have been used more recently are not discarded.</span></span>

    <span data-ttu-id="c575b-121">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\MinPkgAge</span><span class="sxs-lookup"><span data-stu-id="c575b-121">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\MinPkgAge</span></span>

    <span data-ttu-id="c575b-122">**小心** 此登錄機碼的最大值為0x00011111。</span><span class="sxs-lookup"><span data-stu-id="c575b-122">**Caution** The maximum value for this registry key is 0x00011111.</span></span> <span data-ttu-id="c575b-123">較大的值會使快取磁片管理功能的操作無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="c575b-123">Larger values will prevent the correct operation of the cache space management feature.</span></span>

     

## <span data-ttu-id="c575b-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="c575b-124">Related topics</span></span>


[<span data-ttu-id="c575b-125">如何使用命令列設定 App-V 用戶端登錄設定</span><span class="sxs-lookup"><span data-stu-id="c575b-125">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





