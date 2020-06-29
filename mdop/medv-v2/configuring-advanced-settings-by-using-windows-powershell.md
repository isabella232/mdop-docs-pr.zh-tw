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
# 使用 Windows PowerShell 設定進階設定


您建立的 MED-V 工作區套件包含 Windows PowerShell 腳本（ps1）檔案，您可以在測試和部署 MED-V 工作區套件之前進行編輯。 本節提供的資訊與指導方針，可協助您在部署 MED-V 工作區之前，先使用 Windows PowerShell 來管理 MED-V 配置設定。

## 在 MED-V 中使用 Windows PowerShell Cmdlet


您可以在 Microsoft 企業桌面虛擬化（MED-V）2.0 中使用下列 Windows PowerShell Cmdlet：

**新-MedvConfiguration**

**Export-MedvConfiguration**

**新-MedvWorkspace**

**Export-MedvWorkspace**

若要存取 MED-V 的 Windows PowerShell Cmdlet，請開啟 Windows PowerShell，然後輸入下列命令，以匯入 MED-V 模組。

``` syntax
Import-Module microsoft.medv
```

匯入模組之後，您可以使用標準的 Windows PowerShell 說明命令、 **man**或**get-help**來存取 Cmdlet 的串聯說明。 例如，若要存取**MedvConfiguration** Cmdlet 的描述（包括完整的可用參數清單），請輸入下列命令。

``` syntax
get-help New-MedvConfiguration
```

您也可以查看特定參數的說明。 例如，若要查看參數 VmMemory 的說明，請輸入下列資訊：

``` syntax
get-help New-MedvConfiguration -parameter VmMemory
```

若要查看所有 MED-V 設定及其預設值的清單，請輸入下列命令。

``` syntax
New-MedvConfiguration -ForceDefaults
```

若要查看所有 MED-V 設定及其目前值的清單，請輸入下列命令。

``` syntax
gwmi -Class "Setting” -Namespace "root/microsoft/medv”
```

## 使用自訂設定建立 MED-V 工作區


使用 MED-V 工作區包裝程式成功建立 MED-V 工作區套件之後，系統會在您指定用來儲存包裝程式檔案的資料夾中產生 Windows PowerShell 腳本。 此腳本的內容會顯示一些您可以編輯的可用 MED-V 設定。

遵循這些步驟，您可以自訂腳本，然後在 Windows PowerShell 中執行，以使用新的設定來建立 MED-V 工作區。

**重要** 使用管理認證執行 Windows PowerShell，並確保 Windows PowerShell 執行原則允許執行腳本。

1.  編輯由 MED-V 工作區包裝程式所產生的 Windows PowerShell 腳本，或使用您想要的設定設定制作新的腳本。

2.  使用系統管理認證執行 Windows PowerShell，然後在命令提示字元輸入下列命令。

    ``` syntax
    & “.\<workspacename>.ps1”
    ```

    這個命令會執行 Windows PowerShell 腳本並執行**新的 MedvWorkspace** Cmdlet 來產生新的 med-v 工作區套件。 新的包裝程式檔案會儲存在您最初指定用來儲存 MED-V 工作區包裝程式檔案的資料夾中。 如需有關此 Cmdlet 的其他說明，請參閱 Windows PowerShell 說明。

 

## 將 MED-V 設定匯出至登錄檔案


您可以在安裝 MED-V 工作區之後，更新 MED-V 設定設定。 使用**新的-MedvConfiguration** Cmdlet 來指定您要變更的參數。 例如，若要建立變更虛擬機器記憶體設定的註冊表檔，請輸入下列命令。

``` syntax
New-MedvConfiguration  -VmMemory 1024 | Export-MedvConfiguration -Path c:\medvConfiguration\myConfig.reg
```

您可以從主機電腦將產生的登錄檔案匯入到 MED-V 工作區，以套用新的設定設定。

## 相關主題


[管理 MED-V 工作區組態設定](managing-med-v-workspace-configuration-settings.md)

[測試及部署 MED-V 工作區套件](test-and-deploy-the-med-v-workspace-package.md)

 

 





