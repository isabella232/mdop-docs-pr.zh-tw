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
# <span data-ttu-id="0153d-103">MED-V 修剪傳輸技術</span><span class="sxs-lookup"><span data-stu-id="0153d-103">MED-V Trim Transfer Technology</span></span>


## <a href="" id="bkmk-medvtrimtransfertechnology"></a>


<span data-ttu-id="0153d-104">MED-V 高級修剪傳送重復資料消除技術可加速在局域網或 WAN 上下載初始和更新的虛擬機器影像，從而減少將 MED-V 工作區虛擬機器傳輸給多位使用者所需的網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="0153d-104">The MED-V advanced Trim Transfer de-duplication technology accelerates the download of initial and updated virtual machine images over the LAN or WAN, thereby reducing the network bandwidth needed to transport a MED-V workspace virtual machine to multiple end users.</span></span>

<span data-ttu-id="0153d-105">這個突破性技術使用現有的本機資料來建立虛擬機器影像，利用這種情況，在許多情況下，大部分的虛擬機器（例如，系統和應用程式檔案）已經存在於最終使用者的磁片上。</span><span class="sxs-lookup"><span data-stu-id="0153d-105">This breakthrough technology uses existing local data to build the virtual machine image, leveraging the fact that in many cases, much of the virtual machine (for example, system and application files) already exists on the end user's disk.</span></span> <span data-ttu-id="0153d-106">例如，如果將包含 WindowsXP 的虛擬機器傳送給執行 WindowsXP 的本機複本的用戶端，MED-V 會自動從傳輸中移除多餘的 WindowsXP 元素。</span><span class="sxs-lookup"><span data-stu-id="0153d-106">For example, if a virtual machine containing WindowsXP is delivered to a client running a local copy of WindowsXP, MED-V will automatically remove the redundant WindowsXP elements from the transfer.</span></span> <span data-ttu-id="0153d-107">為了確保有效且功能正常的工作區，MED-V 用戶端加密會在使用本機資料之前驗證其完整性，保證本機資料區塊完全比所需虛擬機器影像中的相同。</span><span class="sxs-lookup"><span data-stu-id="0153d-107">To ensure a valid and functional workspace, the MED-V client cryptographically verifies the integrity of local data before it is utilized, guaranteeing that the local blocks of data are absolutely bit-by-bit identical to those in the desired virtual machine image.</span></span> <span data-ttu-id="0153d-108">不會使用不相符的區塊。</span><span class="sxs-lookup"><span data-stu-id="0153d-108">Blocks that do not match are not used.</span></span>

<span data-ttu-id="0153d-109">此程式的頻寬高效且透明，且在背景執行的傳輸是利用未使用的網路和 CPU 資源。</span><span class="sxs-lookup"><span data-stu-id="0153d-109">The process is bandwidth-efficient and transparent, and transfers run in the background, utilizing unused network and CPU resources.</span></span>

<span data-ttu-id="0153d-110">更新為新的影像版本時（例如，當系統管理員想要發佈新的應用程式或修補程式）時，只會下載已變更（"變化"）的元素，而不是整個虛擬機器，以大大減少所需的網路頻寬和傳送時間。</span><span class="sxs-lookup"><span data-stu-id="0153d-110">When updating to a new image version (for example, when administrators want to distribute a new application or patch), only the elements that have changed ("deltas") are downloaded, and not the entire virtual machine, significantly reducing the required network bandwidth and delivery time.</span></span>

<span data-ttu-id="0153d-111">您可以根據主機作業系統，在主機上設定要編制索引的資料夾（修剪傳輸通訊協定的一部分）。</span><span class="sxs-lookup"><span data-stu-id="0153d-111">You can configure which folders are indexed on the host as part of the Trim Transfer protocol, based on the host operating system.</span></span> <span data-ttu-id="0153d-112">這些設定是在*ClientSettings.xml*檔案中設定，可在 [ **Servers\\Configuration Server\\** ] 資料夾中找到。</span><span class="sxs-lookup"><span data-stu-id="0153d-112">These settings are configured in the *ClientSettings.xml* file, which can be found in the **Servers\\Configuration Server\\** folder.</span></span>

<span data-ttu-id="0153d-113">在套用新設定時，必須重新開機該服務。</span><span class="sxs-lookup"><span data-stu-id="0153d-113">When applying new settings, the service must be restarted.</span></span>

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

 

 





