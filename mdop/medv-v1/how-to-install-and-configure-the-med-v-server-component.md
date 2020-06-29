---
title: 如何安裝和設定 MED-V 伺服器元件
description: 如何安裝和設定 MED-V 伺服器元件
author: dansimp
ms.assetid: 2d3c5b15-df2c-4ab6-bf78-f47ef8ae7418
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4fb0cc5c9ffe76e987e316d0285f172dd0b76578
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812080"
---
# <span data-ttu-id="e4058-103">如何安裝和設定 MED-V 伺服器元件</span><span class="sxs-lookup"><span data-stu-id="e4058-103">How to Install and Configure the MED-V Server Component</span></span>


<span data-ttu-id="e4058-104">本節說明如何[安裝](#bkmk-howtoinstallthemedvserver)和[設定](#bkmk-howtoconfigurethemedvserver)med-v 伺服器。</span><span class="sxs-lookup"><span data-stu-id="e4058-104">This section explains how to [install](#bkmk-howtoinstallthemedvserver) and [configure](#bkmk-howtoconfigurethemedvserver) the MED-V server.</span></span>

## <a href="" id="bkmk-howtoinstallthemedvserver"></a><span data-ttu-id="e4058-105">如何安裝 MED-V 伺服器</span><span class="sxs-lookup"><span data-stu-id="e4058-105">How to Install the MED-V Server</span></span>


**<span data-ttu-id="e4058-106">若要安裝 MED-V 伺服器</span><span class="sxs-lookup"><span data-stu-id="e4058-106">To install the MED-V server</span></span>**

1.  <span data-ttu-id="e4058-107">安裝 MED-V Server .msi 封裝。</span><span class="sxs-lookup"><span data-stu-id="e4058-107">Install the MED-V Server .msi package.</span></span>

    <span data-ttu-id="e4058-108">會呼叫 MED-V Server .msi 封裝*MED-V\_Server\_x.msi*，其中 x 是版本號碼。</span><span class="sxs-lookup"><span data-stu-id="e4058-108">The MED-V Server .msi package is called *MED-V\_Server\_x.msi*, where x is the version number.</span></span>

    <span data-ttu-id="e4058-109">例如， *MED-V\_Server\_1.0.65.msi*。</span><span class="sxs-lookup"><span data-stu-id="e4058-109">For example, *MED-V\_Server\_1.0.65.msi*.</span></span>

2.  <span data-ttu-id="e4058-110">出現**InstallShield 嚮導歡迎**畫面時，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e4058-110">When the **InstallShield Wizard Welcome** screen appears, click **Next**.</span></span>

3.  <span data-ttu-id="e4058-111">在 [**授權合約**] 畫面上，閱讀 [授權合約]，按一下 **[我接受授權合約中的條款**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e4058-111">On the **License Agreement** screen, read the license agreement, click **I accept the terms in the license agreement**, and then click **Next**.</span></span>

    <span data-ttu-id="e4058-112">[**目的地資料夾**] 畫面隨即出現，並顯示預設安裝資料夾。</span><span class="sxs-lookup"><span data-stu-id="e4058-112">The **Destination Folder** screen appears, with the default installation folder displayed.</span></span>

    <span data-ttu-id="e4058-113">預設安裝資料夾為 *%Systemdrive%\\Program Files\\Microsoft Enterprise Desktop Virtualization\\*。</span><span class="sxs-lookup"><span data-stu-id="e4058-113">The default installation folder is *%systemdrive%\\Program Files\\Microsoft Enterprise Desktop Virtualization\\*.</span></span>

    -   <span data-ttu-id="e4058-114">若要變更要安裝 MED-V 的資料夾，請按一下 [**變更**]，然後流覽至現有的資料夾。</span><span class="sxs-lookup"><span data-stu-id="e4058-114">To change the folder where MED-V should be installed, click **Change** and browse to an existing folder.</span></span>

4.  <span data-ttu-id="e4058-115">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="e4058-115">Click **Next**.</span></span>

5.  <span data-ttu-id="e4058-116">在 [**準備好安裝程式**] 畫面中，按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="e4058-116">On the **Ready to Install the Program** screen, click **Install**.</span></span>

    <span data-ttu-id="e4058-117">MED-V 伺服器安裝隨即啟動。</span><span class="sxs-lookup"><span data-stu-id="e4058-117">The MED-V server installation starts.</span></span> <span data-ttu-id="e4058-118">這可能需要幾分鐘的時間，而且螢幕可能不會顯示文字。</span><span class="sxs-lookup"><span data-stu-id="e4058-118">This can take several minutes, and the screen might not display text.</span></span> <span data-ttu-id="e4058-119">在安裝期間，會出現幾個進度畫面。</span><span class="sxs-lookup"><span data-stu-id="e4058-119">During installation, several progress screens appear.</span></span> <span data-ttu-id="e4058-120">如果出現訊息，請依照提供的指示進行。</span><span class="sxs-lookup"><span data-stu-id="e4058-120">If a message appears, follow the instructions provided.</span></span>

6.  <span data-ttu-id="e4058-121">當 [ **InstallShield 嚮導完成]** 畫面出現時，請按一下 **[完成**] 以完成嚮導。</span><span class="sxs-lookup"><span data-stu-id="e4058-121">When the **InstallShield Wizard Completed** screen appears, click **Finish** to complete the wizard.</span></span>

**<span data-ttu-id="e4058-122">注意</span><span class="sxs-lookup"><span data-stu-id="e4058-122">Note</span></span>**  
<span data-ttu-id="e4058-123">如果您是透過 Microsoft 遠端桌面安裝 MED-V 伺服器，請使用下列語法： **mstsc/admin**。確定您的 RDP 會話已定向至主機。</span><span class="sxs-lookup"><span data-stu-id="e4058-123">If you are installing the MED-V server via Microsoft Remote Desktop, use the following syntax: **mstsc/admin**. Ensure that your RDP session is directed to the console.</span></span>



## <a href="" id="bkmk-howtoconfigurethemedvserver"></a><span data-ttu-id="e4058-124">如何設定 MED-V 伺服器</span><span class="sxs-lookup"><span data-stu-id="e4058-124">How to Configure the MED-V Server</span></span>


<span data-ttu-id="e4058-125">下列伺服器設定可以設定：</span><span class="sxs-lookup"><span data-stu-id="e4058-125">The following server settings can be configured:</span></span>

-   [<span data-ttu-id="e4058-126">連線</span><span class="sxs-lookup"><span data-stu-id="e4058-126">Connections</span></span>](#bkmk-configuringconnections)

-   [<span data-ttu-id="e4058-127">Images</span><span class="sxs-lookup"><span data-stu-id="e4058-127">Images</span></span>](#bkmk-configuringimages)

-   [<span data-ttu-id="e4058-128">權限</span><span class="sxs-lookup"><span data-stu-id="e4058-128">Permissions</span></span>](#bkmk-configuringpermissions)

-   [<span data-ttu-id="e4058-129">報告</span><span class="sxs-lookup"><span data-stu-id="e4058-129">Reports</span></span>](#bkmk-configuringreports)

### <a href="" id="bkmk-configuringconnections"></a><span data-ttu-id="e4058-130">設定連接</span><span class="sxs-lookup"><span data-stu-id="e4058-130">Configuring Connections</span></span>

**<span data-ttu-id="e4058-131">若要設定連接</span><span class="sxs-lookup"><span data-stu-id="e4058-131">To configure connections</span></span>**

1.  <span data-ttu-id="e4058-132">在 Windows [開始] 功能表上，選取 [**所有程式] &gt; med-v-v &gt; Med-v Server Configuration Manager**。</span><span class="sxs-lookup"><span data-stu-id="e4058-132">On the Windows Start menu, select **All Programs &gt; MED-V &gt; MED-V Server Configuration Manager**.</span></span>

    **<span data-ttu-id="e4058-133">注意</span><span class="sxs-lookup"><span data-stu-id="e4058-133">Note</span></span>**  
    <span data-ttu-id="e4058-134">注意：如果您在伺服器安裝期間選取了 [**啟動 med-v-v Server Configuration Manager** ] 核取方塊，則在伺服器安裝完成後，med-v Server configuration manager 會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="e4058-134">Note: If you selected the **Launch MED-V Server Configuration Manager** check box during the server installation, the MED-V server configuration manager starts automatically after the server installation is complete.</span></span>



~~~
The MED-V Server Configuration Manager appears.
~~~

2. <span data-ttu-id="e4058-135">**在 [連線**] 索引標籤上，設定下列用戶端連線設定：</span><span class="sxs-lookup"><span data-stu-id="e4058-135">On the **Connections** tab, configure the following client connections settings:</span></span>

   -   <span data-ttu-id="e4058-136">**[啟用未加密的連線（HTTP），使用埠**]：選取此核取方塊，以使用指定的埠啟用未加密的連接。</span><span class="sxs-lookup"><span data-stu-id="e4058-136">**Enable unencrypted connections (http), using port**—Select this check box to enable unencrypted connections using a specified port.</span></span> <span data-ttu-id="e4058-137">在 [埠] 方塊中，輸入要接受未加密連線的伺服器埠（HTTP）。</span><span class="sxs-lookup"><span data-stu-id="e4058-137">In the port box, enter the server port on which to accept unencrypted connections (http).</span></span>

   -   <span data-ttu-id="e4058-138">**[啟用加密連線（HTTPs），使用埠**]：選取此核取方塊以啟用使用指定埠的加密連線。</span><span class="sxs-lookup"><span data-stu-id="e4058-138">**Enable encrypted connections (https), using port**—Select this check box to enable encrypted connections using a specified port.</span></span> <span data-ttu-id="e4058-139">在 [埠] 方塊中，輸入要接受加密連線的伺服器埠（HTTPs）。</span><span class="sxs-lookup"><span data-stu-id="e4058-139">In the port box, enter the server port on which to accept encrypted connections (https).</span></span>

       <span data-ttu-id="e4058-140">Https 是一個選用的設定，可以設定以確保 MED-V 伺服器與 MED-V 用戶端之間的安全事務。</span><span class="sxs-lookup"><span data-stu-id="e4058-140">Https is an optional configuration which can be set to ensure secure transactions between the MED-V server and MED-V clients.</span></span> <span data-ttu-id="e4058-141">若要設定 HTTPs，您必須執行下列程式：</span><span class="sxs-lookup"><span data-stu-id="e4058-141">To configure https, you must perform the following procedures:</span></span>

       -   <span data-ttu-id="e4058-142">在伺服器上設定證書。</span><span class="sxs-lookup"><span data-stu-id="e4058-142">Configure a certificate on the server.</span></span>

       -   <span data-ttu-id="e4058-143">將伺服器憑證與使用 netsh 指定的埠建立關聯。</span><span class="sxs-lookup"><span data-stu-id="e4058-143">Associate the server certificate with the port specified using netsh.</span></span> <span data-ttu-id="e4058-144">如需詳細資訊，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="e4058-144">For information, see the following:</span></span>

           -   [<span data-ttu-id="e4058-145">超文字傳輸通訊協定（HTTP）的 Netsh 命令</span><span class="sxs-lookup"><span data-stu-id="e4058-145">Netsh Commands for Hypertext Transfer Protocol (HTTP)</span></span>](https://go.microsoft.com/fwlink/?LinkId=183314)

           -   [<span data-ttu-id="e4058-146">操作方法：使用 SSL 憑證設定埠</span><span class="sxs-lookup"><span data-stu-id="e4058-146">How to: Configure a Port with an SSL Certificate</span></span>](https://go.microsoft.com/fwlink/?LinkID=183315)

           -   [<span data-ttu-id="e4058-147">操作方法：使用 SSL 憑證設定埠</span><span class="sxs-lookup"><span data-stu-id="e4058-147">How to: Configure a Port with an SSL Certificate</span></span>](https://msdn.microsoft.com/library/ms733791.aspx)

3. <span data-ttu-id="e4058-148">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4058-148">Click **OK**.</span></span>

### <a href="" id="bkmk-configuringimages"></a><span data-ttu-id="e4058-149">配置影像</span><span class="sxs-lookup"><span data-stu-id="e4058-149">Configuring Images</span></span>

**<span data-ttu-id="e4058-150">若要設定影像</span><span class="sxs-lookup"><span data-stu-id="e4058-150">To configure images</span></span>**

1.  <span data-ttu-id="e4058-151">按一下 [**影像**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e4058-151">Click the **Images** tab.</span></span>

2.  <span data-ttu-id="e4058-152">設定下列影像管理設定：</span><span class="sxs-lookup"><span data-stu-id="e4058-152">Configure the following image management settings:</span></span>

    -   <span data-ttu-id="e4058-153">**Vm 目錄**：虛擬機器目錄（儲存影像的目錄）。</span><span class="sxs-lookup"><span data-stu-id="e4058-153">**VMs Directory**—The virtual machine directory (the directory where the images are stored).</span></span> <span data-ttu-id="e4058-154">此欄位包含影像發佈伺服器上影像目錄的 UNC 路徑，該路徑應該可從 MED-V 伺服器存取。</span><span class="sxs-lookup"><span data-stu-id="e4058-154">This field contains a UNC path to the image directory on the image distribution server that should be accessible from the MED-V server.</span></span>

    -   <span data-ttu-id="e4058-155">**VM URL**-儲存影像的伺服器位置。</span><span class="sxs-lookup"><span data-stu-id="e4058-155">**VMs URL**—The location of the server where the images are stored.</span></span>

3.  <span data-ttu-id="e4058-156">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4058-156">Click **OK**.</span></span>

### <a href="" id="bkmk-configuringpermissions"></a><span data-ttu-id="e4058-157">設定許可權</span><span class="sxs-lookup"><span data-stu-id="e4058-157">Configuring Permissions</span></span>

**<span data-ttu-id="e4058-158">若要設定許可權</span><span class="sxs-lookup"><span data-stu-id="e4058-158">To configure permissions</span></span>**

1.  <span data-ttu-id="e4058-159">按一下 [**許可權**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e4058-159">Click the **Permissions** tab.</span></span>

2.  <span data-ttu-id="e4058-160">提供可以登入的所有使用者清單。</span><span class="sxs-lookup"><span data-stu-id="e4058-160">A list of all users who can log in is provided.</span></span> <span data-ttu-id="e4058-161">若要將讀取和寫入權限套用至使用者，請選取使用者旁邊的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e4058-161">To apply read and write permissions to a user, select the check box next to the user.</span></span> <span data-ttu-id="e4058-162">若要將唯讀許可權套用至使用者，請清除該核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e4058-162">To apply read-only permissions to a user, clear the check box.</span></span>

3.  <span data-ttu-id="e4058-163">若要新增網域使用者或群組，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="e4058-163">To add domain users or groups, click **Add**.</span></span>

    <span data-ttu-id="e4058-164">[**輸入使用者或組名**] 對話方塊隨即出現。</span><span class="sxs-lookup"><span data-stu-id="e4058-164">The **Enter User or Group names** dialog box appears.</span></span>

    1.  <span data-ttu-id="e4058-165">選取 [網域使用者] 或 [群組]，方法是執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="e4058-165">Select domain users or groups by doing one of the following:</span></span>

        -   <span data-ttu-id="e4058-166">在 [**輸入使用者或組名**] 欄位中，輸入網域中的使用者或群組，或以本機使用者或群組的形式存在於電腦上。</span><span class="sxs-lookup"><span data-stu-id="e4058-166">In the **Enter User or Group names** field, type a user or group that exists in the domain or exists as a local user or group on the computer.</span></span> <span data-ttu-id="e4058-167">然後按一下 [**檢查名稱**]，將它解析成完整的名稱。</span><span class="sxs-lookup"><span data-stu-id="e4058-167">Then click **Check Names** to resolve it to the full existent name.</span></span>

        -   <span data-ttu-id="e4058-168">按一下 [**尋找**] 以開啟 [標準**選取使用者或群組**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="e4058-168">Click **Find** to open the standard **Select Users or Groups** dialog box.</span></span> <span data-ttu-id="e4058-169">然後選取 [網域使用者] 或 [群組]。</span><span class="sxs-lookup"><span data-stu-id="e4058-169">Then select domain users or groups.</span></span>

    2.  <span data-ttu-id="e4058-170">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4058-170">Click **OK**.</span></span>

4.  <span data-ttu-id="e4058-171">若要移除網域使用者或群組，請選取使用者或群組，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="e4058-171">To remove domain users or groups, select a user or group and click **Remove**.</span></span>

5.  <span data-ttu-id="e4058-172">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4058-172">Click **OK**.</span></span>

### <a href="" id="bkmk-configuringreports"></a><span data-ttu-id="e4058-173">配置報表</span><span class="sxs-lookup"><span data-stu-id="e4058-173">Configuring Reports</span></span>

**<span data-ttu-id="e4058-174">若要設定報表</span><span class="sxs-lookup"><span data-stu-id="e4058-174">To configure reports</span></span>**

1.  <span data-ttu-id="e4058-175">按一下 [**報告**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e4058-175">Click the **Reports** tab.</span></span>

2.  <span data-ttu-id="e4058-176">若要支援報表，請選取 [**啟用報表**]。</span><span class="sxs-lookup"><span data-stu-id="e4058-176">To support reports, select **Enable reports**.</span></span>

3.  <span data-ttu-id="e4058-177">在 [**連接字串**] 方塊中，輸入 MSSQL 資料庫的連線字串。</span><span class="sxs-lookup"><span data-stu-id="e4058-177">In the **Connection String** box, enter a connection string for the MSSQL database.</span></span>

    -   <span data-ttu-id="e4058-178">在遠端伺服器上安裝 SQL Server 時，請使用下列連接字串：</span><span class="sxs-lookup"><span data-stu-id="e4058-178">When SQL Server is installed on a remote server, use the following connection string:</span></span>

        `Data Source=<ServerName>;Initial Catalog=<DBName>;uid=sa;pwd=<Password>;`

        **<span data-ttu-id="e4058-179">注意</span><span class="sxs-lookup"><span data-stu-id="e4058-179">Note</span></span>**  
        <span data-ttu-id="e4058-180">注意：若要連接至 SQL Express，請使用：</span><span class="sxs-lookup"><span data-stu-id="e4058-180">Note: To connect to SQL Express, use:</span></span> `Data Source=<ServerName>\sqlexpress.`



4.  <span data-ttu-id="e4058-181">若要建立資料庫，請按一下 [**建立資料庫**]。</span><span class="sxs-lookup"><span data-stu-id="e4058-181">To create the database, click **Create Database**.</span></span>

5.  <span data-ttu-id="e4058-182">若要測試連線，請按一下 [**測試**連線]。</span><span class="sxs-lookup"><span data-stu-id="e4058-182">To test the connection, click **Test Connection**.</span></span>

6.  <span data-ttu-id="e4058-183">若要設定資料庫清除選項，請按一下 [**清除選項**]。</span><span class="sxs-lookup"><span data-stu-id="e4058-183">To configure database clearing options, click **Clear Options**.</span></span>

    <span data-ttu-id="e4058-184">[**清除資料庫選項**] 對話方塊隨即出現。</span><span class="sxs-lookup"><span data-stu-id="e4058-184">The **Clear Database Options** dialog box appears.</span></span>

    1.  <span data-ttu-id="e4058-185">選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="e4058-185">Choose one of the following options:</span></span>

        -   <span data-ttu-id="e4058-186">**清除較舊的資料**：清除超過指定天數的所有資料。在 [數值] 方塊中，輸入天數。</span><span class="sxs-lookup"><span data-stu-id="e4058-186">**Clear data older than**—Clear all data older than the number of days specified; in the number box, enter a number of days.</span></span>

        -   <span data-ttu-id="e4058-187">**清除資料庫中的所有資料**—清除資料庫中所有現有的資料。</span><span class="sxs-lookup"><span data-stu-id="e4058-187">**Clear all data from database**—Clear all existent data in the database.</span></span>

        -   <span data-ttu-id="e4058-188">[**刪除資料庫**]：刪除資料庫。</span><span class="sxs-lookup"><span data-stu-id="e4058-188">**Drop database**—Delete the database.</span></span>

    2.  <span data-ttu-id="e4058-189">按一下 **[確定]** 以套用變更並關閉對話方塊。</span><span class="sxs-lookup"><span data-stu-id="e4058-189">Click **OK** to apply changes and close the dialog box.</span></span>

7.  <span data-ttu-id="e4058-190">按一下 **[確定]** 儲存變更，或按一下 [**取消**] 關閉對話方塊，不儲存變更。</span><span class="sxs-lookup"><span data-stu-id="e4058-190">Click **OK** to save the changes, or click **Cancel** to close the dialog box without saving changes.</span></span>

8.  <span data-ttu-id="e4058-191">如果出現提示，請重新開機 MED-V 伺服器服務，以將變更套用至網路設定。</span><span class="sxs-lookup"><span data-stu-id="e4058-191">If prompted, restart the MED-V server service to apply changes to the network settings.</span></span>

## <span data-ttu-id="e4058-192">相關主題</span><span class="sxs-lookup"><span data-stu-id="e4058-192">Related topics</span></span>


[<span data-ttu-id="e4058-193">支援的設定</span><span class="sxs-lookup"><span data-stu-id="e4058-193">Supported Configurations</span></span>](supported-configurationsmedv-orientation.md)

[<span data-ttu-id="e4058-194">設計 MED-V 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="e4058-194">Design the MED-V Server Infrastructure</span></span>](design-the-med-v-server-infrastructure.md)









