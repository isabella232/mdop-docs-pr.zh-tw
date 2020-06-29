---
title: 如何設定指令碼動作
description: 如何設定指令碼動作
author: dansimp
ms.assetid: 367e28f1-d8c2-4845-a01b-2fff9128ccfd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2bfa264be447a0a8560e4af16ccaadc2ec1db3f6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800081"
---
# <span data-ttu-id="c626a-103">如何設定指令碼動作</span><span class="sxs-lookup"><span data-stu-id="c626a-103">How to Set Up Script Actions</span></span>


<span data-ttu-id="c626a-104">[腳本操作編輯器] 可讓系統管理員建立在 MED-V 工作區設定期間要執行的動作，以及定義其執行順序。</span><span class="sxs-lookup"><span data-stu-id="c626a-104">The script actions editor allows the administrator to create actions to be performed during MED-V workspace setup, as well as to define the order in which they are performed.</span></span>

<span data-ttu-id="c626a-105">以下是可新增至網域設定腳本的動作清單：</span><span class="sxs-lookup"><span data-stu-id="c626a-105">The following is a list of actions that can be added to the domain setup script:</span></span>

-   <span data-ttu-id="c626a-106">**重新開機 windows**-重新開機 windows。</span><span class="sxs-lookup"><span data-stu-id="c626a-106">**Restart Windows**—Restart Windows.</span></span>

-   <span data-ttu-id="c626a-107">**加入網域**-如果加入網域，請加入此動作並設定使用者名稱、密碼、完全限定功能變數名稱、NetBIOS 功能變數名稱及組織單位（選用）。</span><span class="sxs-lookup"><span data-stu-id="c626a-107">**Join Domain**—If joining a domain, include this action and configure the user name, password, fully qualified domain name, NetBIOS domain name, and organization unit (optional).</span></span>

-   <span data-ttu-id="c626a-108">**檢查連線性**-設定要連線的伺服器，並確認 med-v 工作區可以連線到網路資源（例如網域伺服器）。</span><span class="sxs-lookup"><span data-stu-id="c626a-108">**Check Connectivity**—Configure a server to connect to and verify that the MED-V workspace can connect to a network resource (such as the domain server).</span></span>

-   <span data-ttu-id="c626a-109">**命令列**-在 med-v 工作區中設定腳本，然後輸入包含腳本路徑及腳本引數的命令列。</span><span class="sxs-lookup"><span data-stu-id="c626a-109">**Command Line**—Configure a script in the MED-V workspace, and enter a command line that includes the path of the script and the script arguments.</span></span>

-   <span data-ttu-id="c626a-110">[**重新命名電腦**]：根據已定義的設定重新命名虛擬電腦電腦。</span><span class="sxs-lookup"><span data-stu-id="c626a-110">**Rename Computer**—Rename the virtual machine computer based on the defined settings.</span></span>

-   <span data-ttu-id="c626a-111">**停用自動登**入：停用 Windows 自動登入。</span><span class="sxs-lookup"><span data-stu-id="c626a-111">**Disable Auto-Logon**—Disable Windows Auto-Logon.</span></span> <span data-ttu-id="c626a-112">在將電腦新增至網域的腳本結尾，應該新增此動作。</span><span class="sxs-lookup"><span data-stu-id="c626a-112">This action should be added at the end of scripts that add the computer to the domain.</span></span>

## <a href="" id="how-to-set-up-script-actions-"></a><span data-ttu-id="c626a-113">如何設定指令碼動作</span><span class="sxs-lookup"><span data-stu-id="c626a-113">How to Set Up Script Actions</span></span>


**<span data-ttu-id="c626a-114">設定腳本動作</span><span class="sxs-lookup"><span data-stu-id="c626a-114">To set up script actions</span></span>**

1.  <span data-ttu-id="c626a-115">在 [ **VM 設定**] 索引標籤上，按一下 [**腳本編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="c626a-115">On the **VM Setup** tab, click **Script Editor**.</span></span>

2.  <span data-ttu-id="c626a-116">在 [**腳本動作**] 對話方塊中，按一下 [**新增**]，然後在子功能表上，按一下所要的動作。</span><span class="sxs-lookup"><span data-stu-id="c626a-116">In the **Script Actions** dialog box, click **Add**, and on the submenu, click the desired actions.</span></span>

3.  <span data-ttu-id="c626a-117">如下表所述設定動作。</span><span class="sxs-lookup"><span data-stu-id="c626a-117">Configure the actions as described in the following tables.</span></span>

    <span data-ttu-id="c626a-118">**記事** 
    [ **VM 設定**] 索引標籤中的 [**重新命名電腦**] 已設定。如需詳細資訊，請參閱[如何設定 VM 電腦名稱稱模式屬性](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)。</span><span class="sxs-lookup"><span data-stu-id="c626a-118">**Note**
**Rename Computer** is configured in the **VM Settings** tab. For more information, see [How to Configure VM Computer Name Pattern Properties](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md).</span></span>

     

~~~
**Note**  
To rename a computer, Windows must be restarted. It is recommended to add a Restart Windows action following a Rename Computer action.
~~~



4. <span data-ttu-id="c626a-119">選取動作，然後按一下 [**向上**] 或 [**向下**] 來設定動作順序。</span><span class="sxs-lookup"><span data-stu-id="c626a-119">Set the order of the actions by selecting an action and clicking **Up** or **Down**.</span></span>

5. <span data-ttu-id="c626a-120">按一下 **\[確定\]**。</span><span class="sxs-lookup"><span data-stu-id="c626a-120">Click **OK**.</span></span>

**<span data-ttu-id="c626a-121">注意</span><span class="sxs-lookup"><span data-stu-id="c626a-121">Note</span></span>**  
<span data-ttu-id="c626a-122">執行 Join 網域腳本時，若要讓腳本正常運作，登入 MED-V 工作區虛擬機器的使用者必須擁有本機系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="c626a-122">When running the Join Domain script, for the script to work, the user logged into the MED-V workspace virtual machine must have local administrator rights.</span></span>



**<span data-ttu-id="c626a-123">注意</span><span class="sxs-lookup"><span data-stu-id="c626a-123">Note</span></span>**  
<span data-ttu-id="c626a-124">在執行停用自動登入腳本時，建議您在初始設定完成後停用用於自動登入的本機來賓帳戶。</span><span class="sxs-lookup"><span data-stu-id="c626a-124">When running the Disable Auto-Logon script, it is recommended to disable the local guest account used for the auto-logon once the initial setup is complete.</span></span>



### <a href="" id="bkmk-joindomainproperties"></a>

**<span data-ttu-id="c626a-125">加入網域屬性</span><span class="sxs-lookup"><span data-stu-id="c626a-125">Join Domain Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c626a-126">屬性</span><span class="sxs-lookup"><span data-stu-id="c626a-126">Property</span></span></th>
<th align="left"><span data-ttu-id="c626a-127">說明</span><span class="sxs-lookup"><span data-stu-id="c626a-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c626a-128">將 VM 加入網域時要使用的認證</span><span class="sxs-lookup"><span data-stu-id="c626a-128">Credentials to use when joining the VM to the domain</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-129">將 VM 加入網域時，請選取下列其中一個認證：</span><span class="sxs-lookup"><span data-stu-id="c626a-129">Select one of the following credentials to use when joining the VM to the domain:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="c626a-130">使用 MED-V 認證 </strong> -最終使用者認證。</span><span class="sxs-lookup"><span data-stu-id="c626a-130">Use MED-V credentials</strong>—The end-user credentials.</span></span></p></li>
<li><p><strong><span data-ttu-id="c626a-131">使用下列認證 </strong> —指定的認證; 在對應的欄位中輸入使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="c626a-131">Use the following credentials</strong>—The credentials specified; enter a user name and password in the corresponding fields.</span></span></p></li>
</ul>
<div class="alert">
<strong><span data-ttu-id="c626a-132">注意</span><span class="sxs-lookup"><span data-stu-id="c626a-132">Note</span></span></strong><br/><p><span data-ttu-id="c626a-133">所有的 MED-V 工作區使用者都能看到您輸入的認證。</span><span class="sxs-lookup"><span data-stu-id="c626a-133">The credentials you enter are visible to all MED-V workspace users.</span></span> <span data-ttu-id="c626a-134">建議您不要提供網域管理員認證。</span><span class="sxs-lookup"><span data-stu-id="c626a-134">It is not recommended to provide domain administrator credentials.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c626a-135">要加入的網域</span><span class="sxs-lookup"><span data-stu-id="c626a-135">Domain to join</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-136">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="c626a-136">Select one of the following:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="c626a-137">在啟動工作區時使用功能變數名稱 </strong> ，即在登入 med-v 用戶端時加入由最終使用者輸入的網域。</span><span class="sxs-lookup"><span data-stu-id="c626a-137">Use the domain name utilized in starting the Workspace</strong>—Join the domain entered by the end user when logging into the MED-V client.</span></span></p>
<p><span data-ttu-id="c626a-138">若要定義從 NetBIOS 到完全限定功能變數名稱的對應，請按一下 [ <strong> 全域網域對應表] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="c626a-138">To define the mapping from NetBIOS to fully qualified domain names, click <strong>Global domain mapping table</strong>.</span></span> <span data-ttu-id="c626a-139">在 [全域網域對應表] 中，按一下 [ <strong> 新增] </strong> ，輸入 <strong> NetBIOS 功能變數名稱 </strong> 及 <strong> 完整的功能變數名稱 </strong> ，然後按一下 <strong> [確定] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="c626a-139">In the global domain mapping table, click <strong>Add</strong>, enter a <strong>NetBIOS domain name</strong> and a <strong>Fully qualified domain name</strong>, and click <strong>OK</strong>.</span></span></p></li>
<li><p><strong><span data-ttu-id="c626a-140">使用下列功能變數名稱 </strong> —加入指定的網域; 在對應的欄位中輸入功能變數名稱和 NetBIOS 功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="c626a-140">Use the following domain name</strong>—Join the domain specified; enter a domain name and NetBIOS domain name in the corresponding fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c626a-141">組織單位</span><span class="sxs-lookup"><span data-stu-id="c626a-141">Organization Unit</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-142">您可以指定組織單位（OU），將電腦加入特定的 OU。</span><span class="sxs-lookup"><span data-stu-id="c626a-142">An organization unit (OU) may be specified to join the computer to a specific OU.</span></span> <span data-ttu-id="c626a-143">格式必須遵循 OU 辨識名稱： OU = &lt; 組織單位 &gt; 、 &lt; 網網域控制站 &gt; （例如，OU = QATest、DC = IL、DC = med-v、dc = com）。</span><span class="sxs-lookup"><span data-stu-id="c626a-143">The format must follow an OU distinguished name: OU=&lt;Organization Unit&gt;,&lt;Domain Controller&gt; (for example, OU=QATest, DC=il, DC=MED-V, DC=com).</span></span></p>
<div class="alert">
<strong><span data-ttu-id="c626a-144">警告</span><span class="sxs-lookup"><span data-stu-id="c626a-144">Warning</span></span></strong><br/><p><span data-ttu-id="c626a-145">僅支援單一階層 OU，如上述範例所示。</span><span class="sxs-lookup"><span data-stu-id="c626a-145">Only a single level OU is supported as is shown in the example above.</span></span></p>
</div>
<div>
 
</div></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-checkconnectivityproperties"></a>

**<span data-ttu-id="c626a-146">檢查連通性屬性</span><span class="sxs-lookup"><span data-stu-id="c626a-146">Check Connectivity Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c626a-147">屬性</span><span class="sxs-lookup"><span data-stu-id="c626a-147">Property</span></span></th>
<th align="left"><span data-ttu-id="c626a-148">說明</span><span class="sxs-lookup"><span data-stu-id="c626a-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c626a-149">IP 位址</span><span class="sxs-lookup"><span data-stu-id="c626a-149">IP Address</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-150">您要驗證連線之伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c626a-150">The IP Address of the server that you are verifying connection to.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c626a-151">連接埠</span><span class="sxs-lookup"><span data-stu-id="c626a-151">Port</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-152">您要驗證連線之伺服器的埠。</span><span class="sxs-lookup"><span data-stu-id="c626a-152">The port of the server that you are verifying connection to.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c626a-153">逾時</span><span class="sxs-lookup"><span data-stu-id="c626a-153">Timeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-154">超時前等候回應的秒數。</span><span class="sxs-lookup"><span data-stu-id="c626a-154">The number of seconds to wait for a response before timing out.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-commandlineproperties"></a>

**<span data-ttu-id="c626a-155">命令列屬性</span><span class="sxs-lookup"><span data-stu-id="c626a-155">Command-Line Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c626a-156">屬性</span><span class="sxs-lookup"><span data-stu-id="c626a-156">Property</span></span></th>
<th align="left"><span data-ttu-id="c626a-157">說明</span><span class="sxs-lookup"><span data-stu-id="c626a-157">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c626a-158">路徑</span><span class="sxs-lookup"><span data-stu-id="c626a-158">Path</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-159">命令列的路徑。</span><span class="sxs-lookup"><span data-stu-id="c626a-159">The path of the command line.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c626a-160">Arguments</span><span class="sxs-lookup"><span data-stu-id="c626a-160">Arguments</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-161">命令列引數。</span><span class="sxs-lookup"><span data-stu-id="c626a-161">Command-line arguments.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c626a-162">等待退出</span><span class="sxs-lookup"><span data-stu-id="c626a-162">Wait for exit</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-163">選取核取方塊以等待傳回，然後繼續執行腳本動作。</span><span class="sxs-lookup"><span data-stu-id="c626a-163">Select the check box to wait for a return before continuing with the script actions.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c626a-164">失敗的錯誤</span><span class="sxs-lookup"><span data-stu-id="c626a-164">Fail on error</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-165">如果返回的值不是指定的值，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c626a-165">Select this check box if the return is anything but the value specified.</span></span></p>
<p><span data-ttu-id="c626a-166">輸入會將命令指示為成功的值。</span><span class="sxs-lookup"><span data-stu-id="c626a-166">Enter the value that will indicate the command as a success.</span></span></p>
<p><span data-ttu-id="c626a-167">預設值： <strong> 0</span><span class="sxs-lookup"><span data-stu-id="c626a-167">Default: <strong>0</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c626a-168">只執行一次</span><span class="sxs-lookup"><span data-stu-id="c626a-168">Perform only once</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-169">選取此核取方塊，只執行命令列一次。</span><span class="sxs-lookup"><span data-stu-id="c626a-169">Select this check box to run the command line only once.</span></span> <span data-ttu-id="c626a-170">如果腳本失敗或已取消，就不會再執行此命令。</span><span class="sxs-lookup"><span data-stu-id="c626a-170">If the script fails or is canceled, this command will not be performed again.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c626a-171">這個命令列會在工作區中重新開機 Windows</span><span class="sxs-lookup"><span data-stu-id="c626a-171">This command line causes a restart of Windows in the Workspace</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-172">如果命令列在完成後導致重新開機，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c626a-172">Select this check box if the command line causes a restart after completion.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c626a-173">允許互動</span><span class="sxs-lookup"><span data-stu-id="c626a-173">Allow interaction</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-174">如果命令需要使用者互動，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c626a-174">Select this check box if the command will require user interaction.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c626a-175">進度訊息</span><span class="sxs-lookup"><span data-stu-id="c626a-175">Progress message</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-176">在執行命令時要顯示給使用者的訊息。</span><span class="sxs-lookup"><span data-stu-id="c626a-176">Message to be displayed to the user while the command is running.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c626a-177">失敗訊息</span><span class="sxs-lookup"><span data-stu-id="c626a-177">Failure message</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-178">如果命令失敗，要向使用者顯示的訊息。</span><span class="sxs-lookup"><span data-stu-id="c626a-178">Message to be displayed to the user if the command fails.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="c626a-179">設定命令列動作時，可以按照下表中的定義來使用幾個變數。</span><span class="sxs-lookup"><span data-stu-id="c626a-179">When configuring the command-line action, several variables can be used as defined in the following table.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c626a-180">參數</span><span class="sxs-lookup"><span data-stu-id="c626a-180">Parameter</span></span></th>
<th align="left"><span data-ttu-id="c626a-181">值</span><span class="sxs-lookup"><span data-stu-id="c626a-181">Value</span></span></th>
<th align="left"><span data-ttu-id="c626a-182">描述</span><span class="sxs-lookup"><span data-stu-id="c626a-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c626a-183">%MEDVUser%</span><span class="sxs-lookup"><span data-stu-id="c626a-183">%MEDVUser%</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-184">已驗證的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="c626a-184">An authenticated user name.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-185">MED-V 驗證的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="c626a-185">MED-V authenticated user name.</span></span> <span data-ttu-id="c626a-186">您可以在加入網域 VM 設定腳本中使用使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="c626a-186">The user name and password can be used in the join domain VM setup script.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c626a-187">%MEDVPassword%</span><span class="sxs-lookup"><span data-stu-id="c626a-187">%MEDVPassword%</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-188">已驗證的密碼。</span><span class="sxs-lookup"><span data-stu-id="c626a-188">An authenticated password.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-189">MED-V 驗證密碼。</span><span class="sxs-lookup"><span data-stu-id="c626a-189">MED-V authenticated password.</span></span> <span data-ttu-id="c626a-190">您可以在加入網域 VM 設定腳本中使用使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="c626a-190">The user name and password can be used in the join domain VM setup script.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c626a-191">%MEDVDomain%</span><span class="sxs-lookup"><span data-stu-id="c626a-191">%MEDVDomain%</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-192">已設定網域。</span><span class="sxs-lookup"><span data-stu-id="c626a-192">Configured domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-193">在 MED-V 驗證中設定的網域。</span><span class="sxs-lookup"><span data-stu-id="c626a-193">The domain configured in the MED-V authentication.</span></span> <span data-ttu-id="c626a-194">它可以在 VM 設定腳本上使用。</span><span class="sxs-lookup"><span data-stu-id="c626a-194">It can be used on the VM setup script.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c626a-195">%DesiredMachineName%</span><span class="sxs-lookup"><span data-stu-id="c626a-195">%DesiredMachineName%</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-196">[電腦名稱稱]。</span><span class="sxs-lookup"><span data-stu-id="c626a-196">Computer name.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c626a-197">管理應用程式中設定的唯一電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="c626a-197">The unique computer name configured in the management application.</span></span> <span data-ttu-id="c626a-198">您可以在 VM 設定腳本中使用它。</span><span class="sxs-lookup"><span data-stu-id="c626a-198">It can be used in the VM setup script.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="c626a-199">相關主題</span><span class="sxs-lookup"><span data-stu-id="c626a-199">Related topics</span></span>


[<span data-ttu-id="c626a-200">如何設定 MED-V 工作區的虛擬機器設定</span><span class="sxs-lookup"><span data-stu-id="c626a-200">How to Configure the Virtual Machine Setup for a MED-V Workspace</span></span>](how-to-configure-the-virtual-machine-setup-for-a-med-v-workspacemedvv2.md)

[<span data-ttu-id="c626a-201">如何設定 VM 電腦名稱模式內容</span><span class="sxs-lookup"><span data-stu-id="c626a-201">How to Configure VM Computer Name Pattern Properties</span></span>](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)

 

 





