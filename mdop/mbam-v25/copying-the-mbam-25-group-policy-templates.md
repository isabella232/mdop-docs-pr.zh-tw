---
title: 複製 MBAM 2.5 群組原則範本
description: 複製 MBAM 2.5 群組原則範本
author: dansimp
ms.assetid: e526ecec-07ff-435e-bc90-3084b617b84b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/28/2017
ms.openlocfilehash: a3436552256b1632a11037dc94751207cde89d5c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811025"
---
# 複製 MBAM 2.5 群組原則範本


在部署 MBAM 用戶端安裝之前，您必須下載 MBAM 群組原則範本，其中包含定義 BitLocker 磁片磁碟機加密之 MBAM 實現設定的群組原則設定。 下載範本之後，您可以將群組原則設定設定為在整個企業中實現。

## 下載並部署 MDOP 群組原則範本


您可以在自解壓縮、壓縮檔案中下載 MDOP 群組原則範本，並依技術和版本分組。

**如何下載及部署 MDOP 群組原則範本**

1. 從[Microsoft Desktop 最優化 Pack 群群組原則管理範本](https://www.microsoft.com/download/details.aspx?id=55531)下載 MDOP 群組原則範本。

2. 執行已下載的檔案，以解壓範本資料夾。

   **警告**  
   請勿將範本直接解壓縮至 [群組原則] 部署目錄。 在此檔案中捆綁了多種技術與版本。



3. 在解壓縮的資料夾中，找出技術版本的 admx 檔案。 某些 MDOP 技術有多組群組原則物件（Gpo）。 例如，MBAM 包括 MBAM 管理設定和 MBAM 使用者設定。

4. 依語言區域性（也就是*en* -美國）來找出適當的 adml 檔案。

5. 將 admx 與 adml 檔案複製到原則定義資料夾中。 根據您儲存範本的位置，您可以從本機裝置或網域上的任何電腦來設定群組原則設定。

   **本機檔案。** 若要從本機裝置設定群組原則設定，請將範本檔案複製到下列位置：

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



~~~
**Domain central store.** To enable Group Policy settings configuration by a Group Policy administrator from any computer on the domain, copy files to the following locations on the domain controller:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">File type</th>
<th align="left">File location</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Group Policy template (.admx)</p></td>
<td align="left"><p><code>%systemroot%</code>\<strong>sysvol\domain\policies\PolicyDefinitions</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Group Policy language file (.adml)</p></td>
<td align="left"><p><code>%systemroot%</code>\<strong>sysvol\domain\policies\PolicyDefinitions\[MUIculture]</strong><code>\[MUIculture]</code></p>
<p>For example, the U.S. English ADML language-specific file will be stored in %systemroot%\sysvol\domain\policies\PolicyDefinitions\en-us.</p></td>
</tr>
</tbody>
</table>
~~~



6. 使用群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）編輯群組原則設定，以設定 MDOP 技術的群組原則設定。 如需詳細資訊，請參閱[編輯 MBAM 2.5 群組原則設定](editing-the-mbam-25-group-policy-settings.md)。

   如需群組原則設定的說明，請參閱[規劃 MBAM 2.5 群組原則需求](planning-for-mbam-25-group-policy-requirements.md)。


## 相關主題


[部署 MBAM 2.5 群組原則物件](deploying-mbam-25-group-policy-objects.md)


## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。






