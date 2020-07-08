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
# 如何移動 MBAM 2.5 報告


使用這些程式將 [報表] 功能從一部電腦移到另一台電腦，也就是將 [報表] 功能從伺服器 A 移到伺服器 B。

移動報表功能的最高層步驟如下：

1.  停止 MBAM 管理和監視網站的所有實例。

2.  在伺服器 B 上安裝 MBAM 2.5 Server 軟體，並在伺服器 B 上設定 [報告] 功能。

3.  更新 MBAM 管理和監視伺服器上的報表連線資料。

4.  繼續 MBAM 管理和監視網站的實例。

**記事** 若要執行本主題中的 Windows PowerShell 腳本範例，您必須更新 Windows PowerShell 執行原則，才能執行腳本。 請參閱執行[Windows PowerShell 腳本](https://technet.microsoft.com/library/ee176949.aspx)以取得相關指示。

 

**停止 MBAM 管理和監控網站**

-   在執行管理和監視網站的伺服器上，使用 Internet Information Services （IIS）管理員主控台來停止管理和監控網站。

    若要自動化此程式，您可以使用 Windows PowerShell 輸入類似以下的命令：

    ``` syntax
    PS C:\> Stop-Website "Microsoft BitLocker Administration and Monitoring"
    ```

**在伺服器 B 上安裝 MBAM Server 軟體並執行 [MBAM 伺服器設定] 嚮導**

1.  在伺服器 B 上安裝 MBAM Server 軟體。如需相關指示，請參閱[安裝 MBAM 2.5 Server 軟體](installing-the-mbam-25-server-software.md)。

2.  在伺服器 B 上，啟動 [MBAM 伺服器設定] 嚮導，按一下 [新增**功能**]，然後只選取 [**報告**] 功能。

    或者，您也可以使用**Enable-MbamReport** Windows PowerShell Cmdlet 來設定報告。

    如需如何設定報告的相關指示，請參閱[如何設定 MBAM 2.5 報告](how-to-configure-the-mbam-25-reports.md)。

**更新管理和監視伺服器上的報表連線資料**

1.  在執行 [報告] 功能的伺服器上，使用 [網際網路資訊服務（IIS）管理員] 主控台來更新報表 URL。

2.  展開 [ **Microsoft BitLocker 管理及監視**]，然後選取 [**服務台**] 節點。

3.  在 [**功能] 視圖**的 [**管理**] 區段中，選取 [**配置編輯器**]。

4.  在 [**節**] 欄位中，選取 [ **appSettings**]。

5.  選取**集合**列，然後按一下窗格最右側的 [省略號] 按鈕 **（...）** 以開啟**集合編輯器**。

6.  在**集合編輯器**中，選取包含**Mbam**的資料列，然後更新**Mbam**的值，以反映伺服器 B 的 [伺服器名稱]。

    如果您先前已在命名的 SQL Server Reporting Services 實例上設定報表功能，請在 URL 中新增或更新實例的名稱，例如：

    `http://$SERVERNAME$/ReportServer_$SQLSRSINSTANCENAME$/Pages....)`

7.  若要自動化此程式，您可以使用 Windows PowerShell 來執行與下列程式碼範例類似的管理與監視伺服器上的命令。

    ``` syntax
    PS C:\> Set-WebConfigurationProperty '/appSettings/add[@key="Microsoft.Mbam.Reports.Url"]' -PSPath "IIS:\\sites\Microsoft Bitlocker Administration and Monitoring\HelpDesk" -Name "Value" -Value "http://$SERVERNAME$/ReportServer[_$SRSINSTANCENAME$]/Pages/ReportViewer.aspx?/Microsoft+BitLocker+Administration+and+Monitoring/"
    ```

    使用下表中的描述，將程式碼範例中的值取代為與您的環境相符的值。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">參數</th>
    <th align="left">描述</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>$SERVERNAME $</p></td>
    <td align="left"><p>要將報告移至其中的伺服器名稱。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>$SRSINSTANCENAME $</p></td>
    <td align="left"><p>已移動報告之 SQL Server Reporting Services 實例的名稱。</p></td>
    </tr>
    </tbody>
    </table>

     

**繼續管理和監控網站的實例**

1.  在執行管理和監視網站的伺服器上，使用 Internet Information Services （IIS）管理員主控台來啟動 [管理和監控] 網站。

2.  若要自動化此程式，您可以使用 Windows PowerShell 來執行類似下列的命令：

    ``` syntax
    PS C:\> Start-Website "Microsoft BitLocker Administration and Monitoring"
    ```

    **記事** 若要執行此命令，您必須將適用于 Windows PowerShell 的 IIS 模組新增至目前的 Windows PowerShell 實例。

     



## 相關主題


[如何設定 MBAM 2.5 報告](how-to-configure-the-mbam-25-reports.md)

[使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)

[將 MBAM 2.5 功能移到其他伺服器](moving-mbam-25-features-to-another-server.md)

 
## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
 





