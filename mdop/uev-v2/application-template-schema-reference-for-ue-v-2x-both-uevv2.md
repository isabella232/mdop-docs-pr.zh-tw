---
title: UE-V 2. x 的應用程式範本架構參考
description: UE-V 2. x 的應用程式範本架構參考
author: dansimp
ms.assetid: be8735a5-6a3e-4b1f-ba14-2a3bc3e5a8b6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 03ff6eabae68f07c23d5977f901e6a90e292c6ac
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812338"
---
# UE-V 2. x 的應用程式範本架構參考


Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 和 2.1 SP1 使用 XML 設定位置範本來定義由 UE-V 捕獲並套用的桌面應用程式設定和 Windows 設定。 UE-V 包含一組預設的設定位置範本。 您也可以使用 UE-V 發生器建立自訂設定位置範本。

[高級使用者] 可自訂 [設定位置] 範本的 XML 檔案。 本主題詳細說明 UE-V 2.1 （SP1）和2.0 設定位置範本的 XML 結構，並提供編輯這些檔案的指導方針。

## UE-V 2.1 和 2.1 SP1 應用程式範本架構參考


本節詳細說明 UE-V 2.1 和 2.1 SP1 設定位置範本的 XML 結構，並提供編輯此檔案的指導方針。

### 本節內容

-   [XML 宣告與編碼屬性](#xml21)

-   [命名空間與根項目](#namespace21)

-   [資料類型](#data21)

-   [Name 元素](#name21)

-   [識別碼元素](#id21)

-   [Version 元素](#version21)

-   [Author 元素](#author21)

-   [進程與程式元素](#processes21)

-   [Application 元素](#application21)

-   [常見元素](#common21)

-   [SettingsLocationTemplate 元素](#settingslocationtemplate21)

-   [附錄： SettingsLocationTemplate](#appendix21)

### <a href="" id="xml21"></a>XML 宣告與編碼屬性

**強制： True**

**類型： String**

XML 聲明必須指定 XML 版本1.0 屬性（ &lt; ？ XML 版本 = "1.0" &gt; ）。 由 UE-V 發生器建立的設定位置範本會儲存為 UTF-8 編碼，但不明確指定編碼。 我們建議您在這個元素中包含 encoding = "UTF-8" 屬性來做為最佳做法。 產品隨附的所有範本也會指定此標記（請參閱%ProgramFiles%\\Microsoft 使用者體驗 Virtualization\\Templates 中的檔以瞭解參考）。 例如：

`<?xml version="1.0" encoding="UTF-8"?>`

### <a href="" id="namespace21"></a>命名空間與根項目

**強制： True**

**類型： String**

UE-V 使用 https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate 所有應用程式的命名空間。 SettingsLocationTemplate 是根項目，且包含所有其他元素。 使用此標記的所有範本中的參照 SettingsLocationTemplate：

`<SettingsLocationTemplate xmlns='https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate'>`

### <a href="" id="data21"></a>資料類型

以下是 UE-V 應用程式範本架構的資料類型。

<a href="" id="guid"></a>**GUID**GUID 描述標準的全域唯一識別碼正則運算式，形式為 "\\ {\ [a-fA-F0-9 \] {8} -\ [a-fa-F0-9 \]- {4} \] [a-FA-F0-9 \] {4} -\ [a-fa-F0-9 \] {4} -\ [a-fa-F0-9 \] {12} \}"。 這會在 Filesetting\\Root\\KnownFolder 元素中使用，以驗證已知資料夾的格式設定。

<a href="" id="filenamestring"></a>**FilenameString**FilenameString 是指要監視之程式的檔案名。 它的值會受到 RegEx \ [^ \\ \\ * \ \ | &lt; &gt;/： \] +，（也就是說，它們可能不包含反斜線字元、星號或問號萬用字元、管道字元、大於或小於符號、轉寄斜線或冒號字元）。

<a href="" id="idstring"></a>**IDString**IDString 指的是應用程式元素、SettingsLocationTemplate 及常見元素的識別碼值（用來描述共用一般設定的應用程式套件）。 它受到與 FilenameString 相同的 RegEx （\ [^ \\ \\ \\？ \\ * \\ | &lt; &gt;/:\]+).

<a href="" id="templateversion"></a>**TemplateVersion**TemplateVersion 是一個整數值，用於描述設定位置範本的修訂。 其值的範圍可以是0到2147483647。

<a href="" id="empty"></a>**空白**空白代表 null 值。 這會在 Process\\ShellProcess 中使用，表示沒有任何程式可供監視。 您不應該在任何應用程式範本中使用這個值。

<a href="" id="author"></a>**作者**[作者] 資料類型是一種複雜類型，可用於識別範本的作者。 它包含兩個子項目： [**名稱**] 和 [**電子郵件**]。 在 Author 資料類型中，Name 元素是必要的，而 Email 元素是選擇性的。 此類型會在 SettingsLocationTemplate 元素下更詳細的說明。

<a href="" id="range"></a>**範圍**範圍定義由兩個子項目組成的整數類別： [**最小值**] 和 [**最大值**]。 此資料類型是在 ProcessVersion 資料類型中實現。 如果已指定，則必須包含最小值和最大值。

<a href="" id="processversion"></a>**ProcessVersion**ProcessVersion 會定義含有四個子項目的類型：**主要**、**次要**、**組建**及**修補程式**。 此資料類型是由 Process 元素用來填入其 ProductVersion 和 FileVersion 值。 此類型的資料是範圍值。 主要子項目是強制性的，而其他則是選擇性的。

<a href="" id="architecture"></a>**架構**結構列舉了兩個可能的值： **Win32**和**Win64**。 這些值是用來指定處理常式體系結構。

<a href="" id="process"></a>**處理**程式[流程] 資料類型是用來描述要由 UE-V 監視之進程的容器。 它包含六個子項目： **Filename**、**結構**、 **ProductName**、 **FileDescription**、 **ProductVersion**和**FileVersion**。 下表詳細說明每個元素各自的資料類型：

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>元素</strong></p></td>
<td align="left"><p><strong>資料類型</strong></p></td>
<td align="left"><p><strong>Mandatory</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>副檔名</p></td>
<td align="left"><p>FilenameString</p></td>
<td align="left"><p>True</p></td>
</tr>
<tr class="odd">
<td align="left"><p>架構</p></td>
<td align="left"><p>架構</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="even">
<td align="left"><p>ProductName</p></td>
<td align="left"><p>字串</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="odd">
<td align="left"><p>FileDescription</p></td>
<td align="left"><p>字串</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="even">
<td align="left"><p>ProductVersion</p></td>
<td align="left"><p>ProcessVersion</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="odd">
<td align="left"><p>FileVersion</p></td>
<td align="left"><p>ProcessVersion</p></td>
<td align="left"><p>False</p></td>
</tr>
</tbody>
</table>

 

<a href="" id="processes"></a>**處理**程式[進程] 資料類型代表一或多個處理元素集合的容器。 進程式列類型支援兩個子項目： **Process**與**ShellProcess**。 Process 是 Process 類型的元素，且 ShellProcess 的資料類型為空白。 在順序中至少必須辨識一個專案。

<a href="" id="path"></a>**路徑**RegistrySetting 和 FileSetting 會使用 Path 來參照登錄和檔案路徑。 這個元素支援兩個選用的屬性： **Recursive**與**DeleteIfNotFound**。 這兩個值都設定為 default = "False"。

Recursive：表示檔案設定中包含路徑和所有子資料夾，或是所有的子登錄機碼都包含在註冊設定中。 在這兩種情況下，目前層級的所有專案都會包含在捕獲的資料中。 針對 FileSettings 物件，指定資料夾中的所有檔案都包含在 UE-V 捕獲的資料中，但不包含資料夾。 針對登錄路徑，會捕獲目前路徑中的所有值，但不會捕獲子登錄機碼。 在這兩種情況下，請小心考慮避免捕獲大型資料集或大量專案。

DeleteIfNotFound 屬性會從使用者的設定儲存路徑資料中移除設定。 在從套件中移除這些設定時，可能需要這麼做，將大量磁碟空間儲存在設定儲存路徑檔案伺服器上。

<a href="" id="filemask"></a>**FileMask**FileMask 僅指定由 Path 所定義之資料夾的特定檔案類型。 例如，Path 可能是， `C:\users\username\files` 且 FileMask `*.txt` 只能包含文字檔。

<a href="" id="registrysetting"></a>**RegistrySetting**RegistrySetting 代表登錄機碼和值的容器，以及 UE-V Agent 元件上相關聯的所需行為。 此類型中定義了四個子項目： **path**、 **Name**、 **Exclude**以及值**Path**和**Name**的順序。

<a href="" id="filesetting"></a>**FileSetting**FileSetting 包含與檔案和檔案路徑相關聯的參數。 定義了四個子項目： **Root**、 **Path**、 **FileMask**及**Exclude**。 Root 是強制性的，而其他則是選擇性的。

<a href="" id="settings"></a>**設定**[設定] 是適用于特定範本之所有設定的容器。 它包含前面所述的登錄、檔案、SystemParameter 及 CustomAction 設定的實例。 此外，它也可以包含下列含有行為的子項目：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>元素</strong></p></td>
<td align="left"><p><strong>描述</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>非同步</p></td>
<td align="left"><p>在不封鎖應用程式啟動的情況下，會套用非同步設定套件，讓應用程式在設定仍在套用時開始進行。 這對於可以非同步套用的設定（例如 <code>get/set</code> ，透過 API （例如 SystemParameterSetting）而言很有用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>PreventOverlappingSynchronization</p></td>
<td align="left"><p>根據預設，UE-V 只會在使用範本的最後一個應用程式實例關閉時，儲存應用程式的設定。 當這個元素設定為 ' false」時，UE-V 會匯出設定，即使有應用程式的其他實例正在執行也一樣。 適合使用由 UE-V 隨附的常見元素區段的範本（包含通用元素區段）使用此標誌來啟用共用設定，以避免在應用程式關閉時匯出應用程式特定的設定，但在最後一個實例關閉之後，才會進行匯出。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AlwaysApplySettings</p></td>
<td align="left"><p>（2.1 中引入）</p>
<p>此參數會強制會套用匯入的設定套件，即使套件與應用程式的目前狀態之間沒有任何差異也一樣。 這個參數只能在特殊的情況中使用，因為它會減緩設定匯入的速度。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="name21"></a>Name 元素

**強制： True**

**類型： String**

名稱指定 [設定位置] 範本的唯一名稱。 這用於在 WMI、PowerShell、事件檢視器和調試記錄中參照範本時的顯示用途。 一般來說，請避免參照版本資訊，因為這可以從 ProductVersion 元素中 objected。 例如，請指定 `<Name>My Application</Name>` （而非） `<Name>My Application 1.1</Name>` 。

**記事** UE-V 不會參照外部 Dtd，所以無法在設定位置範本中使用命名實體。 例如，請勿用 &reg; 來參照已註冊的商業標誌簽署®。 相反地，請改用規範編號參照來包含這些類型的特殊字元，例如，®字元 & \ #174。 此規則適用于此檔中的所有字串值。

<http://www.w3.org/TR/xhtml1/dtds.html>如需字元實體的完整清單，請參閱。 UTF-8 編碼的檔可能會直接包含 Unicode 字元。 透過 UE-V 發生器儲存範本時會自動將字元實體轉換成其 Unicode 代表。

 

### <a href="" id="id21"></a>識別碼元素

**強制： True**

**類型： String**

[識別碼] 會填入特定範本的唯一識別碼。 此標記會成為 UE-V Agent 在執行時間參考範本時所用的主要識別碼（例如，請參閱 UevTemplate 和 UevTemplateProgram PowerShell Cmdlet 的輸出）。 根據慣例，此標記不應包含任何空格，以簡化腳本撰寫。 應用程式的版本號碼應該在這個元素中指定，以便更輕鬆地識別範本，例如 `<ID>MicrosoftCalculator6</ID>` 或 `<ID>MicrosoftOffice2010Win64</ID>` 。

### <a href="" id="version21"></a>Version 元素

**強制： True**

**類型： Integer**

**最小值：0**

**最大值：2147483647**

[版本] 可識別 [設定位置] 範本的版本，以進行系統管理追蹤變更。 每次儲存範本時，UE-V 發生器都會自動將這個數位遞增1。 請注意，這個欄位必須是整數整數;分數值，例如 `<Version>2.5</Version>` 不允許。

**提示：** 您可以使用 XML comment 標記儲存有關版本變更 `<!-- -->` 的筆記，例如：

```xml
  <!--
     Version History

     Version 1 Jul 05, 2012 Initial template created by Generator - Denise@Contoso.com
     Version 2 Jul 31, 2012 Added support for app.exe v2.1.3 - Mark@Contoso.com
     Version 3 Jan 01, 2013 Added font settings support - Mark@Contoso.com
     Version 4 Jan 31, 2013 Added support for plugin settings - Tony@Contoso.com
   -->
  <Version>4</Version>
```

**重要** 系統會詢問此值，以判斷是否應該在這些範例中將範本的新版本套用至現有的範本：

-   排程範本自動更新工作執行時

-   在執行更新 UevTemplate PowerShell Cmdlet 時

-   透過 WMI 呼叫 microsoft\\uev： SettingsLocationTemplate Update 方法時

 

### <a href="" id="author21"></a>Author 元素

**強制： False**

**類型： String**

[作者] 會識別 [設定位置] 範本的建立者。 支援兩個選用的子項目： [**名稱**] 和 [**電子郵件**]。 這兩個屬性都是選擇性的，但如果指定了電子郵件子項目，則它必須伴隨 Name 元素。 [作者] 是指 [設定位置] 範本的連絡人完整名稱，而電子郵件應該是代表作者的電子郵件地址。 我們建議您在發佈的範本中包含這項資訊，例如，在[Ue-v 範本圖庫](https://gallery.technet.microsoft.com/site/search?f%5B0%5D.Type=RootCategory&f%5B0%5D.Value=UE-V)中。

### <a href="" id="processes21"></a>進程與程式元素

**強制： True**

**Type：元素**

進程至少包含一個 `<Process>` 元素，而該元素又包含下列子項目： **Filename**、**結構**、 **ProductName**、 **FileDescription**、 **ProductVersion**和**FileVersion**。 Filename 子項目是強制性的，而其他則是選擇性的。 完全填入的元素包含與此範例類似的標記：

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <Architecture>Win64</Architecture>
  <ProductName> MyApplication </ProductName>
  <FileDescription>MyApplication.exe</FileDescription>
  <ProductVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </FileVersion>
</Process>
```

### 副檔名

**強制： True**

**類型： String**

Filename 指的是可執行檔在檔案系統中出現的實際檔案名。 這個元素指定 UE-V 用來評估範本是否適用于流程的主要準則。 這個元素必須在 [設定位置] 範本 XML 中指定。

有效的檔案名必須與正則運算式 \ [^ \\ \\ \ \？ \\ * \ | &lt; &gt;/： \] +，也就是不能包含反斜線字元、星號或問號萬用字元、管道字元、大於或小於符號、轉寄斜線或冒號（\\？ \* |&lt; &gt; /或：個字元）。

**提示：** 若要對照此 RegEx 測試字串，請使用 PowerShell 命令視窗，並將您的可執行檔名稱取代為**YourFileName**：

`"YourFileName.exe" -match  "[\\\?\*\|<>/:]+"`

**True**值表示字串包含非法字元。 以下是非法值的一些範例：

-   \\\\server\\share\\program.exe

-   Program \ * .exe

-   Pro？ ram.exe

-   程式 &lt; 1 &gt; .exe

**記事** UE-V 發生器分別對大於和小於字元進行編碼 &gt; &lt; 。

 

在極少數情況下，FileName 值不一定包括 .exe 副檔名，但應該將它指定為值的一部分。 例如， `<Filename>MyApplictication.exe</Filename>` 應指定而不是 `<Filename>MyApplictication</Filename>` 。 如果可執行檔的實際名稱是「MyApplication.exe」，則第二個範例不會將範本套用至程式。

### 架構

**強制： False**

**類型：結構（字串）**

結構指的是編譯目標可執行檔的處理器架構。 有效值為32位應用程式的 Win32，或64位應用程式的 Win64。 如果有，此標記會將 [設定位置] 範本的適用性限制為特定的應用程式結構。 如需這種情況的範例，請比較%ProgramFiles%\\Microsoft 使用者體驗 Virtualization\\templates\\ MicrosoftOffice2010Win32.xml 與 UE-V 隨附的 MicrosoftOffice2010Win64.xml 檔案。 當相對路徑在不同版本的可執行檔之間變更，或在從一個處理器架構移到另一個時，如果已新增或移除設定，這就很有用。

如果此元素不存在，則設定位置範本會忽略進程的體系結構，並同時適用于32和64位程式（如果有的話）。

**記事** UE-V 在這個版本中不支援 ARM 處理器。

 

### ProductName

**強制： False**

**類型： String**

ProductName 是一個可供您用來識別管理用途或報告之產品的選用元素。 ProductName 與 Filename 不同，因為它的值沒有正則運算式限制。 這可讓您更輕鬆地瞭解可執行檔名稱可能不明顯的程式說明。 例如：

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <ProductName>My Application 6.x by Contoso.com</ProductName>
  <ProductVersion>
    <Major Minimum="6" Maximum="6" />
  </ProductVersion>
</Process>
```

### FileDescription

**強制： False**

**類型： String**

FileDescription 是一個可執行檔的系統管理描述的選擇性標記。 這是自由文字欄位，在您需要識別可執行檔之功能的軟體套件中，可能會有説明。

例如，在適用的應用程式中，提供兩個可執行檔（MyApplication.exe 和 MyApplicationHelper.exe）功能的提醒可能會很有用，如下所示：

```xml
<Processes>
  <Process>
    <Filename>MyApplication.exe</Filename>
    <FileDescription>My Application Main Engine</ FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
  <Process>
    <Filename>MyApplicationHelper.exe</Filename>
    <FileDescription>My Application Background Process Executable</FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
</Processes>
```

### ProductVersion

**強制： False**

**類型： String**

ProductVersion 指的是檔案的主要及次要產品版本，以及組建與修補程式層級。 ProductVersion 是一個選用的元素，但如果有指定，它必須包含至少主要的子項目。 此值必須以最小值為 "X" 的範圍來表示最大值 = "X" 上限 = "Y"，其中 X 和 Y 為整數。 [最小值] 和 [最大值] 可以完全相同。

產品和檔案版本元素可能是未指定的。 如此一來，就會將範本設為「不限版本」，這表示該範本會套用至指定的可執行檔的所有版本。

**範例 1：**

UE-V 發生器中指定的產品版本：1.0 會產生下列 XML：

```xml
<ProductVersion>
  <Major Minimum="1" Maximum="1" />
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

**範例 2：**

檔版本： UE-V 發生器中指定的5.0.2.1000 會產生下列 XML：

```xml
<FileVersion>
  <Major Minimum="5" Maximum="5" />
  <Minor Minimum="0" Maximum="0" />
  <Build Minimum="2" Maximum="2" />
  <Patch Minimum="1000" Maximum="1000" />
</FileVersion>
```

**不正確的範例1–不完整範圍：**

只有最小屬性出現。 範圍中也必須包含最大值。

```xml
<ProductVersion>
  <Major Minimum="2" />
</ProductVersion>
```

**不正確的範例2–指定的次要元素沒有主要元素：**

只有次要元素存在。 還必須包含主要版本。

```xml
<ProductVersion>
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

### FileVersion

**強制： False**

**類型： String**

FileVersion 會區分已發佈應用程式的發行版本本，以及元件可執行檔的內部組建詳細資料。 對於大多數商業應用程式而言，這些號碼是完全相同的。 在其他情況下，檔案的產品版本會指示檔案的一般版本識別，而檔案版本則表示檔案的特定組建（例如，修補程式或更新的情況）。 這會唯一識別檔案，而不會中斷偵測邏輯。

若要判斷特定可執行檔的產品版本和檔案版本，請以滑鼠右鍵按一下 Windows 資源管理器中的檔案，選取 [屬性]，然後按一下 [詳細資料] 索引標籤。

包含應用程式的 FileVersion 元素可讓您更精確地微調偵測邏輯，但對於大部分的應用程式來說，不是必要的。 首先會選取 [ProductVersion] 元素設定，然後 FileVersion [已核取]。 您將會套用限制性較強的設定。

FileVersion 的子項目和語法規則與 ProductVersion 相同。

```xml
<Process>
  <Filename>MSACCESS.EXE</Filename>
  <Architecture>Win32</Architecture>
  <ProductVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </FileVersion>
</Process>
```

### <a href="" id="application21"></a>Application 元素

應用程式是適用于特定應用程式的設定容器。 它是下欄欄位/類型的集合。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>欄位/類型</strong></p></td>
<td align="left"><p><strong>描述</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Name</p></td>
<td align="left"><p>指定 [設定位置] 範本的唯一名稱。 這用於在 WMI、PowerShell、事件檢視器和調試記錄中參照範本時的顯示用途。 如需詳細資訊，請參閱 <a href="#name21" data-raw-source="[Name](#name21)"> Name </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>識別碼</p></td>
<td align="left"><p>填入特定範本的唯一識別碼。 此標記會成為 UE-V Agent 在執行時間參考範本時所用的主要識別碼。 如需詳細資訊，請參閱 <a href="#id21" data-raw-source="[ID](#id21)"> 識別碼 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>描述</p></td>
<td align="left"><p>範本的選用描述。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LocalizedNames</p></td>
<td align="left"><p>UI 中顯示的選擇性名稱，由語言地區設定當地語系化。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LocalizedDescriptions</p></td>
<td align="left"><p>依語言地區設定當地語系化的選用範本描述。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>版本</p></td>
<td align="left"><p>識別 [設定位置] 範本的版本，以進行系統管理追蹤變更。 如需詳細資訊，請參閱 <a href="#version21" data-raw-source="[Version](#version21)"> 版本 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeferToMSAccount</p></td>
<td align="left"><p>控制是否將此範本與 Microsoft 帳戶搭配使用。 如果已針對電腦上的使用者啟用 MSA 同步處理，則會自動停用此範本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DeferToOffice365</p></td>
<td align="left"><p>與 MSA 類似，這會控制是否與 Office365 搭配使用此範本。 如果您使用 Office 365 來同步處理設定，此範本會自動停用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>FixedProfile （2.1 中引入）</p></td>
<td align="left"><p>指定這個範本只能與此元素中指定的設定檔相關聯，而且無法透過 WMI 或 PowerShell 進行變更。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>處理程序</p></td>
<td align="left"><p>一個或多個處理元素集合的容器。 如需詳細資訊，請參閱 <a href="#processes21" data-raw-source="[Processes](#processes21)"> 進程 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定</p></td>
<td align="left"><p>適用于特定範本之所有設定的容器。 它包含 Registry、File、SystemParameter 和 CustomAction 設定的實例。 如需詳細資訊，請參閱 <strong> </strong> 資料類型中的設定 <a href="#data21" data-raw-source="[Data types](#data21)"> </a> 。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="common21"></a>常見元素

[常用] 與應用程式元素類似，但它永遠與兩個或更多個應用程式元素相關聯。 [常見] 區段代表在這些應用程式實例之間共用的一組設定。 它是下欄欄位/類型的集合。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>欄位/類型</strong></p></td>
<td align="left"><p><strong>描述</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Name</p></td>
<td align="left"><p>指定 [設定位置] 範本的唯一名稱。 這用於在 WMI、PowerShell、事件檢視器和調試記錄中參照範本時的顯示用途。 如需詳細資訊，請參閱 <a href="#name21" data-raw-source="[Name](#name21)"> Name </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>識別碼</p></td>
<td align="left"><p>填入特定範本的唯一識別碼。 此標記會成為 UE-V Agent 在執行時間參考範本時所用的主要識別碼。 如需詳細資訊，請參閱 <a href="#id21" data-raw-source="[ID](#id21)"> 識別碼 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>描述</p></td>
<td align="left"><p>範本的選用描述。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LocalizedNames</p></td>
<td align="left"><p>UI 中顯示的選擇性名稱，由語言地區設定當地語系化。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LocalizedDescriptions</p></td>
<td align="left"><p>依語言地區設定當地語系化的選用範本描述。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>版本</p></td>
<td align="left"><p>識別 [設定位置] 範本的版本，以進行系統管理追蹤變更。 如需詳細資訊，請參閱 <a href="#version21" data-raw-source="[Version](#version21)"> 版本 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeferToMSAccount</p></td>
<td align="left"><p>控制是否將此範本與 Microsoft 帳戶搭配使用。 如果已針對電腦上的使用者啟用 MSA 同步處理，則會自動停用此範本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DeferToOffice365</p></td>
<td align="left"><p>與 MSA 類似，這會控制是否與 Office365 搭配使用此範本。 如果您使用 Office 365 來同步處理設定，此範本會自動停用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>FixedProfile （2.1 中引入）</p></td>
<td align="left"><p>指定這個範本只能與此元素中指定的設定檔相關聯，而且無法透過 WMI 或 PowerShell 進行變更。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>設定</p></td>
<td align="left"><p>適用于特定範本之所有設定的容器。 它包含 Registry、File、SystemParameter 和 CustomAction 設定的實例。 如需詳細資訊，請參閱 <strong> </strong> 資料類型中的設定 <a href="#data21" data-raw-source="[Data types](#data21)"> </a> 。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="settingslocationtemplate21"></a>SettingsLocationTemplate 元素

這個元素定義單一應用程式或一套應用程式的設定。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>欄位/類型</strong></p></td>
<td align="left"><p><strong>描述</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Name</p></td>
<td align="left"><p>指定 [設定位置] 範本的唯一名稱。 這用於在 WMI、PowerShell、事件檢視器和調試記錄中參照範本時的顯示用途。 如需詳細資訊，請參閱 <a href="#name21" data-raw-source="[Name](#name21)"> Name </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>識別碼</p></td>
<td align="left"><p>填入特定範本的唯一識別碼。 此標記會成為 UE-V Agent 在執行時間參考範本時所用的主要識別碼。 如需詳細資訊，請參閱 <a href="#id21" data-raw-source="[ID](#id21)"> 識別碼 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>描述</p></td>
<td align="left"><p>範本的選用描述。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LocalizedNames</p></td>
<td align="left"><p>UI 中顯示的選擇性名稱，由語言地區設定當地語系化。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LocalizedDescriptions</p></td>
<td align="left"><p>依語言地區設定當地語系化的選用範本描述。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="appendix21"></a>附錄： SettingsLocationTemplate

以下是 SettingsLocationTemplate 檔案，其中顯示其元素、子項目、屬性和參數：

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="UevSettingsLocationTemplate"
  targetNamespace="https://schemas.microsoft.com/UserExperienceVirtualization/2013A/SettingsLocationTemplate"
  elementFormDefault="qualified"
  xmlns="https://schemas.microsoft.com/UserExperienceVirtualization/2013A/SettingsLocationTemplate"
  xmlns:mstns="https://schemas.microsoft.com/UserExperienceVirtualization/2013A/SettingsLocationTemplate"
  xmlns:xs="http://www.w3.org/2001/XMLSchema">

    <xs:simpleType name="Guid">
        <xs:restriction base="xs:string">
            <xs:pattern value="\{[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{12}\}" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="FilenameString">
        <xs:restriction base="xs:string">
            <xs:pattern value="[^\\\?\*\|&lt;&gt;/:]+" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="IDString">
        <xs:restriction base="xs:string">
            <xs:pattern value="[^\\\?\*\|&lt;&gt;/:.]+" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="CompositeIDString">
        <xs:restriction base="xs:string">
            <xs:pattern value="[^\\\?\*\|&lt;&gt;/:.]+([.][^\\\?\*\|&lt;&gt;/:.]+)?" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="TemplateVersion">
        <xs:restriction base="xs:integer">
            <xs:minInclusive value="0" />
            <xs:maxInclusive value="2147483647" />
        </xs:restriction>
    </xs:simpleType>

    <xs:complexType name="Empty">
        <xs:sequence/>
    </xs:complexType>

    <xs:complexType name="LocalizedString">
        <xs:simpleContent>
            <xs:extension base="xs:string">
                <xs:attribute name="Locale" type="xs:string" use="required"/>
            </xs:extension>
        </xs:simpleContent>
    </xs:complexType>

    <xs:complexType name="LocalizedName">
        <xs:sequence>
            <xs:element name="Name" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="LocalizedDescription">
        <xs:sequence>
            <xs:element name="Description" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="ReplacedTemplates">
      <xs:sequence>
        <xs:element name="ID" type="CompositeIDString" minOccurs="1" maxOccurs="unbounded" />
    </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Author">
        <xs:all>
            <xs:element name="Name" type="xs:string" minOccurs="1" />
            <xs:element name="Email" type="xs:string" minOccurs="0" />
        </xs:all>
    </xs:complexType>

    <xs:complexType name="Range">
        <xs:attribute name="Minimum" type="xs:integer" use="required"/>
        <xs:attribute name="Maximum" type="xs:integer" use="required"/>
    </xs:complexType>

    <xs:complexType name="ProcessVersion">
        <xs:sequence>
            <xs:element name="Major" type="Range" minOccurs="1" />
            <xs:element name="Minor" type="Range" minOccurs="0" />
            <xs:element name="Build" type="Range" minOccurs="0" />
            <xs:element name="Patch" type="Range" minOccurs="0" />
        </xs:sequence>
    </xs:complexType>

    <xs:simpleType name="Architecture">
        <xs:restriction base="xs:string">
            <xs:enumeration value="Win32"/>
            <xs:enumeration value="Win64"/>
        </xs:restriction>
    </xs:simpleType>

    <xs:complexType name="Process">
        <xs:sequence>
            <xs:element name="Filename" type="FilenameString" minOccurs="1" />
            <xs:element name="Architecture" type="Architecture" minOccurs="0" />
            <xs:element name="ProductName" type="xs:string" minOccurs="0" />
            <xs:element name="FileDescription" type="xs:string" minOccurs="0" />
            <xs:element name="ProductVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
            <xs:element name="FileVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Processes">
        <xs:sequence>
            <xs:choice minOccurs="1">
                <xs:element name="Process" type="Process" />
                <xs:element name="ShellProcess" type="Empty" />
            </xs:choice>
            <xs:element name="Process" type="Process" minOccurs="0" maxOccurs="unbounded" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Path">
        <xs:simpleContent>
            <xs:extension base="xs:string">
                <xs:attribute name="Recursive" type="xs:boolean" default="false"/>
                <xs:attribute name="DeleteIfNotFound" type="xs:boolean" default="false"/>
            </xs:extension>
        </xs:simpleContent>
    </xs:complexType>

    <xs:complexType name="RegistrySetting">
        <xs:sequence>
            <xs:element name="Path" type="Path" />
            <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
            <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                    <xs:sequence>
                        <xs:element name="Path" type="Path" minOccurs="0" />
                        <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
                    </xs:sequence>
                </xs:complexType>
            </xs:element>
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="FileSetting">
        <xs:sequence>

            <xs:element name="Root">
                <xs:complexType>
                    <xs:choice>
                        <xs:element name="KnownFolder" type="Guid" />
                        <xs:element name="RegistryEntry" type="xs:string" />
                        <xs:element name="EnvironmentVariable" type="xs:string" />
                    </xs:choice>
                </xs:complexType>
            </xs:element>

            <xs:element name="Path" minOccurs="0" type="Path" />
            <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded"/>

            <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                    <xs:sequence>
                        <xs:element name="Path" type="Path" minOccurs="0" />
                        <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
                    </xs:sequence>
                </xs:complexType>
            </xs:element>

        </xs:sequence>
    </xs:complexType>

    <xs:simpleType name="CustomActionSetting">
        <xs:restriction base="xs:anyURI"/>
    </xs:simpleType>

    <xs:simpleType name="SystemParameterSetting">
        <xs:restriction base="xs:string">

            <!-- Accessibility parameters -->
            <xs:enumeration value="AccessTimeout"/>
            <xs:enumeration value="AudioDescription"/>
            <xs:enumeration value="ClientAreaAnimation"/>
            <xs:enumeration value="DisableOverlappedContent"/>
            <xs:enumeration value="FilterKeys"/>
            <xs:enumeration value="FocusBorderHeight"/>
            <xs:enumeration value="FocusBorderWidth"/>
            <xs:enumeration value="HighContrast"/>
            <xs:enumeration value="MessageDuration"/>
            <xs:enumeration value="MouseClickLock"/>
            <xs:enumeration value="MouseClickLockTime"/>
            <xs:enumeration value="MouseKeys"/>
            <xs:enumeration value="MouseSonar"/>
            <xs:enumeration value="MouseVanish"/>
            <xs:enumeration value="ScreenReader"/>
            <xs:enumeration value="ShowSounds"/>
            <xs:enumeration value="SoundSentry"/>
            <xs:enumeration value="StickyKeys"/>
            <xs:enumeration value="ToggleKeys"/>

            <!-- Input parameters -->
            <xs:enumeration value="Beep"/>
            <xs:enumeration value="BlockSendInputResets"/>
            <xs:enumeration value="DefaultInputLang"/>
            <xs:enumeration value="DoubleClickTime"/>
            <xs:enumeration value="DoubleClkHeight"/>
            <xs:enumeration value="DoubleClkWidth"/>
            <xs:enumeration value="KeyboardCues"/>
            <xs:enumeration value="KeyboardDelay"/>
            <xs:enumeration value="KeyboardPref"/>
            <xs:enumeration value="KeyboardSpeed"/>
            <xs:enumeration value="Mouse"/>
            <xs:enumeration value="MouseButtonSwap"/>
            <xs:enumeration value="MouseHoverHeight"/>
            <xs:enumeration value="MouseHoverTime"/>
            <xs:enumeration value="MouseHoverWidth"/>
            <xs:enumeration value="MouseSpeed"/>
            <xs:enumeration value="MouseTrails"/>
            <xs:enumeration value="SnapToDefButton"/>
            <xs:enumeration value="WheelScrollChars"/>
            <xs:enumeration value="WheelScrollLines"/>

            <!-- Desktop parameters (limited subset) -->
            <xs:enumeration value="DeskWallpaper"/>
            <xs:enumeration value="DesktopColor"/>

        </xs:restriction>
    </xs:simpleType>

    <xs:complexType name="Settings">
        <xs:sequence>
            <xs:element name="Asynchronous" type="xs:boolean" minOccurs="0" />
            <xs:element name="PreventOverlappingSynchronization" type="xs:boolean" minOccurs="0" />
            <xs:element name="AlwaysApplySettings" type="xs:boolean" minOccurs="0" />
            <xs:choice minOccurs="0" maxOccurs="unbounded">
                <xs:element name="Registry" type="RegistrySetting" />
                <xs:element name="File" type="FileSetting" />
                <xs:element name="SystemParameter" type="SystemParameterSetting" />
                <xs:element name="CustomAction" type="CustomActionSetting" />
            </xs:choice>
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Common">
        <xs:sequence>
            <xs:element name="Name" type="xs:string" />
            <xs:element name="ID" type="IDString" />
            <xs:element name="ReplacedTemplates" type="ReplacedTemplates" minOccurs="0" />
            <xs:element name="Description" type="xs:string" minOccurs="0" />
            <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
            <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
            <xs:element name="Version" type="xs:integer" />
            <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
            <xs:element name="DeferToOffice365" type="Empty" minOccurs="0" />
            <xs:element name="Settings" type="Settings" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Application">
        <xs:sequence>
            <xs:element name="Name" type="xs:string" />
            <xs:element name="ID" type="IDString" />
            <xs:element name="ReplacedTemplates" type="ReplacedTemplates" minOccurs="0" />
            <xs:element name="Description" type="xs:string" minOccurs="0" />
            <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
            <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
            <xs:element name="Version" type="xs:integer" />
            <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
            <xs:element name="DeferToOffice365" type="Empty" minOccurs="0" />
            <xs:element name="Processes" type="Processes" />
            <xs:element name="Settings" type="Settings" />
        </xs:sequence>
    </xs:complexType>


    <xs:element name="SettingsLocationTemplate">
        <xs:complexType>
            <xs:sequence>

                <xs:element name="Name" type="xs:string" />
                <xs:element name="ID" type="IDString" />
                <xs:element name="Description" type="xs:string" minOccurs="0" />
                <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
                <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />

                <xs:choice>

                    <!-- Single application -->
                    <xs:sequence>
                        <xs:element name="ReplacedTemplates" type="ReplacedTemplates" minOccurs="0" />
                        <xs:element name="Version" type="TemplateVersion" />
                        <xs:element name="Author" type="Author" minOccurs="0" />
                        <xs:element name="FixedProfile" type="xs:string"  minOccurs="0" />
                        <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
                        <xs:element name="DeferToOffice365" type="Empty" minOccurs="0" />
                        <xs:element name="Processes" type="Processes" />
                        <xs:element name="Settings" type="Settings" />
                    </xs:sequence>

                    <!-- Suite of applications -->
                    <xs:sequence>
                        <xs:element name="ManageSuiteOnly" type="xs:boolean" minOccurs="0" />
                        <xs:element name="Author" type="Author" minOccurs="0" />
                        <xs:element name="FixedProfile" type="xs:string"  minOccurs="0" />
                        <xs:element name="Common" type="Common" />
                        <xs:element name="Application" type="Application" minOccurs="2" maxOccurs="unbounded" />
                    </xs:sequence>

                </xs:choice>

            </xs:sequence>
        </xs:complexType>
    </xs:element>
    <!-- SettingsLocationTemplate -->

</xs:schema>
```

## UE-V 2.0 應用程式範本架構參考


本節詳細說明 UE-V 2.0 設定位置範本的 XML 結構，並提供編輯此檔案的指導方針。

### 本節內容

-   [XML 宣告與編碼屬性](#xml)

-   [命名空間與根項目](#namespace)

-   [資料類型](#data)

-   [Name 元素](#name)

-   [識別碼元素](#id)

-   [Version 元素](#version)

-   [Author 元素](#author)

-   [進程與程式元素](#processes)

-   [Application 元素](#application)

-   [常見元素](#common)

-   [SettingsLocationTemplate 元素](#settingslocationtemplate)

-   [附錄： SettingsLocationTemplate](#appendix)

### <a href="" id="xml"></a>XML 宣告與編碼屬性

**強制： True**

**類型： String**

XML 聲明必須指定 XML 版本1.0 屬性（ &lt; ？ XML 版本 = "1.0" &gt; ）。 由 UE-V 發生器建立的設定位置範本會儲存為 UTF-8 編碼，但不明確指定編碼。 我們建議您在這個元素中包含 encoding = "UTF-8" 屬性來做為最佳做法。 產品隨附的所有範本也會指定此標記（請參閱%ProgramFiles%\\Microsoft 使用者體驗 Virtualization\\Templates 中的檔以瞭解參考）。 例如：

`<?xml version="1.0" encoding="UTF-8"?>`

### <a href="" id="namespace"></a>命名空間與根項目

**強制： True**

**類型： String**

UE-V 使用 https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate 所有應用程式的命名空間。 SettingsLocationTemplate 是根項目，且包含所有其他元素。 使用此標記的所有範本中的參照 SettingsLocationTemplate：

`<SettingsLocationTemplate xmlns='https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate'>`

### <a href="" id="data"></a>資料類型

以下是 UE-V 應用程式範本架構的資料類型。

<a href="" id="guid"></a>**GUID**GUID 描述標準的全域唯一識別碼正則運算式，形式為 "\\ {\ [a-fA-F0-9 \] {8} -\ [a-fa-F0-9 \]- {4} \] [a-FA-F0-9 \] {4} -\ [a-fa-F0-9 \] {4} -\ [a-fa-F0-9 \] {12} \}"。 這會在 Filesetting\\Root\\KnownFolder 元素中使用，以驗證已知資料夾的格式設定。

<a href="" id="filenamestring"></a>**FilenameString**FilenameString 是指要監視之程式的檔案名。 它的值會受到 RegEx \ [^ \\ \\ * \ \ | &lt; &gt;/： \] +，（也就是說，它們可能不包含反斜線字元、星號或問號萬用字元、管道字元、大於或小於符號、轉寄斜線或冒號字元）。

<a href="" id="idstring"></a>**IDString**IDString 指的是應用程式元素、SettingsLocationTemplate 及常見元素的識別碼值（用來描述共用一般設定的應用程式套件）。 它受到與 FilenameString 相同的 RegEx （\ [^ \\ \\ \\？ \\ * \\ | &lt; &gt;/:\]+).

<a href="" id="templateversion"></a>**TemplateVersion**TemplateVersion 是一個整數值，用於描述設定位置範本的修訂。 其值的範圍可以是0到2147483647。

<a href="" id="empty"></a>**空白**空白代表 null 值。 這會在 Process\\ShellProcess 中使用，表示沒有任何程式可供監視。 您不應該在任何應用程式範本中使用這個值。

<a href="" id="author"></a>**作者**[作者] 資料類型是一種複雜類型，可用於識別範本的作者。 它包含兩個子項目： [**名稱**] 和 [**電子郵件**]。 在 Author 資料類型中，Name 元素是必要的，而 Email 元素是選擇性的。 此類型會在 SettingsLocationTemplate 元素下更詳細的說明。

<a href="" id="range"></a>**範圍**範圍定義由兩個子項目組成的整數類別： [**最小值**] 和 [**最大值**]。 此資料類型是在 ProcessVersion 資料類型中實現。 如果已指定，則必須包含最小值和最大值。

<a href="" id="processversion"></a>**ProcessVersion**ProcessVersion 會定義含有四個子項目的類型：**主要**、**次要**、**組建**及**修補程式**。 此資料類型是由 Process 元素用來填入其 ProductVersion 和 FileVersion 值。 此類型的資料是範圍值。 主要子項目是強制性的，而其他則是選擇性的。

<a href="" id="architecture"></a>**架構**結構列舉了兩個可能的值： **Win32**和**Win64**。 這些值是用來指定處理常式體系結構。

<a href="" id="process"></a>**處理**程式[流程] 資料類型是用來描述要由 UE-V 監視之進程的容器。 它包含六個子項目： **Filename**、**結構**、 **ProductName**、 **FileDescription**、 **ProductVersion**和**FileVersion**。 下表詳細說明每個元素各自的資料類型：

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">元素</th>
<th align="left">資料類型</th>
<th align="left">Mandatory</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>副檔名</p></td>
<td align="left"><p>FilenameString</p></td>
<td align="left"><p>True</p></td>
</tr>
<tr class="even">
<td align="left"><p>架構</p></td>
<td align="left"><p>架構</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ProductName</p></td>
<td align="left"><p>字串</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="even">
<td align="left"><p>FileDescription</p></td>
<td align="left"><p>字串</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ProductVersion</p></td>
<td align="left"><p>ProcessVersion</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="even">
<td align="left"><p>FileVersion</p></td>
<td align="left"><p>ProcessVersion</p></td>
<td align="left"><p>False</p></td>
</tr>
</tbody>
</table>

 

<a href="" id="processes"></a>**處理**程式[進程] 資料類型代表一或多個處理元素集合的容器。 進程式列類型支援兩個子項目： **Process**與**ShellProcess**。 Process 是 Process 類型的元素，且 ShellProcess 的資料類型為空白。 在順序中至少必須辨識一個專案。

<a href="" id="path"></a>**路徑**RegistrySetting 和 FileSetting 會使用 Path 來參照登錄和檔案路徑。 這個元素支援兩個選用的屬性： **Recursive**與**DeleteIfNotFound**。 這兩個值都設定為 default = "False"。

Recursive：表示檔案設定中包含路徑和所有子資料夾，或是所有的子登錄機碼都包含在註冊設定中。 在這兩種情況下，目前層級的所有專案都會包含在捕獲的資料中。 針對 FileSettings 物件，指定資料夾中的所有檔案都包含在 UE-V 捕獲的資料中，但不包含資料夾。 針對登錄路徑，會捕獲目前路徑中的所有值，但不會捕獲子登錄機碼。 在這兩種情況下，請小心考慮避免捕獲大型資料集或大量專案。

DeleteIfNotFound 屬性會從使用者的設定儲存路徑資料中移除設定。 在從套件中移除這些設定時，可能需要這麼做，將大量磁碟空間儲存在設定儲存路徑檔案伺服器上。

<a href="" id="filemask"></a>**FileMask**FileMask 僅指定由 Path 所定義之資料夾的特定檔案類型。 例如，Path 可能是， `C:\users\username\files` 且 FileMask `*.txt` 只能包含文字檔。

<a href="" id="registrysetting"></a>**RegistrySetting**RegistrySetting 代表登錄機碼和值的容器，以及 UE-V Agent 元件上相關聯的所需行為。 此類型中定義了四個子項目： **path**、 **Name**、 **Exclude**以及值**Path**和**Name**的順序。

<a href="" id="filesetting"></a>**FileSetting**FileSetting 包含與檔案和檔案路徑相關聯的參數。 定義了四個子項目： **Root**、 **Path**、 **FileMask**及**Exclude**。 Root 是強制性的，而其他則是選擇性的。

<a href="" id="settings"></a>**設定**[設定] 是適用于特定範本之所有設定的容器。 它包含前面所述的登錄、檔案、SystemParameter 及 CustomAction 設定的實例。 此外，它也可以包含下列含有行為的子項目：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">元素</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>非同步</p></td>
<td align="left"><p>在不封鎖應用程式啟動的情況下，會套用非同步設定套件，讓應用程式在設定仍在套用時開始進行。 這對於可以非同步套用的設定（例如 <code>get/set</code> ，透過 API （例如 SystemParameterSetting）而言很有用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>PreventOverlappingSynchronization</p></td>
<td align="left"><p>根據預設，UE-V 只會在使用範本的最後一個應用程式實例關閉時，儲存應用程式的設定。 當這個元素設定為 ' false」時，UE-V 會匯出設定，即使有應用程式的其他實例正在執行也一樣。 適合使用由 UE-V 隨附的常見元素區段的範本（包含通用元素區段）使用此標誌來啟用共用設定，以避免在應用程式關閉時匯出應用程式特定的設定，但在最後一個實例關閉之後，才會進行匯出。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="name"></a>Name 元素

**強制： True**

**類型： String**

名稱指定 [設定位置] 範本的唯一名稱。 這用於在 WMI、PowerShell、事件檢視器和調試記錄中參照範本時的顯示用途。 一般來說，請避免參照版本資訊，因為這可以從 ProductVersion 元素中 objected。 例如，請指定 `<Name>My Application</Name>` （而非） `<Name>My Application 1.1</Name>` 。

**記事** UE-V 不會參照外部 Dtd，所以無法在設定位置範本中使用命名實體。 例如，請勿用 &reg; 來參照已註冊的商業標誌簽署®。 相反地，請改用規範編號參照來包含這些類型的特殊字元，例如，®字元 & \ #174。 此規則適用于此檔中的所有字串值。

<http://www.w3.org/TR/xhtml1/dtds.html>如需字元實體的完整清單，請參閱。 UTF-8 編碼的檔可能會直接包含 Unicode 字元。 透過 UE-V 發生器儲存範本時會自動將字元實體轉換成其 Unicode 代表。

 

### <a href="" id="id"></a>識別碼元素

**強制： True**

**類型： String**

[識別碼] 會填入特定範本的唯一識別碼。 此標記會成為 UE-V Agent 在執行時間參考範本時所用的主要識別碼（例如，請參閱 UevTemplate 和 UevTemplateProgram PowerShell Cmdlet 的輸出）。 根據慣例，此標記不應包含任何空格，以簡化腳本撰寫。 應用程式的版本號碼應該在這個元素中指定，以便更輕鬆地識別範本，例如 `<ID>MicrosoftCalculator6</ID>` 或 `<ID>MicrosoftOffice2010Win64</ID>` 。

### <a href="" id="version"></a>Version 元素

**強制： True**

**類型： Integer**

**最小值：0**

**最大值：2147483647**

[版本] 可識別 [設定位置] 範本的版本，以進行系統管理追蹤變更。 每次儲存範本時，UE-V 發生器都會自動將這個數位遞增1。 請注意，這個欄位必須是整數整數;分數值，例如 `<Version>2.5</Version>` 不允許。

**提示：** 您可以使用 XML comment 標記儲存有關版本變更 `<!-- -->` 的筆記，例如：

```xml
<!--
    Version History

    Version 1 Jul 05, 2012 Initial template created by Generator - Denise@Contoso.com
    Version 2 Jul 31, 2012 Added support for app.exe v2.1.3 - Mark@Contoso.com
    Version 3 Jan 01, 2013 Added font settings support - Mark@Contoso.com
    Version 4 Jan 31, 2013 Added support for plugin settings - Tony@Contoso.com
  -->
<Version>4</Version>
```

**重要** 系統會詢問此值，以判斷是否應該在這些範例中將範本的新版本套用至現有的範本：

-   排程範本自動更新工作執行時

-   在執行更新 UevTemplate PowerShell Cmdlet 時

-   透過 WMI 呼叫 microsoft\\uev： SettingsLocationTemplate Update 方法時

 

### <a href="" id="author"></a>Author 元素

**強制： False**

**類型： String**

[作者] 會識別 [設定位置] 範本的建立者。 支援兩個選用的子項目： [**名稱**] 和 [**電子郵件**]。 這兩個屬性都是選擇性的，但如果指定了電子郵件子項目，則它必須伴隨 Name 元素。 [作者] 是指 [設定位置] 範本的連絡人完整名稱，而電子郵件應該是代表作者的電子郵件地址。 我們建議您在發佈的範本中包含這項資訊，例如，在[Ue-v 範本圖庫](https://gallery.technet.microsoft.com/site/search?f%5B0%5D.Type=RootCategory&f%5B0%5D.Value=UE-V)中。

### <a href="" id="processes"></a>進程與程式元素

**強制： True**

**Type：元素**

進程至少包含一個 `<Process>` 元素，而該元素又包含下列子項目： **Filename**、**結構**、 **ProductName**、 **FileDescription**、 **ProductVersion**和**FileVersion**。 Filename 子項目是強制性的，而其他則是選擇性的。 完全填入的元素包含與此範例類似的標記：

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <Architecture>Win64</Architecture>
  <ProductName> MyApplication </ProductName>
  <FileDescription>MyApplication.exe</FileDescription>
  <ProductVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </FileVersion>
</Process>
```

### 副檔名

**強制： True**

**類型： String**

Filename 指的是可執行檔在檔案系統中出現的實際檔案名。 這個元素指定 UE-V 用來評估範本是否適用于流程的主要準則。 這個元素必須在 [設定位置] 範本 XML 中指定。

有效的檔案名必須與正則運算式 \ [^ \\ \\ \ \？ \\ * \ | &lt; &gt;/： \] +，也就是不能包含反斜線字元、星號或問號萬用字元、管道字元、大於或小於符號、轉寄斜線或冒號（\\？ \* |&lt; &gt; /或：個字元）。

**提示：** 若要對照此 RegEx 測試字串，請使用 PowerShell 命令視窗，並將您的可執行檔名稱取代為**YourFileName**：

`"YourFileName.exe" -match  "[\\\?\*\|<>/:]+"`

**True**值表示字串包含非法字元。 以下是非法值的一些範例：

-   \\\\server\\share\\program.exe

-   Program \ * .exe

-   Pro？ ram.exe

-   程式 &lt; 1 &gt; .exe

**記事** UE-V 發生器分別對大於和小於字元進行編碼 &gt; &lt; 。

 

在極少數情況下，FileName 值不一定包括 .exe 副檔名，但應該將它指定為值的一部分。 例如， `<Filename>MyApplictication.exe</Filename>` 應指定而不是 `<Filename>MyApplictication</Filename>` 。 如果可執行檔的實際名稱是「MyApplication.exe」，則第二個範例不會將範本套用至程式。

### 架構

**強制： False**

**類型：結構（字串）**

結構指的是編譯目標可執行檔的處理器架構。 有效值為32位應用程式的 Win32，或64位應用程式的 Win64。 如果有，此標記會將 [設定位置] 範本的適用性限制為特定的應用程式結構。 如需這種情況的範例，請比較%ProgramFiles%\\Microsoft 使用者體驗 Virtualization\\templates\\ MicrosoftOffice2010Win32.xml 與 UE-V 隨附的 MicrosoftOffice2010Win64.xml 檔案。 當相對路徑在不同版本的可執行檔之間變更，或在從一個處理器架構移到另一個時，如果已新增或移除設定，這就很有用。

如果此元素不存在，則設定位置範本會忽略進程的體系結構，並同時適用于32和64位程式（如果有的話）。

**記事** UE-V 在這個版本中不支援 ARM 處理器。

 

### ProductName

**強制： False**

**類型： String**

ProductName 是一個可供您用來識別管理用途或報告之產品的選用元素。 ProductName 與 Filename 不同，因為它的值沒有正則運算式限制。 這可讓您更輕鬆地瞭解可執行檔名稱可能不明顯的程式說明。 例如：

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <ProductName>My Application 6.x by Contoso.com</ProductName>
  <ProductVersion>
    <Major Minimum="6" Maximum="6" />
  </ProductVersion>
</Process>
```

### FileDescription

**強制： False**

**類型： String**

FileDescription 是一個可執行檔的系統管理描述的選擇性標記。 這是自由文字欄位，在您需要識別可執行檔之功能的軟體套件中，可能會有説明。

例如，在適用的應用程式中，提供兩個可執行檔（MyApplication.exe 和 MyApplicationHelper.exe）功能的提醒可能會很有用，如下所示：

```xml
<Processes>
  <Process>
    <Filename>MyApplication.exe</Filename>
    <FileDescription>My Application Main Engine</ FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
  <Process>
    <Filename>MyApplicationHelper.exe</Filename>
    <FileDescription>My Application Background Process Executable</FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
</Processes>
```

### ProductVersion

**強制： False**

**類型： String**

ProductVersion 指的是檔案的主要及次要產品版本，以及組建與修補程式層級。 ProductVersion 是一個選用的元素，但如果有指定，它必須包含至少主要的子項目。 此值必須以最小值為 "X" 的範圍來表示最大值 = "X" 上限 = "Y"，其中 X 和 Y 為整數。 [最小值] 和 [最大值] 可以完全相同。

產品和檔案版本元素可能是未指定的。 如此一來，就會將範本設為「不限版本」，這表示該範本會套用至指定的可執行檔的所有版本。

**範例 1：**

UE-V 發生器中指定的產品版本：1.0 會產生下列 XML：

```xml
<ProductVersion>
  <Major Minimum="1" Maximum="1" />
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

**範例 2：**

檔版本： UE-V 發生器中指定的5.0.2.1000 會產生下列 XML：

```xml
<FileVersion>
  <Major Minimum="5" Maximum="5" />
  <Minor Minimum="0" Maximum="0" />
  <Build Minimum="2" Maximum="2" />
  <Patch Minimum="1000" Maximum="1000" />
</FileVersion>
```

**不正確的範例1–不完整範圍：**

只有最小屬性出現。 範圍中也必須包含最大值。

```xml
<ProductVersion>
  <Major Minimum="2" />
</ProductVersion>
```

**不正確的範例2–指定的次要元素沒有主要元素：**

只有次要元素存在。 還必須包含主要版本。

```xml
<ProductVersion>
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

### FileVersion

**強制： False**

**類型： String**

FileVersion 會區分已發佈應用程式的發行版本本，以及元件可執行檔的內部組建詳細資料。 對於大多數商業應用程式而言，這些號碼是完全相同的。 在其他情況下，檔案的產品版本會指示檔案的一般版本識別，而檔案版本則表示檔案的特定組建（例如，修補程式或更新的情況）。 這會唯一識別檔案，而不會中斷偵測邏輯。

若要判斷特定可執行檔的產品版本和檔案版本，請以滑鼠右鍵按一下 Windows 資源管理器中的檔案，選取 [屬性]，然後按一下 [詳細資料] 索引標籤。

包含應用程式的 FileVersion 元素可讓您更精確地微調偵測邏輯，但對於大部分的應用程式來說，不是必要的。 首先會選取 [ProductVersion] 元素設定，然後 FileVersion [已核取]。 您將會套用限制性較強的設定。

FileVersion 的子項目和語法規則與 ProductVersion 相同。

```xml
<Process>
  <Filename>MSACCESS.EXE</Filename>
  <Architecture>Win32</Architecture>
  <ProductVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </FileVersion>
</Process>
```

### <a href="" id="application"></a>Application 元素

應用程式是適用于特定應用程式的設定容器。 它是下欄欄位/類型的集合。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">欄位/類型</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Name</p></td>
<td align="left"><p>指定 [設定位置] 範本的唯一名稱。 這用於在 WMI、PowerShell、事件檢視器和調試記錄中參照範本時的顯示用途。 如需詳細資訊，請參閱 <a href="#name" data-raw-source="[Name](#name)"> Name </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>識別碼</p></td>
<td align="left"><p>填入特定範本的唯一識別碼。 此標記會成為 UE-V Agent 在執行時間參考範本時所用的主要識別碼。 如需詳細資訊，請參閱 <a href="#id" data-raw-source="[ID](#id)"> 識別碼 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>描述</p></td>
<td align="left"><p>範本的選用描述。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LocalizedNames</p></td>
<td align="left"><p>UI 中顯示的選擇性名稱，由語言地區設定當地語系化。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LocalizedDescriptions</p></td>
<td align="left"><p>依語言地區設定當地語系化的選用範本描述。</p></td>
</tr>
<tr class="even">
<td align="left"><p>版本</p></td>
<td align="left"><p>識別 [設定位置] 範本的版本，以進行系統管理追蹤變更。 如需詳細資訊，請參閱 <a href="#version" data-raw-source="[Version](#version)"> 版本 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DeferToMSAccount</p></td>
<td align="left"><p>控制是否將此範本與 Microsoft 帳戶搭配使用。 如果已針對電腦上的使用者啟用 MSA 同步處理，則會自動停用此範本。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeferToOffice365</p></td>
<td align="left"><p>與 MSA 類似，這會控制是否與 Office365 搭配使用此範本。 如果您使用 Office 365 來同步處理設定，此範本會自動停用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>處理程序</p></td>
<td align="left"><p>一個或多個處理元素集合的容器。 如需詳細資訊，請參閱 <a href="#processes" data-raw-source="[Processes](#processes)"> 進程 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定</p></td>
<td align="left"><p>適用于特定範本之所有設定的容器。 它包含 Registry、File、SystemParameter 和 CustomAction 設定的實例。 如需詳細資訊，請參閱 <strong> </strong> 資料類型中的設定 <a href="#data" data-raw-source="[Data types](#data)"> </a> 。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="common"></a>常見元素

[常用] 與應用程式元素類似，但它永遠與兩個或更多個應用程式元素相關聯。 [常見] 區段代表在這些應用程式實例之間共用的一組設定。 它是下欄欄位/類型的集合。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">欄位/類型</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Name</p></td>
<td align="left"><p>指定 [設定位置] 範本的唯一名稱。 這用於在 WMI、PowerShell、事件檢視器和調試記錄中參照範本時的顯示用途。 如需詳細資訊，請參閱 <a href="#name" data-raw-source="[Name](#name)"> Name </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>識別碼</p></td>
<td align="left"><p>填入特定範本的唯一識別碼。 此標記會成為 UE-V Agent 在執行時間參考範本時所用的主要識別碼。 如需詳細資訊，請參閱 <a href="#id" data-raw-source="[ID](#id)"> 識別碼 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>描述</p></td>
<td align="left"><p>範本的選用描述。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LocalizedNames</p></td>
<td align="left"><p>UI 中顯示的選擇性名稱，由語言地區設定當地語系化。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LocalizedDescriptions</p></td>
<td align="left"><p>依語言地區設定當地語系化的選用範本描述。</p></td>
</tr>
<tr class="even">
<td align="left"><p>版本</p></td>
<td align="left"><p>識別 [設定位置] 範本的版本，以進行系統管理追蹤變更。 如需詳細資訊，請參閱 <a href="#version" data-raw-source="[Version](#version)"> 版本 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DeferToMSAccount</p></td>
<td align="left"><p>控制是否將此範本與 Microsoft 帳戶搭配使用。 如果已針對電腦上的使用者啟用 MSA 同步處理，則會自動停用此範本。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeferToOffice365</p></td>
<td align="left"><p>與 MSA 類似，這會控制是否與 Office365 搭配使用此範本。 如果您使用 Office 365 來同步處理設定，此範本會自動停用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>設定</p></td>
<td align="left"><p>適用于特定範本之所有設定的容器。 它包含 Registry、File、SystemParameter 和 CustomAction 設定的實例。 如需詳細資訊，請參閱 <strong> </strong> 資料類型中的設定 <a href="#data" data-raw-source="[Data types](#data)"> </a> 。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="settingslocationtemplate"></a>SettingsLocationTemplate 元素

這個元素定義單一應用程式或一套應用程式的設定。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">欄位/類型</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Name</p></td>
<td align="left"><p>指定 [設定位置] 範本的唯一名稱。 這用於在 WMI、PowerShell、事件檢視器和調試記錄中參照範本時的顯示用途。 如需詳細資訊，請參閱 <a href="#name" data-raw-source="[Name](#name)"> Name </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>識別碼</p></td>
<td align="left"><p>填入特定範本的唯一識別碼。 此標記會成為 UE-V Agent 在執行時間參考範本時所用的主要識別碼。 如需詳細資訊，請參閱 <a href="#id" data-raw-source="[ID](#id)"> 識別碼 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>描述</p></td>
<td align="left"><p>範本的選用描述。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LocalizedNames</p></td>
<td align="left"><p>UI 中顯示的選擇性名稱，由語言地區設定當地語系化。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LocalizedDescriptions</p></td>
<td align="left"><p>依語言地區設定當地語系化的選用範本描述。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="appendix"></a>附錄： SettingsLocationTemplate

以下是 SettingsLocationTemplate 檔案，其中顯示其元素、子項目、屬性和參數：

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="UevSettingsLocationTemplate"
  targetNamespace="https://schemas.microsoft.com/UserExperienceVirtualization/2013/SettingsLocationTemplate"
  elementFormDefault="qualified"
  xmlns="https://schemas.microsoft.com/UserExperienceVirtualization/2013/SettingsLocationTemplate"
  xmlns:mstns="https://schemas.microsoft.com/UserExperienceVirtualization/2013/SettingsLocationTemplate"
  xmlns:xs="http://www.w3.org/2001/XMLSchema">

  <xs:simpleType name="Guid">
    <xs:restriction base="xs:string">
      <xs:pattern value="\{[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{12}\}" />
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="FilenameString">
    <xs:restriction base="xs:string">
      <xs:pattern value="[^\\\?\*\|&lt;&gt;/:]+" />
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="IDString">
    <xs:restriction base="xs:string">
      <xs:pattern value="[^\\\?\*\|&lt;&gt;/:.]+" />
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="TemplateVersion">
    <xs:restriction base="xs:integer">
      <xs:minInclusive value="0" />
      <xs:maxInclusive value="2147483647" />
    </xs:restriction>
  </xs:simpleType>

  <xs:complexType name="Empty">
    <xs:sequence/>
  </xs:complexType>

  <xs:complexType name="LocalizedString">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="Locale" type="xs:string" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>

  <xs:complexType name="LocalizedName">
    <xs:sequence>
      <xs:element name="Name" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="LocalizedDescription">
    <xs:sequence>
      <xs:element name="Description" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Author">
    <xs:all>
      <xs:element name="Name" type="xs:string" minOccurs="1" />
      <xs:element name="Email" type="xs:string" minOccurs="0" />
    </xs:all>
  </xs:complexType>

  <xs:complexType name="Range">
    <xs:attribute name="Minimum" type="xs:integer" use="required"/>
    <xs:attribute name="Maximum" type="xs:integer" use="required"/>
  </xs:complexType>

  <xs:complexType name="ProcessVersion">
    <xs:sequence>
      <xs:element name="Major" type="Range" minOccurs="1" />
      <xs:element name="Minor" type="Range" minOccurs="0" />
      <xs:element name="Build" type="Range" minOccurs="0" />
      <xs:element name="Patch" type="Range" minOccurs="0" />
    </xs:sequence>
  </xs:complexType>

  <xs:simpleType name="Architecture">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Win32"/>
      <xs:enumeration value="Win64"/>
    </xs:restriction>
  </xs:simpleType>

  <xs:complexType name="Process">
    <xs:sequence>
      <xs:element name="Filename" type="FilenameString" minOccurs="1" />
      <xs:element name="Architecture" type="Architecture" minOccurs="0" />
      <xs:element name="ProductName" type="xs:string" minOccurs="0" />
      <xs:element name="FileDescription" type="xs:string" minOccurs="0" />
      <xs:element name="ProductVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
      <xs:element name="FileVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Processes">
    <xs:sequence>
      <xs:choice minOccurs="1">
        <xs:element name="Process" type="Process" />
        <xs:element name="ShellProcess" type="Empty" />
      </xs:choice>
      <xs:element name="Process" type="Process" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Path">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="Recursive" type="xs:boolean" default="false"/>
        <xs:attribute name="DeleteIfNotFound" type="xs:boolean" default="false"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>

  <xs:complexType name="RegistrySetting">
    <xs:sequence>
      <xs:element name="Path" type="Path" />
      <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
      <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
        <xs:complexType>
          <xs:sequence>
            <xs:element name="Path" type="Path" minOccurs="0" />
            <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
          </xs:sequence>
        </xs:complexType>
      </xs:element>
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="FileSetting">
    <xs:sequence>

      <xs:element name="Root">
        <xs:complexType>
          <xs:choice>
            <xs:element name="KnownFolder" type="Guid" />
            <xs:element name="RegistryEntry" type="xs:string" />
            <xs:element name="EnvironmentVariable" type="xs:string" />
          </xs:choice>
        </xs:complexType>
      </xs:element>

      <xs:element name="Path" minOccurs="0" type="Path" />
      <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded"/>

      <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
        <xs:complexType>
          <xs:sequence>
            <xs:element name="Path" type="Path" minOccurs="0" />
            <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
          </xs:sequence>
        </xs:complexType>
      </xs:element>

    </xs:sequence>
  </xs:complexType>

  <xs:simpleType name="SystemParameterSetting">
    <xs:restriction base="xs:string">

      <!-- Accessibility parameters -->
      <xs:enumeration value="AccessTimeout"/>
      <xs:enumeration value="AudioDescription"/>
      <xs:enumeration value="ClientAreaAnimation"/>
      <xs:enumeration value="DisableOverlappedContent"/>
      <xs:enumeration value="FilterKeys"/>
      <xs:enumeration value="FocusBorderHeight"/>
      <xs:enumeration value="FocusBorderWidth"/>
      <xs:enumeration value="HighContrast"/>
      <xs:enumeration value="MessageDuration"/>
      <xs:enumeration value="MouseClickLock"/>
      <xs:enumeration value="MouseClickLockTime"/>
      <xs:enumeration value="MouseKeys"/>
      <xs:enumeration value="MouseSonar"/>
      <xs:enumeration value="MouseVanish"/>
      <xs:enumeration value="ScreenReader"/>
      <xs:enumeration value="ShowSounds"/>
      <xs:enumeration value="SoundSentry"/>
      <xs:enumeration value="StickyKeys"/>
      <xs:enumeration value="ToggleKeys"/>

      <!-- Input parameters -->
      <xs:enumeration value="Beep"/>
      <xs:enumeration value="BlockSendInputResets"/>
      <xs:enumeration value="DefaultInputLang"/>
      <xs:enumeration value="DoubleClickTime"/>
      <xs:enumeration value="DoubleClkHeight"/>
      <xs:enumeration value="DoubleClkWidth"/>
      <xs:enumeration value="KeyboardCues"/>
      <xs:enumeration value="KeyboardDelay"/>
      <xs:enumeration value="KeyboardPref"/>
      <xs:enumeration value="KeyboardSpeed"/>
      <xs:enumeration value="Mouse"/>
      <xs:enumeration value="MouseButtonSwap"/>
      <xs:enumeration value="MouseHoverHeight"/>
      <xs:enumeration value="MouseHoverTime"/>
      <xs:enumeration value="MouseHoverWidth"/>
      <xs:enumeration value="MouseSpeed"/>
      <xs:enumeration value="MouseTrails"/>
      <xs:enumeration value="SnapToDefButton"/>
      <xs:enumeration value="WheelScrollChars"/>
      <xs:enumeration value="WheelScrollLines"/>

      <!-- Desktop parameters (limited subset) -->
      <xs:enumeration value="DeskWallpaper"/>
      <xs:enumeration value="DesktopColor"/>

    </xs:restriction>
  </xs:simpleType>

  <xs:complexType name="Settings">
    <xs:sequence>
      <xs:element name="Asynchronous" type="xs:boolean" minOccurs="0" />
      <xs:element name="PreventOverlappingSynchronization" type="xs:boolean" minOccurs="0" />
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Registry" type="RegistrySetting" />
        <xs:element name="File" type="FileSetting" />
        <xs:element name="SystemParameter" type="SystemParameterSetting" />
      </xs:choice>
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Common">
    <xs:sequence>
      <xs:element name="Name" type="xs:string" />
      <xs:element name="ID" type="IDString" />
      <xs:element name="Description" type="xs:string" minOccurs="0" />
      <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
      <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
      <xs:element name="Version" type="xs:integer" />
      <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
      <xs:element name="Settings" type="Settings" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Application">
    <xs:sequence>
      <xs:element name="Name" type="xs:string" />
      <xs:element name="ID" type="IDString" />
      <xs:element name="Description" type="xs:string" minOccurs="0" />
      <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
      <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
      <xs:element name="Version" type="xs:integer" />
      <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
      <xs:element name="Processes" type="Processes" />
      <xs:element name="Settings" type="Settings" />
    </xs:sequence>
  </xs:complexType>


  <xs:element name="SettingsLocationTemplate">
    <xs:complexType>
      <xs:sequence>

        <xs:element name="Name" type="xs:string" />
        <xs:element name="ID" type="IDString" />
        <xs:element name="Description" type="xs:string" minOccurs="0" />
        <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
        <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />

        <xs:choice>

          <!-- Single application -->
          <xs:sequence>
            <xs:element name="Version" type="TemplateVersion" />
            <xs:element name="Author" type="Author" minOccurs="0" />
            <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
            <xs:element name="Processes" type="Processes" />
            <xs:element name="Settings" type="Settings" />
          </xs:sequence>

          <!-- Suite of applications -->
          <xs:sequence>
            <xs:element name="ManageSuiteOnly" type="xs:boolean" minOccurs="0" />
            <xs:element name="Author" type="Author" minOccurs="0" />
            <xs:element name="Common" type="Common" />
            <xs:element name="Application" type="Application" minOccurs="2" maxOccurs="unbounded" />
          </xs:sequence>

        </xs:choice>

      </xs:sequence>
    </xs:complexType>
  </xs:element>
  <!-- SettingsLocationTemplate -->

</xs:schema>
```






## 相關主題


[使用自訂的 UE-V 2. x 範本和 UE-V 2. x 發電機](working-with-custom-ue-v-2x-templates-and-the-ue-v-2x-generator-new-uevv2.md)

[UE-V 2.x 技術參考](technical-reference-for-ue-v-2x-both-uevv2.md)

 

 





