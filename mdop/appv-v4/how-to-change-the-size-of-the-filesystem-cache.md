---
title: 如何變更 FileSystem 快取的大小
description: 如何變更 FileSystem 快取的大小
author: dansimp
ms.assetid: 6ed17ba3-293b-4482-b3fa-31e5f606dad6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d63c98d53ccb31e8eb64bc70d3d79b2198c506e2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801642"
---
# <span data-ttu-id="6d136-103">如何變更 FileSystem 快取的大小</span><span class="sxs-lookup"><span data-stu-id="6d136-103">How to Change the Size of the FileSystem Cache</span></span>


<span data-ttu-id="6d136-104">您可以使用命令列來變更 FileSystem 快取的大小。</span><span class="sxs-lookup"><span data-stu-id="6d136-104">You can change the size of the FileSystem cache by using the command line.</span></span> <span data-ttu-id="6d136-105">此動作需要完整的快取重設，且需要管理許可權。</span><span class="sxs-lookup"><span data-stu-id="6d136-105">This action requires a complete reset of the cache, and it requires administrative rights.</span></span>

**<span data-ttu-id="6d136-106">變更 FileSystem 快取的大小</span><span class="sxs-lookup"><span data-stu-id="6d136-106">To change the size of the FileSystem cache</span></span>**

1.  <span data-ttu-id="6d136-107">將下列登錄值設定為0（零）：</span><span class="sxs-lookup"><span data-stu-id="6d136-107">Set the following registry value to 0 (zero):</span></span>

    <span data-ttu-id="6d136-108">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\State</span><span class="sxs-lookup"><span data-stu-id="6d136-108">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\State</span></span>

2.  <span data-ttu-id="6d136-109">將下列登錄值設定為包含套件所需的大小上限（以 MB 為單位），例如，8192 MB：</span><span class="sxs-lookup"><span data-stu-id="6d136-109">Set the following registry value to the maximum cache size, in MB, that is necessary to hold the packages—for example, 8192 MB:</span></span>

    <span data-ttu-id="6d136-110">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\FileSize</span><span class="sxs-lookup"><span data-stu-id="6d136-110">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\FileSize</span></span>

3.  <span data-ttu-id="6d136-111">重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="6d136-111">Restart the computer.</span></span>

## <span data-ttu-id="6d136-112">相關主題</span><span class="sxs-lookup"><span data-stu-id="6d136-112">Related topics</span></span>


[<span data-ttu-id="6d136-113">如何使用命令列設定 App-V 用戶端登錄設定</span><span class="sxs-lookup"><span data-stu-id="6d136-113">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





