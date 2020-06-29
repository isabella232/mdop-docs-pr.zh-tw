---
title: 如何新增封裝
description: 如何新增封裝
author: dansimp
ms.assetid: 5407fdbe-e658-44f6-a9b8-a566b81dedce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c580d7d131017c52e278adda0208ffcb2e86ccf2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808732"
---
# <span data-ttu-id="9ef21-103">如何新增封裝</span><span class="sxs-lookup"><span data-stu-id="9ef21-103">How to Add a Package</span></span>


<span data-ttu-id="9ef21-104">您可以透過下列方式從應用程式虛擬化伺服器管理主控台新增套件：</span><span class="sxs-lookup"><span data-stu-id="9ef21-104">You can add a package from the Application Virtualization Server Management Console in the following ways:</span></span>

-   <span data-ttu-id="9ef21-105">匯入應用程式，這會在程式中自動建立套件。</span><span class="sxs-lookup"><span data-stu-id="9ef21-105">Import an application, which creates the package automatically in the process.</span></span>

-   <span data-ttu-id="9ef21-106">手動新增套件。</span><span class="sxs-lookup"><span data-stu-id="9ef21-106">Add a package manually.</span></span>

<span data-ttu-id="9ef21-107">建議您匯入應用程式，而不是手動新增。</span><span class="sxs-lookup"><span data-stu-id="9ef21-107">It is recommended that you import applications instead of adding them manually.</span></span> <span data-ttu-id="9ef21-108">如需有關匯入應用程式的詳細資訊，請參閱[如何匯入應用程式](how-to-import-an-applicationserver.md)。</span><span class="sxs-lookup"><span data-stu-id="9ef21-108">For more information about importing applications, see [How to Import an Application](how-to-import-an-applicationserver.md).</span></span>

**<span data-ttu-id="9ef21-109">手動新增套件</span><span class="sxs-lookup"><span data-stu-id="9ef21-109">To add a package manually</span></span>**

1.  <span data-ttu-id="9ef21-110">在應用程式虛擬化伺服器管理主控台中，以滑鼠右鍵按一下左窗格中的 [**套件**] 節點，然後選擇 [**新增套件**]。</span><span class="sxs-lookup"><span data-stu-id="9ef21-110">In the Application Virtualization Server Management Console, right-click the **Packages** node in the left pane and choose **New Package**.</span></span>

2.  <span data-ttu-id="9ef21-111">在 [**新增套件**] 對話方塊中，于 [**套件名稱**] 欄位中輸入名稱。</span><span class="sxs-lookup"><span data-stu-id="9ef21-111">In the **New Package** dialog box, type a name in the **Package Name** field.</span></span>

3.  <span data-ttu-id="9ef21-112">在 [封裝檔案] 欄位的 [**完整路徑**] 中流覽或輸入路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="9ef21-112">Browse for or type a path name in the **Full path for package file** field.</span></span> <span data-ttu-id="9ef21-113">這必須是 SFT 檔案。</span><span class="sxs-lookup"><span data-stu-id="9ef21-113">This must be an SFT file.</span></span>

    <span data-ttu-id="9ef21-114">**記事** 如果您流覽到 SFT 檔案，請以伺服器的靜態主機名稱或 IP 位址取代本機路徑（例如，C:\\program files Files\\User\ _Apps \\Virtual\ _App \ _Server \\content）。</span><span class="sxs-lookup"><span data-stu-id="9ef21-114">**Note** If you browse to the SFT file, replace the local path (such as C:\\Program Files\\User\_Apps\\Virtual\_App\_Server\\content) with the server's static host name or IP address.</span></span> <span data-ttu-id="9ef21-115">使用變數 *% SFT \ _SOFTGRIDSERVER%* 需要每用戶端電腦設定。</span><span class="sxs-lookup"><span data-stu-id="9ef21-115">Using the variable *%SFT\_SOFTGRIDSERVER%* requires per-client computer configuration.</span></span>

    <span data-ttu-id="9ef21-116">在參照虛擬應用程式伺服器的對話方塊中，您必須使用使用者可以存取的網路位置（例如伺服器的靜態主機名稱或 IP 位址）。</span><span class="sxs-lookup"><span data-stu-id="9ef21-116">In dialog boxes that refer to Virtual Application Servers, you must use a network location, such as the server's static host name or IP address, that your users can access.</span></span> <span data-ttu-id="9ef21-117">應用程式的開啟軟體描述項（OSD）檔案可以使用伺服器的靜態主機名稱或 IP 位址來取代預留位置變數 *% SFT \ _SOFTGRIDSERER%* 。</span><span class="sxs-lookup"><span data-stu-id="9ef21-117">The application's Open Software Descriptor (OSD) file can replace the placeholder variable *%SFT\_SOFTGRIDSERER%* with the server's static host name or IP address.</span></span> <span data-ttu-id="9ef21-118">如果您保留預留位置變數，就必須在每一個要存取該伺服器的用戶端電腦上設定這個變數。</span><span class="sxs-lookup"><span data-stu-id="9ef21-118">If you leave the placeholder variable, you must set this variable on each client computer that will access that server.</span></span> <span data-ttu-id="9ef21-119">在 SFT \ _SOFTGRIDSERVER 的每台電腦上設定使用者或系統變數。</span><span class="sxs-lookup"><span data-stu-id="9ef21-119">Set a User or System variable on each computer for SFT\_SOFTGRIDSERVER.</span></span> <span data-ttu-id="9ef21-120">變數值必須是伺服器的靜態主機名稱或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="9ef21-120">The variable value must be the server's static host name or IP address.</span></span> <span data-ttu-id="9ef21-121">如果您設定了變數，請結束用戶端會話、登出並返回 Microsoft Windows，然後在執行會話且已設定變數的每一部電腦上重新開機會話。</span><span class="sxs-lookup"><span data-stu-id="9ef21-121">If you set a variable, exit the Client session, log out of and back into Microsoft Windows, and then restart the session on each computer that had a session running and had the variable set.</span></span>

     

4.  <span data-ttu-id="9ef21-122">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="9ef21-122">Click **Next**.</span></span>

5.  <span data-ttu-id="9ef21-123">[**摘要**] 對話方塊會顯示檔案位置，並會提示您將檔案複製到該位置（如果您尚未這麼做的話）。</span><span class="sxs-lookup"><span data-stu-id="9ef21-123">The **Summary** dialog box shows the file location and prompts you to copy the file to the location if you have not already done so.</span></span> <span data-ttu-id="9ef21-124">驗證資訊之後，按一下 **[完成]** 。</span><span class="sxs-lookup"><span data-stu-id="9ef21-124">Click **Finish** after you have verified the information.</span></span>

    <span data-ttu-id="9ef21-125">**記事** 如果您要管理遠端伺服器上的應用程式，請在 [下一步] 對話方塊中，輸入相對於伺服器內容根目錄的檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="9ef21-125">**Note** If you are managing applications on a remote server, in the next dialog box, type only the path of the file relative to the server's content root.</span></span>

     

## <span data-ttu-id="9ef21-126">相關主題</span><span class="sxs-lookup"><span data-stu-id="9ef21-126">Related topics</span></span>


[<span data-ttu-id="9ef21-127">如何匯入應用程式</span><span class="sxs-lookup"><span data-stu-id="9ef21-127">How to Import an Application</span></span>](how-to-import-an-applicationserver.md)

[<span data-ttu-id="9ef21-128">如何在伺服器管理主控台中管理封裝</span><span class="sxs-lookup"><span data-stu-id="9ef21-128">How to Manage Packages in the Server Management Console</span></span>](how-to-manage-packages-in-the-server-management-console.md)

 

 





