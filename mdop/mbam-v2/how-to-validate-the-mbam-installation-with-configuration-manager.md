---
title: 如何使用 Configuration Manager 驗證 MBAM 安裝
description: 如何使用 Configuration Manager 驗證 MBAM 安裝
author: dansimp
ms.assetid: 8e268539-91c3-4e8a-baae-faf3605da818
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 500c6f6ee5138b5677bf1fa20e2627a56981df1f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809476"
---
# <span data-ttu-id="79d63-103">如何使用 Configuration Manager 驗證 MBAM 安裝</span><span class="sxs-lookup"><span data-stu-id="79d63-103">How to Validate the MBAM Installation with Configuration Manager</span></span>


<span data-ttu-id="79d63-104">透過 Configuration Manager 安裝 Microsoft BitLocker 管理和監控（MBAM）之後，請完成下列步驟，以確認安裝已成功設定 MBAM 的所有必要功能。</span><span class="sxs-lookup"><span data-stu-id="79d63-104">After installing Microsoft BitLocker Administration and Monitoring (MBAM) with Configuration Manager, validate that the installation has successfully set up all the necessary features for MBAM by completing the following steps.</span></span>

**<span data-ttu-id="79d63-105">使用 Configuration Manager 驗證 MBAM Server 功能安裝</span><span class="sxs-lookup"><span data-stu-id="79d63-105">To validate the MBAM Server feature installation with Configuration Manager</span></span>**

1.  <span data-ttu-id="79d63-106">在部署 System Center Configuration Manager 的伺服器上，開啟 [**控制台**]。</span><span class="sxs-lookup"><span data-stu-id="79d63-106">On the server where System Center Configuration Manager is deployed, open **Control Panel**.</span></span> <span data-ttu-id="79d63-107">選取用來卸載或變更程式的程式。</span><span class="sxs-lookup"><span data-stu-id="79d63-107">Select the program that is used to uninstall or change a program.</span></span> <span data-ttu-id="79d63-108">確認 [ **Microsoft BitLocker 管理及監視**] 出現在 [程式和功能] 清單中。</span><span class="sxs-lookup"><span data-stu-id="79d63-108">Verify that **Microsoft BitLocker Administration and Monitoring** appears in the list of programs and features.</span></span>

    <span data-ttu-id="79d63-109">**記事** 若要驗證安裝，您必須使用在每個伺服器上都有本機電腦管理認證的網域帳戶。</span><span class="sxs-lookup"><span data-stu-id="79d63-109">**Note** To validate the installation, you must use a domain account that has local computer administrative credentials on each server.</span></span>

     

2.  <span data-ttu-id="79d63-110">使用 Configuration Manager 主控台確認顯示名為「MBAM 支援的電腦」的新集合。</span><span class="sxs-lookup"><span data-stu-id="79d63-110">Use the Configuration Manager console to confirm that a new collection, called “MBAM Supported Computers,” is displayed.</span></span>

    <span data-ttu-id="79d63-111">若要查看 Configuration Manager 2007 的集合：按一下 [**網站資料庫**（ &lt; **SiteCode** &gt;  -  &lt; **ServerName** &gt; 、 &lt; **SiteName** &gt; ）]、[**電腦管理**]。</span><span class="sxs-lookup"><span data-stu-id="79d63-111">To view the collection with Configuration Manager 2007: Click **Site Database** (&lt;**SiteCode**&gt; - &lt;**ServerName**&gt;, &lt;**SiteName**&gt;), **Computer Management**.</span></span>

    <span data-ttu-id="79d63-112">若要使用 SystemCenter2012 ConfigurationManager 來查看集合：按一下 [**資產] 和 [合規性**工作區]、[**裝置集合**]。</span><span class="sxs-lookup"><span data-stu-id="79d63-112">To view the collection with SystemCenter2012 ConfigurationManager: Click the **Assets and Compliance** workspace, **Device Collections**.</span></span>

3.  <span data-ttu-id="79d63-113">使用 Configuration Manager 主控台確認下列報告已列在 [ **MBAM** ] 資料夾中：</span><span class="sxs-lookup"><span data-stu-id="79d63-113">Use the Configuration Manager console to verify that the following reports are listed in the **MBAM** folder:</span></span>

    -   <span data-ttu-id="79d63-114">BitLocker 電腦合規性</span><span class="sxs-lookup"><span data-stu-id="79d63-114">BitLocker Computer Compliance</span></span>

    -   <span data-ttu-id="79d63-115">BitLocker Enterprise 合規性儀表板</span><span class="sxs-lookup"><span data-stu-id="79d63-115">BitLocker Enterprise Compliance Dashboard</span></span>

    -   <span data-ttu-id="79d63-116">BitLocker 企業合規性詳細資料</span><span class="sxs-lookup"><span data-stu-id="79d63-116">BitLocker Enterprise Compliance Details</span></span>

    -   <span data-ttu-id="79d63-117">BitLocker Enterprise 合規性摘要</span><span class="sxs-lookup"><span data-stu-id="79d63-117">BitLocker Enterprise Compliance Summary</span></span>

    <span data-ttu-id="79d63-118">若要查看 Configuration Manager 2007 的報表：按一下 [**報告**]、[**報表服務**]、[\\ &lt; **伺服器名稱**] &gt; 、[**報告資料夾**]</span><span class="sxs-lookup"><span data-stu-id="79d63-118">To view the reports with Configuration Manager 2007: Click **Reporting**, **Reporting Services**, \\\\&lt;**ServerName**&gt;, **Report Folders**</span></span>

    <span data-ttu-id="79d63-119">若要使用 SystemCenter2012 ConfigurationManager 來查看報表：按一下 [**監視**] 工作區、[**報告**]、[**報告**]。</span><span class="sxs-lookup"><span data-stu-id="79d63-119">To view the reports with SystemCenter2012 ConfigurationManager: Click the **Monitoring** workspace, **Reporting**, **Reports**.</span></span>

4.  <span data-ttu-id="79d63-120">使用 Configuration Manager 主控台確認已列出設定比較基準 "BitLocker 保護"。</span><span class="sxs-lookup"><span data-stu-id="79d63-120">Use the Configuration Manager console to confirm that the configuration baseline “BitLocker Protection” is listed.</span></span>

    <span data-ttu-id="79d63-121">若要查看 Configuration Manager 2007 的配置基線：按一下 [想要的設定**管理**]、[**配置基線**]。</span><span class="sxs-lookup"><span data-stu-id="79d63-121">To view the configuration baselines with Configuration Manager 2007: Click **Desired Configuration Management**, **Configuration Baselines**.</span></span>

    <span data-ttu-id="79d63-122">若要使用 SystemCenter2012 ConfigurationManager 來查看配置基線：按一下 [**資產與合規性**工作區]、[**合規性設定**]、[**配置基準**]。</span><span class="sxs-lookup"><span data-stu-id="79d63-122">To view the configuration baselines with SystemCenter2012 ConfigurationManager: Click the **Assets and Compliance** workspace, **Compliance Settings**, **Configuration Baselines**.</span></span>

5.  <span data-ttu-id="79d63-123">使用 Configuration Manager 主控台確認顯示下列新的設定專案：</span><span class="sxs-lookup"><span data-stu-id="79d63-123">Use the Configuration Manager console to confirm that the following new configuration items are displayed:</span></span>

    -   <span data-ttu-id="79d63-124">BitLocker 固定資料磁碟機保護</span><span class="sxs-lookup"><span data-stu-id="79d63-124">BitLocker Fixed Data Drives Protection</span></span>

    -   <span data-ttu-id="79d63-125">BitLocker 作業系統磁片磁碟機保護</span><span class="sxs-lookup"><span data-stu-id="79d63-125">BitLocker Operating System Drive Protection</span></span>

    <span data-ttu-id="79d63-126">若要查看 configuration Manager 2007 的設定專案：按一下 [想要的設定**管理**]、[**設定項目**]。</span><span class="sxs-lookup"><span data-stu-id="79d63-126">To view the configuration items with Configuration Manager 2007: Click **Desired Configuration Management**, **Configuration Items**.</span></span>

    <span data-ttu-id="79d63-127">若要使用 SystemCenter2012 ConfigurationManager 來查看設定專案：按一下 [**資產與合規性**工作區]、[**合規性設定**]、[**設定項目**]。</span><span class="sxs-lookup"><span data-stu-id="79d63-127">To view the configuration items with SystemCenter2012 ConfigurationManager: Click the **Assets and Compliance** workspace, **Compliance Settings**, **Configuration Items**.</span></span>

## <span data-ttu-id="79d63-128">相關主題</span><span class="sxs-lookup"><span data-stu-id="79d63-128">Related topics</span></span>


[<span data-ttu-id="79d63-129">使用設定管理員來部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="79d63-129">Deploying MBAM with Configuration Manager</span></span>](deploying-mbam-with-configuration-manager-mbam2.md)

 

 





