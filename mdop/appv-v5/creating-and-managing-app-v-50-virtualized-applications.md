---
title: 建立和管理 App-V 5.0 虛擬化應用程式
description: 建立和管理 App-V 5.0 虛擬化應用程式
author: dansimp
ms.assetid: 66bab403-d7e0-4e7b-bc8f-a29a98a7160a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 86332c7753b70abbaaf289fc1ba046bf59d1dd89
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800659"
---
# 建立和管理 App-V 5.0 虛擬化應用程式


在您正確部署 Microsoft Application Virtualization （App-v） 5.0 sequencer 之後，您可以使用它來監視及記錄應用程式作為虛擬化應用程式執行的安裝與設定程式。

**記事** 如需有關設定 Microsoft Application Virtualization （App-v） 5.0 sequencer、排序最佳做法，以及建立和更新虛擬應用程式的範例的詳細資訊，請參閱[Microsoft Application virtualization 5.0 排序指南](https://download.microsoft.com/download/F/7/8/F784A197-73BE-48FF-83DA-4102C05A6D44/App-V 5.0 Sequencing Guide.docx)（ https://download.microsoft.com/download/F/7/8/F784A197-73BE-48FF-83DA-4102C05A6D44/App-V 5.0 排序 Guide.docx）。

 

## 為應用程式排序


您可以使用 App-v 5.0 Sequencer 來執行下列工作：

-   建立可部署到執行 App-v 5.0 用戶端之電腦的虛擬套件。

-   升級現有的套件。 您可以將現有的套件展開到執行排序器的電腦上，然後升級應用程式以建立較新的版本。

-   編輯與現有套件相關聯的配置資訊。 例如，您可以新增快捷方式或修改檔案類型關聯。

    **記事** 您必須建立快速鍵，並將其儲存到可用的網路位置，才能允許漫遊。 如果在私人位置建立並儲存快捷方式，套件必須在本機發佈至執行 App-v 5.0 用戶端的電腦上。

     

-   [轉換現有的虛擬套件]。

排序器使用 **% TMP% \ [暫存**] 或 **% TEMP% \\ 暫存**目錄，而**temp**目錄則是在排序期間儲存臨時檔案。 在執行排序器的電腦上，您應該使用相當於估計應用程式安裝需求的可用磁碟空間來設定這些目錄。 在不同的硬碟分區上設定 temp 目錄和 Temp 目錄，可以在排序期間改善效能。

當您使用排序器建立新的虛擬應用程式時，會建立下列列出的檔案。 這些檔案是由 App-v 5.0 套件組成。

-   .msi 檔案。 此 Windows Installer （.msi）檔案是由排序器所建立，並用於在目的電腦上安裝虛擬套件。

-   Report.xml 檔案]。 在此檔案中，sequencer 會儲存在排序期間發現的所有問題、警告及錯誤。 建立套件後，就會顯示資訊。 您可以在此報告進行診斷和疑難排解。

-   appv 檔案。 這是虛擬應用程式檔。

-   部署設定檔。 部署設定檔會決定虛擬應用程式將如何部署至目的電腦。

-   使用者設定檔。 使用者設定檔會決定虛擬應用程式在目的電腦上的執行方式。

**重要** 您必須設定套件轉換器所使用的% TMP% 與% TEMP% 資料夾，才能成為安全的位置和目錄。 只有系統管理員可以存取安全的位置。 此外，當您排列套件時，您應該將套件儲存至安全的位置，或是確定在轉換與監控程式期間不允許登入任何其他使用者。

 

排序器主控台中的 [**選項**] 對話方塊包含下列索引標籤：

-   **[一般**]。 使用此索引標籤可讓 Microsoft 更新在進行排序期間執行。 選取 [**附加套件版本至 Filename** ] 來設定序列，以將版本號碼新增到已排序的虛擬化套件中。 選取 [**永遠信任套件加速器的來源**]，以使用套件加速器建立虛擬化套件，而不會提示您授權。

    **重要** App-V 5.0 不支援使用 App-v 4.6 建立的套件加速器。

     

-   **分析專案**。 這個索引標籤會顯示將在虛擬環境中分析或自動標記的相關檔案路徑位置。 在使用 [**高級編輯**] 中的 [**套件**檔案] 索引標籤新增檔案時，可以使用標記。

-   **排除專案**。 使用此索引標籤，以指定在排序期間不應監視哪些資料夾和目錄。 若要新增儲存在套件中本機應用程式資料檔案夾中的本機應用程式資料，請按一下 [**新增**]，然後指定位置及相關聯的**對應類型**。 某些套件必須有這個選項。

App-v 5.0 支援包含 Microsoft Windows 服務的應用程式。 如果應用程式包含 Windows 服務，則服務會包含在已排序的虛擬套件中，只要由排序器監控，就會包含在已排序的虛擬套件中。 如果虛擬應用程式在初次執行時建立 Windows 服務，然後在安裝之後，應用程式必須在排序器監視時執行，以便將 Windows 服務新增到套件中。 只有在本機系統帳戶下執行的服務才受支援。 針對自動啟動或延遲自動啟動所設定的服務會在套件中的第一個虛擬應用程式在套件的虛擬環境內執行之前先啟動。 當套件內的虛擬應用程式透過 API 呼叫啟動服務時，系統會啟動已設定為按需由應用程式啟動的 Windows 服務。

[如何使用 App-V 5.0 為新應用程式進行序列化](how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md)

## <a href="" id="---------app-v-5-0-sp2-shell-extension-support"></a> App-v 5.0 SP2 命令介面延伸支援


App V 5.0 SP2 支援命令介面延伸。 在排序期間，系統會在套件中檢測並內嵌 Shell 延伸。

在排序過程中，會自動將 Shell 延伸內嵌在套件中。 套件發佈之後，命令介面延伸提供使用者的功能，就如同已在本機安裝應用程式一樣。

**使用命令介面延伸的需求：**

-   包含內嵌命令介面延伸的套件必須全域發佈。 應用程式在用戶端上不需要任何額外的設定或配置，就能啟用 shell 擴充功能。

-   應用程式、Sequencer 和 App-v 用戶端的 "位數" 必須相符，否則 shell 延伸將無法運作。 例如：

    -   應用程式的版本為64位。

    -   排序器正在64位電腦上執行。

    -   套件正在傳送至64位的 App-v 用戶端電腦。

下表列出支援的命令介面延伸：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">處理</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>操作功能表處理常式</p></td>
<td align="left"><p>將功能表項目新增至操作功能表。 在顯示操作功能表前呼叫該內容。</p></td>
</tr>
<tr class="even">
<td align="left"><p>拖放處理常式</p></td>
<td align="left"><p>控制動作在按一下滑鼠右鍵時，拖放並修改所出現的操作功能表。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>拖放目標處理常式</p></td>
<td align="left"><p>控制將資料物件拖曳到拖放目標（例如檔案）之後的動作。</p></td>
</tr>
<tr class="even">
<td align="left"><p>資料物件處理常式</p></td>
<td align="left"><p>控制將檔案複製到剪貼簿，或將檔案拖放到拖放目標上之後的動作。 它可以提供其他剪貼簿格式至拖放目標。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>屬性工作表處理常式</p></td>
<td align="left"><p>取代或新增頁面至物件的 [屬性工作表] 對話方塊。</p></td>
</tr>
<tr class="even">
<td align="left"><p>提示處理常式</p></td>
<td align="left"><p>允許您檢索專案的標誌和資訊提示資訊，並在滑鼠懸停時將它顯示在彈出工具提示內。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>欄處理常式</p></td>
<td align="left"><p>可讓您在 <strong> Windows 資源管理器的詳細資料檢視中建立和顯示自訂欄 </strong> 。 它可以用來延伸排序與分組。</p></td>
</tr>
<tr class="even">
<td align="left"><p>預覽處理常式</p></td>
<td align="left"><p>啟用要在 Windows 資源管理器預覽窗格中顯示的檔案預覽。</p></td>
</tr>
</tbody>
</table>

 

## 寫入時拷貝（牛）副檔名支援


[寫入時拷貝（牛）] 檔案延伸功能可讓 App-v 5.0 動態寫入到所使用的虛擬套件中所包含的特定位置。

下表顯示可在 VFS 目錄下的虛擬套件中存在的檔案類型，但無法在執行 App-v 5.0 用戶端的電腦上更新。 所有其他的檔案和目錄都可以修改。

。

. asa

.asp

.aspx

. ax

.bat

.cer

.chm

clb

.cmd

.cnt

.cnv

.com

.cpl

.cpx

.crt

.dll

.drv

.exe

.fon

.grp

.hlp

.hta

. ime

.inf

.ins

.isp

。它的

.js

.jse

.lnk

.msc

.msi

.msp

.mst

mui

. nls

.ocx

pal

.pcd

.pif

.reg

.scf

.scr

. sct

.shb

.shs

.sys

.tlb

. tsp

.url

.vb

.vbe

.vbs

.vsmacros

.ws

。 esc

.wsf

.wsh

 

## 修改現有的虛擬應用程式套件


您可以使用 sequencer 來修改現有的套件。 您在其上執行這項作業的電腦應該與您用來建立應用程式的電腦的晶片架構相符。 例如，如果您最初是使用執行64位作業系統的電腦將套件排序列化，您應該使用執行64位作業系統的電腦來修改套件。

[如何修改現有的虛擬應用程式套件](how-to-modify-an-existing-virtual-application-package-beta.md)

## 建立專案範本


Appvt 檔案是一個專案範本，可用於儲存常用的自訂設定。 然後，您就可以更輕鬆地使用這些設定來進行未來的 sequencings。

App-v 5.0 專案範本與 App-v 5.0 應用程式加速器不同，因為 App-v 5.0 應用程式加速器是應用程式專用的，而 App-v 5.0 專案範本可以套用到多個應用程式。 此外，當您使用套件加速器建立虛擬應用程式套件時，您無法使用專案範本。 下列一般設定會儲存在 App-v 5.0 專案範本：

範本可以指定及儲存多個設定，如下所示：

-   [**高級監視] 選項**。 可讓 Microsoft 更新在監視期間執行。 儲存 [允許本機互動] 選項設定

-   **一般選項**。 啟用**Windows 安裝程式**，並將**套件版本附加至 Filename**。

-   **排除專案。** 包含 [排除] 模式清單。

[如何建立及使用專案範本](how-to-create-and-use-a-project-template.md)

## 建立套件加速器


**記事** 您必須使用 App-v 5.0 來重新建立使用舊版 App-v 建立的套件加速器。

 

您可以使用 App-v 5.0 封裝加速器來自動產生新的虛擬應用程式套件。 成功建立套件加速器之後，您可以重複使用並共用套件加速器。

在某些情況下，若要建立套件加速器，您可能必須在執行排序器的電腦上本機安裝應用程式。 在這種情況下，您應該先嘗試使用安裝媒體建立套件加速器。 如果需要多個遺失的檔案，您應該在執行排序器的電腦上本機安裝應用程式，然後建立套件加速器。

成功建立套件加速器之後，您可以重複使用並共用套件加速器。 建立 App-v 5.0 套件加速器是一個高級任務。 套件加速器可以包含密碼和使用者專用的資訊。 因此，您必須將套件加速器與關聯安裝媒體儲存在安全的位置，而且您應該在建立套件加速器之後進行數位簽章，以便在套用 app-v 5.0 套件加速器時驗證發行者。

[如何建立封裝加速器](how-to-create-a-package-accelerator.md)

[如何使用 App-V 封裝加速器建立虛擬應用程式套件](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator.md)

## Sequencer 錯誤報表


App-v 5.0 排序器可以在排序期間檢測一般的順序問題。 [順序] 嚮導末端的 [**安裝報告**] 頁面會根據問題的嚴重性，顯示分類為**錯誤**、**警告**及**資訊**的診斷訊息。

您也可以使用 Windows 事件檢視器，找到有關順序錯誤的其他資訊。






## <a href="" id="other-resources-for-the-app-v-5-0-sequencer-"></a>App-v 5.0 排序器的其他資源


-   [App-V 5.0 作業](operations-for-app-v-50.md)

 

 





