---
title: 如何使用 ADMX 範本和群組原則來修改 App-V 5.0 用戶端組態
description: 如何使用 ADMX 範本和群組原則來修改 App-V 5.0 用戶端組態
author: dansimp
ms.assetid: 79d03a2b-2586-4ca7-bbaa-bdeb0a694279
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cd257691bf223baa5e2919d83fdbf53d34f271ac
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800444"
---
# <span data-ttu-id="64cb1-103">如何使用 ADMX 範本和群組原則來修改 App-V 5.0 用戶端組態</span><span class="sxs-lookup"><span data-stu-id="64cb1-103">How to Modify App-V 5.0 Client Configuration Using the ADMX Template and Group Policy</span></span>


<span data-ttu-id="64cb1-104">使用 [App-v 5.0 ADMX] 範本，以使用 ADMX 範本和群組原則來設定 App-v 5.0 用戶端設定。</span><span class="sxs-lookup"><span data-stu-id="64cb1-104">Use the App-V 5.0 ADMX template to configure App-V 5.0 client settings using the ADMX Template and Group Policy.</span></span>

**<span data-ttu-id="64cb1-105">使用群組原則修改 App-v 5.0 用戶端設定</span><span class="sxs-lookup"><span data-stu-id="64cb1-105">To modify App-V 5.0 client configuration using Group Policy</span></span>**

1.  <span data-ttu-id="64cb1-106">若要修改 App-v 5.0 用戶端設定，請找出可在 App-v 5.0 中使用的**ADMXTemplate**檔案。</span><span class="sxs-lookup"><span data-stu-id="64cb1-106">To modify the App-V 5.0 client configuration, locate the **ADMXTemplate** files that are available with App-V 5.0.</span></span>

    <span data-ttu-id="64cb1-107">**記事** 使用下列連結下載 app-v 5.0 **ADMX 範本**： <https://go.microsoft.com/fwlink/p/?LinkId=393941> 。</span><span class="sxs-lookup"><span data-stu-id="64cb1-107">**Note** Use the following link to download the App-V 5.0 **ADMX Templates**: <https://go.microsoft.com/fwlink/p/?LinkId=393941>.</span></span>

     

2.  <span data-ttu-id="64cb1-108">在您管理群組原則的電腦（通常是網網域控制站），請將範本**admx**檔案複製到下列目錄： \*\* &lt; 安裝磁片磁碟機 &gt; \\ Windows \\ PolicyDefinitions\*\*。</span><span class="sxs-lookup"><span data-stu-id="64cb1-108">On the computer where you manage group Policy, typically the domain controller, copy the template **.admx** file to the following directory: **&lt;Installation Drive&gt; \\ Windows \\ PolicyDefinitions**.</span></span>

    <span data-ttu-id="64cb1-109">接著，在同一部電腦上，將**adml**檔案複製到下列目錄： \*\* &lt; InstallationDrive &gt; \\ Windows \\ PolicyDefinitions \ en-us\*\*。</span><span class="sxs-lookup"><span data-stu-id="64cb1-109">Next, on the same computer, copy the **.adml** file to the following directory: **&lt;InstallationDrive&gt; \\ Windows \\ PolicyDefinitions \\ en-US**.</span></span>

3.  <span data-ttu-id="64cb1-110">將檔案複製到 [群組原則管理主控台] 後，若要修改與您的 App 相關聯的原則-v 5.0 用戶端，請流覽至 [**電腦**設定  /  **原則**] 的 [  /  **管理範本**  /  **系統**]  /  **App-v**。</span><span class="sxs-lookup"><span data-stu-id="64cb1-110">After you have copied the files open the Group Policy Management Console, to modify the policies associated with your App-V 5.0 clients browse to **Computer Configuration** / **Policies** / **Administrative Templates** / **System** / **App-V**.</span></span>

    <span data-ttu-id="64cb1-111">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="64cb1-111">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="64cb1-112">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="64cb1-112">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="64cb1-113">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="64cb1-113">Got an App-V issue?</span></span>** <span data-ttu-id="64cb1-114">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="64cb1-114">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="64cb1-115">相關主題</span><span class="sxs-lookup"><span data-stu-id="64cb1-115">Related topics</span></span>


[<span data-ttu-id="64cb1-116">部署 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="64cb1-116">Deploying App-V 5.0</span></span>](deploying-app-v-50.md)

[<span data-ttu-id="64cb1-117">關於 Client 組態設定</span><span class="sxs-lookup"><span data-stu-id="64cb1-117">About Client Configuration Settings</span></span>](about-client-configuration-settings.md)

 

 





