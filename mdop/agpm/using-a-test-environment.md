---
title: 使用測試環境
description: 使用測試環境
author: dansimp
ms.assetid: fc5fcc7c-1ac8-483a-a6bd-2279ae2ee3fb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fc3ad91747c755efe0576cc62473848094b72ed1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801710"
---
# <span data-ttu-id="3376c-103">使用測試環境</span><span class="sxs-lookup"><span data-stu-id="3376c-103">Using a Test Environment</span></span>


<span data-ttu-id="3376c-104">在您要求將群組原則物件（GPO）部署到生產環境之前，您應該在實驗室環境中測試 GPO。</span><span class="sxs-lookup"><span data-stu-id="3376c-104">Before you request that a Group Policy Object (GPO) be deployed to the production environment, you should test the GPO in a lab environment.</span></span> <span data-ttu-id="3376c-105">如果您在測試目錄林中的網域中開發 GPO，您可以將 GPO 匯出至檔案，然後將檔案匯入到生產目錄林中的網域。</span><span class="sxs-lookup"><span data-stu-id="3376c-105">If you develop the GPO in a domain in a test forest, you can export the GPO to a file and import the file to a domain in the production forest.</span></span> <span data-ttu-id="3376c-106">然後，您可以將 GPO 連結到包含測試電腦和使用者的組織單位（OU），以進行測試。</span><span class="sxs-lookup"><span data-stu-id="3376c-106">You can then test the GPO by linking it to an organizational unit (OU) that contains test computers and users.</span></span>

-   [<span data-ttu-id="3376c-107">匯出 GPO 到檔案</span><span class="sxs-lookup"><span data-stu-id="3376c-107">Export a GPO to a File</span></span>](export-a-gpo-to-a-file.md)

-   [<span data-ttu-id="3376c-108">從檔案匯入 GPO</span><span class="sxs-lookup"><span data-stu-id="3376c-108">Import a GPO from a File</span></span>](import-a-gpo-from-a-file-ed.md)

-   [<span data-ttu-id="3376c-109">在不同的組織單位測試 GPO</span><span class="sxs-lookup"><span data-stu-id="3376c-109">Test a GPO in a Separate Organizational Unit</span></span>](test-a-gpo-in-a-separate-organizational-unit-agpm40.md)

<span data-ttu-id="3376c-110">**記事** 您也可以從網域的生產環境中匯入 GPO。</span><span class="sxs-lookup"><span data-stu-id="3376c-110">**Note** You can also import a GPO from the production environment of the domain.</span></span> <span data-ttu-id="3376c-111">如需詳細資訊，請參閱[從生產匯入 GPO](import-a-gpo-from-production-agpm40-ed.md)。</span><span class="sxs-lookup"><span data-stu-id="3376c-111">For more information, see [Import a GPO from Production](import-a-gpo-from-production-agpm40-ed.md).</span></span>

 

 

 





