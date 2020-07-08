---
title: 使用 App-V 部署 Microsoft Office 2016
description: 使用 App-V 部署 Microsoft Office 2016
author: dansimp
ms.assetid: cc675cde-cb8d-4b7c-a700-6104b78f1d89
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 07/25/2017
ms.openlocfilehash: dfedab98e0bdf0a0d5f5e407d9bedadbbf56ad69
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800639"
---
# 使用 App-V 部署 Microsoft Office 2016


使用本文中的資訊來使用 Microsoft Application Virtualization 5.0 或更新版本，將 Microsoft Office 2016 作為虛擬化的應用程式提供給貴組織中的電腦。 如需使用 App-v 來傳送 Office 2013 的詳細資訊，請參閱[使用 App-v 部署 Microsoft Office 2013](deploying-microsoft-office-2013-by-using-app-v.md)。 如需使用 App-v 來傳送 Office 2010 的詳細資訊，請參閱[使用 App-v 部署 Microsoft Office 2010](deploying-microsoft-office-2010-by-using-app-v.md)。

本主題包含下列各節：

-   [開始前的須知](#bkmk-before-you-start)

-   [使用 Office 部署工具為 App-v 建立 Office 2016 套件](#bkmk-create-office-pkg)

-   [發佈應用程式的 Office 套件-V 5。0](#bkmk-pub-pkg-office)

-   [自訂及管理 Office App-v 套件](#bkmk-custmz-manage-office-pkgs)

## <a href="" id="bkmk-before-you-start"></a>開始前的須知


在使用 App-v 部署 Office 2016 之前，請先查看下列規劃資訊。

### <a href="" id="bkmk-supp-vers-coexist"></a>支援的 Office 版本與 Office 共存

您可以使用下表來取得支援的 Office 版本相關資訊，以及如何執行共存的 Office 版本。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">要查看的資訊</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="planning-for-using-app-v-with-office.md#bkmk-office-vers-supp-appv" data-raw-source="[Supported versions of Microsoft Office](planning-for-using-app-v-with-office.md#bkmk-office-vers-supp-appv)">支援的 Microsoft Office 版本</a></p></td>
<td align="left"><ul>
<li><p>支援的 Office 版本</p></li>
<li><p>支援的部署類型（例如，桌面、個人虛擬桌面基礎結構（VDI）、彙集的 VDI）</p></li>
<li><p>Office 授權選項</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><a href="planning-for-using-app-v-with-office.md#bkmk-plan-coexisting" data-raw-source="[Planning for Using App-V with coexisting versions of Office](planning-for-using-app-v-with-office.md#bkmk-plan-coexisting)">規劃與共存版本的 Office 一起使用 App-v</a></p></td>
<td align="left"><p>在同一部電腦上安裝不同版本的 Office 時的考慮</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-pkg-pub-reqs"></a>封裝、發佈和部署需求

在使用 App-v 部署 Office 之前，請先檢查下列需求。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">工作</th>
<th align="left">需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>封裝</p></td>
<td align="left">
<ul>
<li><p>您要部署至使用者的所有 Office 應用程式必須位於單一套件中。</p></li>
<li><p>在 App-v 5.0 及更新版本中，您必須使用 Office 部署工具來建立套件。 您無法使用排序器。</p></li>
<li><p>如果您要部署 Microsoft Visio 2016，以及 Office 的 Microsoft Project 2016，您必須將它們包含在 Office 的同一個套件中。 如需詳細資訊，請參閱 <a href="#bkmk-deploy-visio-project" data-raw-source="[Deploying Visio 2016 and Project 2016 with Office](#bkmk-deploy-visio-project)"> 使用 Office 部署 Visio 2016 和 Project 2016 </a> 。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>發行</p></td>
<td align="left"><ul>
<li><p>您只能將一個 Office 套件發佈至每個用戶端電腦。</p></li>
<li><p>您必須全域發佈 Office 套件。 您無法發佈給使用者。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>使用遠端桌面服務將下列任何產品部署到共用電腦，例如：</p>
<ul>
<li><p>適用于企業的 Microsoft 365 應用程式</p></li>
<li><p>Visio Pro for Office 365</p></li>
<li><p>Project Pro for Office 365</p></li>
</ul></td>
<td align="left"><p>您必須啟用 <a href="https://technet.microsoft.com/library/dn782860.aspx" data-raw-source="[shared computer activation](https://technet.microsoft.com/library/dn782860.aspx)"> 共用電腦啟用 </a> 。</p>
</td>
</tr>
</tbody>
</table>



### 從套件中排除 Office 應用程式

下表說明從套件中排除特定 Office 應用程式的建議方法。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">工作</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>使用 <strong> </strong> Office 部署工具建立套件時，請使用 ExcludeApp 設定。</p></td>
<td align="left"><ul>
<li><p>可讓您在 Office 部署工具建立套件時，從套件中排除特定的 Office 應用程式。 例如，您可以使用這個設定來建立只包含 Microsoft Word 的套件。</p></li>
<li><p>如需詳細資訊，請參閱 <a href="https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement" data-raw-source="[ExcludeApp element](https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement)"> ExcludeApp 元素 </a> 。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>修改 DeploymentConfig.xml 檔案</p></td>
<td align="left"><ul>
<li><p>建立套件之後，請修改 DeploymentConfig.xml 檔案。 此檔案包含執行 App-v 用戶端之電腦上所有使用者的預設套件設定。</p></li>
<li><p>如需詳細資訊，請參閱 <a href="#bkmk-disable-office-apps" data-raw-source="[Disabling Office 2016 applications](#bkmk-disable-office-apps)"> 停用 Office 2016 應用程式 </a> 。</p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-create-office-pkg"></a>使用 Office 部署工具為 App-v 建立 Office 2016 套件


完成下列步驟，以針對 App-v 5.0 或更新版本建立 Office 2016 套件。

>**Important** &nbsp; 重要 &nbsp;在 App-V 5.0 及更新版本中，您必須使用 Office 部署工具來建立套件。 您無法使用 Sequencer 來建立套件。

### 查看使用 Office 部署工具的先決條件

您要安裝 Office 部署工具的電腦必須具備：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必備</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>必備軟體</p></td>
<td align="left"><p>.Net Framework 4</p></td>
</tr>
<tr class="even">
<td align="left"><p>支援的作業系統</p></td>
<td align="left"><ul>
<li><p>64位版本的 Windows 10</p></li>
<li><p>64位版本的 Windows 8 或8。1</p></li>
<li><p>64位版本的 Windows 7</p></li>
</ul></td>
</tr>
</tbody>
</table>


>**記事** 在本主題中，「Office 2016 App-V 封裝」一詞是指訂閱授權。


### 使用 Office 部署工具建立 Office 2016 App-v 套件

您可以使用 Office 部署工具來建立 Office 2016 App-v 套件。 下列指示說明如何使用訂閱授權建立 Office 2016 App-v 套件。

在64位 Windows 電腦上建立 Office 2016 App-v 套件。 建立之後，Office 2016 App-v 套件將會在32位和64位的 Windows 7、Windows 8.1 和 Windows 10 電腦上執行。

### 下載 Office 部署工具

系統會使用 Office 部署工具建立 office 2016 App-v 套件，該工具會產生 Office 2016 App-v 封裝。 無法透過 App-v 排序器建立或修改套件。 開始建立套件：

1.  下載適用于隨選即用的[Office 2016 部署工具](https://www.microsoft.com/download/details.aspx?id=49117)。

> **重要**您必須使用 Office 2016 部署工具來建立 Office 2016 App-v 套件。
> 2. 執行 .exe 檔案，並將其功能解壓至想要的位置。 若要簡化這個程式，您可以建立共用網路資料夾，以儲存功能。

    Example: \\\\Server\\Office2016

3. 檢查 setup.exe 和 configuration.xml 檔案是否存在，且位於您指定的位置。

### 下載 Office 2016 應用程式

下載 Office 部署工具之後，您就可以使用它來取得最新的 Office 2016 應用程式。 在取得 Office 應用程式之後，您會建立 Office 2016 App-v 套件。

Office 部署工具中包含的 XML 檔案會指定產品詳細資料，例如隨附的語言和 Office 應用程式。

1. **自訂範例 XML 設定檔：** 使用您使用 Office 部署工具下載的範例 XML 設定檔，來自訂 Office 應用程式：

   1. 在記事本或您最愛的文字編輯器中開啟範例 XML 檔案。

   2. 在範例 configuration.xml 檔案開啟並準備好進行編輯時，您可以指定產品、語言及儲存 Office 2016 應用程式的路徑。 下列是 configuration.xml 檔案的基本範例：

      ```xml
      <Configuration>
         <Add SourcePath= "\\Server\Office2016” OfficeClientEdition="32" >
          <Product ID="O365ProPlusRetail ">
            <Language ID="en-us" />
          </Product>
          <Product ID="VisioProRetail">
            <Language ID="en-us" />
          </Product>
        </Add>
      </Configuration>
      ```

      >**記事** [配置 XML] 是範例 XML 檔案。 檔案包含已加上注釋的線條。您可以「取消注釋」這些線條，以自訂檔案的其他設定。 若要 "取消注釋" 這些線條，請移除「<！ --從行開頭，然後從行尾的 "-->"。

      上述 XML 設定檔指定 Office 2016 專業增強版32位版本（包括 Visio 專業增強版）將會以英文下載至 \\\\server\\Office 2016，這是儲存 Office 應用程式的位置。 請注意，應用程式的產品識別碼不會影響 Office 的最終授權。 您可以透過在後續階段指定授權，從相同的應用程式建立具有各種授權的 Office 2016 App-v 套件。 下表摘要列出了 XML 檔案的可自訂屬性和元素：

      <table>
      <colgroup>
      <col width="33%" />
      <col width="33%" />
      <col width="33%" />
      </colgroup>
      <thead>
      <tr class="header">
      <th align="left">輸入</th>
      <th align="left">描述</th>
      <th align="left">範例</th>
      </tr>
      </thead>
      <tbody>
      <tr class="odd">
      <td align="left"><p>Add 元素</p></td>
      <td align="left"><p>指定套件中要包含的產品和語言。</p></td>
      <td align="left"><p>無</p></td>
      </tr>
      <tr class="even">
      <td align="left"><p>OfficeClientEdition （Add 元素的屬性）</p></td>
      <td align="left"><p>指定要使用的 Office 2016 產品版本：32位或64位。 如果 <strong> OfficeClientEdition 未 </strong> 設定為有效的值，則操作會失敗。</p></td>
      <td align="left"><p><strong>OfficeClientEdition </strong> = &quot; 32&quot;</p>
      <p><strong>OfficeClientEdition </strong> = &quot; 64&quot;</p></td>
      </tr>
      <tr class="odd">
      <td align="left"><p>Product 元素</p></td>
      <td align="left"><p>指定應用程式。 若要在應用程式中加入，您必須在此處將 Project 2016 和 Visio 2016 指定為已新增的產品。

      如需產品識別碼的詳細資訊，請參閱 <a href="https://support.microsoft.com/kb/2842297" data-raw-source="[Product IDs that are supported by the Office Deployment Tool for Click-to-Run](https://support.microsoft.com/kb/2842297)"> Office 部署工具支援的隨選即用的產品識別碼</a>
      </p></td>
      <td align="left"><p><code>Product ID =&quot;O365ProPlusRetail &quot;</code></p>
      <p><code>Product ID =&quot;VisioProRetail&quot;</code></p>
      <p><code>Product ID =&quot;ProjectProRetail&quot;</code></p>
      </td>
      </tr>
      <tr class="even">
      <td align="left"><p>語言元素</p></td>
      <td align="left"><p>指定應用程式中支援的語言</p></td>
      <td align="left"><p><code>Language ID=&quot;en-us&quot;</code></p></td>
      </tr>
      <tr class="odd">
      <td align="left"><p>版本（Add 元素的屬性）</p></td>
      <td align="left"><p>選用。 指定套件要使用的組建</p>
      <p>預設為最新的播發組建（在 Office 來源 v32.CAB 中定義）。</p></td>
      <td align="left"><p><code>16.1.2.3</code></p></td>
      </tr>
      <tr class="even">
      <td align="left"><p>SourcePath （Add 元素的屬性）</p></td>
      <td align="left"><p>指定要將應用程式儲存到哪個位置。</p></td>
      <td align="left"><p><code>Sourcepath = &quot;\Server\Office2016”</code></p></td>
      </tr>
      <tr class="even">
      <td align="left"><p>通道（Add 元素的屬性）</p></td>
      <td align="left"><p>選用。 指定您要下載或安裝之產品的更新通道。 </p><p>如需更新通道的詳細資訊，請參閱適用于企業的 Microsoft 365 應用程式更新通道的概覽。</p></td>
      <td align="left"><p><code>Channel=&quot;Deferred&quot;</code></p></td>
      </tr>
      </tbody>
      </table>

      在編輯 configuration.xml 檔案以指定所需的產品、語言，以及 Office 2016 應用程式儲存到的位置之後，您可以儲存設定檔，例如 Customconfig.xml。

2. **將應用程式下載到指定位置：** 使用提升許可權的命令提示字元與64位作業系統，下載稍後將轉換成 App-v 套件的 Office 2016 應用程式。 以下是包含詳細描述的範例命令：

   ``` syntax
   \\server\Office2016\setup.exe /download \\server\Office2016\Customconfig.xml
   ```

   在範例中：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>\server\Office2016</strong></p></td>
   <td align="left"><p>是包含 Office 部署工具以及自訂 Configuration.xml 檔案的網路共用位置 Customconfig.xml。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>Setup.exe</strong></p></td>
   <td align="left"><p>是 Office 部署工具。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>/download</strong></p></td>
   <td align="left"><p>下載您在 customConfig.xml 檔案中指定的 Office 2016 應用程式。 這些 bits 可以在 Office 2016 App-v 套件中以大量授權進行轉換。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>\server\Office2016\Customconfig.xml</strong></p></td>
   <td align="left"><p>傳遞完成下載程式所需的 XML 設定檔，在此範例中 customconfig.xml。 使用 [下載] 命令之後，請在配置 xml 檔案中指定的位置找到 Office 應用程式，此範例 \Server\Office2016。</p></td>
   </tr>
   </tbody>
   </table>



### 將 Office 應用程式轉換成 App-v 套件

透過 Office 部署工具下載 Office 2016 應用程式之後，請使用 Office 部署工具，將它們轉換成 Office 2016 App-v 套件。 完成與您的授權模型相對應的步驟。

**您需要執行的作業摘要：**

-   在64位 Windows 電腦上建立 Office 2016 App-v 套件。 不過，套件將在32位和64位 Windows 7、Windows 8 或8.1 以及 Windows 10 電腦上執行。

-   使用 Office 部署工具建立訂閱授權套件的 Office App-v 套件，然後修改 CustomConfig.xml 設定檔。

    下表摘要列出您所使用的授權模型 CustomConfig.xml 檔案中所需輸入的值。 表格後續各節中的步驟將會指定您所需的確切專案。

>**Note** &nbsp; 記事 &nbsp;您可以使用 Office 部署工具來為適用于企業的 Microsoft 365 應用程式建立 app-v 套件。 不支援為大量授權版本的 Office 專業增強版或 Office Standard 建立套件。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">產品識別碼</th>
<th align="left">訂閱授權</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Office 2016</strong></p></td>
<td align="left"><p>O365ProPlusRetail</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Office 2016 與 Visio 2016</strong></p></td>
<td align="left"><p>O365ProPlusRetail</p>
<p>VisioProRetail</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Office 2016 與 Visio 2016 和 Project 2016</strong></p></td>
<td align="left"><p>O365ProPlusRetail</p>
<p>VisioProRetail</p>
<p>ProjectProRetail</p></td>
</tr>
</tbody>
</table>



**如何將 Office 應用程式轉換成 App-v 套件**

1. 在 [記事本] 中，重新開啟 CustomConfig.xml 檔案，然後對檔案進行下列變更：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">參數</th>
   <th align="left">要變更值的專案</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>SourcePath</p></td>
   <td align="left"><p>指向先前下載的 Office 應用程式。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>ProductID</p></td>
   <td align="left"><p>指定訂閱授權，如下列範例所示：</p>
   <pre class="syntax" space="preserve"><code>&lt;Configuration&gt;
      &lt;Add SourcePath= &quot;\server\Office 2016&quot; OfficeClientEdition=&quot;32&quot; &gt;
       &lt;Product ID=&quot;O365ProPlusRetail&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
       &lt;Product ID=&quot;VisioProRetail&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
     &lt;/Add&gt;
   &lt;/Configuration&gt; </code></pre>
   <p>在這個範例中，建立含訂閱授權的套件的下列變更：</p>
   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>SourcePath</strong></p></td>
   <td align="left"><p>路徑，該路徑已變更為指向先前下載的 Office 應用程式。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>產品識別碼</strong></p></td>
   <td align="left"><p>[Office 的變更為] <code>O365ProPlusRetail</code> 。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>產品識別碼</strong></p></td>
   <td align="left"><p>Visio 的 [變更為] <code>VisioProRetail</code> 。</p></td>
   </tr>
   </tbody>
   </table>
   <p></p>
   <tr class="odd">
   <td align="left"><p>ExcludeApp （選用）</p></td>
   <td align="left"><p>可讓您指定您不想要包含在 Office 部署工具所建立的 App-v 套件中的 Office 程式。 例如，您可以排除 Access 和 InfoPath。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>PACKAGEGUID （選用）</p></td>
   <td align="left"><p>根據預設，Office 部署工具所建立的所有 app-v 套件都共用相同的 App-v 套件識別碼。 您可以使用 PACKAGEGUID 為每個套件指定不同的套件識別碼，這可讓您發佈由 Office 部署工具所建立的多個 App-v 套件，並使用 App-v 伺服器來管理它們。</p>
   <p>若要在不同的使用者建立不同的套件時，使用這個參數的範例。 例如，您可以建立一個包含適用于部分使用者之 Office 2016 的套件，並使用 Office 2016 和 Visio 2016 為其他使用者組建立另一個套件。</p>
&gt;<strong>注意 </strong> 即使您使用的是唯一的套件識別碼，您仍然可以只將一個 app-v 套件部署到單一裝置。
   </td>
   </tr>
   </tbody>
   </table>



2. 使用/packager 命令，將 Office 應用程式轉換為 Office 2016 App-v 套件。

   例如：

   ``` syntax
   \\server\Office2016\setup.exe /packager \\server\Office2016\Customconfig.xml  \\server\share\Office2016AppV
   ```

   在範例中：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>\server\Office2016</strong></p></td>
   <td align="left"><p>是包含 Office 部署工具以及自訂 Configuration.xml 檔案的網路共用位置 Customconfig.xml。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>Setup.exe</strong></p></td>
   <td align="left"><p>是 Office 部署工具。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>/packager</strong></p></td>
   <td align="left"><p>使用 customConfig.xml 檔案中指定的授權類型建立 Office 2016 App-v 套件。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>\server\Office2016\Customconfig.xml</strong></p></td>
   <td align="left"><p>傳送已針對封裝階段準備的設定 XML 檔案（在此案例中為 customConfig）。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>\server\share\Office 2016AppV</strong></p></td>
   <td align="left"><p>指定新建立的 Office App-v 封裝的位置。</p></td>
   </tr>
   </tbody>
   </table>



~~~
After you run the **/packager** command, the following folders appear up in the directory where you specified the package should be saved:

-   **App-V Packages** – contains an Office 2016 App-V package and two deployment configuration files.

-   **WorkingDir**

**Note** To troubleshoot any issues, see the log files in the %temp% directory (default).
~~~



3. 確認 Office 2016 App-v 套件正常運作：

   1.  將您全域建立的 Office 2016 App-v 套件發佈至測試電腦，並確認 [Office 2016] 快捷方式隨即出現。

   2.  啟動幾個 Office 2016 應用程式（例如 Excel 或 Word），以確保您的套件如預期的那樣正常運作。

## <a href="" id="bkmk-pub-pkg-office"></a>發佈應用程式的 Office 套件-V


使用下列資訊發佈 Office 套件。

### 發佈 Office App-v 套件的方法

使用您用於任何其他套件的相同方法，部署適用于 Office 2016 的 app-v 套件：

-   System Center Configuration Manager

-   App-v Server

-   從 PowerShell 命令中獨立

### 發佈先決條件與需求

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">先決條件或需求</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在 App-V 用戶端上啟用 PowerShell 腳本</p></td>
<td align="left"><p>若要發佈 Office 2016 套件，您必須執行腳本。</p>
<p>預設會停用 App-v 用戶端上的套件腳本。 若要啟用腳本，請執行下列 PowerShell 命令：</p>
<pre class="syntax" space="preserve"><code>Set-AppvClientConfiguration –EnablePackageScripts 1</code></pre></td>
</tr>
<tr class="even">
<td align="left"><p>全域發佈 Office 2016 套件</p></td>
<td align="left"><p>Office App-v 套件中的延伸點需要在電腦層級進行安裝。</p>
<p>當您在電腦層級發佈時，不需要任何必備動作或可轉散發元件，而且 Office 2016 套件全域可讓其應用程式像是原本安裝的 Office，而不需要系統管理員自訂套件。</p></td>
</tr>
</tbody>
</table>



### 如何發佈 Office 套件

執行下列命令以全域發佈 Office 套件：

-   `Add-AppvClientPackage <Path_to_AppV_Package> | Publish-AppvClientPackage –global`

-   從 App-v Server 上的 Web 管理主控台，您可以將許可權新增至電腦群組，而不是使用者群組，以便將套件全域發佈至對應群組中的電腦。

## <a href="" id="bkmk-custmz-manage-office-pkgs"></a>自訂及管理 Office App-v 套件


若要管理您的 Office App-v 套件，請使用與任何其他套件相同的作業，但有幾個例外狀況，如下列各節所述。

-   [使用連線群組啟用 Office 外掛程式](#bkmk-enable-office-plugins)

-   [停用 Office 2016 應用程式](#bkmk-disable-office-apps)

-   [停用 Office 2016 快速鍵](#bkmk-disable-shortcuts)

-   [管理 Office 2016 套件升級](#bkmk-manage-office-pkg-upgrd)

-   [使用 Office 部署 Visio 2016 和 Project 2016](#bkmk-deploy-visio-project)

### <a href="" id="bkmk-enable-office-plugins"></a>使用連線群組啟用 Office 外掛程式

使用本節中的步驟，啟用 office 外掛程式與您的 Office 套件。 若要使用 Office 外掛程式，您必須使用 App-v 排序器來建立只包含外掛程式的個別套件。您無法使用 Office 部署工具來建立外掛程式封裝。 接著，您可以建立包含 Office 套件和外掛程式套件的連線群組，如以下步驟所述。

**若要啟用 Office App-v 的外掛程式套件**

1.  透過 App-V Server、System Center Configuration Manager 或 PowerShell Cmdlet 新增連線群組。

2.  使用 App-v 排序器來排序您的外掛程式。 確定使用的電腦上已安裝 Office 2016 來為外掛程式進行排序。 我們建議您在順序電腦上使用 Microsoft 365 App for enterprise （非虛擬），當您依序排列 Office 2016 外掛程式。

3.  建立包含所需外掛程式的 app-v 套件。

4.  透過 App-V server、System Center Configuration Manager 或 PowerShell Cmdlet 新增連線群組。

5.  新增 Office 2016 App-v 套件，以及您已排序到您所建立之連線群組的外掛程式套件。

    >**重要**[連線] 群組中的套件順序決定了套件內容的合併順序。 在您的連線群組描述項檔案中，先新增 Office 2016 App-v 套件，然後再新增外掛程式 App-v 套件。



6.  請確定這兩個套件都發佈到目的電腦，且該外掛程式套件是以全域方式發佈，以符合已發佈的 Office 2016 App-v 套件的全域設定。

7.  確認外掛程式套件的部署設定檔與 Office 2016 App-v 套件具有相同的設定。

    因為 Office 2016 App-v 套件與作業系統整合，所以外掛程式套件設定應該會相符。 您可以在部署設定檔中搜尋「COM Mode」，並確保您的外掛程式套件將此值設定為「整合」，且 "InProcessEnabled" 和 "OutOfProcessEnabled" 與您發佈的 Office 2016 App-v 套件的設定相符。

8.  開啟部署設定檔，並將**物件**的值設為**false**。

9.  如果您在排序之後對部署設定檔進行任何變更，請確定該外掛程式套件是與檔案一起發佈。

10. 確定您所建立的連線群組已啟用至所需的電腦上。 如果啟用連線群組時，所建立的連線群組可能會「待定」，如果是使用 Office 2016 App-v 套件。 如果發生這種情況，您必須重新開機，才能成功啟用連線群組。

11. 當您成功發佈這兩個套件並啟用連線群組之後，請啟動目標 Office 2016 應用程式，並確認您發佈並新增至連線群組的外掛程式會如預期的那樣運作。

### <a href="" id="bkmk-disable-office-apps"></a>停用 Office 2016 應用程式

您可能會想要停用 Office App-v 封裝中的特定應用程式。 例如，您可以停用 Access，但讓所有其他 Office 應用程式成為主要的可用。 當您停用應用程式時，最終使用者將不再看到該應用程式的快捷方式。 您不需要重新排序應用程式。 當您在 Office 2016 App-v 套件發佈之後變更部署設定檔之後，您將會儲存變更、新增 Office 2016 App-v 套件，然後使用新的部署設定檔重新發佈，以將新設定套用至 Office 2016 App-v 封裝應用程式。

>**記事**若要排除特定的 Office 應用程式（例如，Access 和 InfoPath），當您使用 Office 部署工具建立 App-v 套件時，請使用**ExcludeApp**設定。


**停用 Office 2016 應用程式**

1.  使用文字編輯器（如**記事本**）開啟部署設定檔，然後搜尋「應用程式」。

2.  搜尋您想要停用的 Office 應用程式，例如 Access 2016。

3.  將 [Enabled] 的值從 "true" 變更為 "false"。

4.  儲存部署設定檔。

5.  使用新的部署設定檔新增 Office 2016 App-v 套件。

    ```xml
    <Application Id="[{AppVPackageRoot}]\office16\lync.exe" Enabled="true">
      <VisualElements>
        <Name>Lync 2016</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    <Application Id="[(AppVPackageRoot}]\office16\MSACCESS.EXE" Enabled="true">
      <VisualElements>
        <Name>Access 2016</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    ```

6.  重新新增 Office 2016 App-v 套件，然後使用新的部署設定檔重新發佈，以將新設定套用至 Office 2016 App-v 封裝應用程式。

### <a href="" id="bkmk-disable-shortcuts"></a>停用 Office 2016 快速鍵

您可能會想要針對特定的 Office 應用程式停用快速鍵，而不是取消發佈或移除套件。 下列範例顯示如何停用 Microsoft Access 的快速鍵。

**若要停用 Office 2016 應用程式的快速鍵**

1.  在記事本中開啟部署設定檔案，然後搜尋 [快速鍵]。

2.  若要停用某些快速鍵，請刪除或批註您不想要的特定快速鍵。 您必須讓子系統保持存在且已啟用。 例如，在下列範例中，刪除 Microsoft Access 快速鍵，同時保持子系統 &lt; 快捷方式/shortcut， &gt; &lt; &gt; 以停用 Microsoft Access 快速鍵。

    ``` syntax
    Shortcuts

    -->
     <Shortcuts Enabled="true">
      <Extensions>
        <Extension Category="AppV.Shortcut">
          <Shortcut>
           <File>[{Common Programs}]\Microsoft Office 2016\Access 2016.lnk</File>
           <Target>[{AppvPackageRoot}])office16\MSACCESS.EXE</Target>
           <Icon>[{Windows}]\Installer\{90150000-000F-0000-0000-000000FF1CE)\accicons.exe.Ø.ico</Icon>
           <Arguments />
           <WorkingDirectory />
           <AppuserModelId>Microsoft.Office.MSACCESS.EXE.15</AppUserModelId>
           <AppUserModelExcludeFromShowInNewInstall>true</AppUserModelExcludeFromShowInNewInstall>
           <Description>Build a professional app quickly to manage data.</Description>
           <ShowCommand>l</ShowCommand>
           <ApplicationId>[{AppVPackageRoot}]\office16\MSACCESS.EXE</ApplicationId>
        </Shortcut>
    ```

3.  儲存部署設定檔。

4.  使用新的部署設定檔重新發佈 Office 2016 App-v 套件。

您可以透過修改 App-v 套件的部署設定來變更許多其他設定，例如，檔案類型關聯、虛擬檔案系統等。 如需如何使用部署設定檔來變更 app-v 套件設定的其他資訊，請參閱本文結尾的 [其他資源] 區段。

### <a href="" id="bkmk-manage-office-pkg-upgrd"></a>管理 Office 2016 套件升級

若要升級 Office 2016 套件，請使用 Office 部署工具。 若要升級先前部署的 Office 2016 套件，請執行下列步驟。

**如何升級先前部署的 Office 2016 套件**

1. 使用最新的 Office 2016 應用程式軟體，透過 Office 部署工具建立新的 Office 2016 套件。 最新的 Office 2016 bits 隨時都可以透過建立 Office 2016 App-v 套件的下載階段取得。 新建立的 Office 2016 套件將會有最新的更新及新的版本 ID。 使用 Office 部署工具所建立的所有套件都有相同的沿襲。

   > **記事**Office App-v 封裝有兩個版本識別碼：
   > <ul>
   > <li>在使用 Office 部署工具所建立的所有套件中，都是唯一的 Office 2016 App-v 套件版本 ID。</li>
   > <li>第二個 App-v 套件版本 ID： x.x.x.x （例如，在 AppX 資訊清單中，只要有新版 Office 本身，就只會變更）。 例如，如果有可升級的新 Office 2016 版本，且已透過 Office 部署工具建立套件以納入這些升級，則 X.x.x.x 版本 ID 將會變更，以反映 Office 版本本身已變更。 App-v server 會使用 X.x.x.x 版本 ID 來區分此套件，並辨識它包含先前已發佈套件的新升級，因此，將其發佈為現有 Office 2016 套件的升級。。</li>
   > </ul>


2. 將新建立的 Office 2016 App-v 套件，全域發佈到您想要套用新更新的電腦上。 由於新的套件與舊版 Office 2016 App-v 套件有相同的沿襲，所以發佈含有更新的新套件只會將新的變更套用至舊的套件，因此會快速進行。

3. 將會以任何全域發佈的 app-v 套件相同的方式來套用升級。 因為應用程式可能正在使用，所以升級可能會延遲，直到電腦重新開機為止。


### <a href="" id="bkmk-deploy-visio-project"></a>使用 Office 部署 Visio 2016 和 Project 2016

下表說明使用 Office 部署 Visio 2016 和 Project 2016 的需求和選項。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">工作</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>我要如何使用 Office 封裝及發佈 Visio 2016 和 Project 2016？</p></td>
<td align="left"><p>您必須在與 Office 相同的套件中包含 Visio 2016 和 Project 2016。</p>
<p>如果您不是部署 Office，只要遵循本主題中所述的封裝、發佈和部署需求，就可以建立內含 Visio 與/或專案的套件。</p></td>
</tr>
<tr class="even">
<td align="left"><p>我要如何將 Visio 2016 和 Project 2016 部署至特定使用者？</p></td>
<td align="left"><p>使用下列其中一種方法：</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">如果您想要 .。。</th>
<th align="left">...然後使用此方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>建立兩個不同的套件，並將每個套件部署至不同的使用者群組</p></td>
<td align="left"><p>建立及部署下列套件：</p>
<ul>
<li><p>僅包含 Office 部署至使用者只需要 Office 的電腦的套件。</p></li>
<li><p>包含 Office、Visio 和 Project-部署至使用者需要所有三個應用程式的電腦的套件。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>如果您只想在整個組織中使用一個套件，或者如果您有共用電腦的使用者：</p></td>
<td align="left"><p>遵循下列步驟：</p>
<ol>
<li><p>建立包含 Office、Visio 和 Project 的套件。</p></li>
<li><p>將套件部署到所有使用者。</p></li>
<li><p>使用 <a href="https://technet.microsoft.com/library/dd723678.aspx" data-raw-source="[Microsoft AppLocker](https://technet.microsoft.com/library/dd723678.aspx)"> Microsoft AppLocker </a> 來防止特定使用者使用 Visio 和 Project。</p></li>
</ol></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>



## 其他資源


[使用 App-V 部署 Microsoft Office 2013](deploying-microsoft-office-2013-by-using-app-v.md)

[使用 App-V 部署 Microsoft Office 2010](deploying-microsoft-office-2010-by-using-app-v.md)

[「隨選即用」的 Office 2016 部署工具](https://www.microsoft.com/download/details.aspx?id=49117)

**連線群組**

[在 Microsoft App 中部署連線群組-V v5](https://go.microsoft.com/fwlink/p/?LinkId=330683)

[管理連線群組](managing-connection-groups.md)

**動態設定**

[關於 App-V 5.1 動態組態](about-app-v-51-dynamic-configuration.md)





