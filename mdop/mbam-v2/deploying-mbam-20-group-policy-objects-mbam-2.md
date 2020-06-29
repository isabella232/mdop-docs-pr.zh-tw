---
title: 部署 MBAM 2.0 群組原則物件
description: 部署 MBAM 2.0 群組原則物件
author: dansimp
ms.assetid: f17f3897-73ab-431b-a6ec-5a6cff9f279a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1ce2c2a37631d9d678d6de7c1d66b7fdafb2ade9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809987"
---
# <span data-ttu-id="63f65-103">部署 MBAM 2.0 群組原則物件</span><span class="sxs-lookup"><span data-stu-id="63f65-103">Deploying MBAM 2.0 Group Policy Objects</span></span>


<span data-ttu-id="63f65-104">若要成功部署 Microsoft BitLocker 管理和監控（MBAM），您必須先決定您要在實施 Microsoft BitLocker 管理和監控時使用的群組原則。</span><span class="sxs-lookup"><span data-stu-id="63f65-104">To successfully deploy Microsoft BitLocker Administration and Monitoring (MBAM), you first have to determine the Group Policies that you will use in your implementation of Microsoft BitLocker Administration and Monitoring.</span></span> <span data-ttu-id="63f65-105">如需其他可用原則的詳細資訊，請參閱[規劃 MBAM 2.0 群組原則需求](planning-for-mbam-20-group-policy-requirements-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="63f65-105">See [Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md) for more information on the different policies that are available.</span></span> <span data-ttu-id="63f65-106">在您決定要使用的原則之後，您必須使用 MBAM 2.0 群組原則範本，建立及部署一個或多個包含 MBAM 原則設定的群組原則物件（GPO）。</span><span class="sxs-lookup"><span data-stu-id="63f65-106">When you have determined the policies that you are going to use, you then must create and deploy one or more Group Policy Objects (GPO) that include the policy settings for MBAM by using the MBAM 2.0 Group Policy template.</span></span>

## <span data-ttu-id="63f65-107">安裝 MBAM 2.0 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="63f65-107">Install the MBAM 2.0 Group Policy Template</span></span>


<span data-ttu-id="63f65-108">除了伺服器相關的 Microsoft BitLocker 管理和監視功能之外，伺服器安裝應用程式還包含 MBAM 組原則範本。</span><span class="sxs-lookup"><span data-stu-id="63f65-108">In addition to the server-related Microsoft BitLocker Administration and Monitoring features, the server setup application includes a MBAM Group Policy template.</span></span> <span data-ttu-id="63f65-109">此範本可安裝在任何能夠執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）的電腦上。</span><span class="sxs-lookup"><span data-stu-id="63f65-109">This template can be installed on any computer able to run the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

[<span data-ttu-id="63f65-110">如何安裝 MBAM 2.0 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="63f65-110">How to Install the MBAM 2.0 Group Policy Template</span></span>](how-to-install-the-mbam-20-group-policy-template-mbam-2.md)

## <span data-ttu-id="63f65-111">部署 MBAM 2.0 群組原則設定</span><span class="sxs-lookup"><span data-stu-id="63f65-111">Deploy MBAM 2.0 Group Policy Settings</span></span>


<span data-ttu-id="63f65-112">在您建立必要的 Gpo 之後，您必須將 MBAM 群組原則設定部署到貴組織的用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="63f65-112">After you create the necessary GPOs, you must deploy the MBAM Group Policy settings to your organization’s client computers.</span></span>

[<span data-ttu-id="63f65-113">如何編輯 MBAM 2.0 GPO 設定</span><span class="sxs-lookup"><span data-stu-id="63f65-113">How to Edit MBAM 2.0 GPO Settings</span></span>](how-to-edit-mbam-20-gpo-settings-mbam-2.md)

## <span data-ttu-id="63f65-114">在 Windows 中顯示 [MBAM] 控制台</span><span class="sxs-lookup"><span data-stu-id="63f65-114">Display the MBAM Control Panel in Windows</span></span>


<span data-ttu-id="63f65-115">因為 MBAM 提供自訂的 MBAM 控制台，可以取代預設的 Windows BitLocker 控制台，您也可以選擇透過使用群組原則來隱藏使用者的預設 BitLocker 控制台。</span><span class="sxs-lookup"><span data-stu-id="63f65-115">Because MBAM offers a customized MBAM control panel that can replace the default Windows BitLocker control panel, you can also choose to hide the default BitLocker Control Panel from end users by using Group Policy.</span></span>

[<span data-ttu-id="63f65-116">如何在 Windows 控制台中隱藏預設 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="63f65-116">How to Hide Default BitLocker Encryption in the Windows Control Panel</span></span>](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel-mbam-2.md)

## <span data-ttu-id="63f65-117">部署 MBAM 2.0 群組原則物件的其他資源</span><span class="sxs-lookup"><span data-stu-id="63f65-117">Other Resources for Deploying MBAM 2.0 Group Policy Objects</span></span>


[<span data-ttu-id="63f65-118">部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="63f65-118">Deploying MBAM 2.0</span></span>](deploying-mbam-20-mbam-2.md)

 

 





