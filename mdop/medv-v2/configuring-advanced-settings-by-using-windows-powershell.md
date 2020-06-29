---
title: 使用 Windows PowerShell 設定進階設定
description: 使用 Windows PowerShell 設定進階設定
author: dansimp
ms.assetid: 437a31cc-2a11-456f-b448-b0b869fb53f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 45a3ece3f76f6e982913aad2b25cfe0084542f32
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812327"
---
# <span data-ttu-id="7109a-103">使用 Windows PowerShell 設定進階設定</span><span class="sxs-lookup"><span data-stu-id="7109a-103">Configuring Advanced Settings by Using Windows PowerShell</span></span>


<span data-ttu-id="7109a-104">您建立的 MED-V 工作區套件包含 Windows PowerShell 腳本（ps1）檔案，您可以在測試和部署 MED-V 工作區套件之前進行編輯。</span><span class="sxs-lookup"><span data-stu-id="7109a-104">The MED-V workspace package that you create includes a Windows PowerShell script (.ps1) file that you can edit before you test and deploy your MED-V workspace package.</span></span> <span data-ttu-id="7109a-105">本節提供的資訊與指導方針，可協助您在部署 MED-V 工作區之前，先使用 Windows PowerShell 來管理 MED-V 配置設定。</span><span class="sxs-lookup"><span data-stu-id="7109a-105">This section provides information and guidance to help you manage MED-V configuration settings by using Windows PowerShell before you deploy the MED-V workspaces.</span></span>

## <span data-ttu-id="7109a-106">在 MED-V 中使用 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="7109a-106">Using Windows PowerShell Cmdlets in MED-V</span></span>


<span data-ttu-id="7109a-107">您可以在 Microsoft 企業桌面虛擬化（MED-V）2.0 中使用下列 Windows PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7109a-107">The following Windows PowerShell cmdlets are available in Microsoft Enterprise Desktop Virtualization (MED-V) 2.0:</span></span>

**<span data-ttu-id="7109a-108">新-MedvConfiguration</span><span class="sxs-lookup"><span data-stu-id="7109a-108">New-MedvConfiguration</span></span>**

**<span data-ttu-id="7109a-109">Export-MedvConfiguration</span><span class="sxs-lookup"><span data-stu-id="7109a-109">Export-MedvConfiguration</span></span>**

**<span data-ttu-id="7109a-110">新-MedvWorkspace</span><span class="sxs-lookup"><span data-stu-id="7109a-110">New-MedvWorkspace</span></span>**

**<span data-ttu-id="7109a-111">Export-MedvWorkspace</span><span class="sxs-lookup"><span data-stu-id="7109a-111">Export-MedvWorkspace</span></span>**

<span data-ttu-id="7109a-112">若要存取 MED-V 的 Windows PowerShell Cmdlet，請開啟 Windows PowerShell，然後輸入下列命令，以匯入 MED-V 模組。</span><span class="sxs-lookup"><span data-stu-id="7109a-112">To access Windows PowerShell cmdlets for MED-V, open Windows PowerShell and type the following command to import the MED-V modules.</span></span>

``` syntax
Import-Module microsoft.medv
```

<span data-ttu-id="7109a-113">匯入模組之後，您可以使用標準的 Windows PowerShell 說明命令、 **man**或**get-help**來存取 Cmdlet 的串聯說明。</span><span class="sxs-lookup"><span data-stu-id="7109a-113">After the modules are imported, you can access inline help for the cmdlets by using the standard Windows PowerShell Help commands, **man** or **get-help**.</span></span> <span data-ttu-id="7109a-114">例如，若要存取**MedvConfiguration** Cmdlet 的描述（包括完整的可用參數清單），請輸入下列命令。</span><span class="sxs-lookup"><span data-stu-id="7109a-114">For example, to access a description of the **New-MedvConfiguration** cmdlet including a complete list of available parameters, type the following command.</span></span>

``` syntax
get-help New-MedvConfiguration
```

<span data-ttu-id="7109a-115">您也可以查看特定參數的說明。</span><span class="sxs-lookup"><span data-stu-id="7109a-115">You can also view help for specific parameters.</span></span> <span data-ttu-id="7109a-116">例如，若要查看參數 VmMemory 的說明，請輸入下列資訊：</span><span class="sxs-lookup"><span data-stu-id="7109a-116">For example, to view help for the parameter VmMemory, type the following:</span></span>

``` syntax
get-help New-MedvConfiguration -parameter VmMemory
```

<span data-ttu-id="7109a-117">若要查看所有 MED-V 設定及其預設值的清單，請輸入下列命令。</span><span class="sxs-lookup"><span data-stu-id="7109a-117">To view a list of all MED-V configuration settings and their defaults, type the following command.</span></span>

``` syntax
New-MedvConfiguration -ForceDefaults
```

<span data-ttu-id="7109a-118">若要查看所有 MED-V 設定及其目前值的清單，請輸入下列命令。</span><span class="sxs-lookup"><span data-stu-id="7109a-118">To view a list of all MED-V configuration settings and their current values, type the following command.</span></span>

``` syntax
gwmi -Class "Setting” -Namespace "root/microsoft/medv”
```

## <span data-ttu-id="7109a-119">使用自訂設定建立 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="7109a-119">Creating a MED-V Workspace with Custom Settings</span></span>


<span data-ttu-id="7109a-120">使用 MED-V 工作區包裝程式成功建立 MED-V 工作區套件之後，系統會在您指定用來儲存包裝程式檔案的資料夾中產生 Windows PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="7109a-120">After you successfully create a MED-V workspace package by using the MED-V Workspace Packager, a Windows PowerShell script is generated in the folder you specified for saving your packager files.</span></span> <span data-ttu-id="7109a-121">此腳本的內容會顯示一些您可以編輯的可用 MED-V 設定。</span><span class="sxs-lookup"><span data-stu-id="7109a-121">The contents of this script show some of the available MED-V configuration settings that you can edit.</span></span>

<span data-ttu-id="7109a-122">遵循這些步驟，您可以自訂腳本，然後在 Windows PowerShell 中執行，以使用新的設定來建立 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="7109a-122">Following these steps, you can customize the script and then run it in Windows PowerShell to create a MED-V workspace with the new settings.</span></span>

<span data-ttu-id="7109a-123">**重要** 使用管理認證執行 Windows PowerShell，並確保 Windows PowerShell 執行原則允許執行腳本。</span><span class="sxs-lookup"><span data-stu-id="7109a-123">**Important** Run Windows PowerShell with administrative credentials, and ensure that the Windows PowerShell execution policy allows the running of scripts.</span></span>

1.  <span data-ttu-id="7109a-124">編輯由 MED-V 工作區包裝程式所產生的 Windows PowerShell 腳本，或使用您想要的設定設定制作新的腳本。</span><span class="sxs-lookup"><span data-stu-id="7109a-124">Edit the Windows PowerShell script that was generated by the MED-V Workspace Packager, or author a new script with the configuration settings that you want.</span></span>

2.  <span data-ttu-id="7109a-125">使用系統管理認證執行 Windows PowerShell，然後在命令提示字元輸入下列命令。</span><span class="sxs-lookup"><span data-stu-id="7109a-125">Run Windows PowerShell with administrative credentials and at the command prompt, type the following command.</span></span>

    ``` syntax
    & “.\<workspacename>.ps1”
    ```

    <span data-ttu-id="7109a-126">這個命令會執行 Windows PowerShell 腳本並執行**新的 MedvWorkspace** Cmdlet 來產生新的 med-v 工作區套件。</span><span class="sxs-lookup"><span data-stu-id="7109a-126">This command runs the Windows PowerShell script and runs the **New-MedvWorkspace** cmdlet to generate a new MED-V workspace package.</span></span> <span data-ttu-id="7109a-127">新的包裝程式檔案會儲存在您最初指定用來儲存 MED-V 工作區包裝程式檔案的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="7109a-127">The new packager files are saved in the folder that you originally specified for storing your MED-V Workspace Packager files.</span></span> <span data-ttu-id="7109a-128">如需有關此 Cmdlet 的其他說明，請參閱 Windows PowerShell 說明。</span><span class="sxs-lookup"><span data-stu-id="7109a-128">For additional help about this cmdlet, see the Windows PowerShell Help.</span></span>

 

## <span data-ttu-id="7109a-129">將 MED-V 設定匯出至登錄檔案</span><span class="sxs-lookup"><span data-stu-id="7109a-129">Exporting a MED-V Configuration to a Registry File</span></span>


<span data-ttu-id="7109a-130">您可以在安裝 MED-V 工作區之後，更新 MED-V 設定設定。</span><span class="sxs-lookup"><span data-stu-id="7109a-130">You can update MED-V configuration settings after the MED-V workspace is installed.</span></span> <span data-ttu-id="7109a-131">使用**新的-MedvConfiguration** Cmdlet 來指定您要變更的參數。</span><span class="sxs-lookup"><span data-stu-id="7109a-131">Use the **New-MedvConfiguration** cmdlet to specify the parameters that you want to change.</span></span> <span data-ttu-id="7109a-132">例如，若要建立變更虛擬機器記憶體設定的註冊表檔，請輸入下列命令。</span><span class="sxs-lookup"><span data-stu-id="7109a-132">For example, to create a registry file that changes the virtual machine memory setting, type the following commands.</span></span>

``` syntax
New-MedvConfiguration  -VmMemory 1024 | Export-MedvConfiguration -Path c:\medvConfiguration\myConfig.reg
```

<span data-ttu-id="7109a-133">您可以從主機電腦將產生的登錄檔案匯入到 MED-V 工作區，以套用新的設定設定。</span><span class="sxs-lookup"><span data-stu-id="7109a-133">You can import the resultant registry file from the host computer to a MED-V workspace to apply the new configuration settings.</span></span>

## <span data-ttu-id="7109a-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="7109a-134">Related topics</span></span>


[<span data-ttu-id="7109a-135">管理 MED-V 工作區組態設定</span><span class="sxs-lookup"><span data-stu-id="7109a-135">Managing MED-V Workspace Configuration Settings</span></span>](managing-med-v-workspace-configuration-settings.md)

[<span data-ttu-id="7109a-136">測試及部署 MED-V 工作區套件</span><span class="sxs-lookup"><span data-stu-id="7109a-136">Test And Deploy the MED-V Workspace Package</span></span>](test-and-deploy-the-med-v-workspace-package.md)

 

 





