---
title: 如何設定安裝後續串流伺服器安全性
description: 如何設定安裝後續串流伺服器安全性
author: dansimp
ms.assetid: 9bde3677-d1aa-4dcc-904e-bb49a268d748
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e1945b38da5dd50c0bd2fb0c741bd92012e78586
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801602"
---
# <span data-ttu-id="bc110-103">如何設定安裝後續串流伺服器安全性</span><span class="sxs-lookup"><span data-stu-id="bc110-103">How to Configure Streaming Server Security Post-Installation</span></span>


<span data-ttu-id="bc110-104">透過登錄設定 [App-v 流式處理伺服器] 以增強安全性。</span><span class="sxs-lookup"><span data-stu-id="bc110-104">Configure the App-V Streaming Server for enhanced security through the registry.</span></span> <span data-ttu-id="bc110-105">就像應用程式 V 管理伺服器一樣，必須在完成下列安裝後程式之後，使用伺服器驗證的正確 EKU 識別碼正確地提供憑證。</span><span class="sxs-lookup"><span data-stu-id="bc110-105">As with the App-V Management Server, a certificate must be correctly provisioned with the correct EKU identifier for Server Authentication before you complete the following post-installation procedure.</span></span>

**<span data-ttu-id="bc110-106">在安裝後設定流式伺服器安全性</span><span class="sxs-lookup"><span data-stu-id="bc110-106">To configure Streaming Server security post-installation</span></span>**

1.  <span data-ttu-id="bc110-107">建立 MMC，新增 [**憑證**] 管理單元，然後選取 [**本機電腦憑證存放區**]。</span><span class="sxs-lookup"><span data-stu-id="bc110-107">Create an MMC, add the **Certificates** snap-in, and select **Local Machine certificate store**.</span></span>

2.  <span data-ttu-id="bc110-108">開啟電腦的**個人**憑證，然後開啟為 app-v 預配的憑證。</span><span class="sxs-lookup"><span data-stu-id="bc110-108">Open the **Personal** certificates for the computer, and open the certificate provisioned for App-V.</span></span>

3.  <span data-ttu-id="bc110-109">在 [**詳細資料**] 索引標籤上，向下滾動至 [指紋]，然後在詳細資料窗格中複製雜湊。</span><span class="sxs-lookup"><span data-stu-id="bc110-109">On the **Details** tab, scroll down to the thumbprint and copy the hash in the details pane.</span></span>

4.  <span data-ttu-id="bc110-110">開啟 [登錄編輯程式]，然後流覽至 `HKLM\Software\Microsoft\SoftGrid\4.5\Distribution server` 。</span><span class="sxs-lookup"><span data-stu-id="bc110-110">Open the registry editor, and navigate to `HKLM\Software\Microsoft\SoftGrid\4.5\Distribution server`.</span></span>

5.  <span data-ttu-id="bc110-111">編輯 `X509CertHash` 值，在 [值] 欄位中貼上指紋雜湊，並移除所有空格。</span><span class="sxs-lookup"><span data-stu-id="bc110-111">Edit the `X509CertHash` value, paste the thumbprint hash in the value field, and remove all spaces.</span></span> <span data-ttu-id="bc110-112">按一下 **[確定]** 接受編輯。</span><span class="sxs-lookup"><span data-stu-id="bc110-112">Click **OK** to accept the edit.</span></span>

6.  <span data-ttu-id="bc110-113">在 [登錄編輯程式] 中，流覽至 `HKLM\Software\Microsoft\SoftGrid\4.5\Distribution server\RtspsPorts` 。</span><span class="sxs-lookup"><span data-stu-id="bc110-113">In the registry editor, navigate to `HKLM\Software\Microsoft\SoftGrid\4.5\Distribution server\RtspsPorts`.</span></span>

7.  <span data-ttu-id="bc110-114">建立名為 "322" 的新**DWORD**值，然後將十進位值輸入為322或十六進位值做為142。</span><span class="sxs-lookup"><span data-stu-id="bc110-114">Create a new **DWORD** value named "322," and then enter the decimal value as 322 or the hexadecimal value as 142.</span></span>

8.  <span data-ttu-id="bc110-115">重新開機流式處理服務。</span><span class="sxs-lookup"><span data-stu-id="bc110-115">Restart the streaming service.</span></span>

## <span data-ttu-id="bc110-116">相關主題</span><span class="sxs-lookup"><span data-stu-id="bc110-116">Related topics</span></span>


[<span data-ttu-id="bc110-117">如何設定安裝後續管理伺服器安全性</span><span class="sxs-lookup"><span data-stu-id="bc110-117">How to Configure Management Server Security Post-Installation</span></span>](how-to-configure-management-server-security-post-installation.md)

[<span data-ttu-id="bc110-118">疑難排解憑證權限問題</span><span class="sxs-lookup"><span data-stu-id="bc110-118">Troubleshooting Certificate Permission Issues</span></span>](troubleshooting-certificate-permission-issues.md)

 

 





