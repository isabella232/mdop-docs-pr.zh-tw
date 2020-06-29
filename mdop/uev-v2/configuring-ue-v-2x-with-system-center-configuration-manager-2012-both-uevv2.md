---
title: 使用 System Center Configuration Manager 2012 設定 UE-V 2. x
description: 使用 System Center Configuration Manager 2012 設定 UE-V 2. x
author: dansimp
ms.assetid: 9a4e2a74-7646-4a77-b58f-2b4456487295
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 2ff9ccc1a17db31471549ece37461558768c3a2b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810538"
---
# 使用 System Center Configuration Manager 2012 設定 UE-V 2. x


在您安裝 Microsoft 使用者體驗 Virtualization （UE-V）2.0、2.1 或 2.1 SP1 及其必要功能之後，就必須設定 UE-V。 UE-V 設定套件提供一種方式，讓管理員使用 System Center Configuration Manager 2012 SP1 或更新版本的相容性設定功能，在安裝了 UE-V 和 Configuration Manager 的各個網站上套用一致的配置。

## UE-V Configuration Pack 支援的功能


UE-V Configuration Pack 包括執行下列工作的工具：

-   建立或更新 UE-V 設定位置範本發佈比較基準。

    -   定義要註冊或取消註冊的 UE-V 範本

    -   在新增或更新範本時更新 UE-V 範本設定專案和比較基準

    -   使用標準設定專案修正來散佈及註冊 UE-V 範本

-   建立或更新 UE-V Agent 策略設定專案，以設定或清除這些設定。

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>套件大小上限</p></td>
    <td align="left"><p>啟用/停用 Windows 應用程式同步處理</p></td>
    <td align="left"><p>在應用程式啟動時等待同步處理</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>設定匯入延遲</p></td>
    <td align="left"><p>同步未列出的 Windows 應用程式</p></td>
    <td align="left"><p>在登入後等待同步處理</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>設定匯入通知</p></td>
    <td align="left"><p>IT 連絡人 URL</p></td>
    <td align="left"><p>等待同步處理超時</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>設定儲存路徑</p></td>
    <td align="left"><p>IT 連絡人描述文字</p></td>
    <td align="left"><p>設定範本目錄路徑</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>啟用同步處理</p></td>
    <td align="left"><p>已啟用工作列圖示</p></td>
    <td align="left"><p>開始/停止 UE-V agent 服務</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>同步處理方法</p></td>
    <td align="left"><p>第一次使用通知</p></td>
    <td align="left"><p>定義哪些 Windows 應用程式將漫遊設定</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>同步處理超時</p></td>
    <td align="left"><p></p></td>
    <td align="left"><p></p></td>
    </tr>
    </tbody>
    </table>

     

-   確認 UE-V 正在執行，以驗證合規性。

## 產生 UE-V Agent 原則設定項目


所有 UE-V Agent 原則和設定都是透過使用 UevAgentPolicyGenerator.exe 工具所產生的單一設定專案來發佈。 這個工具會從 XML 設定檔中讀取所需的設定，並建立 CI，其中包含將電腦納入合規性所需的探索與修正設定。

UE-V Agent 原則設定專案 CAB 檔案是使用 UevTemplateBaselineGenerator.exe 命令列工具建立的，其中包含下列參數：

-   網站 &lt; 網站程式碼&gt;

-   PolicyName &lt; 名稱 &gt; 選用：預設為 "Ue-v Agent Policy" （如果沒有的話）

-   PolicyDescription &lt; 說明 &gt; （選用）：如果不存在，就會提供描述

-   CabFilePath &lt; 設定項目的完整路徑。CAB 檔&gt;

-   ConfigurationFile &lt; 代理程式配置 XML 檔案的完整路徑&gt;

**記事** 可能需要變更 PowerShell 執行原則，以允許這些腳本在您的環境中執行。 在 Configuration Manager 主控台中執行這些步驟：

1.  選取**管理 &gt; 用戶端設定 &gt; 屬性**

2.  在 [**使用者代理程式**] 索引標籤中，將**PowerShell 執行原則**設定為 [**略過**]

<a href="" id="create"></a>**建立第一個 UE-V 原則設定項目**

1.  從 UE-V Config Pack 安裝目錄將預設設定配置檔案複製到您的 ConfigMgr 系統管理主控台可看見的位置：

    ``` syntax
    C:\Program Files (x86)\Microsoft User Experience Virtualization\ConfigPack\AgentConfiguration.xml c:\<target path>
    ```

    預設的設定檔包含五個區段：

    <a href="" id="computer-policy"></a>**電腦原則**  
    所有 UE-V 電腦層級設定。 DesiredState 屬性可以是

    -   **設定**為在註冊表中指派值

    -   **清除**以移除設定

    -   **未受管理**，無法將設定項目保留在目前狀態

    請勿移除此區段中的線條。 相反地，如果您不想讓 Configuration Manager 變更目前或預設值，請將 DesiredState 設定為 [未受管理的]。

    <a href="" id="currentcomputeruserpolicy"></a>**CurrentComputerUserPolicy**  
    所有 UE-V 使用者層級設定。 這些專案會覆寫使用者的電腦設定。 DesiredState 屬性可以是

    -   **設定**為在註冊表中指派值

    -   **清除**以移除設定

    -   **未受管理**，無法將設定項目保留在目前狀態

    請勿移除此區段中的線條。 相反地，如果您不想讓 Configuration Manager 變更目前或預設值，請將 DesiredState 設定為 [未受管理的]。

    <a href="" id="services"></a>**服務**  
    此區段控制服務作業中的專案。 預設的設定檔包含 UevAgentService 的單一專案。 DesiredState 屬性可以**設定為 [** 執行] 或 [**停止**]。

    <a href="" id="windows8appscomputerpolicy"></a>**Windows8AppsComputerPolicy**  
    所有電腦層級 Windows 應用程式同步處理設定。 此區段中所列的每個 PackageFamilyName 都可以指派 DesiredState

    -   **已啟用**[設定] 漫遊

    -   [**已停用**] 以防止漫遊的設定

    -   已**清除**以從 ue-v 控制項移除專案

    您可以根據已安裝的 Windows app 清單（可使用 PowerShell Cmdlet GetAppxPackage 查看），在此區段中新增其他行。

    <a href="" id="windows8appscurrentcomputeruserpolicy"></a>**Windows8AppsCurrentComputerUserPolicy**  
    與 Windows8AppsComputerPolicy 相同，其設定會覆寫個別使用者的電腦設定。

2.  變更 [所需的狀態] 和 [值] 欄位以編輯設定檔。

3.  在執行 ConfigMgr 系統管理主控台的電腦上執行此命令：

    ``` syntax
    C:\Program Files (x86)\Microsoft User Experience Virtualization\ConfigPack\UevAgentPolicyGenerator.exe –Site ABC –CabFilePath "C:\MyCabFiles\UevPolicyItem.cab" –ConfigurationFile "c:\AgentConfiguration.xml"
    ```

4.  使用 ConfigMgr 主機或 PowerShell Import 匯入 CAB 檔案 CMConfigurationItem

**更新 UE-V 原則設定專案**

1.  變更 [所需的狀態] 和 [值] 欄位以編輯設定檔。

2.  在[建立第一個 Ue-v 原則設定專案](#create)中，從步驟3執行命令。 如果您使用 PolicyName 參數變更了名稱，請確認輸入相同的名稱。

3.  重新導入 CAB 檔案。 將會更新 ConfigMgr 中的版本。

## 產生 UE-V 範本比較基準
UE-V 範本是使用包含多個設定專案的比較基準來散佈。 每個設定專案都包含安裝一個 UE-V 範本所需的探索與修正腳本。 實際的 UE-V 範本內嵌在修正腳本中，以使用標準設定專案功能進行發佈。

UE-V 範本比較基準是使用 UevTemplateBaselineGenerator.exe 命令列工具建立的，其中包含下列參數：

-   網站 &lt; 網站程式碼&gt;

-   BaselineName &lt; 名稱 &gt; （選用：預設為 "Ue-v 範本發佈比較基準" （如果沒有的話））

-   BaselineDescription &lt; 說明 &gt; （選用：如果不存在，就會提供描述）

-   TemplateFolder &lt; ue-v 範本資料夾&gt;

-   註冊 &lt; 逗號分隔的範本檔案清單&gt;

-   取消註冊 &lt; 以逗號分隔的範本清單&gt;

-   CabFilePath 要 &lt; 產生的基線 CAB 檔案完整路徑&gt;

結果是已準備好匯入 Configuration Manager 的基線 CAB 檔案。 如果您是在未來的日期更新或新增範本，您可以使用相同的比較基準名稱重新執行命令。 匯入 CAB 會導致 CI 版本在變更的範本上更新。

### <a href="" id="create2"></a>建立第一個 UE-V 範本比較基準

1.  在執行 ConfigMgr 系統管理主控台的電腦可見的穩定資料夾位置中，建立一組 UE-V 範本。 在新增或更新範本時，此資料夾是用來進行發佈的位置。 範本的初始清單可以從安裝了 UE-V 的電腦複製。 預設範本位置是 C:\\program files Files\\Microsoft 使用者體驗 Virtualization\\Templates。

2.  建立 text.bat 檔案，您可以在其中新增 [範本發生器] 命令。 這是選擇性的，但如果您儲存命令參數，就會使再生更簡單。

3.  將命令和參數新增至將產生比較基準的 .bat 檔案。 下列範例會建立一個分發記事本和計算機的比較基準：

    ``` syntax
    C:\Program Files (x86)\Microsoft User Experience Virtualization\ConfigPack\UevTemplateBaselineGenerator.exe –Site "ABC" –TemplateFolder "C:\ProductionUevTemplates" –Register "MicrosoftNotepad.xml, MicrosoftCalculator.xml" –CabFilePath "C:\MyCabFiles\UevTemplateBaseline.cab"
    ```

4.  執行 .bat 檔案，建立 UevTemplateBaseline.cab 準備匯入 Configuration Manager。

### 更新 UE-V 範本比較基準

範本發生器使用範本版本來判斷是否應該更新範本。 如果您進行範本變更並更新版本，比較基準發生器會將主資料夾中的範本與 ConfigMgr 伺服器上 CI 中包含的範本進行比較。 如果找到差異，就會更新產生的比較基準與已修改的 CI 版本。

若要散佈新的記事本範本，請執行下列步驟：

1.  更新位於 &lt; 範本之版本元素中的範本和範本版本 &gt; 。

2.  將範本複製到您的主範本目錄。

3.  在[建立第一個 Ue-v 範本比較基準](#create2)的 .bat 檔案中，執行您在步驟3所建立的命令。

4.  使用主控台或 PowerShell 匯入 CMBaseline，將產生的 CAB 檔案匯入到 ConfigMgr。

## 取得 UE-V Configuration Pack


Configuration Manager 2012 SP1 或更新版本的 UE-V Configuration Pack 可以在[此](https://go.microsoft.com/fwlink/?LinkId=317263)下載。






## 相關主題


[管理 UE-V 2.x 的設定](manage-configurations-for-ue-v-2x-new-uevv2.md)

 

 





