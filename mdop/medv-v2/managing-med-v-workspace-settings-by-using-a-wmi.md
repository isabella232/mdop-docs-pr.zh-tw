---
title: 使用 WMI 管理 MED-V 工作區設定
description: 使用 WMI 管理 MED-V 工作區設定
author: dansimp
ms.assetid: 05a665a3-2309-46c1-babb-a3e3bbb0b1f9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e74e6fa4944ce0dacd5503baec73044b231abe83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811571"
---
# <span data-ttu-id="1f544-103">使用 WMI 管理 MED-V 工作區設定</span><span class="sxs-lookup"><span data-stu-id="1f544-103">Managing MED-V Workspace Settings by Using a WMI</span></span>


<span data-ttu-id="1f544-104">您可以在 Microsoft 企業版桌面虛擬化（MED-V）2.0 中使用 Windows 管理工具（WMI）來管理您目前的設定。</span><span class="sxs-lookup"><span data-stu-id="1f544-104">You can use Windows Management Instrumentation (WMI) in Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 to manage your current configuration settings.</span></span>

## <span data-ttu-id="1f544-105">使用 WMI 管理 MED-V 工作區設定</span><span class="sxs-lookup"><span data-stu-id="1f544-105">To manage MED-V workspace settings with a WMI</span></span>


<span data-ttu-id="1f544-106">WMI 流覽工具可讓您在 MED-V 工作區中查看及編輯設定。</span><span class="sxs-lookup"><span data-stu-id="1f544-106">A WMI browsing tool lets you view and edit the settings in a MED-V workspace.</span></span> <span data-ttu-id="1f544-107">WMI 提供者是使用來自 Microsoft .Net Framework 3.5 的 WMI 提供程式擴充架構來實現。</span><span class="sxs-lookup"><span data-stu-id="1f544-107">The WMI provider is implemented by using the WMI Provider Extension framework from the Microsoft .Net Framework 3.5.</span></span>

<span data-ttu-id="1f544-108">WMI 提供者是在**root\\microsoft\\medv**命名空間中實現並實現類別**設定**。</span><span class="sxs-lookup"><span data-stu-id="1f544-108">The WMI provider is implemented in the **root\\microsoft\\medv** namespace and implements the class **Setting**.</span></span> <span data-ttu-id="1f544-109">Class**設定**包含的屬性對應至 HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\medv 登錄機碼下的系統登錄中的設定。</span><span class="sxs-lookup"><span data-stu-id="1f544-109">The class **Setting** contains properties that correspond to the settings in the system registry under the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Medv registry key.</span></span>

<span data-ttu-id="1f544-110">**小心** WMI 流覽工具可用於刪除或修改類別和實例。</span><span class="sxs-lookup"><span data-stu-id="1f544-110">**Caution** WMI browsing tools can be used to delete or modify classes and instances.</span></span> <span data-ttu-id="1f544-111">刪除或修改某些類別和實例可能會造成寶貴的資料遺失，並導致 MED-V 無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="1f544-111">Deleting or modifying certain classes and instances can result in the loss of valuable data and cause MED-V to function unpredictably.</span></span>

 

<span data-ttu-id="1f544-112">您可以依照下列步驟，使用您慣用的 WMI 流覽工具來查看及編輯 MED-V 設定。</span><span class="sxs-lookup"><span data-stu-id="1f544-112">You can use your preferred WMI browsing tool to view and edit MED-V configuration settings by following these steps.</span></span>

1.  <span data-ttu-id="1f544-113">以系統管理員許可權開啟您慣用的 WMI 流覽工具。</span><span class="sxs-lookup"><span data-stu-id="1f544-113">Open your preferred WMI browsing tool with administrator permissions.</span></span>

2.  <span data-ttu-id="1f544-114">連接到命名空間**root\\microsoft\\medv**。</span><span class="sxs-lookup"><span data-stu-id="1f544-114">Connect to the namespace **root\\microsoft\\medv**.</span></span>

3.  <span data-ttu-id="1f544-115">列舉實例以連接到執行中的實例。</span><span class="sxs-lookup"><span data-stu-id="1f544-115">Enumerate the instances to connect to the running instance.</span></span> <span data-ttu-id="1f544-116">您想要連線到 [課程]**設定**的實例。</span><span class="sxs-lookup"><span data-stu-id="1f544-116">You want to connect to the instance of the class **Setting**.</span></span>

    <span data-ttu-id="1f544-117">隨即會開啟 [**物件編輯器**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="1f544-117">An **Object Editor** window opens.</span></span> <span data-ttu-id="1f544-118">MED-V 設定會列為 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="1f544-118">The MED-V configuration settings are listed as **Properties**.</span></span>

<span data-ttu-id="1f544-119">在 WMI 中，請執行下列步驟來編輯 MED-V 設定。</span><span class="sxs-lookup"><span data-stu-id="1f544-119">Perform the following steps to edit a MED-V configuration setting in the WMI.</span></span>

1.  <span data-ttu-id="1f544-120">在 [**物件編輯器**] 視窗的**屬性**清單中，按兩下您要編輯的設定的名稱。</span><span class="sxs-lookup"><span data-stu-id="1f544-120">In the list of **Properties** on the **Object Editor** window, double-click the name of the configuration setting you want to edit.</span></span> <span data-ttu-id="1f544-121">例如，若要編輯 MED-V URL 重新導向資訊，請按兩下屬性**UxRedirectUrls**。</span><span class="sxs-lookup"><span data-stu-id="1f544-121">For example, to edit MED-V URL redirection information, double-click the property **UxRedirectUrls**.</span></span>

    <span data-ttu-id="1f544-122">[**屬性編輯器**] 視窗隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="1f544-122">A **Property Editor** window opens.</span></span>

2.  <span data-ttu-id="1f544-123">編輯值以更新配置資訊。</span><span class="sxs-lookup"><span data-stu-id="1f544-123">Edit the value to update the configuration information.</span></span> <span data-ttu-id="1f544-124">例如，若要編輯 MED-V URL 重新導向資訊，請在清單中新增或移除網址。</span><span class="sxs-lookup"><span data-stu-id="1f544-124">For example, to edit MED-V URL redirection information, add or remove a web address in the list.</span></span>

3.  <span data-ttu-id="1f544-125">儲存更新的屬性設定。</span><span class="sxs-lookup"><span data-stu-id="1f544-125">Save the updated property settings.</span></span>

<span data-ttu-id="1f544-126">完成查看或編輯 MED-V 設定設定之後，請關閉 WMI 流覽工具。</span><span class="sxs-lookup"><span data-stu-id="1f544-126">After you have finished viewing or editing MED-V configuration settings, close the WMI browsing tool.</span></span>

<span data-ttu-id="1f544-127">**重要** 在某些情況下，MED-V 設定的變更必須重新開機 MED-V 工作區，才能生效。</span><span class="sxs-lookup"><span data-stu-id="1f544-127">**Important** In some cases, a restart of the MED-V workspace is required for changes to MED-V configuration settings to take effect.</span></span>

 

<span data-ttu-id="1f544-128">下列程式碼會顯示定義**設定**類別的 Managed 物件格式（MOF）檔案。</span><span class="sxs-lookup"><span data-stu-id="1f544-128">The following code shows the Managed Object Format (MOF) file that defines the **Setting** class.</span></span>

``` syntax
[dynamic: ToInstance, provider("TroubleShooting, Version=2.0.392.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"), singleton: DisableOverride ToInstance ToSubClass]
class Setting : ConfigValueProvider
{
                boolean UxSmartCardLogonEnabled = TRUE;
                [read] string User;
                [implemented] void Clear([in] string propertyName);
};
```

<span data-ttu-id="1f544-129">此**設定**類別繼承自**ConfigValueProvider**類別。</span><span class="sxs-lookup"><span data-stu-id="1f544-129">The **Setting** class inherits from the **ConfigValueProvider** class.</span></span> <span data-ttu-id="1f544-130">下列程式碼顯示定義**ConfigValueProvider**類別的 Managed 物件格式（MOF）檔案。</span><span class="sxs-lookup"><span data-stu-id="1f544-130">The following code shows the Managed Object Format (MOF) file that defines the **ConfigValueProvider** class.</span></span>

``` syntax
[abstract]
class ConfigValueProvider
{
                [write] string DiagEventLogLevel;
                [write] boolean FtsAddUserToAdminGroupEnabled;
                [write] string FtsComputerNameMask;
                [write] sint32 FtsDeleteVMStateTimeout;
                [write] sint32 FtsDetachVfdTimeout;
                [write] string FtsDialogUrl;
                [write] sint32 FtsExplorerTimeout;
                [write] string FtsFailureDialogMsg;
                [write] string FtsLogFilePaths[];
                [write] sint32 FtsMaxPostponeTime;
                [write] sint32 FtsMaxRetryCount;
                [write] string FtsMode;
                [write] sint32 FtsNonInteractiveRetryTimeoutInc;
                [write] sint32 FtsNonInteractiveTimeout;
                [write] string FtsPostponeUtcDateTimeLimit;
                [write] string FtsRetryDialogMsg;
                [write] boolean FtsSetComputerNameEnabled;
                [write] boolean FtsSetJoinDomainEnabled;
                [write] boolean FtsSetMachineObjectOUEnabled;
                [write] boolean FtsSetRegionalSettingsEnabled;
                [write] boolean FtsSetUserDataEnabled;
                [write] string FtsStartDialogMsg;
                [write] sint32 FtsTaskCancelTimeout;
                [write] sint32 FtsTaskVMTurnOffTimeout;
                [write] sint32 FtsUpgradeTimeout;
                [write] boolean UxAppPublishingEnabled;
                [write] boolean UxAudioSharingEnabled;
                [write] boolean UxClipboardSharingEnabled;
                [write] boolean UxCredentialCacheEnabled;
                [write] sint32 UxDialogTimeout;
                [write] sint32 UxHideVmTimeout;
                [write] boolean UxLogonStartEnabled;
                [write] boolean UxPrinterSharingEnabled;
                [write] sint32 UxRebootAbsoluteDelayTimeout;
                [write] string UxRedirectUrls[];
                [write] boolean UxShowExit;
                [write] boolean UxSmartCardLogonEnabled;
                [write] boolean UxSmartCardSharingEnabled;
                [write] boolean UxUSBDeviceSharingEnabled;
                [write] string VmCloseAction;
                [write] sint32 VmGuestMemFromHostMem[];
                [write] sint32 VmGuestUpdateDuration;
                [write] string VmGuestUpdateTime;
                [write] sint32 VmHostMemToGuestMem[];
                [write] boolean VmHostMemToGuestMemCalcEnabled;
                [write] sint32 VmMemory;
                [write] boolean VmMultiUserEnabled;
                [write] string VmNetworkingMode;
                [write] sint32 VmTaskTimeout;
};
```

## <span data-ttu-id="1f544-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="1f544-131">Related topics</span></span>


[<span data-ttu-id="1f544-132">管理 MED-V 工作區組態設定</span><span class="sxs-lookup"><span data-stu-id="1f544-132">Managing MED-V Workspace Configuration Settings</span></span>](managing-med-v-workspace-configuration-settings.md)

[<span data-ttu-id="1f544-133">管理 MED-V 工作區設定</span><span class="sxs-lookup"><span data-stu-id="1f544-133">Manage MED-V Workspace Settings</span></span>](manage-med-v-workspace-settings.md)

 

 





