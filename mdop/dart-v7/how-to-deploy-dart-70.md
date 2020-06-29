---
title: 如何部署 DaRT 7.0
description: 如何部署 DaRT 7.0
author: dansimp
ms.assetid: 30522441-40cb-4eca-99b4-dff758f5c647
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2059b64e5f3ae7af8926bc00e5965598ede4288
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800246"
---
# <span data-ttu-id="cc7f1-103">如何部署 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="cc7f1-103">How to Deploy DaRT 7.0</span></span>


<span data-ttu-id="cc7f1-104">本主題提供在您的環境中部署 Microsoft Diagnostics 與修復工具集（DaRT）7的指示。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-104">This topic provides instructions to deploy Microsoft Diagnostics and Recovery Toolset (DaRT)7 in your environment.</span></span> <span data-ttu-id="cc7f1-105">本主題中的第一個程式假設您要在一部系統管理員電腦上安裝所有功能。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-105">The first procedure in this topic assumes that you are installing all functionality on one administrator computer.</span></span> <span data-ttu-id="cc7f1-106">如果您需要在多部電腦上部署或卸載 DaRT （例如，使用電子軟體發佈系統），可能會比較容易使用命令列安裝選項。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-106">When you need to deploy or uninstall DaRT on multiple computers, using an electronic software distribution system for example, it might be easier to use command line installation options.</span></span> <span data-ttu-id="cc7f1-107">這些選項是在本主題的第二個程式中定義的，提供可用命令列選項的範例用法。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-107">Those options are defined in the second procedure in this topic which provides example usage for the available command line options.</span></span>

<span data-ttu-id="cc7f1-108">**重要** 在您安裝 DaRT 前，請確定電腦符合[DaRT 7.0 支援](dart-70-supported-configurations-dart-7.md)的設定中所列的最低系統需求。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-108">**Important** Before you install DaRT, ensure that the computer meets the minimum system requirements listed in [DaRT 7.0 Supported Configurations](dart-70-supported-configurations-dart-7.md).</span></span>

 

**<span data-ttu-id="cc7f1-109">在管理員電腦上安裝 DaRT</span><span class="sxs-lookup"><span data-stu-id="cc7f1-109">To install DaRT on an administrator computer</span></span>**

1.  <span data-ttu-id="cc7f1-110">找出您在軟體下載中收到的 DaRT 安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-110">Locate the DaRT installation files that you received as part of your software download.</span></span>

2.  <span data-ttu-id="cc7f1-111">按兩下與您的系統需求相對應的 DaRT 安裝檔案（32位或64位）。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-111">Double-click the DaRT installation file that corresponds to your system requirements, either 32-bit or 64-bit.</span></span> <span data-ttu-id="cc7f1-112">DaRT 安裝檔案命名為 [ **MSDaRT70.msi**]。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-112">The DaRT installation file is named **MSDaRT70.msi**.</span></span>

3.  <span data-ttu-id="cc7f1-113">接受 Microsoft 軟體授權條款，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-113">Accept the Microsoft Software License Terms, and then click **Next**.</span></span>

4.  <span data-ttu-id="cc7f1-114">選取要安裝 DaRT 的目的地資料夾，選取是要為所有使用者安裝 DaRT，還是只針對目前的使用者安裝 DaRT，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-114">Select the destination folder for installing DaRT, select whether DaRT should be installed for all users or just the current user, and then click **Next**.</span></span>

5.  <span data-ttu-id="cc7f1-115">選取安裝應該是**一般**、**自訂**或**完成**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-115">Select whether the installation should be **Typical**, **Custom**, or **Complete**, and then click **Next**.</span></span>

    -   <span data-ttu-id="cc7f1-116">**一般**會安裝最常使用的工具。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-116">**Typical** installs the tools that are most frequently used.</span></span> <span data-ttu-id="cc7f1-117">建議針對大多數使用者使用這個方法。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-117">This method is recommended for most users.</span></span>

    -   <span data-ttu-id="cc7f1-118">[**自訂**] 可讓您選取已安裝的工具以及安裝位置。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-118">**Custom** lets you select the tools that are installed and where they will be installed.</span></span> <span data-ttu-id="cc7f1-119">對於高級使用者，尤其是當您在不同的技術支援電腦上安裝不同的 DaRT 工具時，尤其需要這麼做。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-119">This is recommended for advanced users, especially if you are installing different DaRT tools on different helpdesk computers.</span></span>

    -   <span data-ttu-id="cc7f1-120">**完整**安裝所有的 DaRT 工具，且需要最大的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-120">**Complete** installs all DaRT tools and requires the most disk space.</span></span>

    <span data-ttu-id="cc7f1-121">選取您的安裝方法之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-121">After you have selected your method of installation, click **Next**.</span></span>

6.  <span data-ttu-id="cc7f1-122">若要開始安裝，請按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-122">To start the installation, click **Install**.</span></span>

7.  <span data-ttu-id="cc7f1-123">成功完成安裝後，請按一下 **[完成**] 結束嚮導。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-123">After the installation is completed successfully, click **Finish** to exit the wizard.</span></span>

**<span data-ttu-id="cc7f1-124">在命令提示字元中安裝 DaRT</span><span class="sxs-lookup"><span data-stu-id="cc7f1-124">To install DaRT at the command prompt</span></span>**

1.  <span data-ttu-id="cc7f1-125">下列範例顯示如何安裝所有的 DaRT 功能。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-125">The following example shows how to install all DaRT functionality.</span></span>

    ``` syntax
    msiexec /i MSDaRT70.msi ADDLOCAL=CommonFiles,MSDaRTHelp,DaRTRecoveryImage,CrashAnalyzer,RemoteViewer 
    ```

2.  <span data-ttu-id="cc7f1-126">下列範例顯示如何只安裝**DaRT 復原影像嚮導**。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-126">The following example shows how to install only the **DaRT Recovery Image Wizard**.</span></span>

    ``` syntax
    msiexec /i MSDaRT70.msi ADDLOCAL=CommonFiles,MSDaRTHelp,DaRTRecoveryImage
    ```

3.  <span data-ttu-id="cc7f1-127">下列範例顯示如何只安裝 [損毀分析器] 和 [DaRT 遠端連線檢視器]。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-127">The following example shows how to install only the Crash Analyzer and the DaRT Remote Connection Viewer.</span></span>

    ``` syntax
    msiexec /i MSDaRT70.msi ADDLOCAL=CommonFiles,MSDaRTHelp,CrashAnalyzer,RemoteViewer 
    ```

4.  <span data-ttu-id="cc7f1-128">下列範例會建立 Windows 安裝程式的安裝記錄。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-128">The following example creates a setup log for the Windows Installer.</span></span> <span data-ttu-id="cc7f1-129">這對於調試很有用。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-129">This is valuable for debugging.</span></span>

    ``` syntax
    msiexec.exe /i MSDaRT70.msi /l*v log.txt 
    ```

<span data-ttu-id="cc7f1-130">**記事** 您可以將/qn 或/qb 新增至任何 DaRT 安裝命令提示字元選項，以執行緘默安裝。</span><span class="sxs-lookup"><span data-stu-id="cc7f1-130">**Note** You can add /qn or /qb to any of the DaRT installation command prompt options to perform a silent installation.</span></span>

 

## <span data-ttu-id="cc7f1-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="cc7f1-131">Related topics</span></span>


[<span data-ttu-id="cc7f1-132">部署 DaRT 7.0 到系統管理員電腦</span><span class="sxs-lookup"><span data-stu-id="cc7f1-132">Deploying DaRT 7.0 to Administrator Computers</span></span>](deploying-dart-70-to-administrator-computers-dart-7.md)

 

 





