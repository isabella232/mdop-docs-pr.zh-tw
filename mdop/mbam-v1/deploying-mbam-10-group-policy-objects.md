---
title: 部署 MBAM 1.0 群組原則物件
description: 部署 MBAM 1.0 群組原則物件
author: dansimp
ms.assetid: 2129291e-d2b2-41ed-b643-1e311c49fee7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8d14123f1d5b197146e425cba063e8ce4c180641
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808624"
---
# <span data-ttu-id="29976-103">部署 MBAM 1.0 群組原則物件</span><span class="sxs-lookup"><span data-stu-id="29976-103">Deploying MBAM 1.0 Group Policy Objects</span></span>


<span data-ttu-id="29976-104">若要成功部署 Microsoft BitLocker 管理和監控（MBAM），您必須先決定將在您的 MBAM 中使用的群組原則。</span><span class="sxs-lookup"><span data-stu-id="29976-104">To successfully deploy Microsoft BitLocker Administration and Monitoring (MBAM), you must first determine the Group Policies that you will use in your implementation of MBAM.</span></span> <span data-ttu-id="29976-105">如需各種可用原則的詳細資訊，請參閱[規劃 MBAM 1.0 群組原則需求](planning-for-mbam-10-group-policy-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="29976-105">For more information about the various available policies, see [Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md).</span></span> <span data-ttu-id="29976-106">當您決定要使用的原則之後，您必須使用 MBAM 1.0 群組原則範本來建立及部署一個或多個包含 MBAM 原則設定的群組原則物件（GPO）。</span><span class="sxs-lookup"><span data-stu-id="29976-106">When you have determined the policies that you are going to use, you must use the MBAM 1.0 Group Policy template to create and deploy one or more Group Policy objects (GPO) that include the MBAM policy settings.</span></span>

## <span data-ttu-id="29976-107">安裝 MBAM 1.0 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="29976-107">Install the MBAM 1.0 Group Policy template</span></span>


<span data-ttu-id="29976-108">除了提供 MBAM 的伺服器相關功能之外，伺服器安裝應用程式還包含 MBAM 群組原則範本。</span><span class="sxs-lookup"><span data-stu-id="29976-108">In addition to providing server-related features of MBAM, the server setup application includes an MBAM Group Policy template.</span></span> <span data-ttu-id="29976-109">您可以在任何能夠執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）的電腦上安裝此範本。</span><span class="sxs-lookup"><span data-stu-id="29976-109">You can install this template on any computer that is able to run the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

[<span data-ttu-id="29976-110">如何安裝 MBAM 1.0 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="29976-110">How to Install the MBAM 1.0 Group Policy Template</span></span>](how-to-install-the-mbam-10-group-policy-template.md)

## <span data-ttu-id="29976-111">部署 MBAM 1.0 群組原則設定</span><span class="sxs-lookup"><span data-stu-id="29976-111">Deploy MBAM 1.0 Group Policy settings</span></span>


<span data-ttu-id="29976-112">在您建立必要的 Gpo 之後，您必須將 MBAM 群組原則設定部署到貴組織的用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="29976-112">After you create the necessary GPOs, you must deploy the MBAM Group Policy settings to your organization’s client computers.</span></span>

[<span data-ttu-id="29976-113">如何編輯 MBAM 1.0 GPO 設定</span><span class="sxs-lookup"><span data-stu-id="29976-113">How to Edit MBAM 1.0 GPO Settings</span></span>](how-to-edit-mbam-10-gpo-settings.md)

## <span data-ttu-id="29976-114">在 Windows 中顯示 [MBAM] 控制台</span><span class="sxs-lookup"><span data-stu-id="29976-114">Display the MBAM Control Panel in Windows</span></span>


<span data-ttu-id="29976-115">因為 MBAM 提供自訂的 MBAM 控制台，可以取代預設的 Windows BitLocker 控制台，您也可以選擇透過使用群組原則來隱藏使用者的預設 BitLocker 控制台。</span><span class="sxs-lookup"><span data-stu-id="29976-115">Because MBAM offers a customized MBAM control panel that can replace the default Windows BitLocker control panel, you can also choose to hide the default BitLocker Control Panel from end users by using Group Policy.</span></span>

[<span data-ttu-id="29976-116">如何在 Windows 控制台中隱藏預設 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="29976-116">How to Hide Default BitLocker Encryption in The Windows Control Panel</span></span>](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel.md)

## <span data-ttu-id="29976-117">部署 MBAM 1.0 群組原則物件的其他資源</span><span class="sxs-lookup"><span data-stu-id="29976-117">Other resources for deploying MBAM 1.0 Group Policy Objects</span></span>


[<span data-ttu-id="29976-118">部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="29976-118">Deploying MBAM 1.0</span></span>](deploying-mbam-10.md)

 

 





