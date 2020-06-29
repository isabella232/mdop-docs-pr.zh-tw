---
title: 如何變更部署內容
description: 如何變更部署內容
author: dansimp
ms.assetid: 0a214a7a-cc83-4d04-89f9-5727153be918
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dfb42962d41159479db61da9c3beb3771ef35502
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801666"
---
# <span data-ttu-id="2030c-103">如何變更部署內容</span><span class="sxs-lookup"><span data-stu-id="2030c-103">How to Change Deployment Properties</span></span>


<span data-ttu-id="2030c-104">您可以使用下列程式來變更您要排序之應用程式的 [**部署**] 索引標籤資訊，包括應用程式虛擬化伺服器 URL、虛擬化應用程式所需的作業系統，以及要安裝之虛擬應用程式的輸出選項。</span><span class="sxs-lookup"><span data-stu-id="2030c-104">You can use the following procedures to change the **Deployment** tab information for an application you are sequencing, including the Application Virtualization server URL, the operating systems required by the virtualized applications, and the output options for the virtual application to be installed.</span></span>

**<span data-ttu-id="2030c-105">若要變更伺服器 URL</span><span class="sxs-lookup"><span data-stu-id="2030c-105">To change the server URL</span></span>**

1.  <span data-ttu-id="2030c-106">從下拉式清單方塊中選取 [串流] 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="2030c-106">Select the streaming protocol from the drop-down list box.</span></span>

2.  <span data-ttu-id="2030c-107">輸入虛擬應用程式伺服器的主機名稱或伺服器群組的負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="2030c-107">Enter the host name of the virtual application server or the server group's load balancer.</span></span> <span data-ttu-id="2030c-108">您可以使用 [實際主機名稱] 或 [IP 位址]。</span><span class="sxs-lookup"><span data-stu-id="2030c-108">You can use the actual host name or IP address.</span></span>

3.  <span data-ttu-id="2030c-109">指定虛擬應用程式伺服器或負載平衡器針對流程式應用程式偵聽應用程式虛擬化桌面用戶端要求的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="2030c-109">Specify the port number on which the virtual application server or load balancer will listen for an Application Virtualization Desktop Client request for the streamed application.</span></span>

4.  <span data-ttu-id="2030c-110">指定儲存軟體套件之虛擬應用程式伺服器上的相對路徑。</span><span class="sxs-lookup"><span data-stu-id="2030c-110">Specify the relative path on the virtual application server where the software package is stored.</span></span>

**<span data-ttu-id="2030c-111">變更應用程式作業系統需求</span><span class="sxs-lookup"><span data-stu-id="2030c-111">To change the application operating systems requirements</span></span>**

1.  <span data-ttu-id="2030c-112">若要新增所需的作業系統，請在 [**可用**] 清單中選取它，然後按一下指向**選取**的作業系統清單控制項的箭號按鈕。</span><span class="sxs-lookup"><span data-stu-id="2030c-112">To add the required operating system(s), select it in the **Available** list and click the arrow button pointing to the **Selected** operating systems list control.</span></span>

2.  <span data-ttu-id="2030c-113">若要移除作業系統，請在**選取**的清單控制項中選取它，然後按一下指向 [**可用**的作業系統] 清單控制項的箭號按鈕。</span><span class="sxs-lookup"><span data-stu-id="2030c-113">To remove an operating system, select it in the **Selected** list control, and click the arrow button pointing to the **Available** operating systems list control.</span></span>

**<span data-ttu-id="2030c-114">變更應用程式輸出選項</span><span class="sxs-lookup"><span data-stu-id="2030c-114">To change the application output options</span></span>**

1.  <span data-ttu-id="2030c-115">從 [**壓縮演算法]** 下拉式清單中，選取要在流式處理應用程式時使用的壓縮方式。</span><span class="sxs-lookup"><span data-stu-id="2030c-115">From the **Compression Algorithm** drop-down list, select the compression method to use when streaming the application.</span></span>

2.  <span data-ttu-id="2030c-116">選取 [**強制安全性描述項**] 核取方塊，以確保已部署封裝應用程式的安全性描述項。</span><span class="sxs-lookup"><span data-stu-id="2030c-116">Select the **Enforce Security Descriptors** check box to ensure security descriptors of the packaged applications are enforced when deployed.</span></span>

3.  <span data-ttu-id="2030c-117">選取 [**產生差異**檔案]，以產生來自先前已排序版本之應用程式的差異檔案。</span><span class="sxs-lookup"><span data-stu-id="2030c-117">Select **Generate Difference File** to generate a difference file for the application from the previous sequenced version.</span></span>

4.  <span data-ttu-id="2030c-118">選取 **[產生 Microsoft Windows Installer （MSI）套件**] 來建立安裝程式套件。</span><span class="sxs-lookup"><span data-stu-id="2030c-118">Select **Generate Microsoft Windows Installer (MSI) Package** to create an installer package.</span></span>

## <span data-ttu-id="2030c-119">相關主題</span><span class="sxs-lookup"><span data-stu-id="2030c-119">Related topics</span></span>


[<span data-ttu-id="2030c-120">關於部署索引標籤</span><span class="sxs-lookup"><span data-stu-id="2030c-120">About the Deployment Tab</span></span>](about-the-deployment-tab.md)

[<span data-ttu-id="2030c-121">排序器主控台</span><span class="sxs-lookup"><span data-stu-id="2030c-121">Sequencer Console</span></span>](sequencer-console.md)

 

 





