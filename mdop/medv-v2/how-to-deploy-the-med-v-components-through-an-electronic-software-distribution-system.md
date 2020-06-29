---
title: 如何透過電子軟體發佈系統來部署 MED-V 元件
description: 如何透過電子軟體發佈系統來部署 MED-V 元件
author: dansimp
ms.assetid: 8a800bdf-6fa4-47b4-b417-df053289d4e8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: d772702c770340796fe770273146bd0308617a69
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810803"
---
# 如何透過電子軟體發佈系統來部署 MED-V 元件


電子軟體發佈系統可協助您透過慢速或快速網路連線將軟體快速移至多部電腦。 下列章節提供資訊與指示，以協助您使用軟體發佈系統在整個企業中部署 Microsoft 企業版桌面虛擬化（MED-V）2.0 元件。

**注意**  
無論您使用哪一個軟體發佈方案，您都必須熟悉特定解決方案的需求。 如果您使用的是 System Center Configuration Manager 2007 R2 或更新版本，請參閱 Microsoft 技術文件庫中的[Configuration Manager 檔庫](https://go.microsoft.com/fwlink/?LinkId=66999)（ https://go.microsoft.com/fwlink/?LinkId=66999) 。



**重要**  
如果您使用 System Center Configuration Manager 2007 SP2，而您的 MED-V 工作區已設定為在**NAT**模式下運作，則虛擬機器會分類為網際網路用戶端，而且找不到最接近要下載內容的發佈點。

此[熱修復程式可改善由 med-v 管理的 vm 功能（針對](https://go.microsoft.com/fwlink/?LinkId=201088) https://go.microsoft.com/fwlink/?LinkId=201088) 由 med-v 管理且已設定為在**NAT**模式下運作的虛擬機器），增加新功能。 新功能可讓虛擬機器存取最接近的發佈點。 因此，系統管理員可以以相同的方式管理虛擬機器與主機電腦。 此熱修復程式必須先安裝在網站伺服器上，然後再安裝在用戶端。

此更新公開提供。 不過，系統可能會提示您接受 Microsoft 服務的合約。 依照後續網頁上的提示進行，以取得此熱修復程式。



**注意**  
您必須先安裝 MED-V 工作區包裝程式，然後建立您的 MED-V 工作區，才能透過您的軟體發佈系統部署 MED-V 元件。 如需如何準備影像及建立 MED-V 工作區的詳細資訊，請參閱[med-v 的操作](operations-for-med-v.md)。



**使用軟體發佈系統部署 MED-V 元件**

1.  在電子軟體發佈系統中定義一組電腦和使用者作為電腦/使用者的目標群組。

2.  針對每個需要發佈的 Microsoft 安裝檔建立套件。 下列是所需的檔案，以及它們必須安裝的順序：

    1.  **Windows 虛擬電腦**–如果尚未安裝（需要重新開機電腦）。 如需詳細資訊，請參閱[設定安裝必備元件](configure-installation-prerequisites.md)。

    2.  **Windows 虛擬電腦新增和更新**–如果尚未安裝。 如需詳細資訊，請參閱[設定安裝必備元件](configure-installation-prerequisites.md)。

    3.  **Med-v 主機代理安裝**檔案–安裝主機代理程式（med-v \ _HostAgent \ _Setup 安裝檔案）。 如需詳細資訊，請參閱[如何手動安裝 Med-v 主機代理程式](how-to-manually-install-the-med-v-host-agent.md)。

        **警告**  
        在安裝 MED-V 主機代理程式前關閉 Internet Explorer，否則可能會在 URL 重新導向之後發生衝突。 您也可以在發佈期間指定電腦重新開機來執行此動作。   

    4.  **Med-v 工作區安裝程式、VHD 及安裝程式可執行檔**-在**Med-v 工作區包裝**程式中建立。 如需詳細資訊，請參閱[建立 Med-v 工作區套件](create-a-med-v-workspace-package.md)。

        **重要**  
        壓縮的虛擬硬碟檔案（medv）和 Setup executable 程式（setup.exe）必須與 MED-V 工作區安裝程式位於同一個資料夾中。 然後，透過執行 setup.exe 來安裝 MED-V 工作區安裝程式。

        **提示**  
        因為從網路位置安裝 MED-V 時會發生問題，所以建議您在本機複製 MED-V 工作區安裝程式檔案，然後執行 setup.exe。       

3.  將套件設定為在安靜模式中執行（不需要使用者互動）。

    在安靜模式下執行時，不會提示您關閉 Internet Explorer （如果它正在執行），並提示您啟動 MED-V 主機代理程式。 重新開機電腦時，會執行這兩個動作。

    **注意**  
    安裝 Windows Virtual 電腦時，必須重新開機電腦。 如果您隱含重新開機並忽略 MED-V 安裝所需的先決條件，您就可以建立單一安裝程式並同時安裝所有元件。 您也可以使用命令列引數來執行此動作。 如需這些引數的範例，請參閱[使用批次檔案安裝 med-v 元件](#bkmk-batch)。 在電腦重新開機時，MED-V 會自動啟動。

4.  安裝 Windows 虛擬電腦之前，請先安裝 MED-V 及其元件。 請參閱本主題稍後的範例批次檔案。

    **重要**  
    選取 [**忽略 \ _PREREQUISITES** ] 選項（如範例批次檔案所示），以便在所需的 VPC 元件之前安裝 med-v 元件。 安裝 MED-V 元件，以允許單一重新開機。

5.  找出安裝所需的任何其他需求，以及軟體發佈系統（例如目標平臺和可用磁碟空間）。

6.  將套件指派給電腦/使用者的目標群組。

    當電腦執行時，軟體發佈系統用戶端會辨識新套件可用，並開始根據定義和需求來安裝套件。 安裝應以緘默模式循序執行。 我們建議您將它做為單一處理程式，而不需要重新開機，直到安裝完所有套件為止。

7.  安裝完成後，請重新開機更新的電腦。

    根據軟體發佈系統，您可以排程重新開機電腦，或最終使用者可以在正常運作期間手動重新開機電腦。 重新開機電腦之後，MED-V 會在使用者登入時自動啟動。 當 MED-V 第一次啟動時，會第一次執行安裝程式。

第一次安裝開始，可能需要幾分鐘的時間完成，視您指定的虛擬硬碟大小以及啟動時所套用到 MED-V 工作區的原則數而定。 使用者可以透過在通知區域中觀察 MED-V 圖示來追蹤進度。 如需第一次設定的詳細資訊，請參閱[med-v 2.0 部署概覽](med-v-20-deployment-overview.md)。

<a href="" id="bkmk-batch"></a>**使用批次處理檔案安裝 MED-V 元件**

1.  使用系統管理認證在命令提示字元執行安裝。

2.  將每個元件部署到單一目錄。 如果從網路共用執行，則需要較長的時間來解壓縮 medv 檔案。

3.  最佳做法是指定在 MED-V 主機代理程式和 MED-V 工作區套件檔案之後，安裝 Windows 虛擬電腦和 Windows 虛擬電腦熱修復程式。 這表示 Windows 更新不會對安裝程式造成任何干擾，只要需要重新開機即可。

4.  批次處理檔案完成後，請重新開機電腦。

重新開機之後，系統會提示使用者第一次執行安裝並完成 MED-V 的設定。

下列含有指定引數的範例說明如何在單一程式中安裝64位 MED-V 元件：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">引數</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>/norestart</p></td>
<td align="left"><p>防止安裝 Windows Virtual PC 和 Windows Virtual PC 更新，因為重新開機主機電腦。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/quiet</p></td>
<td align="left"><p>在沒有使用者互動的安靜模式中安裝 MED-V 元件。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/qn</p></td>
<td align="left"><p>安裝 MED-V 元件（不含使用者介面）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>IGNORE_PREREQUISITES</p></td>
<td align="left"><p>安裝而不檢查 Windows 虛擬電腦。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果您是在此安裝中安裝 Windows 虛擬電腦，請只指定此引數。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>OVERWRITEVHD</p></td>
<td align="left"><p>強制安裝 MED-V 工作區，並防止它可能產生的任何提示。</p></td>
</tr>
</tbody>
</table>



## 範例


``` syntax
:: Install MED-V and the Pre-requisites

:: Install the MED-V Host Agent: install in quiet mode, ignore that Windows Virtual PC is not installed completely, and log results
start /WAIT .\MED-V_HostAgent_Setup.exe /qn IGNORE_PREREQUISITES=1 /l* %TEMP%\MEDVhost.log

:: Install the MED-V Workspace: install in quiet mode, Overwrite the VHD if it already exists, and log results
start /WAIT .\setup.exe /qn OVERWRITEVHD=1 /l* %TEMP%\MEDVworkspace.log

:: Install Windows Virtual PC: install in quiet mode and do not reboot
start /WAIT wusa.exe Windows6.1-KB958559-x64.msu /norestart /quiet

:: Install Windows Virtual PC patch to support non-HAV: install in quiet mode and do not reboot
wusa.exe Windows6.1-KB977206-x64.msu /norestart /quiet

:: After successful installation of the above components, a reboot of the host computer is required to complete installation.
```

## 相關主題


[MED-V 2.0 部署概觀](med-v-20-deployment-overview.md)

[部署 MED-V 元件](deploy-the-med-v-components.md)









