---
title: 如何使用命令列升級虛擬應用程式
description: 如何使用命令列升級虛擬應用程式
author: dansimp
ms.assetid: 83c97767-6ea1-42aa-b411-ccc9fa61cf81
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8612deb31a1692dd85cfee88ca4b18cbc5ac2ab2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801026"
---
# <span data-ttu-id="4c990-103">如何使用命令列升級虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="4c990-103">How to Upgrade a Virtual Application by Using the Command Line</span></span>


<span data-ttu-id="4c990-104">使用下列程式，使用命令列來升級虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="4c990-104">Use the following procedure to upgrade a virtual application by using a command line.</span></span>

**<span data-ttu-id="4c990-105">若要升級虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="4c990-105">To upgrade a virtual application</span></span>**

1.  <span data-ttu-id="4c990-106">在執行應用程式虛擬化（App-v） Sequencer 的電腦上，若要開啟命令提示字元，請選取 [**開始**]、[**執行**]，然後輸入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="4c990-106">On the computer that is running the Application Virtualization (App-V) Sequencer, to open the command prompt, select **Start**, **Run**, and type **cmd**.</span></span> <span data-ttu-id="4c990-107">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4c990-107">Click **OK**.</span></span>

2.  <span data-ttu-id="4c990-108">在命令提示字元中，指定安裝 App-v 排序器的位置。</span><span class="sxs-lookup"><span data-stu-id="4c990-108">At the command prompt, specify the location where the App-V Sequencer is installed.</span></span> <span data-ttu-id="4c990-109">例如，在命令提示字元中，您可以輸入下列內容： **cd C:\\program files Files\\Microsoft Application Virtualization 排序**器。</span><span class="sxs-lookup"><span data-stu-id="4c990-109">For example, at the command prompt, you could type the following: **cd C:\\Program Files\\Microsoft Application Virtualization Sequencer**.</span></span>

3.  <span data-ttu-id="4c990-110">在命令提示字元中，輸入下列命令，並使用您的值取代引號中的文字：</span><span class="sxs-lookup"><span data-stu-id="4c990-110">At the command prompt, type the following command, replacing the text in quotation marks with your values:</span></span>

    `SFTSequencer /UPGRADE:"pathtosourceSPRJ" /INSTALLPACKAGE:"pathtoUpgradeInstaller" /DECODEPATH:"pathtodecodefolder" /OUTPUTFILE:"pathtodestinationSPRJ"`

    **<span data-ttu-id="4c990-111">注意</span><span class="sxs-lookup"><span data-stu-id="4c990-111">Note</span></span>**  
    <span data-ttu-id="4c990-112">您可以根據您所升級之應用程式的複雜性，使用命令列來指定其他參數。</span><span class="sxs-lookup"><span data-stu-id="4c990-112">You can specify additional parameters by using the command line, depending on the complexity of the application you are upgrading.</span></span> <span data-ttu-id="4c990-113">如需可與 App-v 排序器搭配使用的完整參數清單，請參閱[Sequencer 命令列參數](sequencer-command-line-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="4c990-113">For a complete list of parameters that are available for use with the App-V Sequencer, see [Sequencer Command-Line Parameters](sequencer-command-line-parameters.md).</span></span>



~~~
Use the value descriptions in the following table to help you determine the actual text you will use in the preceding command.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Value</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><em>pathtosourceSPRJ</em></p></td>
<td align="left"><p>Specifies the directory location of the virtual application to be upgraded.</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>pathtoUpgradeInstaller</em></p></td>
<td align="left"><p>Specifies the Windows Installer or a batch file that will be used to install an upgrade to the application.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>pathtodecodefolder</em></p></td>
<td align="left"><p>Specify the directory in which to unpack the SFT file.</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>pathtodestinationSPRJ</em></p></td>
<td align="left"><p>Specifies the path and file name of the SPRJ file that will be created.</p></td>
</tr>
</tbody>
</table>
~~~



4. <span data-ttu-id="4c990-114">按**enter**。</span><span class="sxs-lookup"><span data-stu-id="4c990-114">Press **Enter**.</span></span>

## <span data-ttu-id="4c990-115">相關主題</span><span class="sxs-lookup"><span data-stu-id="4c990-115">Related topics</span></span>


[<span data-ttu-id="4c990-116">如何使用 App-v 排序器建立或升級虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="4c990-116">How to Create or Upgrade Virtual Applications Using the App-V Sequencer</span></span>](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)

[<span data-ttu-id="4c990-117">排序器命令列錯誤碼</span><span class="sxs-lookup"><span data-stu-id="4c990-117">Sequencer Command-Line Error Codes</span></span>](sequencer-command-line-error-codes.md)

[<span data-ttu-id="4c990-118">排序器命令列參數</span><span class="sxs-lookup"><span data-stu-id="4c990-118">Sequencer Command-Line Parameters</span></span>](sequencer-command-line-parameters.md)









