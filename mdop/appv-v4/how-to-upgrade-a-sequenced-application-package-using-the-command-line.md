---
title: 如何使用命令列來升級循序應用程式封裝
description: 如何使用命令列來升級循序應用程式封裝
author: dansimp
ms.assetid: 682fac46-c71d-4731-831b-81bfd5032764
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: eade2ced43852419176f635918f0a6b7c3444aee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801037"
---
# <span data-ttu-id="b26b0-103">如何使用命令列來升級循序應用程式封裝</span><span class="sxs-lookup"><span data-stu-id="b26b0-103">How to Upgrade a Sequenced Application Package Using the Command Line</span></span>


<span data-ttu-id="b26b0-104">使用下列程式，使用命令列來升級虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="b26b0-104">Use the following procedure to upgrade a virtual application by using a command line.</span></span> <span data-ttu-id="b26b0-105">當您使用命令列升級現有的虛擬應用程式套件時，會刪除該版本的 sft 檔案的原始版本。</span><span class="sxs-lookup"><span data-stu-id="b26b0-105">When you upgrade an existing virtual application package by using the command line, the original version of the .sft file is deleted.</span></span> <span data-ttu-id="b26b0-106">您應該先備份關聯的 sft 檔案，然後再使用命令列升級套件。</span><span class="sxs-lookup"><span data-stu-id="b26b0-106">You should back up the associated .sft file before upgrading the package by using the command line.</span></span>

**<span data-ttu-id="b26b0-107">若要升級虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="b26b0-107">To upgrade a virtual application</span></span>**

1.  <span data-ttu-id="b26b0-108">在執行應用程式虛擬化（App-v） Sequencer 的電腦上，若要開啟命令提示字元，請選取 [**開始**]、[**執行**]，然後輸入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="b26b0-108">On the computer that is running the Application Virtualization (App-V) Sequencer, to open the command prompt, select **Start**, **Run**, and type **cmd**.</span></span> <span data-ttu-id="b26b0-109">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b26b0-109">Click **OK**.</span></span>

2.  <span data-ttu-id="b26b0-110">在命令提示字元中，指定安裝 App-v 排序器的位置。</span><span class="sxs-lookup"><span data-stu-id="b26b0-110">At the command prompt, specify the location where the App-V Sequencer is installed.</span></span> <span data-ttu-id="b26b0-111">例如，在命令提示字元中，您可以輸入下列內容： **cd C:\\program files Files\\Microsoft Application Virtualization 排序**器。</span><span class="sxs-lookup"><span data-stu-id="b26b0-111">For example, at the command prompt, you could type the following: **cd C:\\Program Files\\Microsoft Application Virtualization Sequencer**.</span></span>

3.  <span data-ttu-id="b26b0-112">在命令提示字元中，輸入下列命令，並使用您的值取代引號中的文字：</span><span class="sxs-lookup"><span data-stu-id="b26b0-112">At the command prompt, type the following command, replacing the text in quotation marks with your values:</span></span>

    `SFTSequencer /UPGRADE:"pathtosourceSPRJ" /INSTALLPACKAGE:"pathtoUpgradeInstaller" /DECODEPATH:"pathtodecodefolder" /OUTPUTFILE:"pathtodestinationSPRJ"`

    **<span data-ttu-id="b26b0-113">注意</span><span class="sxs-lookup"><span data-stu-id="b26b0-113">Note</span></span>**  
    <span data-ttu-id="b26b0-114">您可以根據您所升級之應用程式的複雜性，使用命令列來指定其他參數。</span><span class="sxs-lookup"><span data-stu-id="b26b0-114">You can specify additional parameters by using the command line, depending on the complexity of the application you are upgrading.</span></span> <span data-ttu-id="b26b0-115">如需可與 App-v 排序器搭配使用的完整參數清單，請參閱[命令列參數](command-line-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="b26b0-115">For a complete list of parameters that are available for use with the App-V Sequencer, see [Command-Line Parameters](command-line-parameters.md).</span></span>



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



4. <span data-ttu-id="b26b0-116">按**enter**。</span><span class="sxs-lookup"><span data-stu-id="b26b0-116">Press **Enter**.</span></span>

## <span data-ttu-id="b26b0-117">相關主題</span><span class="sxs-lookup"><span data-stu-id="b26b0-117">Related topics</span></span>


[<span data-ttu-id="b26b0-118">如何使用命令列管理虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="b26b0-118">How to Manage Virtual Applications Using the Command Line</span></span>](how-to-manage-virtual-applications-using-the-command-line.md)









