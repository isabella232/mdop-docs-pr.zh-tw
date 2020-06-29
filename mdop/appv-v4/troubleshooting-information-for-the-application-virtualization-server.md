---
title: Application Virtualization 伺服器的疑難排解資訊
description: Application Virtualization 伺服器的疑難排解資訊
author: dansimp
ms.assetid: e9d43d9b-84f2-4d1b-bb90-a13740151e0c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7c98ad42a00e20900263d0598822a6381e2df1ef
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800769"
---
# <span data-ttu-id="621e8-103">Application Virtualization 伺服器的疑難排解資訊</span><span class="sxs-lookup"><span data-stu-id="621e8-103">Troubleshooting Information for the Application Virtualization Server</span></span>


<span data-ttu-id="621e8-104">本主題包含一些資訊，您可以用來針對應用程式虛擬化（App-v）伺服器上的各種問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="621e8-104">This topic includes information that you can use to troubleshoot various issues on the Application Virtualization (App-V) Servers.</span></span>

## <span data-ttu-id="621e8-105">安裝伺服器後，在安裝程式記錄中出現警告訊息25017</span><span class="sxs-lookup"><span data-stu-id="621e8-105">Warning Message 25017 in Setup Log After Installing the Server</span></span>


<span data-ttu-id="621e8-106">安裝之後，您可能會在伺服器安裝程式記錄中找到下列訊息。</span><span class="sxs-lookup"><span data-stu-id="621e8-106">You might find the following message in the server setup log after installation.</span></span>

*<span data-ttu-id="621e8-107">警告25017。</span><span class="sxs-lookup"><span data-stu-id="621e8-107">Warning 25017.</span></span> <span data-ttu-id="621e8-108">安裝程式無法為伺服器建立 Active Directory 標記物件。</span><span class="sxs-lookup"><span data-stu-id="621e8-108">The installation Program could not create the Active Directory marker object for the server.</span></span> <span data-ttu-id="621e8-109">用於安裝的帳戶沒有足夠的許可權寫入 Active Directory 或 Active Directory 無法使用。</span><span class="sxs-lookup"><span data-stu-id="621e8-109">The account used to install did not have the sufficient rights to write to Active Directory or Active Directory was unavailable.</span></span>*

<span data-ttu-id="621e8-110">App-V 管理或流式伺服器安裝程式會在 Active Directory 網域服務（新增）中的電腦物件底下建立服務連接點專案，而如果用來執行安裝程式的帳戶具有適當的許可權，就會在安裝伺服器的電腦上建立對應。</span><span class="sxs-lookup"><span data-stu-id="621e8-110">The App-V Management or Streaming Server installer creates a Service Connection Point entry under the Computer object in Active Directory Domain Services (ADDS) that corresponds to the computer on which the server is installed if the account used to run the installer has the appropriate rights.</span></span> <span data-ttu-id="621e8-111">無法建立此專案，不會導致安裝失敗，而且應該不會影響產品的運作。</span><span class="sxs-lookup"><span data-stu-id="621e8-111">Failure to create this entry will not cause the install to fail and this should not otherwise affect the functioning of the product.</span></span> <span data-ttu-id="621e8-112">發生任何失敗的可能原因是，用來執行安裝的使用者帳戶沒有足夠的許可權來寫入。</span><span class="sxs-lookup"><span data-stu-id="621e8-112">The likely cause of any failure is that the user account used to run the install did not have sufficient rights to write to ADDS.</span></span> <span data-ttu-id="621e8-113">雖然在新增中註冊 app-v server 是選擇性的，但這樣做有一個優點，就能讓集中式管理工具找到適用于庫存與管理目的的 App-v 伺服器。</span><span class="sxs-lookup"><span data-stu-id="621e8-113">Although registering the App-V server in ADDS is optional, one benefit of doing so enables centralized management tools to locate the App-V server for inventory and management purposes.</span></span>

## <span data-ttu-id="621e8-114">相關主題</span><span class="sxs-lookup"><span data-stu-id="621e8-114">Related topics</span></span>


[<span data-ttu-id="621e8-115">Application Virtualization 伺服器</span><span class="sxs-lookup"><span data-stu-id="621e8-115">Application Virtualization Server</span></span>](application-virtualization-server.md)

 

 





