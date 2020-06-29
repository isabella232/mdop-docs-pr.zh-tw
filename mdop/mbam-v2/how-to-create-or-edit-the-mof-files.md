---
title: 如何建立或編輯 mof 檔案
description: 如何建立或編輯 mof 檔案
author: dansimp
ms.assetid: 4d19d707-b90f-4057-a6e9-e4221a607190
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5f59e9133dd25ecf45d16a5cb704d6ea00923d9e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811085"
---
# <span data-ttu-id="9631e-103">如何建立或編輯 mof 檔案</span><span class="sxs-lookup"><span data-stu-id="9631e-103">How to Create or Edit the mof Files</span></span>


<span data-ttu-id="9631e-104">在使用 Configuration Manager 安裝 Microsoft BitLocker 管理及監視（MBAM）之前，您必須先編輯 Configuration mof 檔案。</span><span class="sxs-lookup"><span data-stu-id="9631e-104">Before you install Microsoft BitLocker Administration and Monitoring (MBAM) with Configuration Manager, you need to edit the Configuration.mof file.</span></span> <span data-ttu-id="9631e-105">您也需要編輯或建立 Sms \ _def 的 mof 檔案，視您所使用的 Configuration Manager 版本而定。</span><span class="sxs-lookup"><span data-stu-id="9631e-105">You also need to either edit or create the Sms\_def.mof file, depending on which version of Configuration Manager you are using.</span></span>

## <span data-ttu-id="9631e-106">編輯 Configuration.mof 檔案</span><span class="sxs-lookup"><span data-stu-id="9631e-106">Edit the Configuration.mof File</span></span>


<span data-ttu-id="9631e-107">若要讓用戶端電腦透過 MBAM Configuration Manager 報告來報告 BitLocker 合規性詳細資料，您必須編輯 Microsoft System Center Configuration Manager 2007 和 SystemCenter2012 ConfigurationManager 的 mof 檔案。</span><span class="sxs-lookup"><span data-stu-id="9631e-107">To enable the client computers to report BitLocker compliance details through the MBAM Configuration Manager reports, you have to edit the Configuration.mof file for Microsoft System Center Configuration Manager 2007 and SystemCenter2012 ConfigurationManager.</span></span>

[<span data-ttu-id="9631e-108">編輯 Configuration.mof 檔案</span><span class="sxs-lookup"><span data-stu-id="9631e-108">Edit the Configuration.mof File</span></span>](edit-the-configurationmof-file.md)

## <a href="" id="create-or-edit-the-sms-def-mof-file"></a><span data-ttu-id="9631e-109">建立或編輯 Sms \ _def 的 mof 檔案</span><span class="sxs-lookup"><span data-stu-id="9631e-109">Create or Edit the Sms\_def.mof File</span></span>


<span data-ttu-id="9631e-110">若要讓用戶端電腦在 MBAM Configuration Manager 報告中報告 BitLocker 相容性詳細資料，您必須建立或編輯 Sms \ _def. mof 檔案。</span><span class="sxs-lookup"><span data-stu-id="9631e-110">To enable the client computers to report BitLocker compliance details in the MBAM Configuration Manager reports, you have to create or edit the Sms\_def.mof file.</span></span> <span data-ttu-id="9631e-111">在 Configuration Manager 2007 中，檔案已經存在，因此您必須編輯現有的檔案，但不需要覆寫該檔案。</span><span class="sxs-lookup"><span data-stu-id="9631e-111">In Configuration Manager 2007, the file already exists, so you need to edit, but not overwrite, the existing file.</span></span> <span data-ttu-id="9631e-112">如果您使用的是 SystemCenter2012 ConfigurationManager，則必須建立檔案。</span><span class="sxs-lookup"><span data-stu-id="9631e-112">If you are using SystemCenter2012 ConfigurationManager, you must create the file.</span></span>

[<span data-ttu-id="9631e-113">建立或編輯 Sms \ _def 的 mof 檔案</span><span class="sxs-lookup"><span data-stu-id="9631e-113">Create or Edit the Sms\_def.mof File</span></span>](create-or-edit-the-sms-defmof-file.md)

## <span data-ttu-id="9631e-114">相關主題</span><span class="sxs-lookup"><span data-stu-id="9631e-114">Related topics</span></span>


[<span data-ttu-id="9631e-115">使用設定管理員來部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="9631e-115">Deploying MBAM with Configuration Manager</span></span>](deploying-mbam-with-configuration-manager-mbam2.md)

 

 





