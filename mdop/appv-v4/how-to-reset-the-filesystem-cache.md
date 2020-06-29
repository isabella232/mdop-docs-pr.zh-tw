---
title: 如何重設 FileSystem 快取
description: 如何重設 FileSystem 快取
author: dansimp
ms.assetid: 7777259d-8c21-4c06-9384-9599b69f9828
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 680634d98f8aac048af605c62029a0ee6b20af03
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801126"
---
# <span data-ttu-id="4047b-103">如何重設 FileSystem 快取</span><span class="sxs-lookup"><span data-stu-id="4047b-103">How to Reset the FileSystem Cache</span></span>


<span data-ttu-id="4047b-104">重設 FileSystem 快取並不是通常應該需要的操作。</span><span class="sxs-lookup"><span data-stu-id="4047b-104">Resetting the FileSystem cache is not something that should usually be necessary.</span></span> <span data-ttu-id="4047b-105">不過，如果您需要完全重設 FileSystem 快取，可能是出於疑難排解目的，您可以使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="4047b-105">However if you need to completely reset the FileSystem cache, perhaps for troubleshooting purposes, you can use the following procedure.</span></span> <span data-ttu-id="4047b-106">需要系統管理許可權才能執行此動作。</span><span class="sxs-lookup"><span data-stu-id="4047b-106">Administrative rights are required to perform this action.</span></span>

**<span data-ttu-id="4047b-107">重設 FileSystem 快取</span><span class="sxs-lookup"><span data-stu-id="4047b-107">To reset the FileSystem cache</span></span>**

1.  <span data-ttu-id="4047b-108">將下列登錄值設定為0（零）：</span><span class="sxs-lookup"><span data-stu-id="4047b-108">Set the following registry value to 0 (zero):</span></span>

    <span data-ttu-id="4047b-109">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\State</span><span class="sxs-lookup"><span data-stu-id="4047b-109">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\State</span></span>

2.  <span data-ttu-id="4047b-110">重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="4047b-110">Restart the computer.</span></span>

## <span data-ttu-id="4047b-111">相關主題</span><span class="sxs-lookup"><span data-stu-id="4047b-111">Related topics</span></span>


[<span data-ttu-id="4047b-112">如何使用命令列設定 App-V 用戶端登錄設定</span><span class="sxs-lookup"><span data-stu-id="4047b-112">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





