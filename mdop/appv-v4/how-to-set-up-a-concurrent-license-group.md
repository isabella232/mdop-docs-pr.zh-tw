---
title: 如何設定並行授權群組
description: 如何設定並行授權群組
author: dansimp
ms.assetid: 031abcf6-d8ed-49be-bddb-91b2c695d411
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6e3035362cd645b6488b07408d6a9444f632fc88
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801093"
---
# <span data-ttu-id="49a94-103">如何設定並行授權群組</span><span class="sxs-lookup"><span data-stu-id="49a94-103">How to Set Up a Concurrent License Group</span></span>


<span data-ttu-id="49a94-104">您可以在應用程式虛擬化伺服器管理主控台中使用下列程式來設定併發授權群組。</span><span class="sxs-lookup"><span data-stu-id="49a94-104">You can use the following procedure in the Application Virtualization Server Management Console to set up a concurrent license group.</span></span> <span data-ttu-id="49a94-105">當您設定併發授權群組時，您可以將應用程式的存取許可權制為特定數量的併發使用者。</span><span class="sxs-lookup"><span data-stu-id="49a94-105">When you set up a concurrent license group, you can limit access to applications to a specific number of concurrent users.</span></span>

**<span data-ttu-id="49a94-106">若要設定併發授權群組</span><span class="sxs-lookup"><span data-stu-id="49a94-106">To set up a concurrent license group</span></span>**

1.  <span data-ttu-id="49a94-107">在應用程式虛擬化伺服器管理主控台的左窗格中，以滑鼠右鍵按一下 [**應用程式授權**] 節點。</span><span class="sxs-lookup"><span data-stu-id="49a94-107">In the left pane of the Application Virtualization Server Management Console, right-click the **Application Licenses** node.</span></span>

2.  <span data-ttu-id="49a94-108">選取 [**新的並行授權**]。</span><span class="sxs-lookup"><span data-stu-id="49a94-108">Select **New Concurrent License**.</span></span>

3.  <span data-ttu-id="49a94-109">在 [**應用程式授權] 群組**的 [名稱] 欄位中輸入名稱。</span><span class="sxs-lookup"><span data-stu-id="49a94-109">Enter a name in the **Application License Group Name** field.</span></span>

4.  <span data-ttu-id="49a94-110">在 [**授權到期警告**] 欄位中輸入一個值（以分鐘為單位）。</span><span class="sxs-lookup"><span data-stu-id="49a94-110">Enter a value (in minutes) in the **License Expiration Warning** field.</span></span>

5.  <span data-ttu-id="49a94-111">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="49a94-111">Click **Next**.</span></span>

6.  <span data-ttu-id="49a94-112">在 [**授權描述**] 欄位中輸入描述文字。</span><span class="sxs-lookup"><span data-stu-id="49a94-112">Enter descriptive text in the **License Description** field.</span></span>

7.  <span data-ttu-id="49a94-113">在 [**併發授權數量**] 欄位中輸入值。</span><span class="sxs-lookup"><span data-stu-id="49a94-113">Enter a value in the **Concurrent License Quantity** field.</span></span>

8.  <span data-ttu-id="49a94-114">選取 [**已啟用**] 核取方塊以啟用授權。</span><span class="sxs-lookup"><span data-stu-id="49a94-114">Select the **Enabled** check box to enable the license.</span></span>

9.  <span data-ttu-id="49a94-115">選取 [**到期日**] 核取方塊（如果您想要設定到期日），然後輸入到期日，或使用行事曆實用程式選取日期。</span><span class="sxs-lookup"><span data-stu-id="49a94-115">Select the **Expiration Date** check box (if you want to set an expiration date), and enter the expiration date or use the calendar utility to select a date.</span></span>

10. <span data-ttu-id="49a94-116">如果您需要將金鑰與授權建立關聯，請在 [**授權金鑰**] 欄位中輸入授權金鑰資訊。</span><span class="sxs-lookup"><span data-stu-id="49a94-116">If you need to associate a key with the license, enter the license key information in the **License Key** field.</span></span>

11. <span data-ttu-id="49a94-117">按一下 **\[完成\]**。</span><span class="sxs-lookup"><span data-stu-id="49a94-117">Click **Finish**.</span></span>

## <span data-ttu-id="49a94-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="49a94-118">Related topics</span></span>


[<span data-ttu-id="49a94-119">如何建立應用程式與授權群組的關聯</span><span class="sxs-lookup"><span data-stu-id="49a94-119">How to Associate an Application with a License Group</span></span>](how-to-associate-an-application-with-a-license-group.md)

[<span data-ttu-id="49a94-120">如何建立應用程式授權群組</span><span class="sxs-lookup"><span data-stu-id="49a94-120">How to Create an Application License Group</span></span>](how-to-create-an-application-license-group.md)

[<span data-ttu-id="49a94-121">如何從授權群組移除應用程式</span><span class="sxs-lookup"><span data-stu-id="49a94-121">How to Remove an Application from a License Group</span></span>](how-to-remove-an-application-from-a-license-group.md)

[<span data-ttu-id="49a94-122">如何設定指定授權群組</span><span class="sxs-lookup"><span data-stu-id="49a94-122">How to Set Up a Named License Group</span></span>](how-to-set-up-a-named-license-group.md)

[<span data-ttu-id="49a94-123">如何設定無限授權群組</span><span class="sxs-lookup"><span data-stu-id="49a94-123">How to Set Up an Unlimited License Group</span></span>](how-to-set-up-an-unlimited-license-group.md)

 

 





