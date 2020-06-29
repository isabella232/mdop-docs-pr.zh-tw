---
title: 如何備份與還原 MED-V 伺服器
description: 如何備份與還原 MED-V 伺服器
author: dansimp
ms.assetid: 8d05e3a4-279b-4ce6-a319-8a09e7a30c60
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d51cfe3727896ed68a1fd67441174a294a1073cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809746"
---
# <span data-ttu-id="36fc0-103">如何備份與還原 MED-V 伺服器</span><span class="sxs-lookup"><span data-stu-id="36fc0-103">How to Back Up and Restore a MED-V Server</span></span>


<span data-ttu-id="36fc0-104">可以備份位於伺服器上的 XML 檔案，然後在伺服器上的資料遺失時還原。</span><span class="sxs-lookup"><span data-stu-id="36fc0-104">XML files located on the server can be backed up and then restored in case of loss of data on the server.</span></span>

**<span data-ttu-id="36fc0-105">若要備份 MED-V 伺服器</span><span class="sxs-lookup"><span data-stu-id="36fc0-105">To back up a MED-V server</span></span>**

-   <span data-ttu-id="36fc0-106">備份下列檔案（位於\* &lt; InstallDir &gt; \\Servers\\ConfigurationServer\*中）：</span><span class="sxs-lookup"><span data-stu-id="36fc0-106">Back up the following files, located in *&lt;InstallDir&gt;\\Servers\\ConfigurationServer*:</span></span>

    <span data-ttu-id="36fc0-107">**記事** 如果設定已從預設值變更，則檔案可能會儲存在不同的位置。</span><span class="sxs-lookup"><span data-stu-id="36fc0-107">**Note** If the configuration has been changed from the default, the files might be stored in a different location.</span></span>

     

    -   <span data-ttu-id="36fc0-108">ClientPolicy.xml</span><span class="sxs-lookup"><span data-stu-id="36fc0-108">ClientPolicy.xml</span></span>

    -   <span data-ttu-id="36fc0-109">ClientSettings.xml</span><span class="sxs-lookup"><span data-stu-id="36fc0-109">ClientSettings.xml</span></span>

    -   <span data-ttu-id="36fc0-110">ConfigurationFiles.xml</span><span class="sxs-lookup"><span data-stu-id="36fc0-110">ConfigurationFiles.xml</span></span>

    -   <span data-ttu-id="36fc0-111">OrganizationPolicy.xml</span><span class="sxs-lookup"><span data-stu-id="36fc0-111">OrganizationPolicy.xml</span></span>

    -   <span data-ttu-id="36fc0-112">WorkspaceKeys.xml</span><span class="sxs-lookup"><span data-stu-id="36fc0-112">WorkspaceKeys.xml</span></span>

    <span data-ttu-id="36fc0-113">**記事** 您也可以備份 ServerSettings.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="36fc0-113">**Note** The ServerSettings.xml file can be backed up as well.</span></span> <span data-ttu-id="36fc0-114">不過，如果已變更特定設定（例如，在原始伺服器上），則 MED-V VM 目錄位於 [*C:\\Vms*]，而新伺服器上不存在這類目錄），可能會導致錯誤。</span><span class="sxs-lookup"><span data-stu-id="36fc0-114">However, if a specific configuration has been changed (for example, on the original server, the MED-V VMS directory is located in "*C:\\Vms*" and such a directory does not exist on the new server), it can cause an error.</span></span>

     

**<span data-ttu-id="36fc0-115">若要還原 MED-V 伺服器</span><span class="sxs-lookup"><span data-stu-id="36fc0-115">To restore a MED-V server</span></span>**

1.  <span data-ttu-id="36fc0-116">安裝新的 MED-V 伺服器。</span><span class="sxs-lookup"><span data-stu-id="36fc0-116">Install a new MED-V server.</span></span>

2.  <span data-ttu-id="36fc0-117">將備份檔案複製到下列目錄：</span><span class="sxs-lookup"><span data-stu-id="36fc0-117">Copy the backup files to the following directory:</span></span>

    *<span data-ttu-id="36fc0-118">&lt;InstallDir &gt; \\Servers\\ConfigurationServer</span><span class="sxs-lookup"><span data-stu-id="36fc0-118">&lt;InstallDir&gt;\\Servers\\ConfigurationServer</span></span>*

3.  <span data-ttu-id="36fc0-119">重新開機 MED-V 服務。</span><span class="sxs-lookup"><span data-stu-id="36fc0-119">Restart the MED-V service.</span></span>

 

 





