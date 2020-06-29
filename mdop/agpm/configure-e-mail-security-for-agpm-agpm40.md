---
title: 設定 AGPM 的電子郵件安全性
description: 設定 AGPM 的電子郵件安全性
author: dansimp
ms.assetid: b9c48894-0a10-4d03-8027-50ed3b02485a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a384c2a21f912ca7ec55a5e4c74ca7062bfe864c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802038"
---
# <span data-ttu-id="2ab21-103">設定 AGPM 的電子郵件安全性</span><span class="sxs-lookup"><span data-stu-id="2ab21-103">Configure E-Mail Security for AGPM</span></span>


<span data-ttu-id="2ab21-104">根據預設，由於高級群組原則管理（AGPM）中的動作而傳送的電子郵件通知不會加密，而且會透過 SMTP 埠25傳送。</span><span class="sxs-lookup"><span data-stu-id="2ab21-104">By default, e-mail notifications sent because of actions in Advanced Group Policy Management (AGPM) are not encrypted and are sent through SMTP port 25.</span></span> <span data-ttu-id="2ab21-105">不過，您可以使用登錄設定來設定 AGPM 的電子郵件安全性，以指定是否要使用安全通訊端層（SSL）加密，以及要使用哪個 SMTP 埠。</span><span class="sxs-lookup"><span data-stu-id="2ab21-105">However, you can configure e-mail security for AGPM by using registry settings to specify whether to use Secure Sockets Layer (SSL) encryption and which SMTP port to use.</span></span>

<span data-ttu-id="2ab21-106">透過加密 AGPM 電子郵件通知，您可以更好地保護那些可能會揭示貴組織安全性機密資訊的人。</span><span class="sxs-lookup"><span data-stu-id="2ab21-106">By encrypting AGPM e-mail notifications, you can better protect those that could reveal sensitive information about your organization’s security.</span></span> <span data-ttu-id="2ab21-107">如果您是透過遠端郵件伺服器來中繼電子郵件通知，則建議您進行加密，而某些規範規範可能需要它。</span><span class="sxs-lookup"><span data-stu-id="2ab21-107">Encrypting e-mail notifications is recommended when they are being relayed through remote mail servers, and may be required by some compliance regulations.</span></span>

<span data-ttu-id="2ab21-108">**小心** 不正確地編輯註冊表可能會嚴重損壞您的系統。</span><span class="sxs-lookup"><span data-stu-id="2ab21-108">**Caution** Incorrectly editing the registry may severely damage your system.</span></span> <span data-ttu-id="2ab21-109">在變更註冊表之前，您應該先備份電腦上任何有價值的資料。</span><span class="sxs-lookup"><span data-stu-id="2ab21-109">Before making changes to the registry, you should back up any valued data on the computer.</span></span>

 

<span data-ttu-id="2ab21-110">擁有 AGPM 系統管理員（完全控制）角色的使用者帳戶、在這些程式中建立群組原則物件（GPO）的核准者使用者帳戶，或是在 AGPM 中具有必要許可權的使用者帳戶，以完成這些程式。</span><span class="sxs-lookup"><span data-stu-id="2ab21-110">A user account that has the AGPM Administrator (Full Control) role, the user account of the Approver who created the Group Policy Object (GPO) used in these procedures, or a user account that has the necessary permissions in AGPM is required to complete these procedures.</span></span> <span data-ttu-id="2ab21-111">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2ab21-111">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="2ab21-112">使用群組原則喜好設定來設定 AGPM 的電子郵件安全性</span><span class="sxs-lookup"><span data-stu-id="2ab21-112">To configure e-mail security for AGPM by using Group Policy preferences</span></span>**

1.  <span data-ttu-id="2ab21-113">在 [**群組原則管理] 主控台**樹狀結構中，編輯套用到您要設定電子郵件安全性之所有 AGPM 服務器的 GPO。</span><span class="sxs-lookup"><span data-stu-id="2ab21-113">In the **Group Policy Management Console** tree, edit a GPO that is applied to all AGPM Servers for which you want to configure e-mail security.</span></span> <span data-ttu-id="2ab21-114">（如需詳細資訊，請參閱[編輯 GPO](editing-a-gpo-agpm40.md)）。</span><span class="sxs-lookup"><span data-stu-id="2ab21-114">(For more information, see [Editing a GPO](editing-a-gpo-agpm40.md).)</span></span>

2.  <span data-ttu-id="2ab21-115">在 [**群組原則管理編輯器**] 視窗中，展開 [**電腦**設定]、[**喜好**設定]、[ **Windows 設定**] 和 [**註冊表**資料夾]。</span><span class="sxs-lookup"><span data-stu-id="2ab21-115">In the **Group Policy Management Editor** window, expand the **Computer Configuration**, **Preferences**, **Windows Settings**, and **Registry** folders.</span></span>

3.  <span data-ttu-id="2ab21-116">在主控台樹中，以滑鼠右鍵按一下 [**註冊表**]，指向 [**新增**]，按一下 [**收集項目**]，然後輸入 [ **AGPM 電子郵件安全性**]。</span><span class="sxs-lookup"><span data-stu-id="2ab21-116">In the console tree, right-click **Registry**, point to **New**, click **Collection Item**, and type **AGPM e-mail security**.</span></span>

4.  <span data-ttu-id="2ab21-117">建立登錄的 [喜好設定] 專案來開啟加密：</span><span class="sxs-lookup"><span data-stu-id="2ab21-117">Create a Registry preference item to turn on encryption:</span></span>

    1.  <span data-ttu-id="2ab21-118">在主控台樹中，以滑鼠右鍵按一下 [ **AGPM 電子郵件安全性**]，指向 [**新增**]，然後按一下 [**登錄機碼目**]。</span><span class="sxs-lookup"><span data-stu-id="2ab21-118">In the console tree, right-click **AGPM e-mail security**, point to **New**, and then click **Registry Item**.</span></span>

    2.  <span data-ttu-id="2ab21-119">在 [**新的註冊表屬性**] 對話方塊中，選取 [**更新**] 動作。</span><span class="sxs-lookup"><span data-stu-id="2ab21-119">In the **New Registry Properties** dialog box, select the **Update** action.</span></span>

    3.  <span data-ttu-id="2ab21-120">針對**Hive**，請選取 [ **HKEY \ _LOCAL \ _MACHINE**]。</span><span class="sxs-lookup"><span data-stu-id="2ab21-120">For **Hive**, select **HKEY\_LOCAL\_MACHINE**.</span></span>

    4.  <span data-ttu-id="2ab21-121">針對 [**主要路徑**]，請輸入**SOFTWARE\\Microsoft\\AGPM**。</span><span class="sxs-lookup"><span data-stu-id="2ab21-121">For **Key Path**, type **SOFTWARE\\Microsoft\\AGPM**.</span></span>

    5.  <span data-ttu-id="2ab21-122">針對 [**值名稱**]，請輸入**EncryptSmtp**。</span><span class="sxs-lookup"><span data-stu-id="2ab21-122">For **Value name**, type **EncryptSmtp**.</span></span>

    6.  <span data-ttu-id="2ab21-123">針對 [**數值型別**]，選取 [ **REG \ _DWORD**]。</span><span class="sxs-lookup"><span data-stu-id="2ab21-123">For **Value type**, select **REG\_DWORD**.</span></span>

    7.  <span data-ttu-id="2ab21-124">針對 [**基數**]，選取 [**小數**]，對於 [**數值資料**]，輸入**1**以使用 SSL 加密，或輸入**0**以讓電子郵件不需加密即可傳送。</span><span class="sxs-lookup"><span data-stu-id="2ab21-124">For **Base**, select **Decimal**, and for **Value data**, type **1** to use SSL encryption, or **0** to let e-mail to be sent without encryption.</span></span> <span data-ttu-id="2ab21-125">根據預設，電子郵件不需加密即可傳送。</span><span class="sxs-lookup"><span data-stu-id="2ab21-125">By default, e-mail is sent without encryption.</span></span> <span data-ttu-id="2ab21-126">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2ab21-126">Click **OK**.</span></span>

5.  <span data-ttu-id="2ab21-127">建立 Registry 喜好設定專案以指定 SMTP 埠：</span><span class="sxs-lookup"><span data-stu-id="2ab21-127">Create a Registry preference item to specify the SMTP port:</span></span>

    1.  <span data-ttu-id="2ab21-128">在主控台樹中，以滑鼠右鍵按一下 [ **AGPM 電子郵件安全性**]，指向 [**新增**]，然後按一下 [**登錄機碼目**]。</span><span class="sxs-lookup"><span data-stu-id="2ab21-128">In the console tree, right-click **AGPM E-mail security**, point to **New**, and then click **Registry Item**.</span></span>

    2.  <span data-ttu-id="2ab21-129">在 [**新的註冊表屬性**] 對話方塊中，選取 [**更新**] 動作。</span><span class="sxs-lookup"><span data-stu-id="2ab21-129">In the **New Registry Properties** dialog box, select the **Update** action.</span></span>

    3.  <span data-ttu-id="2ab21-130">針對**Hive**，請選取 [ **HKEY \ _LOCAL \ _MACHINE**]。</span><span class="sxs-lookup"><span data-stu-id="2ab21-130">For **Hive**, select **HKEY\_LOCAL\_MACHINE**.</span></span>

    4.  <span data-ttu-id="2ab21-131">在 [**主要路徑**] 對話方塊中，輸入**SOFTWARE\\Microsoft\\AGPM**。</span><span class="sxs-lookup"><span data-stu-id="2ab21-131">For **Key Path** dialog box, type **SOFTWARE\\Microsoft\\AGPM**.</span></span>

    5.  <span data-ttu-id="2ab21-132">針對 [**值名稱**]，請輸入**SmtpPort**。</span><span class="sxs-lookup"><span data-stu-id="2ab21-132">For **Value name**, type **SmtpPort**.</span></span>

    6.  <span data-ttu-id="2ab21-133">針對 [**數值型別**]，選取 [ **REG \ _DWORD**]。</span><span class="sxs-lookup"><span data-stu-id="2ab21-133">For **Value type**, select **REG\_DWORD**.</span></span>

    7.  <span data-ttu-id="2ab21-134">針對 [**基數**]，選取 [**小數**]，然後針對 [**數值資料**] 輸入 SMTP 埠的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="2ab21-134">For **Base**, select **Decimal**, and for **Value data**, type a port number for the SMTP port.</span></span> <span data-ttu-id="2ab21-135">根據預設，如果未啟用加密，則 SMTP 埠是埠25，或者如果啟用 SSL 加密，則是埠587。</span><span class="sxs-lookup"><span data-stu-id="2ab21-135">By default, the SMTP port is port 25 if encryption is not enabled or port 587 if SSL encryption is enabled.</span></span> <span data-ttu-id="2ab21-136">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2ab21-136">Click **OK**.</span></span>

6.  <span data-ttu-id="2ab21-137">關閉 [**群組原則管理編輯器**] 視窗，然後存回並部署該 GPO。</span><span class="sxs-lookup"><span data-stu-id="2ab21-137">Close the **Group Policy Management Editor** window, and then check in and deploy the GPO.</span></span> <span data-ttu-id="2ab21-138">如需詳細資訊，請參閱[部署 GPO](deploy-a-gpo-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="2ab21-138">For more information, see [Deploy a GPO](deploy-a-gpo-agpm40.md).</span></span>

### <span data-ttu-id="2ab21-139">其他考量</span><span class="sxs-lookup"><span data-stu-id="2ab21-139">Additional considerations</span></span>

-   <span data-ttu-id="2ab21-140">您必須能夠編輯和部署 GPO，才能使用 [群組原則喜好設定] 來設定註冊表設定。</span><span class="sxs-lookup"><span data-stu-id="2ab21-140">You must be able to edit and deploy a GPO to configure registry settings by using Group Policy Preferences.</span></span> <span data-ttu-id="2ab21-141">如需更多詳細資料，請參閱[編輯 gpo](editing-a-gpo-agpm40.md)及[部署 gpo](deploy-a-gpo-agpm40.md) 。</span><span class="sxs-lookup"><span data-stu-id="2ab21-141">See [Editing a GPO](editing-a-gpo-agpm40.md) and [Deploy a GPO](deploy-a-gpo-agpm40.md) for additional detail.</span></span>

### <span data-ttu-id="2ab21-142">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="2ab21-142">Additional references</span></span>

-   [<span data-ttu-id="2ab21-143">設定進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="2ab21-143">Configuring Advanced Group Policy Management</span></span>](configuring-advanced-group-policy-management-agpm40.md)

 

 





