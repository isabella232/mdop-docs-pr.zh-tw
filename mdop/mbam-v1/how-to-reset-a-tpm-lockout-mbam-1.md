---
title: 如何重設 TPM 鎖定
description: 如何重設 TPM 鎖定
author: dansimp
ms.assetid: 91ec6666-1ae2-4e76-9459-ad65c405f639
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dde77a12e97d050777dac15d4106124ec111b3cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800214"
---
# <span data-ttu-id="9811c-103">如何重設 TPM 鎖定</span><span class="sxs-lookup"><span data-stu-id="9811c-103">How to Reset a TPM Lockout</span></span>


<span data-ttu-id="9811c-104">Microsoft BitLocker 管理與監視（MBAM）的加密磁片磁碟機復原功能包含了資料的捕獲與儲存，以及管理受信任的平臺模組（TPM）所需的工具可用性。</span><span class="sxs-lookup"><span data-stu-id="9811c-104">The Encrypted Drive Recovery feature of Microsoft BitLocker Administration and Monitoring (MBAM) encompasses both the capture and storage of data and the availability for tools that are required to manage the Trusted Platform Module (TPM).</span></span> <span data-ttu-id="9811c-105">本主題涵蓋如何在 _admmon \ _tlanextref 管理網站中存取集中式金鑰復原資料系統。</span><span class="sxs-lookup"><span data-stu-id="9811c-105">This topic covers how to access the centralized Key Recovery data system in the bit\_admmon\_tlanextref administration website.</span></span> <span data-ttu-id="9811c-106">金鑰復原資料系統可在提供電腦身分識別及相關聯的使用者識別碼時提供 TPM 擁有者密碼檔案。</span><span class="sxs-lookup"><span data-stu-id="9811c-106">The Key Recovery data system can provide a TPM owner password file when the computer identity and the associated user identifier are supplied.</span></span>

<span data-ttu-id="9811c-107">如果使用者輸入錯誤的 PIN 太多次，可能會發生 TPM 封鎖。</span><span class="sxs-lookup"><span data-stu-id="9811c-107">A TPM lockout can occur if a user enters an incorrect PIN too many times.</span></span> <span data-ttu-id="9811c-108">在 TPM 封鎖之前，使用者可以輸入不正確 PIN 的次數，以電腦製造商的規格為基礎。</span><span class="sxs-lookup"><span data-stu-id="9811c-108">The number of times that a user can enter an incorrect PIN before the TPM lockout is based on the computer manufacturer's specification.</span></span>

**<span data-ttu-id="9811c-109">重設 TPM 封鎖</span><span class="sxs-lookup"><span data-stu-id="9811c-109">To reset a TPM lockout</span></span>**

1.  <span data-ttu-id="9811c-110">開啟 [MBAM 管理] 網站。</span><span class="sxs-lookup"><span data-stu-id="9811c-110">Open the MBAM administration website.</span></span>

2.  <span data-ttu-id="9811c-111">在 [功能窗格] 中，選取 [**管理 TPM**]。</span><span class="sxs-lookup"><span data-stu-id="9811c-111">In the navigation pane, select **Manage TPM**.</span></span> <span data-ttu-id="9811c-112">這會開啟 [**管理 TPM** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="9811c-112">This opens the **Manage TPM** page.</span></span>

3.  <span data-ttu-id="9811c-113">輸入電腦和電腦名稱稱的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="9811c-113">Enter the fully qualified domain name (FQDN) for the computer and the computer name.</span></span> <span data-ttu-id="9811c-114">輸入使用者的 Windows 登入網域和使用者的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="9811c-114">Enter the user’s Windows Logon domain and the user’s user name.</span></span> <span data-ttu-id="9811c-115">在 [**要求 TPM 擁有者密碼**檔案的原因] 下拉式功能表中，選取其中一個預先定義的選項。</span><span class="sxs-lookup"><span data-stu-id="9811c-115">Select one of the predefined options in the **Reason for requesting TPM owner password file** drop-down menu.</span></span> <span data-ttu-id="9811c-116">按一下 **\[提交\]**。</span><span class="sxs-lookup"><span data-stu-id="9811c-116">Click **Submit**.</span></span>

4.  <span data-ttu-id="9811c-117">MBAM 將會返回下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="9811c-117">MBAM will return one of the following:</span></span>

    -   <span data-ttu-id="9811c-118">找不到符合的 TPM 擁有者密碼檔案時的錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="9811c-118">An error message if no matching TPM owner password file is found</span></span>

    -   <span data-ttu-id="9811c-119">已提交電腦的 TPM 擁有者密碼檔</span><span class="sxs-lookup"><span data-stu-id="9811c-119">The TPM owner password file for the submitted computer</span></span>

    <span data-ttu-id="9811c-120">**記事** 如果您是「高級服務台」使用者，則不需要 [使用者網域] 和 [使用者識別碼] 欄位。</span><span class="sxs-lookup"><span data-stu-id="9811c-120">**Note** If you are an Advanced Helpdesk User, the user domain and user ID fields are not required.</span></span>

     

5.  <span data-ttu-id="9811c-121">檢索時，會顯示擁有者密碼。</span><span class="sxs-lookup"><span data-stu-id="9811c-121">Upon retrieval, the owner password is displayed.</span></span> <span data-ttu-id="9811c-122">若要將此密碼儲存至 tpm 檔案，請按一下 [**儲存**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="9811c-122">To save this password to a .tpm file, click the **Save** button.</span></span>

6.  <span data-ttu-id="9811c-123">使用者會執行 TPM 管理主控台，然後選取 [**重設 tpm 封鎖**] 選項，並提供 tpm 擁有者密碼檔來重設 tpm 封鎖。</span><span class="sxs-lookup"><span data-stu-id="9811c-123">The user will run the TPM management console and select the **Reset TPM lockout** option and provide the TPM owner password file to reset the TPM lockout.</span></span>

## <span data-ttu-id="9811c-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="9811c-124">Related topics</span></span>


[<span data-ttu-id="9811c-125">使用 MBAM 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="9811c-125">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam.md)

 

 





