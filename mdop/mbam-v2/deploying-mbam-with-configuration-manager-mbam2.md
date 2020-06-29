---
title: 使用設定管理員來部署 MBAM
description: 使用設定管理員來部署 MBAM
author: dansimp
ms.assetid: 89d03e29-457a-471d-b893-e0b74a83ec50
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c6cffc1cf51a26aeaa94fcb265199c19f0f34abe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809963"
---
# <span data-ttu-id="71e1a-103">使用設定管理員來部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="71e1a-103">Deploying MBAM with Configuration Manager</span></span>


<span data-ttu-id="71e1a-104">下列程式說明如何使用 Microsoft System Center Configuration Manager 2007 或 MicrosoftSystemCenter2012 ConfigurationManager 部署 Microsoft BitLocker 管理和監控（MBAM），方法是 usingthe 建議的設定，這會在 [[開始使用 MBAM 與 Configuration Manager](getting-started---using-mbam-with-configuration-manager.md)] 中說明。</span><span class="sxs-lookup"><span data-stu-id="71e1a-104">The following procedures describe how to deploy Microsoft BitLocker Administration and Monitoring (MBAM) with Microsoft System Center Configuration Manager 2007 or MicrosoftSystemCenter2012 ConfigurationManager by usingthe recommended configuration, which is described in [Getting Started - Using MBAM with Configuration Manager](getting-started---using-mbam-with-configuration-manager.md).</span></span> <span data-ttu-id="71e1a-105">建議的設定是在一或多個 Microsoft BitLocker 管理和監控伺服器上安裝管理和監控功能，並在個別的伺服器上安裝 Microsoft System Center Configuration Manager 2007 或 MicrosoftSystemCenter2012 ConfigurationManager。</span><span class="sxs-lookup"><span data-stu-id="71e1a-105">The recommended configuration is to install the Administration and Monitoring features on one or more Microsoft BitLocker Administration and Monitoring servers, and install Microsoft System Center Configuration Manager 2007 or MicrosoftSystemCenter2012 ConfigurationManager on a separate server.</span></span>

<span data-ttu-id="71e1a-106">在您開始安裝之前，請先檢查[規劃，透過 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md)，以確保您已滿足安裝 MBAM 與 configuration manager 的先決條件與硬體和軟體需求。</span><span class="sxs-lookup"><span data-stu-id="71e1a-106">Before you start the installation, ensure that you have met the prerequisites and hardware and software requirements for installing MBAM with Configuration Manager by reviewing [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md).</span></span>

<span data-ttu-id="71e1a-107">如果您需要重新安裝 Configuration Manager 拓撲 MBAM，您必須先移除某些 Configuration Manager 物件。</span><span class="sxs-lookup"><span data-stu-id="71e1a-107">If you ever have to reinstall MBAM with the Configuration Manager topology, you will need to remove certain Configuration Manager objects first.</span></span> <span data-ttu-id="71e1a-108">如需詳細資訊，請參閱[知識庫文章](https://go.microsoft.com/fwlink/?LinkId=286306)。</span><span class="sxs-lookup"><span data-stu-id="71e1a-108">Read the [Knowledge Base article](https://go.microsoft.com/fwlink/?LinkId=286306) for more information.</span></span>

<span data-ttu-id="71e1a-109">在 Configuration Manager 中安裝 MBAM 的步驟，分為下列類別。</span><span class="sxs-lookup"><span data-stu-id="71e1a-109">The steps to install MBAM with Configuration Manager are grouped into the following categories.</span></span> <span data-ttu-id="71e1a-110">完成每個類別的步驟以完成安裝。</span><span class="sxs-lookup"><span data-stu-id="71e1a-110">Complete the steps for each category to complete the installation.</span></span>

## <span data-ttu-id="71e1a-111">如何建立或編輯 mof 檔案</span><span class="sxs-lookup"><span data-stu-id="71e1a-111">How to Create or Edit the mof Files</span></span>


<span data-ttu-id="71e1a-112">若要讓用戶端電腦透過 MBAM Configuration Manager 報告來報告 BitLocker 合規性詳細資料，您必須編輯**Configuration mof**檔案，然後根據您使用的 Configuration Manager 版本，編輯或建立 Sms \ _def 的 mof 檔案。</span><span class="sxs-lookup"><span data-stu-id="71e1a-112">To enable the client computers to report BitLocker compliance details through the MBAM Configuration Manager reports, you have to edit the **Configuration.mof** file, and either edit or create the Sms\_def.mof file, depending on which version of Configuration Manager you are using.</span></span>

[<span data-ttu-id="71e1a-113">如何建立或編輯 mof 檔案</span><span class="sxs-lookup"><span data-stu-id="71e1a-113">How to Create or Edit the mof Files</span></span>](how-to-create-or-edit-the-mof-files.md)

## <span data-ttu-id="71e1a-114">如何安裝 MBAM 搭配 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="71e1a-114">How to Install MBAM with Configuration Manager</span></span>


<span data-ttu-id="71e1a-115">本節提供有關如何在 Configuration Manager 伺服器上安裝下列專案的步驟： MBAM;資料庫伺服器上的復原和審核資料庫;以及管理和監視伺服器上的 [管理與監控伺服器] 功能。</span><span class="sxs-lookup"><span data-stu-id="71e1a-115">This section provides steps about how to install the following: MBAM on the Configuration Manager Server; the Recovery and Audit Databases on the Database Server; and the Administration and Monitoring Server features on the Administration and Monitoring Server.</span></span>

[<span data-ttu-id="71e1a-116">如何安裝 MBAM 搭配 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="71e1a-116">How to Install MBAM with Configuration Manager</span></span>](how-to-install-mbam-with-configuration-manager.md)

## <span data-ttu-id="71e1a-117">如何驗證 Configuration Manager 伺服器上的 MBAM Server 功能安裝</span><span class="sxs-lookup"><span data-stu-id="71e1a-117">How to Validate the MBAM Server Feature Installation on the Configuration Manager Server</span></span>


<span data-ttu-id="71e1a-118">當 Microsoft BitLocker 管理和監視安裝完成時，請確認安裝已成功設定 Configuration Manager 伺服器所需的所有必要 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="71e1a-118">When the Microsoft BitLocker Administration and Monitoring installation is complete, validate that the installation has successfully set up all the necessary MBAM features required for the Configuration Manager Server.</span></span>

[<span data-ttu-id="71e1a-119">如何使用 Configuration Manager 驗證 MBAM 安裝</span><span class="sxs-lookup"><span data-stu-id="71e1a-119">How to Validate the MBAM Installation with Configuration Manager</span></span>](how-to-validate-the-mbam-installation-with-configuration-manager.md)

## <span data-ttu-id="71e1a-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="71e1a-120">Related topics</span></span>


[<span data-ttu-id="71e1a-121">使用 MBAM 搭配 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="71e1a-121">Using MBAM with Configuration Manager</span></span>](using-mbam-with-configuration-manager.md)

 

 





