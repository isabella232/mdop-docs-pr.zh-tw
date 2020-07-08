---
title: 如何下載及部署 MDOP 群組原則 (.admx) 範本
description: 如何下載及部署 MDOP 群組原則 (.admx) 範本
author: dansimp
ms.assetid: fdb64505-6c66-4fdf-ad74-a6a161191e3f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/15/2018
ms.openlocfilehash: 5bc5f8d536c113ccbc0a1931e6c7e4ed3c7a9a37
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812044"
---
# 如何下載及部署 MDOP 群組原則 (.admx) 範本


您可以使用群組原則範本（admx 與 adml 檔案），管理某些 Microsoft 桌面優化套件（MDOP）技術（例如，App-v、UE-V 或 MBAM）的功能設定。 您可以在自解壓縮、壓縮檔案中下載 MDOP 群組原則範本，並依技術和版本分組。

## MDOP 群組原則範本

**如何下載及部署 MDOP 群組原則範本**

1. 下載最新的[MDOP 群組原則範本](https://www.microsoft.com/download/details.aspx?id=55531) 

2. 透過執行來展開已下載的 .cab 檔案 `expand <download_folder>\MDOP_ADMX_Templates.cab -F:* <destination_folder>`

   **警告**  
   請勿將範本直接解壓縮至 [群組原則] 部署目錄。 在此檔案中捆綁了多種技術與版本。

3. 在解壓縮的資料夾中，找出技術版本的 admx 檔案。 某些 MDOP 技術有多組群組原則物件（Gpo）。 例如，MBAM 包括 MBAM 管理設定和 MBAM 使用者設定。

4. 依語言區域性（也就是*en-us* -美國）來找出適當的 adml 檔案。

5. 將 admx 與 adml 檔案複製到原則定義資料夾中。 根據您儲存範本的位置，您可以從本機裝置或網域上的任何電腦來設定群組原則設定。

   - **本機檔案：** 若要從本機裝置設定群組原則設定，請將範本檔案複製到下列位置：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">檔案類型</th>
   <th align="left">檔案位置</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>群組原則範本（admx）</p></td>
   <td align="left"><p><code>%systemroot%</code>&lt;強勁 &gt; policyDefinitions</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>群組原則語言檔（adml）</p></td>
   <td align="left"><p><code>%systemroot%</code>&lt;強勁 &gt; policyDefinitions</strong><code>[MUIculture]</code></p></td>
   </tr>
   </tbody>
   </table>

   - **網域中央商店：** 若要從網域上任何電腦的群群組原則管理員啟用群組原則設定，請將檔案複製到網網域控制站上的下列位置：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">檔案類型</th>
   <th align="left">檔案位置</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>群組原則範本（admx）</p></td>
   <td align="left"><p><code>%systemroot%</code>&lt;強勁 &gt; sysvol\domain\policies\PolicyDefinitions</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>群組原則語言檔（adml）</p></td>
   <td align="left"><p><code>%systemroot%</code>&lt;強勁 &gt; sysvol\domain\policies\PolicyDefinitions [MUIculture]</strong><code>[MUIculture]</code></p>
   <p>例如，美國英文 ADML 語言專用檔案將會儲存在%systemroot%\sysvol\domain\policies\PolicyDefinitions\en-us。</p></td>
   </tr>
   </tbody>
   </table>

6. 使用群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）編輯群組原則設定，以設定 MDOP 技術的群組原則設定。

### MDOP 群組原則（依技術）

如需支援的 MDOP 群組原則的詳細資訊，請參閱該技術的特定檔。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">MDOP 技術</th>
<th align="left">版本束</th>
<th align="left">附註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Application Virtualization (App-V)</strong></p></td>
<td align="left"><p>App-v 5.0 和 App-v 5.0 Service Pack</p></td>
<td align="left"><p><a href="../appv-v5/how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md" data-raw-source="[How to Modify App-V 5.0 Client Configuration Using the ADMX Template and Group Policy](../appv-v5/how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md)">如何使用 ADMX 範本和群組原則來修改 App-V 5.0 用戶端組態</a></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>User Experience Virtualization (UE-V)</strong></p></td>
<td align="left"><p>UE-V 2.0 和 UE-V 2。1</p></td>
<td align="left"><p><a href="../uev-v2/configuring-ue-v-2x-with-group-policy-objects-both-uevv2.md" data-raw-source="[Configuring UE-V 2.x with Group Policy Objects](../uev-v2/configuring-ue-v-2x-with-group-policy-objects-both-uevv2.md)">使用群組原則物件設定 UE-V 2. x</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>UE-V 1.0 （包括 1.0 SP1）</p></td>
<td align="left"><p><a href="../uev-v1/configuring-ue-v-with-group-policy-objects.md" data-raw-source="[Configuring UE-V with Group Policy Objects](../uev-v1/configuring-ue-v-with-group-policy-objects.md)">使用群組原則物件來設定 UE-V</a></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Microsoft BitLocker 管理和監視 (MBAM)</strong></p></td>
<td align="left"><p>MBAM 2。5</p></td>
<td align="left"><p><a href="../mbam-v25/planning-for-mbam-25-group-policy-requirements.md" data-raw-source="[Planning for MBAM 2.5 Group Policy Requirements](../mbam-v25/planning-for-mbam-25-group-policy-requirements.md)">MBAM 2.5 群組原則需求規劃</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>MBAM 2.0 （含 2.0 SP1）</p></td>
<td align="left"><p><a href="../mbam-v2/planning-for-mbam-20-group-policy-requirements-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Group Policy Requirements](../mbam-v2/planning-for-mbam-20-group-policy-requirements-mbam-2.md)">MBAM 2.0 群組原則需求規劃</a></p>
<p><a href="../mbam-v2/deploying-mbam-20-group-policy-objects-mbam-2.md" data-raw-source="[Deploying MBAM 2.0 Group Policy Objects](../mbam-v2/deploying-mbam-20-group-policy-objects-mbam-2.md)">部署 MBAM 2.0 群組原則物件</a></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>MBAM 1。0</p></td>
<td align="left"><p><a href="../mbam-v1/how-to-edit-mbam-10-gpo-settings.md" data-raw-source="[How to Edit MBAM 1.0 GPO Settings](../mbam-v1/how-to-edit-mbam-10-gpo-settings.md)">如何編輯 MBAM 1.0 GPO 設定</a></p></td>
</tr>
</tbody>
</table>

 

 

 





