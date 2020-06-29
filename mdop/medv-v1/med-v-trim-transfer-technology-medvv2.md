---
title: MED-V 修剪傳輸技術
description: MED-V 修剪傳輸技術
author: dansimp
ms.assetid: 2744e855-a486-4028-9606-f0084794ec65
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa11c8036954070bbff465a6ad78992fdd52f3a2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811606"
---
# MED-V 修剪傳輸技術


## <a href="" id="bkmk-medvtrimtransfertechnology"></a>


MED-V 高級修剪傳送重復資料消除技術可加速在局域網或 WAN 上下載初始和更新的虛擬機器影像，從而減少將 MED-V 工作區虛擬機器傳輸給多位使用者所需的網路頻寬。

這個突破性技術使用現有的本機資料來建立虛擬機器影像，利用這種情況，在許多情況下，大部分的虛擬機器（例如，系統和應用程式檔案）已經存在於最終使用者的磁片上。 例如，如果將包含 WindowsXP 的虛擬機器傳送給執行 WindowsXP 的本機複本的用戶端，MED-V 會自動從傳輸中移除多餘的 WindowsXP 元素。 為了確保有效且功能正常的工作區，MED-V 用戶端加密會在使用本機資料之前驗證其完整性，保證本機資料區塊完全比所需虛擬機器影像中的相同。 不會使用不相符的區塊。

此程式的頻寬高效且透明，且在背景執行的傳輸是利用未使用的網路和 CPU 資源。

更新為新的影像版本時（例如，當系統管理員想要發佈新的應用程式或修補程式）時，只會下載已變更（"變化"）的元素，而不是整個虛擬機器，以大大減少所需的網路頻寬和傳送時間。

您可以根據主機作業系統，在主機上設定要編制索引的資料夾（修剪傳輸通訊協定的一部分）。 這些設定是在*ClientSettings.xml*檔案中設定，可在 [ **Servers\\Configuration Server\\** ] 資料夾中找到。

在套用新設定時，必須重新開機該服務。

```xml
<HostIndexingXP type="System.String[]"> 
- <ArrayOfString>
<string>%WINDIR%</string> 
<string>%ProgramFiles%\Common Files</string> 
<string>%ProgramFiles%\Internet Explorer</string> 
<string>%ProgramFiles%\MED-V</string> 
<string>%ProgramFiles%\Microsoft Office</string> 
<string>%ProgramFiles%\Windows NT</string> 
<string>%ProgramFiles%\Messenger</string> 
<string>%ProgramFiles%\Adobe</string> 
<string>%ProgramFiles%\Outlook Express</string> 
</ArrayOfString> 
</HostIndexingXP> 
- <HostIndexingVista type="System.String[]"> 
- <ArrayOfString> 
<string>%WINDIR%\MSAgent</string> 
<string>%WINDIR%\winsxs</string> 
<string>%WINDIR%\system</string> 
<string>%WINDIR%\system32</string> 
<string>%WINDIR%\Microsoft.NET</string> 
<string>%WINDIR%\SoftwareDistribution</string> 
<string>%WINDIR%\L2Schemas</string> 
<string>%WINDIR%\Cursors</string> 
<string>%WINDIR%\Boot</string> 
<string>%WINDIR%\Help</string> 
<string>%WINDIR%\assembly</string> 
<string>%WINDIR%\inf</string> 
<string>%WINDIR%\fonts</string> 
<string>%WINDIR%\Installer</string> 
<string>%WINDIR%\IME</string> 
<string>%WINDIR%\Resources</string> 
<string>%WINDIR%\servicing</string> 
<string>%ProgramFiles%\MED-V</string> 
<string>%ProgramFiles%\Microsoft Office</string> 
</ArrayOfString> 
</HostIndexingVista>
```

 

 





