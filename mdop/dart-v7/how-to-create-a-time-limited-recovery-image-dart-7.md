---
title: 如何建立限時復原映像
description: 如何建立限時復原映像
author: dansimp
ms.assetid: d2e29cac-c24c-4239-997f-0320b8a830ae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a11891753f80d41f0089311771b906865950337c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800142"
---
# <span data-ttu-id="ad49a-103">如何建立限時復原映像</span><span class="sxs-lookup"><span data-stu-id="ad49a-103">How to Create a Time Limited Recovery Image</span></span>


<span data-ttu-id="ad49a-104">您可以建立一個只能在產生特定天數後使用的 DaRT 恢復影像。</span><span class="sxs-lookup"><span data-stu-id="ad49a-104">You can create a DaRT recovery image that can only be used for a certain number of days after it is generated.</span></span> <span data-ttu-id="ad49a-105">若要這樣做，您必須在命令提示字元執行**DaRT 復原映射嚮導**，並指定天數。</span><span class="sxs-lookup"><span data-stu-id="ad49a-105">To do this, you must run the **DaRT Recovery Image Wizard** at a command prompt and specify the number of days.</span></span>

**<span data-ttu-id="ad49a-106">建立具有時間限制的復原影像</span><span class="sxs-lookup"><span data-stu-id="ad49a-106">To create a recovery image that has a time limit</span></span>**

1.  <span data-ttu-id="ad49a-107">使用系統管理員認證開啟命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="ad49a-107">Open a Command Prompt with administrator credentials.</span></span>

2.  <span data-ttu-id="ad49a-108">將目錄變更為 ERDC.exe 程式的位置。</span><span class="sxs-lookup"><span data-stu-id="ad49a-108">Change the directory to the location of the ERDC.exe program.</span></span>

3.  <span data-ttu-id="ad49a-109">使用下列語法，執行 DaRT 復原**影像嚮導**。</span><span class="sxs-lookup"><span data-stu-id="ad49a-109">Using the following syntax, run the **DaRT Recovery Image Wizard**.</span></span> <span data-ttu-id="ad49a-110">*Numberofdays 後*是一個正整數，代表 DaRT 復原影像可使用的天數。</span><span class="sxs-lookup"><span data-stu-id="ad49a-110">*NumberOfDays* is a positive integer that represents the number of days that the DaRT recovery image will be usable.</span></span>

    ``` syntax
    ERDC /e NumberOfDays
    ```

## <span data-ttu-id="ad49a-111">相關主題</span><span class="sxs-lookup"><span data-stu-id="ad49a-111">Related topics</span></span>


[<span data-ttu-id="ad49a-112">建立 DaRT 7.0 復原映像</span><span class="sxs-lookup"><span data-stu-id="ad49a-112">Creating the DaRT 7.0 Recovery Image</span></span>](creating-the-dart-70-recovery-image-dart-7.md)

 

 





