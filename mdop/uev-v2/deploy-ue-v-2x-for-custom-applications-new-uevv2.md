---
title: 部署自訂應用程式的 UE-V 2. x
description: 部署自訂應用程式的 UE-V 2. x
author: dansimp
ms.assetid: f7cb089f-d764-4a93-82b6-926fe0385a23
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 07/19/2016
ms.openlocfilehash: 217f647d948df016c4a6b72736669c2b3305b705
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810533"
---
# 部署自訂應用程式的 UE-V 2. x


Microsoft 使用者體驗虛擬化（UE-V）2.0。 2.1 和 2.1 SP1 使用名為 [**設定位置範本**] 的 XML 檔案，在使用者電腦之間監視及同步處理桌面應用程式設定與 Windows 桌面設定。 根據預設值，UE-V 中包含一些設定位置範本。 但如果您想要同步處理桌面應用程式的設定，而不包含在預設範本中，您可以使用 UE-V 發生器建立自己的自訂設定位置範本。

當您在[準備 ue-v 2. x 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)中閱讀規劃資料並決定要同步處理自訂應用程式（協力廠商、商務線等）的設定後，您將會按照本主題中所述的方式來部署 ue-v 的功能。 若要開始，以下是同步處理自訂應用程式設定所需的主要步驟：

-   [安裝 UEV 發生器](#uevgen)

    使用 UEV 發生器來建立自訂 XML 設定位置範本。

-   [設定 UE-V 設定範本目錄](#deploycatalogue)

    您可以定義儲存自訂設定位置範本的這個路徑。

-   [建立自訂設定位置範本](#createcustomtemplates)

    這些自訂範本可讓使用者同步處理自訂應用程式的設定。

-   [部署自訂設定位置範本](#deploycustomtemplates)

    在您測試自訂範本以確保正確同步處理之後，您可以透過下列其中一種方式來部署這些範本：

    -   透過您現有的部署基礎結構，例如 Configuration Manager

    -   使用群組原則喜好設定

    -   [部署 UE-V 設定範本目錄](#deploycatalogue)

    **記事** 使用 ESD 或群組原則部署的範本，必須在 UE-V Windows Management Instrumentation （WMI）或 Windows PowerShell 中註冊。

     

## 準備部署自訂應用程式的 UE-V 2. x


開始部署處理自訂應用程式的 UE-V 功能前，只需要複習幾個事項。

### UE-V 發生器

UE-V 發生器會監視應用程式，以探索和捕獲應用程式儲存其設定的位置。 受監視的應用程式必須是傳統的應用程式。 您可以使用 UE-V 發生器來建立設定位置範本，但無法從這些應用程式類型建立設定位置範本：

-   虛擬化應用程式

-   透過終端服務提供的應用程式

-   JAVA 應用程式

-   Windows 應用程式

**記事** UE-V 設定位置範本無法從虛擬化應用程式或終端服務應用程式建立。 不過，使用範本同步處理的設定可以套用到那些應用程式。 若要建立支援虛擬桌面基礎結構（VDI）和終端服務應用程式的範本，請使用 UE-V 發生器開啟應用程式的 Windows Installer （.msi）套件版本。 如需有關同步處理虛擬應用程式設定的詳細資訊，請參閱[使用 ue-v 2. 與應用程式虛擬化應用程式](using-ue-v-2x-with-application-virtualization-applications-both-uevv2.md)。

 

已**排除的位置：** 探索程式會排除通常儲存應用程式軟體檔案的位置，而這些檔案不會在使用者電腦或計算環境之間同步處理設定。 根據預設，會排除這些專案：

-   HKEY \ _CURRENT \ _USER 登錄的使用者無法寫入值的登錄機碼和檔案

-   HKEY \ _CURRENT \ _USER 與 Windows 作業系統核心功能相關聯的登錄機碼和檔案

-   位於 HKEY \ _LOCAL \ _MACHINE hive 中的所有登錄機碼

-   位於 [Program Files] 目錄中的檔案

-   位於使用者 \\ [User name \] \\ AppData \\ LocalLow 中的檔案

-   位於% Systemroot% 中的 Windows 作業系統檔案

如果您需要儲存在排除位置的登錄機碼和檔案，才能同步處理應用程式設定，您可以在範本建立期間將位置手動新增到 [設定位置] 範本。
不過，只有對 HKEY \ _CURRENT \ _USER hive 的變更才會同步處理。

### 取代預設的 Microsoft 範本

UE-V Agent 會安裝適用于常見 Microsoft 應用程式和 Windows 設定的預設設定位置範本組。 如果您自訂這些範本，或建立設定位置範本來同步處理自訂應用程式的設定，則可以將 UE-V Agent 設定為使用設定範本目錄來儲存範本。 在這種情況下，您將需要在 [設定] 範本目錄中加入預設範本以及自訂範本。

當您[部署 Ue-v Agent](https://technet.microsoft.com/library/dn458891.aspx#agent)時，您可以使用命令列參數 `RegisterMSTemplates` 來停用預設的 Microsoft 範本。

當您使用群組原則來設定設定範本目錄路徑時，您可以選擇取代預設的 Microsoft 範本。 如果您將原則設定設定為取代預設的 Microsoft 範本，則會刪除由 UE-V Agent 安裝的所有預設 Microsoft 範本，而且只會使用位於設定範本目錄中的範本。 UE-V Agent 設定參數 `RegisterMSTemplates` 必須設定為*true* ，才能覆寫預設的 Microsoft 範本。

**記事** 如果您在啟用此原則設定後停用它，UE-V Agent 就不會還原預設的 Microsoft 範本。

 

如果設定範本目錄中存在使用與預設 Microsoft 範本相同識別碼的自訂範本，而 UE-V Agent 並未設定為取代預設的 Microsoft 範本，則會忽略 Microsoft 範本。

您也可以使用 UE-V Windows PowerShell 功能取代預設範本。 若要使用 Windows PowerShell 取代預設的 Microsoft 範本，請登出所有預設的 Microsoft 範本，然後註冊自訂範本。

**記事** 即使您為應用程式部署新的設定位置範本，舊的設定套件仍會保留在 [設定] 儲存位置。 這些套件不會由代理程式讀取，但它們不會自動刪除。

 

## <a href="" id="uevgen"></a>安裝 UEV （2. x）產生器


在電腦上安裝 Microsoft 使用者體驗 Virtualization （UE-V）2.0 發生器，您可以用來建立自訂設定位置範本。 此電腦應該已安裝的應用程式是要產生的自訂設定位置範本。

**若要安裝 UE-V 發生器**

1.  以擁有本機系統管理員許可權的使用者的身分，找出 ue-v 發生器安裝檔案**ToolSetup.exe**提供給 ue-v 軟體。 或者，如果您知道電腦架構，您可以執行適當的 Windows Installer （.msi）檔案， **ToolsSetupx64.msi**或**ToolsSetupx86.msi**。

2.  按兩下安裝檔。 隨即會開啟 [使用者體驗虛擬化發生器設定] 嚮導。 按 \[**下一步**\] 繼續。

3.  接受 Microsoft 軟體授權條款，然後按一下 **[下一步]**。

4.  按一下 [Microsoft 更新] 和 [客戶經驗改進計畫] 的選項。

5.  選取要安裝 UE-V 發生器的目的地資料夾，然後按一下 **[下一步]**。

6.  按一下 [**安裝**] 以開始安裝。

    **記事** 在安裝應用程式之前，會出現 [**使用者帳戶控制**] 提示。 必須具備許可權，才能安裝 UE-V 發生器。

     

7.  安裝完成後，按一下 **[完成**] 以關閉嚮導。 您必須重新開機電腦，才能執行 UE-V 發生器。

    若要確認安裝已成功，請依序按一下 [**開始**]、[**所有程式**]、[ **microsoft 使用者體驗虛擬化**]，然後按一下 [ **microsoft 使用者體驗虛擬化發生器**]。

    **記事** UE-V 2 發生器只能用來建立 UE-V 2 個代理程式的範本。 在 UE-V 1.0 Agent 與 UE-V 2 Agent 的混合式部署中，您應該繼續使用 UE-V 1.0 發生器，直到您升級完所有 UE-V Agent 為止。

     

## <a href="" id="deploycatalogue"></a>部署設定範本目錄


使用者體驗虛擬化設定範本目錄是 UE-V 電腦或伺服器郵件區塊（SMB）網路共用上的資料夾路徑，可儲存所有的自訂設定位置範本。 UE-V Agent 中的排程任務會根據此資料夾中的範本，每日檢查一次此位置，並更新其同步處理行為。

UE-V Agent 會在您最後一次檢查資料夾並登出已移除的範本之後，註冊此資料夾中新增或更新的範本。 根據預設，範本是在每天淩晨3:30 登錄並取消註冊一次。 [任務排程器] 和 [系統啟動] 中的 [當地時間]。 若要自訂此排程任務的頻率，請參閱[變更 ue-v 2. x 排程任務的頻率](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)。

您可以使用安裝命令列選項、群組原則、WMI 或 Windows PowerShell，來設定設定範本的目錄路徑。 儲存在設定範本目錄路徑的範本會自動由排程的工作進行註冊和取消註冊。

**若要設定 UE-V 2. x 的設定範本目錄**

1.  在儲存 UE-V 設定範本目錄的電腦上建立新資料夾。

2.  針對設定範本目錄資料夾設定下列共用層（SMB）許可權。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>使用者帳戶</strong></th>
    <th align="left"><strong>建議的許可權</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>所有人</p></td>
    <td align="left"><p>沒有許可權</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>網域電腦</p></td>
    <td align="left"><p>讀取權限等級</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>管理員</p></td>
    <td align="left"><p>讀取/寫入權限等級</p></td>
    </tr>
    </tbody>
    </table>

     

3.  針對 [設定範本目錄] 資料夾設定下列 NTFS 檔案系統許可權。

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">使用者帳戶</th>
    <th align="left">建議的許可權</th>
    <th align="left">套用至</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>建立者/擁有者</p></td>
    <td align="left"><p>完全控制</p></td>
    <td align="left"><p>這個資料夾、子資料夾及檔案</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>網域電腦</p></td>
    <td align="left"><p>列出資料夾內容並閱讀</p></td>
    <td align="left"><p>這個資料夾、子資料夾及檔案</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>所有人</p></td>
    <td align="left"><p>沒有許可權</p></td>
    <td align="left"><p>沒有許可權</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>管理員</p></td>
    <td align="left"><p>完全控制</p></td>
    <td align="left"><p>這個資料夾、子資料夾及檔案</p></td>
    </tr>
    </tbody>
    </table>

     

4.  按一下 **[確定**] 以關閉對話方塊。

網路共用至少必須授與 Domain 電腦群組的許可權。 此外，請將網路共用資料夾的存取權限授與要管理已儲存範本的管理員。

## <a href="" id="createcustomtemplates"></a>建立自訂設定位置範本


使用 UE-V 發生器來建立商務用應用程式或其他自訂應用程式的設定位置範本。 在建立應用程式的範本之後，您可以將它部署到電腦，讓該應用程式的設定同步處理。

**使用 UE-V 發生器建立 UE-V 設定位置範本**

1.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **microsoft 使用者體驗虛擬化**]，然後按一下 [ **microsoft 使用者體驗虛擬化發生器**]。

2.  按一下 [**建立設定位置] 範本**。

3.  指定應用程式。 流覽至應用程式（.exe）的檔案路徑，或是您想要建立設定位置範本的應用程式快捷方式（.lnk）。 指定命令列引數（如果有的話），以及工作目錄（如果有的話）。 按 \[**下一步**\] 繼續。

    **記事** 在應用程式啟動之前，系統會顯示**使用者帳戶控制**的提示。 必須具備許可權，才能監視應用程式用來儲存設定的登錄和檔案位置。

     

4.  應用程式啟動後，請關閉應用程式。 UE-V 發生器會記錄應用程式儲存其設定的位置。

5.  處理常式完成後，請按 **[下一步]** 繼續。

6.  檢查並選取適當的登錄位置旁邊的核取方塊，以及要針對此應用程式同步處理的設定檔位置。 此清單包含下列兩個類別的設定位置：

    -   **標準**：儲存在登錄中的 [HKEY \ _CURRENT \ _USER] 索引卷名或 **[使用者名稱**\]] 下的檔案資料夾中的應用程式設定，請**AppData**  \\  **漫遊**。 UE-V 發生器預設會包含這些設定。

    -   **非標準**：儲存在位置以外的應用程式設定是在設定資料儲存區的最佳做法中指定（選用）。 其中包括 [**使用者**] \\ [使用者名稱 \] \\ **AppData**Local] 下的檔案和資料夾  \\  ** **。 請查看這些位置，判斷是否要在 [設定位置] 範本中包含這些位置。 選取 [位置] 核取方塊以包含它們。

    按 \[**下一步**\] 繼續。

7.  針對 [設定位置] 範本，查看及編輯任何**屬性** **、登錄位置及****檔案位置。**

    -   在 [**屬性**] 索引標籤上編輯下列屬性：

        -   **應用程式名稱**：已寫入程式檔案屬性描述的應用程式名稱。

        -   **程式名稱**：從程式檔案屬性提取的程式名稱。 這個名稱通常具有 .exe 副檔名。

        -   **產品版本**：應用程式 .exe 檔案的產品版本號碼。 這個屬性與檔案**版本**搭配使用，可協助判斷設定位置範本所針對的是哪些應用程式。 這個屬性接受主要版本號碼。 如果這個屬性是空的，設定位置範本會套用至所有版本的產品。

        -   [檔案**版本**]：應用程式 .exe 檔案的檔案版本號碼。 這個屬性會與**產品版本**搭配使用，協助判斷設定位置範本所針對的是哪些應用程式。 這個屬性接受主要版本號碼。 如果這個屬性是空的，設定位置範本會套用至所有版本的程式。

        -   **範本作者名稱**（選用）：設定位置範本作者的名稱。

        -   **範本作者電子郵件**（選用）：設定位置範本作者的電子郵件地址。

    -   [**登錄] 索引**標籤會列出 [設定位置] 範本中所包含的登錄位置**金鑰**和**範圍**。 使用 [**任務**] 下拉式功能表編輯登錄位置。 [工作] 可讓您新增金鑰、編輯現有金鑰的名稱或範圍、刪除金鑰，以及流覽金鑰所在的註冊表。 使用**All 設定**範圍，將所有的登錄設定都包含在指定的索引鍵底下。 使用 [**所有設定] 和 [子項**]，將所有的登錄設定都包含在指定的索引鍵、子項和子項設定底下。

    -   [**檔案] 索引**標籤會列出 [設定位置] 範本中所包含之檔案位置的檔案路徑和檔案檢測。 使用 [**任務**] 下拉式功能表來編輯檔案位置。 檔案位置的工作可讓您新增檔案或資料夾位置、編輯現有檔案或資料夾的範圍、刪除檔案或資料夾，以及在 Windows 資源管理器中開啟所選的位置。 將檔案遮罩保留為空白，以包含指定資料夾中的所有檔案。

8.  按一下 [**建立**]，然後按一下 [**儲存**] 以儲存電腦上的 [設定位置] 範本。

9.  按一下 [**關閉**]，關閉 [設定範本] 嚮導。 退出 UE-V 發生器應用程式。

    在您為應用程式建立設定位置範本之後，您應該測試該範本。 在實驗室環境中部署範本，然後將它放入企業中的生產環境。

[Ue-v 的應用程式範本架構參考](https://technet.microsoft.com/library/dn763947.aspx)[ue-v 設定位置] 範本的 XML 結構，並提供編輯這些檔案的指導方針。

## <a href="" id="deploycustomtemplates"></a>部署自訂設定位置範本


在使用 UE-V 發生器建立設定位置範本後，您應該對它進行測試，以確保正確同步處理應用程式設定。 然後，您就可以將設定位置範本安全地部署到企業中的電腦上。

您可以使用下列其中一種方法來部署設定位置範本：

-   企業軟體發佈（ESD）系統，例如 System Center Configuration Manager

-   群組原則喜好設定

-   UE-V 設定範本目錄

使用 ESD 系統或群組原則物件所部署的範本，必須透過 UE-V Windows 管理規範（WMI）或 Windows PowerShell 進行註冊。 儲存在設定範本目錄位置的範本會自動由 UE-V Agent 進行註冊。

**使用設定範本目錄路徑來部署 UE-V 設定位置範本**

1.  流覽至定義為 [設定] 範本目錄的網路共用資料夾。

2.  在設定範本目錄中新增、移除或更新設定位置範本，以反映您想要用於 UE-V 電腦的 UE-V Agent 範本配置。

    **記事** 電腦上的範本每天都會更新。 更新是以設定範本目錄的變更為基礎。

     

3.  若要在執行 UE-V Agent 的電腦上手動更新範本，請開啟提升許可權的命令提示字元，然後流覽到 **% Program Files%\\Microsoft 使用者體驗虛擬化 \\ Agent \\ &lt; x86 或 x64 &gt; **，然後執行**ApplySettingsTemplateCatalog.exe**。

    **記事** 這個程式會在電腦啟動期間自動執行，而在3:30 時則會在 M。 收集最近新增到目錄中的任何新範本。

     






## 相關主題


[準備 UE-V a.x 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[部署 UE-V 2.x 的必要功能](deploy-required-features-for-ue-v-2x-new-uevv2.md)

 

 





