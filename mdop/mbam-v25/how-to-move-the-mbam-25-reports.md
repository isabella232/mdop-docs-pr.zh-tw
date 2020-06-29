---
title: 如何移動 MBAM 2.5 報告
description: 如何移動 MBAM 2.5 報告
author: dansimp
ms.assetid: c8223656-ca9d-41c8-94a3-64d07a6b99e9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1cdef260b4381671a1b9de66565ece0b70876200
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800082"
---
# <span data-ttu-id="6e4c3-103">如何移動 MBAM 2.5 報告</span><span class="sxs-lookup"><span data-stu-id="6e4c3-103">How to Move the MBAM 2.5 Reports</span></span>


<span data-ttu-id="6e4c3-104">使用這些程式將 [報表] 功能從一部電腦移到另一台電腦，也就是將 [報表] 功能從伺服器 A 移到伺服器 B。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-104">Use these procedures to move the Reports feature from one computer to another, that is, to move the Reports feature from Server A to Server B.</span></span>

<span data-ttu-id="6e4c3-105">移動報表功能的最高層步驟如下：</span><span class="sxs-lookup"><span data-stu-id="6e4c3-105">The high-level steps for moving the Reports feature are:</span></span>

1.  <span data-ttu-id="6e4c3-106">停止 MBAM 管理和監視網站的所有實例。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-106">Stop all instances of the MBAM Administration and Monitoring Website.</span></span>

2.  <span data-ttu-id="6e4c3-107">在伺服器 B 上安裝 MBAM 2.5 Server 軟體，並在伺服器 B 上設定 [報告] 功能。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-107">Install the MBAM 2.5 Server software on Server B and configure the Reports feature on Server B.</span></span>

3.  <span data-ttu-id="6e4c3-108">更新 MBAM 管理和監視伺服器上的報表連線資料。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-108">Update the reports connection data on the MBAM Administration and Monitoring servers.</span></span>

4.  <span data-ttu-id="6e4c3-109">繼續 MBAM 管理和監視網站的實例。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-109">Resume the instance of the MBAM Administration and Monitoring Website.</span></span>

<span data-ttu-id="6e4c3-110">**記事** 若要執行本主題中的 Windows PowerShell 腳本範例，您必須更新 Windows PowerShell 執行原則，才能執行腳本。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-110">**Note** To run the example Windows PowerShell scripts in this topic, you must update the Windows PowerShell execution policy to enable scripts to be run.</span></span> <span data-ttu-id="6e4c3-111">請參閱執行[Windows PowerShell 腳本](https://technet.microsoft.com/library/ee176949.aspx)以取得相關指示。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-111">See [Running Windows PowerShell Scripts](https://technet.microsoft.com/library/ee176949.aspx) for instructions.</span></span>

 

**<span data-ttu-id="6e4c3-112">停止 MBAM 管理和監控網站</span><span class="sxs-lookup"><span data-stu-id="6e4c3-112">Stop the MBAM Administration and Monitoring Website</span></span>**

-   <span data-ttu-id="6e4c3-113">在執行管理和監視網站的伺服器上，使用 Internet Information Services （IIS）管理員主控台來停止管理和監控網站。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-113">On the server that is running the Administration and Monitoring Website, use the Internet Information Services (IIS) Manager console to stop the Administration and Monitoring Website.</span></span>

    <span data-ttu-id="6e4c3-114">若要自動化此程式，您可以使用 Windows PowerShell 輸入類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="6e4c3-114">To automate this procedure, you can use Windows PowerShell to enter a command that is similar to the following:</span></span>

    ``` syntax
    PS C:\> Stop-Website "Microsoft BitLocker Administration and Monitoring"
    ```

**<span data-ttu-id="6e4c3-115">在伺服器 B 上安裝 MBAM Server 軟體並執行 [MBAM 伺服器設定] 嚮導</span><span class="sxs-lookup"><span data-stu-id="6e4c3-115">Install MBAM Server software and run the MBAM Server Configuration wizard on Server B</span></span>**

1.  <span data-ttu-id="6e4c3-116">在伺服器 B 上安裝 MBAM Server 軟體。如需相關指示，請參閱[安裝 MBAM 2.5 Server 軟體](installing-the-mbam-25-server-software.md)。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-116">Install the MBAM Server software on Server B. For instructions, see [Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md).</span></span>

2.  <span data-ttu-id="6e4c3-117">在伺服器 B 上，啟動 [MBAM 伺服器設定] 嚮導，按一下 [新增**功能**]，然後只選取 [**報告**] 功能。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-117">On Server B, start the MBAM Server Configuration wizard, click **Add New Features**, and then select only the **Reports** feature.</span></span>

    <span data-ttu-id="6e4c3-118">或者，您也可以使用**Enable-MbamReport** Windows PowerShell Cmdlet 來設定報告。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-118">Alternatively, you can use the **Enable-MbamReport** Windows PowerShell cmdlet to configure the Reports.</span></span>

    <span data-ttu-id="6e4c3-119">如需如何設定報告的相關指示，請參閱[如何設定 MBAM 2.5 報告](how-to-configure-the-mbam-25-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-119">For instructions on how to configure the Reports, see [How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md).</span></span>

**<span data-ttu-id="6e4c3-120">更新管理和監視伺服器上的報表連線資料</span><span class="sxs-lookup"><span data-stu-id="6e4c3-120">Update the reports connection data on the Administration and Monitoring Server</span></span>**

1.  <span data-ttu-id="6e4c3-121">在執行 [報告] 功能的伺服器上，使用 [網際網路資訊服務（IIS）管理員] 主控台來更新報表 URL。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-121">On the server that is running the Reports feature, use the Internet Information Services (IIS) Manager console to update the Reports URL.</span></span>

2.  <span data-ttu-id="6e4c3-122">展開 [ **Microsoft BitLocker 管理及監視**]，然後選取 [**服務台**] 節點。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-122">Expand **Microsoft BitLocker Administration and Monitoring**, and then select the **HelpDesk** node.</span></span>

3.  <span data-ttu-id="6e4c3-123">在 [**功能] 視圖**的 [**管理**] 區段中，選取 [**配置編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-123">In the **Management** section of the **Features View**, select **Configuration Editor**.</span></span>

4.  <span data-ttu-id="6e4c3-124">在 [**節**] 欄位中，選取 [ **appSettings**]。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-124">In the **Section** field, select **appSettings**.</span></span>

5.  <span data-ttu-id="6e4c3-125">選取**集合**列，然後按一下窗格最右側的 [省略號] 按鈕 **（...）** 以開啟**集合編輯器**。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-125">Select the **Collection** row, and then click the "ellipses" button **(…)** at the far right of the pane to open the **Collection Editor**.</span></span>

6.  <span data-ttu-id="6e4c3-126">在**集合編輯器**中，選取包含**Mbam**的資料列，然後更新**Mbam**的值，以反映伺服器 B 的 [伺服器名稱]。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-126">In the **Collection Editor**, select the row that contains **Microsoft.Mbam.Reports.Url**, and update the value for **Microsoft.Mbam.Reports.Url** to reflect the server name for Server B.</span></span>

    <span data-ttu-id="6e4c3-127">如果您先前已在命名的 SQL Server Reporting Services 實例上設定報表功能，請在 URL 中新增或更新實例的名稱，例如：</span><span class="sxs-lookup"><span data-stu-id="6e4c3-127">If you previously configured the Reports feature on a named instance of SQL Server Reporting Services, add or update the name of the instance to the URL, for example:</span></span>

    `http://$SERVERNAME$/ReportServer_$SQLSRSINSTANCENAME$/Pages....)`

7.  <span data-ttu-id="6e4c3-128">若要自動化此程式，您可以使用 Windows PowerShell 來執行與下列程式碼範例類似的管理與監視伺服器上的命令。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-128">To automate this procedure, you can use Windows PowerShell to run a command on the Administration and Monitoring Server that is similar to the following code example.</span></span>

    ``` syntax
    PS C:\> Set-WebConfigurationProperty '/appSettings/add[@key="Microsoft.Mbam.Reports.Url"]' -PSPath "IIS:\\sites\Microsoft Bitlocker Administration and Monitoring\HelpDesk" -Name "Value" -Value "http://$SERVERNAME$/ReportServer[_$SRSINSTANCENAME$]/Pages/ReportViewer.aspx?/Microsoft+BitLocker+Administration+and+Monitoring/"
    ```

    <span data-ttu-id="6e4c3-129">使用下表中的描述，將程式碼範例中的值取代為與您的環境相符的值。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-129">Using the descriptions in the following table, replace the values in the code example with values that match your environment.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="6e4c3-130">參數</span><span class="sxs-lookup"><span data-stu-id="6e4c3-130">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="6e4c3-131">描述</span><span class="sxs-lookup"><span data-stu-id="6e4c3-131">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="6e4c3-132">$SERVERNAME $</span><span class="sxs-lookup"><span data-stu-id="6e4c3-132">$SERVERNAME$</span></span></p></td>
    <td align="left"><p><span data-ttu-id="6e4c3-133">要將報告移至其中的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-133">Name of the server to which the Reports were moved.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="6e4c3-134">$SRSINSTANCENAME $</span><span class="sxs-lookup"><span data-stu-id="6e4c3-134">$SRSINSTANCENAME$</span></span></p></td>
    <td align="left"><p><span data-ttu-id="6e4c3-135">已移動報告之 SQL Server Reporting Services 實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-135">Name of the instance of SQL Server Reporting Services to which the Reports were moved.</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

**<span data-ttu-id="6e4c3-136">繼續管理和監控網站的實例</span><span class="sxs-lookup"><span data-stu-id="6e4c3-136">Resume the instance of the Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="6e4c3-137">在執行管理和監視網站的伺服器上，使用 Internet Information Services （IIS）管理員主控台來啟動 [管理和監控] 網站。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-137">On the server that is running the Administration and Monitoring Website, use the Internet Information Services (IIS) Manager console to start the Administration and Monitoring Website.</span></span>

2.  <span data-ttu-id="6e4c3-138">若要自動化此程式，您可以使用 Windows PowerShell 來執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="6e4c3-138">To automate this procedure, you can use Windows PowerShell to run a command that is similar to the following:</span></span>

    ``` syntax
    PS C:\> Start-Website "Microsoft BitLocker Administration and Monitoring"
    ```

    <span data-ttu-id="6e4c3-139">**記事** 若要執行此命令，您必須將適用于 Windows PowerShell 的 IIS 模組新增至目前的 Windows PowerShell 實例。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-139">**Note** To run this command, you must add the IIS module for Windows PowerShell to the current instance of Windows PowerShell.</span></span>

     



## <span data-ttu-id="6e4c3-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="6e4c3-140">Related topics</span></span>


[<span data-ttu-id="6e4c3-141">如何設定 MBAM 2.5 報告</span><span class="sxs-lookup"><span data-stu-id="6e4c3-141">How to Configure the MBAM 2.5 Reports</span></span>](how-to-configure-the-mbam-25-reports.md)

[<span data-ttu-id="6e4c3-142">使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="6e4c3-142">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span>](configuring-mbam-25-server-features-by-using-windows-powershell.md)

[<span data-ttu-id="6e4c3-143">將 MBAM 2.5 功能移到其他伺服器</span><span class="sxs-lookup"><span data-stu-id="6e4c3-143">Moving MBAM 2.5 Features to Another Server</span></span>](moving-mbam-25-features-to-another-server.md)

 
## <span data-ttu-id="6e4c3-144">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="6e4c3-144">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="6e4c3-145">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-145">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="6e4c3-146">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="6e4c3-146">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





