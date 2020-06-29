---
title: 如何使用 Setup.exe 安裝 App-V Client
description: 如何使用 Setup.exe 安裝 App-V Client
author: dansimp
ms.assetid: 106a5d97-b5f6-4a16-bf52-a84f4d558c74
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 60f79a2d2f74848ab121ba13cdf8c215088d54db
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801377"
---
# <span data-ttu-id="7c93f-103">如何使用 Setup.exe 安裝 App-V Client</span><span class="sxs-lookup"><span data-stu-id="7c93f-103">How to Install the App-V Client by Using Setup.exe</span></span>


<span data-ttu-id="7c93f-104">本主題描述如何使用 setup.exe 程式來安裝 App-v 用戶端。</span><span class="sxs-lookup"><span data-stu-id="7c93f-104">This topic describes how to install the App-V client by using the setup.exe program.</span></span> <span data-ttu-id="7c93f-105">當您使用 setup.exe 程式安裝 App-V 用戶端時，安裝程式會決定需要哪些必備軟體，並在安裝用戶端之前自動安裝。</span><span class="sxs-lookup"><span data-stu-id="7c93f-105">When you install the App-V client using the setup.exe program, the installer determines which prerequisite software is needed and installs it automatically before it installs the client.</span></span>

**<span data-ttu-id="7c93f-106">使用 Setup.exe 安裝應用程式虛擬化用戶端</span><span class="sxs-lookup"><span data-stu-id="7c93f-106">To install the Application Virtualization Client by Using Setup.exe</span></span>**

1.  <span data-ttu-id="7c93f-107">確認您是以在電腦上擁有系統管理員許可權的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="7c93f-107">Make sure you are logged on with an account that has administrator rights on the computer.</span></span>

2.  <span data-ttu-id="7c93f-108">開啟命令提示字元視窗，然後將目錄變更為內含安裝程式檔案的資料夾。</span><span class="sxs-lookup"><span data-stu-id="7c93f-108">Open a Command Prompt window, and then change the directory to the folder that contains the setup files.</span></span> <span data-ttu-id="7c93f-109">在安裝版本4.6 或更新版本的 App-v 用戶端時，您必須針對電腦的作業系統、32位或64位使用正確的安裝程式。</span><span class="sxs-lookup"><span data-stu-id="7c93f-109">When installing version4.6 or a later version of the App-V client, you must use the correct installer for the computer’s operating system, 32-bit or 64-bit.</span></span> <span data-ttu-id="7c93f-110">如果您使用的是錯誤的安裝程式，安裝將會失敗，並會顯示錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="7c93f-110">The installation will fail and an error message will be displayed if you use the wrong installer.</span></span>

3.  <span data-ttu-id="7c93f-111">在命令提示字元中輸入安裝命令字串。</span><span class="sxs-lookup"><span data-stu-id="7c93f-111">Enter the install command string at the command prompt.</span></span> <span data-ttu-id="7c93f-112">或者，您可以建立命令檔，然後從命令提示字元執行它。</span><span class="sxs-lookup"><span data-stu-id="7c93f-112">Alternatively, you can create a command file and run it from the command prompt.</span></span> <span data-ttu-id="7c93f-113">您也可以使用「VBScript」或「Windows PowerShell」等指令碼語言來執行命令。</span><span class="sxs-lookup"><span data-stu-id="7c93f-113">You can also use a scripting language such as VBScript or Windows PowerShell to run the command.</span></span>

4.  <span data-ttu-id="7c93f-114">下列命令列範例會說明如何將 setup.exe 用於許多選用的參數。</span><span class="sxs-lookup"><span data-stu-id="7c93f-114">The following command-line example shows how setup.exe can be used with a number of optional parameters.</span></span> <span data-ttu-id="7c93f-115">如需這些參數的詳細資訊，請參閱[應用程式虛擬化用戶端安裝程式命令列參數](application-virtualization-client-installer-command-line-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="7c93f-115">For more information about these parameters, see [Application Virtualization Client Installer Command-Line Parameters](application-virtualization-client-installer-command-line-parameters.md).</span></span>

    **<span data-ttu-id="7c93f-116">"setup.exe"/s/v "/qn SWICACHESIZE = \ \" 10240 \\ "SWIPUBSVRDISPLAY = \\" = \ "HTTP SWIPUBSVRTYPE"/SECURE\\ = \ "SWIPUBSVRHOST" PRODSYS\\ = \\ "443 \\" SWIPUBSVRPATH = \ "/AppVirt/appsntype.xml \ [SWIPUBSVRREFRESH = \ \" on\\ "SWIGLOBALDATA = \ \" D:\\AppVirt\\Global\\ "SWIUSERDATA = \\" ^% LOCALAPPDATA ^%\\Windows\\Application 虛擬化 Client\\ "SWIFSDRIVE = \ \" Q\\ ""</span><span class="sxs-lookup"><span data-stu-id="7c93f-116">"setup.exe" /s /v"/qn SWICACHESIZE=\\"10240\\" SWIPUBSVRDISPLAY=\\"Production System\\" SWIPUBSVRTYPE=\\"HTTP /secure\\" SWIPUBSVRHOST=\\"PRODSYS\\" SWIPUBSVRPORT=\\"443\\" SWIPUBSVRPATH=\\"/AppVirt/appsntype.xml\\" SWIPUBSVRREFRESH=\\"on\\" SWIGLOBALDATA=\\"D:\\AppVirt\\Global\\" SWIUSERDATA=\\"^% LOCALAPPDATA ^%\\Windows\\Application Virtualization Client\\" SWIFSDRIVE=\\"Q\\""</span></span>**

    **<span data-ttu-id="7c93f-117">重要</span><span class="sxs-lookup"><span data-stu-id="7c93f-117">Important</span></span>**  
    -   <span data-ttu-id="7c93f-118">出現在 [**/v**] 區段中的引號必須被視為特殊字元，並以前面的 " **\\** " 輸入。</span><span class="sxs-lookup"><span data-stu-id="7c93f-118">The quotation marks that appear in the "**/v**" section must be treated as special characters and entered with a preceding "**\\**".</span></span> <span data-ttu-id="7c93f-119">只有在值包含空格時，才需要使用引號;不過，在一致性中，前面範例中的所有實例都會顯示為引號。</span><span class="sxs-lookup"><span data-stu-id="7c93f-119">The quotation marks are required only when the value contains a space; however, for consistency, all the instances in the preceding example are shown as having quotation marks.</span></span>

    -   <span data-ttu-id="7c93f-120">" **%** **% HomeDrive%**" 中的 "" 字元前面必須是 " **^** " 逸出字元。</span><span class="sxs-lookup"><span data-stu-id="7c93f-120">The "**%**" characters in "**%HomeDrive%**" must be preceded by the "**^**" escape character.</span></span> <span data-ttu-id="7c93f-121">否則，Windows 命令 shell 會將值設定為執行安裝的使用者。</span><span class="sxs-lookup"><span data-stu-id="7c93f-121">Otherwise, the Windows command shell sets the value to that of the user who is performing the installation.</span></span>

    -   <span data-ttu-id="7c93f-122">需要**InstallShield**開關 **/s**和 **/qn** ，才能讓它成為無訊息安裝。</span><span class="sxs-lookup"><span data-stu-id="7c93f-122">The **InstallShield** switches **/s** and **/qn** are needed to make this a silent install.</span></span> <span data-ttu-id="7c93f-123">**/Qn**開關必須跟在 **/v**開關之後，並以不含空格的引號字元分隔。</span><span class="sxs-lookup"><span data-stu-id="7c93f-123">The **/qn** switch must follow the **/v** switch, separated by only a quote character with no intervening spaces.</span></span>

    -   <span data-ttu-id="7c93f-124">**SWIGLOBALDATA**值中指定的資料夾必須已經存在。</span><span class="sxs-lookup"><span data-stu-id="7c93f-124">The folder specified in the **SWIGLOBALDATA** value must already exist.</span></span>

     

5.  <span data-ttu-id="7c93f-125">安裝完成後，建議您執行 Microsoft 更新掃描，以確保已安裝最新的更新。</span><span class="sxs-lookup"><span data-stu-id="7c93f-125">When the installation is complete, we recommend that you run a Microsoft Update scan to ensure the latest updates are installed.</span></span>

## <span data-ttu-id="7c93f-126">相關主題</span><span class="sxs-lookup"><span data-stu-id="7c93f-126">Related topics</span></span>


[<span data-ttu-id="7c93f-127">如何使用命令列安裝用戶端</span><span class="sxs-lookup"><span data-stu-id="7c93f-127">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)

 

 





