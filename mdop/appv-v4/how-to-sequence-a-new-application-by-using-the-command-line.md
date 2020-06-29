---
title: 如何使用命令列來排列新應用程式的順序
description: 如何使用命令列來排列新應用程式的順序
author: dansimp
ms.assetid: c3b5c842-6a91-4d0a-9a22-c7b8d1aeb09a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ea7b1222dc00a0a4649cb342ac1ba41338484889
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801117"
---
# <span data-ttu-id="b49b4-103">如何使用命令列來排列新應用程式的順序</span><span class="sxs-lookup"><span data-stu-id="b49b4-103">How to Sequence a New Application by Using the Command Line</span></span>


<span data-ttu-id="b49b4-104">您可以使用命令列來排序新的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b49b4-104">You can use a command line to sequence a new application.</span></span> <span data-ttu-id="b49b4-105">當您必須建立大量的虛擬應用程式，或需要定期建立順序化的應用程式時，使用命令列很有用。</span><span class="sxs-lookup"><span data-stu-id="b49b4-105">Using a command line is useful when you have to create a large number of virtual applications or when you need to create sequenced applications on a recurring basis.</span></span>

**<span data-ttu-id="b49b4-106">重要</span><span class="sxs-lookup"><span data-stu-id="b49b4-106">Important</span></span>**  
<span data-ttu-id="b49b4-107">[命令列順序] 只允許預設排序。</span><span class="sxs-lookup"><span data-stu-id="b49b4-107">Command-line sequencing allows for default sequencing only.</span></span> <span data-ttu-id="b49b4-108">如果您需要變更您要排序之應用程式的預設安裝設定，您必須手動修改虛擬應用程式，或使用應用程式虛擬化（App-v） Sequencer 來更新虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="b49b4-108">If you need to change default installation settings for the application you are sequencing, you must either manually modify the virtual application or update the virtual application by using the Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="b49b4-109">如需使用 App-v 排序器更新虛擬應用程式的詳細資訊，請參閱[如何升級現有的虛擬應用程式](how-to-upgrade-an-existing-virtual-application.md)。</span><span class="sxs-lookup"><span data-stu-id="b49b4-109">For more information about updating a virtual application by using the App-V Sequencer, see [How to Upgrade an Existing Virtual Application](how-to-upgrade-an-existing-virtual-application.md).</span></span>



<span data-ttu-id="b49b4-110">使用下列程式，使用命令列來建立虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="b49b4-110">Use the following procedure to create a virtual application by using the command line.</span></span>

**<span data-ttu-id="b49b4-111">使用命令列來排序應用程式</span><span class="sxs-lookup"><span data-stu-id="b49b4-111">To sequence an application by using the command line</span></span>**

1.  <span data-ttu-id="b49b4-112">在執行 App-v 排序器的電腦上，選取 [**開始**]、[**執行**]，然後輸入**cmd**來開啟命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="b49b4-112">On the computer that is running the App-V Sequencer, open the command prompt by selecting **Start**, **Run**, and then type **cmd**.</span></span> <span data-ttu-id="b49b4-113">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b49b4-113">Click **OK**.</span></span>

2.  <span data-ttu-id="b49b4-114">使用命令提示字元指定 App V 排序器的安裝位置。</span><span class="sxs-lookup"><span data-stu-id="b49b4-114">Use the command prompt to specify the location of where the App-V Sequencer is installed.</span></span> <span data-ttu-id="b49b4-115">例如，在命令提示字元中，您可以輸入下列內容： **cd C:\\program files Files\\Microsoft Application Virtualization 排序**器。</span><span class="sxs-lookup"><span data-stu-id="b49b4-115">For example, at the command prompt, you could type the following: **cd C:\\Program Files\\Microsoft Application Virtualization Sequencer**.</span></span>

3.  <span data-ttu-id="b49b4-116">在命令提示字元中，輸入下列命令，並使用您的值取代引號中的文字：</span><span class="sxs-lookup"><span data-stu-id="b49b4-116">At the command prompt, type the following command, replacing the text in quotation marks with your values:</span></span>

    `SFTSequencer /INSTALLPACKAGE:"pathtoMSI" /INSTALLPATH:"pathtopackageroot" /OUTPUTFILE:"pathtodestinationSPRJ"`

    **<span data-ttu-id="b49b4-117">注意</span><span class="sxs-lookup"><span data-stu-id="b49b4-117">Note</span></span>**  
    <span data-ttu-id="b49b4-118">您可以使用命令列來指定其他參數，這取決於您所排序的應用程式的複雜性。</span><span class="sxs-lookup"><span data-stu-id="b49b4-118">You can specify additional parameters by using the command line, depending on the complexity of the application you are sequencing.</span></span> <span data-ttu-id="b49b4-119">如需可與 App-v 排序器搭配使用的完整參數清單，請參閱[Sequencer 命令列參數](sequencer-command-line-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="b49b4-119">For a complete list of parameters that are available for use with the App-V Sequencer, see [Sequencer Command-Line Parameters](sequencer-command-line-parameters.md).</span></span>



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
<td align="left"><p><em>pathtoMSI</em></p></td>
<td align="left"><p>Specifies the Windows Installer or a batch file that will be used to install an application so that it can be sequenced.</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>pathtopackageroot</em></p></td>
<td align="left"><p>Specify the package root directory.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>pathtodestinationSPRJ</em></p></td>
<td align="left"><p>Specifies the path and file name of the SPRJ file that will be created.</p></td>
</tr>
</tbody>
</table>
~~~



4. <span data-ttu-id="b49b4-120">按**enter**。</span><span class="sxs-lookup"><span data-stu-id="b49b4-120">Press **Enter**.</span></span>

## <span data-ttu-id="b49b4-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="b49b4-121">Related topics</span></span>


[<span data-ttu-id="b49b4-122">如何使用 App-v 排序器建立或升級虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="b49b4-122">How to Create or Upgrade Virtual Applications Using the App-V Sequencer</span></span>](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)

[<span data-ttu-id="b49b4-123">排序器命令列錯誤碼</span><span class="sxs-lookup"><span data-stu-id="b49b4-123">Sequencer Command-Line Error Codes</span></span>](sequencer-command-line-error-codes.md)

[<span data-ttu-id="b49b4-124">排序器命令列參數</span><span class="sxs-lookup"><span data-stu-id="b49b4-124">Sequencer Command-Line Parameters</span></span>](sequencer-command-line-parameters.md)









