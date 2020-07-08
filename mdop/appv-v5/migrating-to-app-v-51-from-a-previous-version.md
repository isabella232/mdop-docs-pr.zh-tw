---
title: 從舊版移轉到 App-V 5.1
description: 從舊版移轉到 App-V 5.1
author: dansimp
ms.assetid: e7ee0edc-7544-4c0a-aaca-d922a33bc1bb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7fb6ddbfed4f6fd1ae9613d2ee86361a51918a65
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800372"
---
# 從舊版移轉到 App-V 5.1


使用 Microsoft Application Virtualization （App-v）5.1，您可以將現有的 App-v 4.6 或 App-v 5.0 基礎結構遷移至更具彈性、整合且更輕鬆管理的 App-v 5.1 基礎結構。
不過，您無法直接從 App-v-V 到 App-v 5.1 的遷移，您必須先將 App 遷移至 app-v 5.0。 如需從 App-v-V 到 App-v 5.0 的遷移的詳細資訊，請參閱[從舊版進行遷移](migrating-from-a-previous-version-app-v-50.md)  

**記事** App-v 5.1 套件與 App-v 5.0 套件完全相同。 版本之間沒有任何套件格式的變更，因此不需要將 App-v 5.0 套件轉換成 App-v 5.1 套件。

如需 App-v 4.6 與 App-v 5.1 之間差異的詳細資訊，請參閱[關於 app-v 5.0](about-app-v-50.md)的**app-v 4.6 與 app-v 5.0 區段之間的差異**。

 

## <a href="" id="bkmk-pkgconvimprove"></a>應用程式-V 5.1 套件轉換器的改良功能


您現在可以使用套件轉換器來轉換內含腳本的 App-v 4.6 套件，而來源 .osd 檔案的登錄資訊和腳本現在已包含在套件轉換程式輸出中。

您也可以在 `–OSDsToIncludeInPackage` Cmdlet 中使用參數， `ConvertFrom-AppvLegacyPackage` 指定哪些 osd 檔案的資訊已轉換並放在新套件中。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 5.1 中的新功能</th>
<th align="left">App-v 5.1 之前</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>新的 .xml 檔案是與與套件相關聯的 .osd 檔案建立的。這些檔案包括下列資訊：</p>
<ul>
<li><p>環境變數</p></li>
<li><p>方式</p></li>
<li><p>檔案類型關聯</p></li>
<li><p>註冊資訊</p></li>
<li><p>上下</p></li>
</ul>
<p>您現在可以選擇從來原始目錄將來自 osd 檔案子集的資訊新增到使用參數的套件中 <code>-OSDsToIncludeInPackage</code> 。</p></td>
<td align="left"><p>與套件相關聯的 .osd 檔案中所包含的登錄資訊與腳本並不包含在套件轉換器輸出中。</p>
<p>套件轉換器會使用來原始目錄中所有 .osd 檔案的資訊來填入新套件。</p></td>
</tr>
</tbody>
</table>

 

### 轉換語句範例

若要瞭解新程式，請參閱下列範例 `ConvertFrom-AppvLegacyPackage` 封裝轉換器語句。

**如果來原始目錄（\\\\OldPkgStore\\ContosoApp）包含下列專案：**

-   ContosoApp

-   ContosoApp.msi

-   ContosoApp.sprj

-   ContosoApp\_manifest.xml

-   X.x.x。x

-   .Osd

-   Z. osd

**然後執行此命令：**

``` syntax
ConvertFrom-AppvLegacyPackage –SourcePath \\OldPkgStore\ContosoApp\ 
-DestinationPath \\NewPkgStore\ContosoApp\
-OSDsToIncludeInPackage X.osd,Y.osd
```

**在目的地目錄（\\\\NewPkgStore\\ContosoApp）中會建立下列專案：**

-   ContosoApp appv

-   ContosoApp.msi

-   ContosoApp\_DeploymentConfig.xml

-   ContosoApp\_UserConfig.xml

-   X\_Config.xml

-   Y\_Config.xml

-   Z\_Config.xml

**在上述範例中：**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">這些來原始目錄檔案 .。。</th>
<th align="left">...會轉換成這些目的地目錄檔案 .。。</th>
<th align="left">...並且將包含這些專案</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><ul>
<li><p>X.x.x。x</p></li>
<li><p>.Osd</p></li>
<li><p>Z. osd</p></li>
</ul></td>
<td align="left"><ul>
<li><p>X_Config.xml</p></li>
<li><p>Y_Config.xml</p></li>
<li><p>Z_Config.xml</p></li>
</ul></td>
<td align="left"><ul>
<li><p>環境變數</p></li>
<li><p>方式</p></li>
<li><p>檔案類型關聯</p></li>
<li><p>註冊資訊</p></li>
<li><p>指令碼</p></li>
</ul></td>
<td align="left"><p>每個 .osd 檔案都會轉換成個別的對應 .xml 檔案，其中包含此處在 App-v 5.1 部署設定格式中所列的專案。 然後，您就可以從這些 .xml 檔案複製這些專案，並視需要將它們放在部署配置或使用者設定檔中。</p>
<p>在這個範例中，有三個 .xml 檔案，對應至來原始目錄中的三個 .osd 檔案。 每個 .xml 檔案都包含其對應的 .osd 檔案中的環境變數、快速鍵、檔案類型關聯、登錄資訊和腳本。</p></td>
</tr>
<tr class="even">
<td align="left"><ul>
<li><p>X.x.x。x</p></li>
<li><p>.Osd</p></li>
</ul></td>
<td align="left"><ul>
<li><p>ContosoApp appv</p></li>
<li><p>ContosoApp_DeploymentConfig.xml</p></li>
<li><p>ContosoApp_UserConfig.xml</p></li>
</ul></td>
<td align="left"><ul>
<li><p>環境變數</p></li>
<li><p>方式</p></li>
<li><p>檔案類型關聯</p></li>
</ul></td>
<td align="left"><p>在參數中指定的 .osd 檔案中的資訊 <code>-OSDsToIncludeInPackage</code> 會轉換並放在套件內。 接著，轉換器會使用套件內容填入部署設定檔和使用者配置檔案，就像在排序新套件時，App-v 排序器所做的一樣。</p>
<p>在這個範例中，在 X-blade 和 Y 中包含的環境變數、快捷方式和檔案類型關聯，都已轉換並放在應用程式 V 套件中，而其中一些資訊也包含在部署設定和使用者設定檔中。 之所以使用 x.x 和 a.x，是因為它們是作為引數包含在參數中 <code>-OSDsToIncludeInPackage</code> 。 不包含來自 Z 的任何資訊，因為它不是包含在其中一個引數中。</p></td>
</tr>
</tbody>
</table>

 

## 轉換使用舊版 App-v （V）建立的套件


使用套件轉換器實用程式來升級在 App-v 5.0 之前使用 app-v 版本建立的虛擬應用程式套件。 套件轉換器使用 PowerShell 來轉換套件，如果您有多個需要轉換的套件，就能協助自動處理常式。

**重要** 在您轉換現有的套件之後，您應該先測試套件，然後再部署套件，以確保轉換程式已成功完成。

 

**轉換現有套件前的須知事項**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">問題</th>
<th align="left">因應措施</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在轉換之後，使用 DSC 的虛擬套件不會連結。</p></td>
<td align="left"><p>使用連線群組連結封裝。 請參閱 <a href="managing-connection-groups51.md" data-raw-source="[Managing Connection Groups](managing-connection-groups51.md)"> 管理連線群組 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在轉換期間偵測到環境變數衝突。</p></td>
<td align="left"><p>解決相關的 .osd 檔案中的任何衝突 <strong> </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>在轉換期間檢測到硬編碼路徑。</p></td>
<td align="left"><p>硬編碼路徑難以正確轉換。 套件轉換器會檢測並傳回內含硬編碼路徑之檔案的套件。 使用硬編碼路徑來查看檔案，並判斷套件是否需要該檔案。 如果是，建議您重新排列套件。</p></td>
</tr>
</tbody>
</table>

 

轉換套件時，請檢查是否有失敗的檔案或快速鍵。 在 App-v 4.6 套件中找出該專案。 它可能是硬式編碼路徑。 轉換路徑。

**記事** 建議您使用 App-v 5.1 sequencer 來轉換需要利用功能的重要應用程式或應用程式。 請參閱[如何使用 app-v 5.1 來排序新的應用程式](how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md)。

如果轉換後的套件未在轉換後開啟，建議您使用 App-v 5.1 排序器重新排序應用程式。

 

[如何轉換在舊版 App-V 中建立的套件](how-to-convert-a-package-created-in-a-previous-version-of-app-v51.md)

## 遷移用戶端


下表顯示升級用戶端的建議方法。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">工作</th>
<th align="left">其他資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>將您的環境升級至最新版本的 App-V 4。6</p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)">應用程式虛擬化部署和升級考慮 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>安裝 App-V 5.1 用戶端（含共存功能）。</p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md" data-raw-source="[How to Deploy the App-V 4.6 and the App-V 5.1 Client on the Same Computer](how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md)">如何在同一部電腦上部署 app-v 4.6 和 App-v 5.1 用戶端 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>順序及推出 app-v 5.1 套件。 視需要，取消發佈 App-v 4.6 套件。</p></td>
<td align="left"><p><a href="how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md" data-raw-source="[How to Sequence a New Application with App-V 5.1](how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md)">如何使用 App-v 5.1 來排序新的應用程式 </a> 。</p></td>
</tr>
</tbody>
</table>

 

**重要** 您必須執行最新版 App-V 4.6 才能使用共存模式。 此外，當您排列套件時，您必須設定 [管理機構] 設定（位於 **[使用者設定**] 中的 [**使用者**設定] 區段中）。

 

## 遷移 app-v 5.1 Server 的完整基礎結構


沒有直接的方法可升級至完整的 App-v 5.1 基礎結構。 請使用下一節中的資訊，以取得有關升級 App-v 伺服器的資訊。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">工作</th>
<th align="left">其他資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>將您的環境升級至最新版的 App-V 4.6。</p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)">應用程式虛擬化部署和升級考慮 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>部署 app-v 5.1 版本的用戶端。</p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-client-51gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-51gb18030.md)">如何部署 App-v 用戶端 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>安裝 App-V 5.1 server。</p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-51-server.md" data-raw-source="[How to Deploy the App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md)">如何部署 app-v 5.1 伺服器 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>[遷移現有的套件]。</p></td>
<td align="left"><p>請參閱本文中的 [ <strong> 使用先前版本的 app-v 建立的套件] </strong> 區段。</p></td>
</tr>
</tbody>
</table>

 

## 其他遷移任務


您也可以執行額外的遷移工作，例如重新配置端點，以及開啟在執行 App-v 5.1 用戶端的電腦上使用先前版本建立的套件。 下列連結提供執行這些工作的詳細資訊。

[如何為特定電腦上的所有使用者，將擴充點從 App-V 4.6 封裝移轉至轉換的 App-V 5.1 封裝](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-51-package-for-all-users-on-a-specific-computer.md)

[如何為特定使用者，將擴充點從 App-V 4.6 封裝移轉至 App-V 5.1](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md)

[如何為特定電腦上的所有使用者，將擴充點從 App-V 5.1 封裝移轉至 App-V 4.6 封裝](how-to-revert-extension-points-from-an-app-v-51-package-to-an-app-v-46-package-for-all-users-on-a-specific-computer.md)

[如何為特定使用者，將擴充點從 App-V 5.1 封裝移轉至 App-V 4.6 封裝](how-to-revert-extension-points-from-an-app-v-51-package-to-an-app-v-46-package-for-a-specific-user.md)







## 執行 App-v 遷移任務的其他資源


[App-V 5.1 作業](operations-for-app-v-51.md)

[簡化的 Microsoft App-v 5.1 管理伺服器升級程式](https://go.microsoft.com/fwlink/p/?LinkId=786330)

 

 





