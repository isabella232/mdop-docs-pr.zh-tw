---
title: 如何修改私密金鑰權限以支援管理伺服器或串流伺服器
description: 如何修改私密金鑰權限以支援管理伺服器或串流伺服器
author: dansimp
ms.assetid: 1ebe86fa-0fbc-4512-aebc-0a5da991cd43
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2e35c2df518f22ba81a070d2c40ad3862f376a6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801253"
---
# <span data-ttu-id="9fddb-103">如何修改私密金鑰權限以支援管理伺服器或串流伺服器</span><span class="sxs-lookup"><span data-stu-id="9fddb-103">How to Modify Private Key Permissions to Support Management Server or Streaming Server</span></span>


<span data-ttu-id="9fddb-104">若要支援更安全的 App-v 安裝，您可以使用下列程式來修改 Windows Server2003 或 Windows Server2008 中的私人金鑰。</span><span class="sxs-lookup"><span data-stu-id="9fddb-104">To support a more secure App-V installation, you can use the following procedures to modify private keys in either Windows Server2003 or Windows Server2008.</span></span> <span data-ttu-id="9fddb-105">若要修改私用金鑰的許可權，您可以使用 Windows Server2003 資源套件工具 `WinHttpCertCfg.exe` 。</span><span class="sxs-lookup"><span data-stu-id="9fddb-105">To modify the permissions of the private key, you can use the Windows Server2003 Resource Kit tool `WinHttpCertCfg.exe`.</span></span>

<span data-ttu-id="9fddb-106">針對 Windows Server2003，程式需要符合本檔所列先決條件的憑證，才會安裝在您要安裝 App V 管理或流式處理伺服器的電腦上。</span><span class="sxs-lookup"><span data-stu-id="9fddb-106">For Windows Server2003, the procedure requires that a certificate that meets the prerequisites listed in this document is installed on the computer or computers on which you will install the App-V Management or Streaming Server.</span></span> <span data-ttu-id="9fddb-107">您可以在使用此工具的其他相關資訊 `WinHttpCertCfg.exe` <https://go.microsoft.com/fwlink/?LinkId=151981> 。</span><span class="sxs-lookup"><span data-stu-id="9fddb-107">Additional information about using the `WinHttpCertCfg.exe` tool is available at <https://go.microsoft.com/fwlink/?LinkId=151981>.</span></span>

<span data-ttu-id="9fddb-108">在 Windows Server2008 中，變更私人金鑰上的 Acl 的程式會更簡單。</span><span class="sxs-lookup"><span data-stu-id="9fddb-108">In Windows Server2008, the process of changing the ACLs on the private key is much simpler.</span></span> <span data-ttu-id="9fddb-109">證書的使用者介面可用於管理私密金鑰許可權。</span><span class="sxs-lookup"><span data-stu-id="9fddb-109">The certificate’s user interface can be used to manage private key permissions.</span></span>

<span data-ttu-id="9fddb-110">**記事** 預設的安全性內容是 [網路服務];不過，您可以改為使用網域帳戶。</span><span class="sxs-lookup"><span data-stu-id="9fddb-110">**Note** The default security context is Network Service; however, a domain account can be used instead.</span></span>

 

**<span data-ttu-id="9fddb-111">在 Windows Server2003 中管理私人金鑰</span><span class="sxs-lookup"><span data-stu-id="9fddb-111">To manage private keys in Windows Server2003</span></span>**

1.  <span data-ttu-id="9fddb-112">在將成為 App V 管理或流式處理伺服器的電腦上，于命令提示字元中輸入下列命令，以列出指派給特定憑證的目前許可權：</span><span class="sxs-lookup"><span data-stu-id="9fddb-112">On the computer that will become the App-V Management or Streaming Server, type the following command in a command prompt to list the current permissions assigned to a specific certificate:</span></span>

    `winhttpcertcfg -l -c LOCAL_MACHINE\My -s Name_of_cert`

2.  <span data-ttu-id="9fddb-113">如有必要，請修改憑證的許可權，以便提供對將用於管理或流式處理服務之安全內容的讀取存取：</span><span class="sxs-lookup"><span data-stu-id="9fddb-113">If necessary, modify the permissions of the certificate to provide read access to the security context that will be used for Management or Streaming Service:</span></span>

    `winhttpcertcfg -g -c LOCAL_MACHINE\My -s Name_of_cert -a NetworkService`

3.  <span data-ttu-id="9fddb-114">列出憑證上的許可權，確認已正確新增安全性內容：</span><span class="sxs-lookup"><span data-stu-id="9fddb-114">Verify that the security context was properly added by listing the permissions on the certificate:</span></span>

    `winhttpcertcfg –l –c LOCAL_MACHINE\My –s Name_of_cert`

**<span data-ttu-id="9fddb-115">在 Windows Server2008 中管理私人金鑰</span><span class="sxs-lookup"><span data-stu-id="9fddb-115">To manage private keys in Windows Server2008</span></span>**

1.  <span data-ttu-id="9fddb-116">使用以*本機電腦*憑證存放的*憑證*管理單元來建立 MICROSOFT 管理主控台（MMC）。</span><span class="sxs-lookup"><span data-stu-id="9fddb-116">Create a Microsoft Management Console (MMC) with the *Certificates* snap-in that targets the *Local Machine* certificate store.</span></span>

2.  <span data-ttu-id="9fddb-117">展開 MMC，然後選取 [**管理私人金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="9fddb-117">Expand the MMC and select **Manage Private Keys**.</span></span>

3.  <span data-ttu-id="9fddb-118">在 [**安全性**] 索引標籤上，將 [**網路服務**] 帳戶新增為 [**讀取**存取]。</span><span class="sxs-lookup"><span data-stu-id="9fddb-118">On the **Security** tab, add the **Network Service** account with **Read** access.</span></span>

## <span data-ttu-id="9fddb-119">相關主題</span><span class="sxs-lookup"><span data-stu-id="9fddb-119">Related topics</span></span>


[<span data-ttu-id="9fddb-120">設定憑證以支援 APP-V Management Server 或 Streaming Server</span><span class="sxs-lookup"><span data-stu-id="9fddb-120">Configuring Certificates to Support App-V Management Server or Streaming Server</span></span>](configuring-certificates-to-support-app-v-management-server-or-streaming-server.md)

[<span data-ttu-id="9fddb-121">支援憑證以支援安全串流</span><span class="sxs-lookup"><span data-stu-id="9fddb-121">Configuring Certificates to Support Secure Streaming</span></span>](configuring-certificates-to-support-secure-streaming.md)

 

 





