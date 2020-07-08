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
# 使用 WMI 管理 MED-V 工作區設定


您可以在 Microsoft 企業版桌面虛擬化（MED-V）2.0 中使用 Windows 管理工具（WMI）來管理您目前的設定。

## 使用 WMI 管理 MED-V 工作區設定


WMI 流覽工具可讓您在 MED-V 工作區中查看及編輯設定。 WMI 提供者是使用來自 Microsoft .Net Framework 3.5 的 WMI 提供程式擴充架構來實現。

WMI 提供者是在**root\\microsoft\\medv**命名空間中實現並實現類別**設定**。 Class**設定**包含的屬性對應至 HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\medv 登錄機碼下的系統登錄中的設定。

**小心** WMI 流覽工具可用於刪除或修改類別和實例。 刪除或修改某些類別和實例可能會造成寶貴的資料遺失，並導致 MED-V 無法正常運作。

 

您可以依照下列步驟，使用您慣用的 WMI 流覽工具來查看及編輯 MED-V 設定。

1.  以系統管理員許可權開啟您慣用的 WMI 流覽工具。

2.  連接到命名空間**root\\microsoft\\medv**。

3.  列舉實例以連接到執行中的實例。 您想要連線到 [課程]**設定**的實例。

    隨即會開啟 [**物件編輯器**] 視窗。 MED-V 設定會列為 [**屬性**]。

在 WMI 中，請執行下列步驟來編輯 MED-V 設定。

1.  在 [**物件編輯器**] 視窗的**屬性**清單中，按兩下您要編輯的設定的名稱。 例如，若要編輯 MED-V URL 重新導向資訊，請按兩下屬性**UxRedirectUrls**。

    [**屬性編輯器**] 視窗隨即開啟。

2.  編輯值以更新配置資訊。 例如，若要編輯 MED-V URL 重新導向資訊，請在清單中新增或移除網址。

3.  儲存更新的屬性設定。

完成查看或編輯 MED-V 設定設定之後，請關閉 WMI 流覽工具。

**重要** 在某些情況下，MED-V 設定的變更必須重新開機 MED-V 工作區，才能生效。

 

下列程式碼會顯示定義**設定**類別的 Managed 物件格式（MOF）檔案。

``` syntax
[dynamic: ToInstance, provider("TroubleShooting, Version=2.0.392.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"), singleton: DisableOverride ToInstance ToSubClass]
class Setting : ConfigValueProvider
{
                boolean UxSmartCardLogonEnabled = TRUE;
                [read] string User;
                [implemented] void Clear([in] string propertyName);
};
```

此**設定**類別繼承自**ConfigValueProvider**類別。 下列程式碼顯示定義**ConfigValueProvider**類別的 Managed 物件格式（MOF）檔案。

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

## 相關主題


[管理 MED-V 工作區組態設定](managing-med-v-workspace-configuration-settings.md)

[管理 MED-V 工作區設定](manage-med-v-workspace-settings.md)

 

 





