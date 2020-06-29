---
title: 疑難排解憑證權限問題
description: 疑難排解憑證權限問題
author: dansimp
ms.assetid: 06b8cbbc-93fd-44aa-af39-2d780792d3c3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 728c35b9f51c8f2e18db8acd63708c70bb5d3100
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800773"
---
# <span data-ttu-id="ba632-103">疑難排解憑證權限問題</span><span class="sxs-lookup"><span data-stu-id="ba632-103">Troubleshooting Certificate Permission Issues</span></span>


<span data-ttu-id="ba632-104">安裝 App-v 4.5 之後，如果尚未針對網路服務的適當 ACL 設定私密金鑰，則會在 NT 事件記錄檔中記錄一個事件，並在檔案中放入一個專案 `Sft-server.log` 。</span><span class="sxs-lookup"><span data-stu-id="ba632-104">After the installation of App-V4.5, if the private key has not been configured with the proper ACL for the Network Service, an event is logged in the NT Event Log and an entry is placed in the `Sft-server.log` file.</span></span>

## <span data-ttu-id="ba632-105">錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="ba632-105">Error Messages</span></span>


### <span data-ttu-id="ba632-106">Windows Server2003</span><span class="sxs-lookup"><span data-stu-id="ba632-106">Windows Server2003</span></span>

<span data-ttu-id="ba632-107">事件識別碼 36870-嘗試存取 SSL 伺服器認證私密金鑰時發生致命錯誤。</span><span class="sxs-lookup"><span data-stu-id="ba632-107">Event ID 36870—A fatal error occurred when attempting to access the SSL server credential private key.</span></span> <span data-ttu-id="ba632-108">從加密模組傳回的錯誤碼是0x80090016。</span><span class="sxs-lookup"><span data-stu-id="ba632-108">The error code returned from the cryptographic module is 0x80090016.</span></span>

### <span data-ttu-id="ba632-109">Windows Server2008</span><span class="sxs-lookup"><span data-stu-id="ba632-109">Windows Server2008</span></span>

<span data-ttu-id="ba632-110">事件識別碼 36870-嘗試存取 SSL 伺服器認證私密金鑰時發生致命錯誤。</span><span class="sxs-lookup"><span data-stu-id="ba632-110">Event ID 36870—A fatal error occurred when attempting to access the SSL server credential private key.</span></span> <span data-ttu-id="ba632-111">從加密模組傳回的錯誤碼是0x8009030d。</span><span class="sxs-lookup"><span data-stu-id="ba632-111">The error code returned from the cryptographic module is 0x8009030d.</span></span>

## <span data-ttu-id="ba632-112">Sft-server 記錄</span><span class="sxs-lookup"><span data-stu-id="ba632-112">Sft-server.log</span></span>


<span data-ttu-id="ba632-113">下列錯誤會放在 `sft-server.log` 位於目錄中的檔案中 `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\logs` ：</span><span class="sxs-lookup"><span data-stu-id="ba632-113">The following error is placed in the `sft-server.log` file located in the `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\logs` directory:</span></span>

<span data-ttu-id="ba632-114">無法載入憑證。</span><span class="sxs-lookup"><span data-stu-id="ba632-114">Certificate could not be loaded.</span></span> <span data-ttu-id="ba632-115">錯誤碼 \ [-2146893043 \]。</span><span class="sxs-lookup"><span data-stu-id="ba632-115">Error code \[-2146893043\].</span></span> <span data-ttu-id="ba632-116">確認 [網路服務] 帳戶具有正確的憑證存取權和其對應的私密金鑰檔案。</span><span class="sxs-lookup"><span data-stu-id="ba632-116">Make sure that the Network Service account has proper access to the certificate and its corresponding private key file.</span></span>

 

 





