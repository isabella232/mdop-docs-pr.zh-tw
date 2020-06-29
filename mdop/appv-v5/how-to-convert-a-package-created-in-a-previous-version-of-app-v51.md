---
title: 如何轉換在舊版 App-V 中建立的套件
description: 如何轉換在舊版 App-V 中建立的套件
author: dansimp
ms.assetid: 3366d399-2891-491d-8de1-f8cfdf39bbab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 402e64e3bdbc55eea1edb91d070bb7ebb11c912b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800573"
---
# 如何轉換在舊版 App-V 中建立的套件


您可以使用套件轉換器實用程式來升級已使用舊版 App-V 建立的虛擬應用程式套件。

**注意**  
如果您執行的是64位架構的電腦，則必須使用 PowerShell 的 x86 版本。



套件轉換器只能直接轉換使用 App-v 4.5 排序器或後續版本建立的套件。 使用 App-v 4.5 之前的版本所建立的套件，必須先升級到 app-v 4.5 或 App-v 4.6 格式，然後再進行轉換。

下列資訊提供轉換現有虛擬應用程式套件的方向。

**重要**  
您必須設定套件轉換器，才能將套件要素檔案儲存到安全的位置和目錄。 只有系統管理員才能存取安全的位置。 此外，當您部署套件時，您應該將套件儲存至安全的位置，或確定在轉換過程中不允許其他使用者登入。



**App-v 4.6 安裝資料夾會重新導向至虛擬檔案系統根目錄**

當您將套件從 App-v 4.6 轉換為5.1 時，App-v 5.1 套件可以存取您在建立4.6 套件時所需使用的硬驅式硬碟。 磁碟機盤符就是您在4.6 順序電腦上選取為安裝磁碟機的磁片磁碟機。 （預設的磁片磁碟機盤符為 Q:\\.）

在 App-V 5.1 之前，無法辨識4.6 根資料夾，且 App-v 5.0 套件無法存取。 現在，App-v 5.1 套件可透過完整路徑存取硬編碼檔案，或以程式設計方式列舉 App-v 4.6 安裝根目錄下的檔案。

**技術詳細資料：** App-v 5.1 套件轉換器將在 Filesystem 元素的 FilesystemMetadata.xml 檔案中儲存 App-V 4.6 安裝根資料夾和短資料夾名稱。 當 App-v 5.1 用戶端建立虛擬流程時，它會將 App-v 4.6 安裝根的要求對應至虛擬檔案系統根目錄。

**開始使用**

1.  在您的環境中的電腦上安裝 app-v 排序器。 如需如何安裝排序器的詳細資訊，請參閱[如何安裝排序](how-to-install-the-sequencer-51beta-gb18030.md)器。

2.  

    可使用下列 Cmdlet：

    -   Test-AppvLegacyPackage –此 Cmdlet 專用來檢查套件。 它會傳回有關套件任何失敗的資訊，例如缺少**的 sft**檔案、不正確來源、 **osd**檔案錯誤，或套件版本無效。 這個 Cmdlet 不會分析**sft**檔案或執行任何深度驗證。 如需此 Cmdlet 之選項和基本功能的相關資訊，請使用 PowerShell cmdline 輸入 `Test-AppvLegacyPackage -?` 。

    -   ConvertFrom-AppvLegacyPackage –若要轉換現有的套件，請輸入 `ConvertFrom-AppvLegacyPackage c:\contentStore c:\convertedPackages` 。 在這個命令中，會 `c:\contentStore` 代表現有套件的位置，也 `c:\convertedPackages` 就是將儲存產生的 app-v 5.1 虛擬應用程式套件檔案的輸出目錄。 根據預設，如果您沒有指定新名稱，舊的套件名稱將會用於 App-v 5.1 檔案名。

        此外，套件轉換器會將應用程式的套件設定為串流式 App-v 套件，以優化 App-v 5.1 中套件的效能。  這比主要功能區塊更具性能，且完全下載套件。 [旗標**DownloadFullPackageOnFirstLaunch** ] 可讓您轉換套件，並將預設的套件設定為完全下載。

        **注意**  
        在您指定輸出目錄之前，您必須先建立輸出目錄。



~~~
**Advanced Conversion Tips**

-   Piping - PowerShell supports piping. Piping allows you to call `dir c:\contentStore\myPackage | Test-AppvLegacyPackage`. In this example, the directory object that represents `myPackage` will be given as input to the `Test-AppvLegacyPackage` command and bound to the `-Source` parameter. Piping like this is especially useful when you want to batch commands together; for example, `dir .\ | Test-AppvLegacyPackage | ConvertFrom-AppvLegacyAppvPackage -Target .\ConvertedPackages`. This piped command would test the packages and then pass those objects on to actually be converted. You can also apply a filter on packages without errors or only specify a directory which contains an **.sprj** file or pipe them to another cmdlet that adds the filtered package to the server or publishes them to the App-V 5.1 client.

-   Batching - The PowerShell command enables batching. More specifically, the cmdlets support taking a string\[\] object for the `-Source` parameter which represents a list of directory paths. This allows you to enter `$packages = dir c:\contentStore` and then call `ConvertFrom-AppvLegacyAppvPackage-Source $packages -Target c:\ConvertedPackages` or to use piping and call `dir c:\ContentStore | ConvertFrom-AppvLegacyAppvPackage -Target C:\ConvertedPackages`.

-   Other functionality - PowerShell has other built-in functionality for features such as aliases, piping, lazy-binding, .NET object, and many others. All of these are usable in PowerShell and can help you create advanced scenarios for the Package Converter.

**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 相關主題


[App-V 5.1 作業](operations-for-app-v-51.md)









