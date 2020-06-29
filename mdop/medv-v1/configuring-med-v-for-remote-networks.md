---
title: 設定遠端網路的 MED V
description: 設定遠端網路的 MED V
author: dansimp
ms.assetid: 4d2f0081-622f-4a6f-8d73-f8c2108036e0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 328376046ee5213f3d5bb09be7adf8c81f8508b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811925"
---
# <span data-ttu-id="0644b-103">設定遠端網路的 MED V</span><span class="sxs-lookup"><span data-stu-id="0644b-103">Configuring MED-V for Remote Networks</span></span>


<span data-ttu-id="0644b-104">您可以將 MED-V 設定為在網路內部、遠端或從網路內部或遠端從網路內部進行工作。</span><span class="sxs-lookup"><span data-stu-id="0644b-104">You can configure MED-V to work from inside a network, remotely, or both from inside the network and remotely.</span></span>

## <a href="" id="bkmk-howtoconfiguremedvtoworkfrominsideanetworkorremotely"></a>


**<span data-ttu-id="0644b-105">將 MED-V 設定為從網路內工作</span><span class="sxs-lookup"><span data-stu-id="0644b-105">To configure MED-V to work from inside a network</span></span>**

-   <span data-ttu-id="0644b-106">在網路內設定 MED-V 伺服器與影像發佈。</span><span class="sxs-lookup"><span data-stu-id="0644b-106">Configure a MED-V server and image distribution inside the network.</span></span>

**<span data-ttu-id="0644b-107">將 MED-V 設定為遠端作業</span><span class="sxs-lookup"><span data-stu-id="0644b-107">To configure MED-V to work remotely</span></span>**

1.  <span data-ttu-id="0644b-108">設定 MED-V 伺服器以及可從網際網路存取的影像發佈伺服器。</span><span class="sxs-lookup"><span data-stu-id="0644b-108">Configure a MED-V server and an image distribution server that are accessible from the Internet.</span></span>

2.  <span data-ttu-id="0644b-109">如有需要，請設定周邊網路（也稱為 DMZ）反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="0644b-109">If needed, configure a perimeter network (also called a DMZ) reverse proxy.</span></span>

3.  <span data-ttu-id="0644b-110">在*ClientSettings.xml*檔案中設定驗證方法，可在 [ **Servers\\Configuration Server\\** ] 資料夾中找到該檔案。</span><span class="sxs-lookup"><span data-stu-id="0644b-110">Set the authentication method, in the *ClientSettings.xml* file, which can be found in the **Servers\\Configuration Server\\** folder.</span></span>

**<span data-ttu-id="0644b-111">將 MED-V 設定為從網路內部和遠端使用</span><span class="sxs-lookup"><span data-stu-id="0644b-111">To configure MED-V to work both from inside a network and remotely</span></span>**

1.  <span data-ttu-id="0644b-112">在網路內設定 MED-V 伺服器與影像發佈伺服器。</span><span class="sxs-lookup"><span data-stu-id="0644b-112">Configure a MED-V server and image distribution server inside the network.</span></span>

2.  <span data-ttu-id="0644b-113">確保伺服器可從網際網路存取。</span><span class="sxs-lookup"><span data-stu-id="0644b-113">Ensure that the servers are accessible from the Internet.</span></span>

3.  <span data-ttu-id="0644b-114">設定 DNS 解析，讓用戶端嘗試連線到伺服器時，會根據用戶端位置自動連接到正確的伺服器（在網路或網際網路內）。</span><span class="sxs-lookup"><span data-stu-id="0644b-114">Configure the DNS resolution so that when the client attempts to connect to a server, it automatically connects to the correct server (within the network or over the Internet) based on the client location.</span></span>

4.  <span data-ttu-id="0644b-115">如有需要，請設定周邊網路反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="0644b-115">If needed, configure a perimeter network reverse proxy.</span></span>

5.  <span data-ttu-id="0644b-116">在*ClientSettings.xml*檔案中設定驗證方法，可在 [ **Servers\\Configuration Server\\** ] 資料夾中找到該檔案。</span><span class="sxs-lookup"><span data-stu-id="0644b-116">Set the authentication method, in the *ClientSettings.xml* file, which can be found in the **Servers\\Configuration Server\\** folder.</span></span>

<span data-ttu-id="0644b-117">**記事** 在套用新設定時，必須重新開機該服務。</span><span class="sxs-lookup"><span data-stu-id="0644b-117">**Note** When applying new settings, the service must be restarted.</span></span>

 

-   <span data-ttu-id="0644b-118">您可以將 IIS 驗證配置變更為下列其中一項：基本、摘要、NTLM 或協商。</span><span class="sxs-lookup"><span data-stu-id="0644b-118">You can change the IIS authentication scheme to one of the following: BASIC, DIGEST, NTLM, or NEGOTIATE.</span></span> <span data-ttu-id="0644b-119">預設為 [協商]，並使用下列專案：</span><span class="sxs-lookup"><span data-stu-id="0644b-119">The default is NEGOTIATE and uses the following entry:</span></span>

    ```xml
    <ImageDistribution>
    <!-- The authentication used for image download. Basic and digest authentication should be used only under SSL.-->
       <!-- The line below can be one of the following: -->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_BASIC</BG_AUTH_SCHEME-->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_DIGEST</BG_AUTH_SCHEME-->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_NTLM</BG_AUTH_SCHEME-->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_NEGOTIATE</BG_AUTH_SCHEME-->
       <Authentication type="Kidaro.Foundation.Bits.BG_AUTH_SCHEME">
          <BG_AUTH_SCHEME>BG_AUTH_SCHEME_NEGOTIATE</BG_AUTH_SCHEME>
       </Authentication>
    </ImageDistribution>
    ```

## <span data-ttu-id="0644b-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="0644b-120">Related topics</span></span>


[<span data-ttu-id="0644b-121">MED-V 基礎結構規劃和設計</span><span class="sxs-lookup"><span data-stu-id="0644b-121">MED-V Infrastructure Planning and Design</span></span>](med-v-infrastructure-planning-and-design.md)

 

 





