---
title: 如何安裝及設定 APP-V 管理主控台以用於更安全的環境
description: 如何安裝及設定 APP-V 管理主控台以用於更安全的環境
author: dansimp
ms.assetid: 9d89ef09-cdbf-48fc-99da-b24fc987ef8f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9887787d1e203410b5517439d897260305d7526e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801390"
---
# <span data-ttu-id="d230d-103">如何安裝及設定 APP-V 管理主控台以用於更安全的環境</span><span class="sxs-lookup"><span data-stu-id="d230d-103">How to Install and Configure the App-V Management Console for a More Secure Environment</span></span>


<span data-ttu-id="d230d-104">App V 管理主控台的預設安裝包含對安全通訊的支援。</span><span class="sxs-lookup"><span data-stu-id="d230d-104">The default installation of the App-V Management Console includes support for secure communications.</span></span> <span data-ttu-id="d230d-105">當您第一次啟動或連線到其他 App-v Web 管理服務時，系統會針對每個連接設定每個管理主控台。</span><span class="sxs-lookup"><span data-stu-id="d230d-105">Each Management Console is configured on a per-connection basis when the console is started for the first time or when connecting to an additional App-V Web Management Service.</span></span> <span data-ttu-id="d230d-106">預設設定會在 TCP 埠443上使用 SSL。</span><span class="sxs-lookup"><span data-stu-id="d230d-106">The default configuration uses SSL over TCP port 443.</span></span> <span data-ttu-id="d230d-107">如果伺服器上的埠號碼已修改，您可以變更埠號碼。</span><span class="sxs-lookup"><span data-stu-id="d230d-107">You can change the port number if the port number was modified on the server.</span></span> <span data-ttu-id="d230d-108">您可以使用下列程式，透過安全連線來連線到 App-v Web 管理服務。</span><span class="sxs-lookup"><span data-stu-id="d230d-108">You can use the following procedure to connect to an App-V Web Management Service by using a secure connection.</span></span>

**<span data-ttu-id="d230d-109">如何使用 SSL 連線連線到 App V 管理服務</span><span class="sxs-lookup"><span data-stu-id="d230d-109">How to Connect to an App-V Management Service by Using an SSL Connection</span></span>**

1.  <span data-ttu-id="d230d-110">啟動應用程式虛擬化管理主控台。</span><span class="sxs-lookup"><span data-stu-id="d230d-110">Start the Application Virtualization Management Console.</span></span>

2.  <span data-ttu-id="d230d-111">在主控台的 [動作] 窗格中，按一下 [**設定**連線]。</span><span class="sxs-lookup"><span data-stu-id="d230d-111">Click **Configure Connection** in the actions pane of the console.</span></span>

3.  <span data-ttu-id="d230d-112">輸入**Web 服務主機名稱**，並確認已選取 [**使用安全**連線]。</span><span class="sxs-lookup"><span data-stu-id="d230d-112">Type the **Web Service Host Name**, and ensure that **Use Secure Connection** is selected.</span></span>

    <span data-ttu-id="d230d-113">**重要** 在 Web 服務主機名稱中提供的名稱必須與憑證上的通用名稱相符，否則連線將會失敗。</span><span class="sxs-lookup"><span data-stu-id="d230d-113">**Important** The name provided in the Web Service Host Name must match the common name on the certificate, or the connection will fail.</span></span>

     

4.  <span data-ttu-id="d230d-114">選取適當的登入認證，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d230d-114">Select the appropriate login credentials, and click **OK**.</span></span>

## <span data-ttu-id="d230d-115">相關主題</span><span class="sxs-lookup"><span data-stu-id="d230d-115">Related topics</span></span>


[<span data-ttu-id="d230d-116">設定憑證以支援 APP-V Web 管理服務</span><span class="sxs-lookup"><span data-stu-id="d230d-116">Configuring Certificates to Support the App-V Web Management Service</span></span>](configuring-certificates-to-support-the-app-v-web-management-service.md)

 

 





