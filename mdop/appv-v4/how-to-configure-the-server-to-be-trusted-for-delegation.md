---
title: 如何將伺服器設定成受信任可以委派
description: 如何將伺服器設定成受信任可以委派
author: dansimp
ms.assetid: d8d11588-17c0-4bcb-a7e6-86b5e4ba7e1c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7164b3046671853216b870d68e651fed4fd84695
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801541"
---
# <span data-ttu-id="04579-103">如何將伺服器設定成受信任可以委派</span><span class="sxs-lookup"><span data-stu-id="04579-103">How to Configure the Server to be Trusted for Delegation</span></span>


<span data-ttu-id="04579-104">當您安裝 Microsoft Application Virtualization （App-v）管理伺服器軟體時，您可以選擇使用分散式系統架構來安裝它。</span><span class="sxs-lookup"><span data-stu-id="04579-104">When you install the Microsoft Application Virtualization (App-V) Management Server software, you can choose to install it by using a distributed system architecture.</span></span> <span data-ttu-id="04579-105">如果您在不同的電腦上安裝主控台、管理 Web 服務和資料庫，您必須將網際網路資訊服務（IIS）伺服器設定為信任委派。</span><span class="sxs-lookup"><span data-stu-id="04579-105">If you install the console, the Management Web Service, and the database on different computers, you must configure the Internet Information Services (IIS) server to be trusted for delegation.</span></span> <span data-ttu-id="04579-106">這是必要的，因為管理 Web 服務會使用使用主機的 App-v 管理員認證，嘗試連線到 App-v 資料存放區。</span><span class="sxs-lookup"><span data-stu-id="04579-106">This is necessary because the Management Web Service will attempt to connect to the App-V data store by using the credentials of the App-V administrator who is using the console.</span></span> <span data-ttu-id="04579-107">安裝資料存放區的資料庫伺服器不會接受來自 IIS 伺服器的系統管理員認證，除非已將 IIS 伺服器設定為信任委派，且管理 Web 服務將無法連線到 App-v 資料儲存區。</span><span class="sxs-lookup"><span data-stu-id="04579-107">The database server on which the data store is installed will not accept the administrator’s credentials from the IIS server unless the IIS server is configured to be trusted for delegation, and so the Management Web Service will not be able to connect to the App-V data store.</span></span>

<span data-ttu-id="04579-108">**記事** 如果您在單一伺服器上安裝 App-v Management Server 軟體，並將資料存放區放在另一個伺服器上，則有一個情況是您仍必須將伺服器設定為信任委派，即使管理 Web 服務與管理主控台位於相同的伺服器上也一樣。</span><span class="sxs-lookup"><span data-stu-id="04579-108">**Note** If you install the App-V Management Server software on a single server and place the data store on a separate server, there is one situation in which you must still configure the server to be trusted for delegation even though the Management Web Service and Management Console are on the same server.</span></span> <span data-ttu-id="04579-109">如果您需要使用 [**使用替代認證**] 選項連線到主控台中的管理 Web 服務，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="04579-109">This situation occurs if you need to connect to the Management Web Service in the console by using the **Use Alternate Credentials** option.</span></span>

 

<span data-ttu-id="04579-110">您可以使用的委派類型，取決於您在 Active Directory 網域服務（新增）基礎結構中設定的網域功能層級。</span><span class="sxs-lookup"><span data-stu-id="04579-110">The type of delegation that you can use depends on the Domain Functional Level that you have configured in your Active Directory Domain Services (ADDS) infrastructure.</span></span> <span data-ttu-id="04579-111">下表列出可針對 App-v 的每個網域功能層級設定的委派類型。</span><span class="sxs-lookup"><span data-stu-id="04579-111">The following table lists the types of delegation that can be configured for each Domain Functional Level for App-V.</span></span> <span data-ttu-id="04579-112">表格後面的詳細指示。</span><span class="sxs-lookup"><span data-stu-id="04579-112">Detailed instructions follow the table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="04579-113">網域功能層級</span><span class="sxs-lookup"><span data-stu-id="04579-113">Domain Functional Level</span></span></th>
<th align="left"><span data-ttu-id="04579-114">提供委派層次</span><span class="sxs-lookup"><span data-stu-id="04579-114">Delegation Levels Available</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="04579-115">Windows 2000 原生</span><span class="sxs-lookup"><span data-stu-id="04579-115">Windows 2000 native</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="04579-116">無委派（預設）</span><span class="sxs-lookup"><span data-stu-id="04579-116">No delegation (default)</span></span></p></li>
<li><p><span data-ttu-id="04579-117">無限制委派</span><span class="sxs-lookup"><span data-stu-id="04579-117">Unconstrained delegation</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="04579-118">Windows Server 2003、Windows Server 2008 或 Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="04579-118">Windows Server 2003, Windows Server 2008, or Windows Server 2008 R2</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="04579-119">無委派（預設）</span><span class="sxs-lookup"><span data-stu-id="04579-119">No delegation (default)</span></span></p></li>
<li><p><span data-ttu-id="04579-120">無限制的委派¹</span><span class="sxs-lookup"><span data-stu-id="04579-120">Unconstrained delegation¹</span></span></p></li>
<li><p><span data-ttu-id="04579-121">受限制的委派（使用 Kerberos 專用通訊協定）</span><span class="sxs-lookup"><span data-stu-id="04579-121">Constrained delegation (Use Kerberos Only Protocols)</span></span></p></li>
<li><p><span data-ttu-id="04579-122">受限制的委派（使用任何驗證通訊協定）¹</span><span class="sxs-lookup"><span data-stu-id="04579-122">Constrained delegation (Use any authentication protocol) ¹</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="04579-123">¹不要使用。</span><span class="sxs-lookup"><span data-stu-id="04579-123">¹ Not recommended.</span></span>

## <span data-ttu-id="04579-124">若要在網域功能層級為 Windows 2000 原生時設定無限制的委派</span><span class="sxs-lookup"><span data-stu-id="04579-124">To configure unconstrained delegation when the Domain Functional Level is Windows 2000 native</span></span>


<span data-ttu-id="04579-125">在您的 Web 服務器網域的網網域控制站上，完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="04579-125">On the domain controller for your Web server’s domain, complete the following steps.</span></span>

****

1.  <span data-ttu-id="04579-126">按一下 [**開始**]、[系統**管理工具**]，然後按一下 [ **Active Directory 使用者和電腦**]。</span><span class="sxs-lookup"><span data-stu-id="04579-126">Click **Start**, **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

2.  <span data-ttu-id="04579-127">展開 [網域]，然後展開 [電腦] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="04579-127">Expand domain, and then expand the Computers folder.</span></span>

3.  <span data-ttu-id="04579-128">在右窗格中，以滑鼠右鍵按一下網頁伺服器的電腦名稱稱，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="04579-128">In the right pane, right-click the computer name for the Web server, and then click **Properties**.</span></span>

4.  <span data-ttu-id="04579-129">在 [**一般**] 索引標籤上，確認已選取 [**信任電腦以進行委派**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="04579-129">On the **General** tab, ensure that the **Trust computer for delegation** check box is selected.</span></span>

5.  <span data-ttu-id="04579-130">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="04579-130">Click **OK**.</span></span>

## <span data-ttu-id="04579-131">若要在網域功能層級為 Windows Server 2003、Windows Server 2008 或 Windows Server 2008 R2 時設定無限制的委派</span><span class="sxs-lookup"><span data-stu-id="04579-131">To configure unconstrained delegation when the Domain Functional Level is Windows Server 2003, Windows Server 2008, or Windows Server 2008 R2</span></span>


<span data-ttu-id="04579-132">在您的 Web 服務器網域的網網域控制站上，完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="04579-132">On the domain controller for your Web server’s domain, complete the following steps.</span></span>

****

1.  <span data-ttu-id="04579-133">按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **Active Directory 使用者和電腦**]。</span><span class="sxs-lookup"><span data-stu-id="04579-133">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

2.  <span data-ttu-id="04579-134">展開 [網域]，然後展開 [電腦] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="04579-134">Expand domain, and expand the Computers folder.</span></span>

3.  <span data-ttu-id="04579-135">在右窗格中，以滑鼠右鍵按一下網頁伺服器的電腦名稱稱，選取 [**屬性**]，然後按一下 [**委派**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="04579-135">In the right pane, right-click the computer name for the Web server, select **Properties**, and then click the **Delegation** tab.</span></span>

4.  <span data-ttu-id="04579-136">按一下以選取 **[信任此電腦以委派給任何服務（僅限 Kerberos）**]。</span><span class="sxs-lookup"><span data-stu-id="04579-136">Click to select **Trust this computer for delegation to any service (Kerberos only)**.</span></span>

5.  <span data-ttu-id="04579-137">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="04579-137">Click **OK**.</span></span>

## <span data-ttu-id="04579-138">若要在網域功能層級為 Windows Server 2003、Windows Server 2008 或 Windows Server 2008 R2 時設定受限制的委派</span><span class="sxs-lookup"><span data-stu-id="04579-138">To configure constrained delegation when the Domain Functional Level is Windows Server 2003, Windows Server 2008, or Windows Server 2008 R2</span></span>


<span data-ttu-id="04579-139">在您的 Web 服務器網域的網網域控制站上，完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="04579-139">On the domain controller for your Web server’s domain, complete the following steps.</span></span>

****

1.  <span data-ttu-id="04579-140">按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **Active Directory 使用者和電腦**]。</span><span class="sxs-lookup"><span data-stu-id="04579-140">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

2.  <span data-ttu-id="04579-141">展開 [網域]，然後展開 [電腦] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="04579-141">Expand domain, and then expand the Computers folder.</span></span>

3.  <span data-ttu-id="04579-142">在右窗格中，以滑鼠右鍵按一下網頁伺服器的電腦名稱稱，選取 [**屬性**]，然後按一下 [**委派**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="04579-142">In the right pane, right-click the computer name for the Web server, select **Properties**, and then click the **Delegation** tab.</span></span>

4.  <span data-ttu-id="04579-143">按一下以選取 [**信任此電腦只委派指定的服務**]。</span><span class="sxs-lookup"><span data-stu-id="04579-143">Click to select **Trust this computer for delegation to specified services only**.</span></span>

5.  <span data-ttu-id="04579-144">確定已選取 [**僅使用 Kerberos** ]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="04579-144">Ensure that **Use Kerberos only** is selected, and then click **OK**.</span></span>

6.  <span data-ttu-id="04579-145">按一下 [**新增**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="04579-145">Click the **Add** button.</span></span> <span data-ttu-id="04579-146">在 [**新增服務**] 對話方塊中，按一下 [**使用者或電腦**]，然後流覽至或輸入含有 app-v 資料存放區之 Microsoft SQL server 的名稱，然後從 IIS 接收使用者認證。</span><span class="sxs-lookup"><span data-stu-id="04579-146">In the **Add Services** dialog box, click **Users or Computers**, and then browse to or type the name of the Microsoft SQL server that has the App-V data store and is to receive the users credentials from IIS.</span></span> <span data-ttu-id="04579-147">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="04579-147">Click **OK**.</span></span>

7.  <span data-ttu-id="04579-148">在 [**可用的服務**] 清單中，選取列出埠號碼的 MSSQLSvc 服務，Microsoft SQL Server 會接受該埠編號（預設埠為1433）。</span><span class="sxs-lookup"><span data-stu-id="04579-148">In the **Available Services** list, select the MSSQLSvc service that lists port number on which the Microsoft SQL Server is accepting connections for the App-V database (the default port is 1433).</span></span> <span data-ttu-id="04579-149">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="04579-149">Click **OK**.</span></span>

### <span data-ttu-id="04579-150">針對受限制委派設定 IIS 7 的其他步驟</span><span class="sxs-lookup"><span data-stu-id="04579-150">Additional steps to configure IIS 7 for constrained delegation</span></span>

<span data-ttu-id="04579-151">如果您在 IIS 7 伺服器上執行管理 Web 服務，您必須完成下列步驟，才能將 IIS 7 *useAppPoolCredentials*變數設定為 True。</span><span class="sxs-lookup"><span data-stu-id="04579-151">If you are running the Management Web Service on an IIS 7 server, you must complete the following steps to set the IIS 7 *useAppPoolCredentials* variable to True.</span></span>

1.  <span data-ttu-id="04579-152">開啟提升許可權的命令提示字元視窗。</span><span class="sxs-lookup"><span data-stu-id="04579-152">Open an elevated Command Prompt window.</span></span> <span data-ttu-id="04579-153">若要開啟提升許可權的命令提示字元視窗，請按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**附件**]，以滑鼠右鍵按一下**命令提示**字元，然後按一下 [**以系統管理員**身分</span><span class="sxs-lookup"><span data-stu-id="04579-153">To open an elevated Command Prompt window, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="04579-154">流覽至%windir%\\system32\\inetsrv。</span><span class="sxs-lookup"><span data-stu-id="04579-154">Navigate to %windir%\\system32\\inetsrv.</span></span>

3.  <span data-ttu-id="04579-155">輸入**appcmd.exe 設定 config-section： system.webserver/security/authentication/windowsAuthentication-useAppPoolCredentials： true**，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="04579-155">Type **appcmd.exe set config -section:system.webServer/security/authentication/windowsAuthentication -useAppPoolCredentials:true**, and then press ENTER.</span></span>

 

 





