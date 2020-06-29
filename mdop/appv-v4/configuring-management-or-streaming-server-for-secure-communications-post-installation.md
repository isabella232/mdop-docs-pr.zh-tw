---
title: 設定管理或串流伺服器以供安裝後續安全通訊
description: 設定管理或串流伺服器以供安裝後續安全通訊
author: dansimp
ms.assetid: 1062a213-470b-4ae2-b12f-b3e28a6ab745
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2a2713f130809c431b7444f3e928a523838597a6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809020"
---
# <span data-ttu-id="47bb9-103">設定管理或串流伺服器以供安裝後續安全通訊</span><span class="sxs-lookup"><span data-stu-id="47bb9-103">Configuring Management or Streaming Server for Secure Communications Post-Installation</span></span>


<span data-ttu-id="47bb9-104">如果在安裝應用程式 V 管理伺服器或 App-v 流式處理伺服器之前未預配過適當的憑證，App-v 可以設定為在初始安裝之後加強安全性。</span><span class="sxs-lookup"><span data-stu-id="47bb9-104">If the proper certificate was not provisioned before the installation of the App-V Management Server or the App-V Streaming Server, App-V can be configured for enhanced security after the initial installation.</span></span> <span data-ttu-id="47bb9-105">您可以透過應用程式 V 管理主控台來設定 App-v 管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="47bb9-105">You can configure the App-V Management Server through the App-V Management Console.</span></span> <span data-ttu-id="47bb9-106">不過，App-v 流式處理伺服器是透過登錄來管理。</span><span class="sxs-lookup"><span data-stu-id="47bb9-106">However, the App-V Streaming Server is managed through the registry.</span></span> <span data-ttu-id="47bb9-107">不論是哪一種情況，憑證都必須包含正確的伺服器驗證*擴展金鑰用法*（EKU），而且網路服務必須擁有私密金鑰的讀取存取權。</span><span class="sxs-lookup"><span data-stu-id="47bb9-107">In either case, the certificate must include the proper *extended key usage* (EKU) for Server authentication and the Network Service must have read access to the private key.</span></span>

## <span data-ttu-id="47bb9-108">本節內容</span><span class="sxs-lookup"><span data-stu-id="47bb9-108">In This Section</span></span>


<a href="" id="how-to-configure-management-server-security-post-installation"></a>[<span data-ttu-id="47bb9-109">如何設定安裝後續管理伺服器安全性</span><span class="sxs-lookup"><span data-stu-id="47bb9-109">How to Configure Management Server Security Post-Installation</span></span>](how-to-configure-management-server-security-post-installation.md)  
<span data-ttu-id="47bb9-110">提供可使用 App-v 管理主控台執行安裝後的程式，以新增憑證並設定 App-v Management Server 以增強安全性。</span><span class="sxs-lookup"><span data-stu-id="47bb9-110">Provides a procedure that can be performed post-installation, using the App-V Management Console, to add the certificate and configure the App-V Management Server for enhanced security.</span></span>

<a href="" id="how-to-configure-streaming-server-security-post-installation"></a>[<span data-ttu-id="47bb9-111">如何設定安裝後續串流伺服器安全性</span><span class="sxs-lookup"><span data-stu-id="47bb9-111">How to Configure Streaming Server Security Post-Installation</span></span>](how-to-configure-streaming-server-security-post-installation.md)  
<span data-ttu-id="47bb9-112">提供可在安裝後執行的程式，以新增憑證並設定 App-v 資料流程伺服器以增強安全性。</span><span class="sxs-lookup"><span data-stu-id="47bb9-112">Provides a procedure that can be performed post-installation, to add the certificate and configure the App-V Streaming Server for enhanced security.</span></span>

<a href="" id="troubleshooting-certificate-permission-issues"></a>[<span data-ttu-id="47bb9-113">疑難排解憑證權限問題</span><span class="sxs-lookup"><span data-stu-id="47bb9-113">Troubleshooting Certificate Permission Issues</span></span>](troubleshooting-certificate-permission-issues.md)  
<span data-ttu-id="47bb9-114">提供針對網路服務的適當 ACL 沒有設定私密金鑰的疑難排解指南。</span><span class="sxs-lookup"><span data-stu-id="47bb9-114">Provides troubleshooting guidance for when the private key has not been configured with the proper ACL for the Network Service.</span></span>

 

 





