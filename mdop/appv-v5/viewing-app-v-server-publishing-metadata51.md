---
title: 檢視 App-V Server 發佈中繼資料
description: 檢視 App-V Server 發佈中繼資料
author: dansimp
ms.assetid: d5fa9eb5-647c-478d-8a4d-0ecda018bce6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 97c59301678280febe23b8061c08033a88ae49c7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800292"
---
# 檢視 App-V Server 發佈中繼資料


您可以使用此程式來查看發佈中繼資料，這可協助您解決與發佈相關的問題。 您必須使用 App-v Management server 才能使用此程式。

本文包含下列資訊：

-   [用於查看發佈中繼資料的 app-v 5.1 需求](#bkmk-51-reqs-pub-meta)

-   [用來查看發佈中繼資料的語法](#bkmk-syntax-view-pub-meta)

-   [用戶端作業系統與版本的查詢值](#bkmk-values-query-pub-meta)

-   [發佈中繼資料的定義](#bkmk-whatis-pub-metadata)

## <a href="" id="bkmk-51-reqs-pub-meta"></a>用於查看發佈中繼資料的 app-v 5.1 需求


在 App-V 5.1 中，當您查詢 app-v 發佈伺服器以取得中繼資料時，您必須在位址中提供下列值：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">值</th>
<th align="left">其他詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>ClientVersion</strong></p></td>
<td align="left"><p>如果您省略 <strong> 查詢的 ClientVersion </strong> 參數，中繼資料會排除 APP-V 5.0 SP3 中新的功能。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>ClientOS</strong></p></td>
<td align="left"><p>您必須在順序套件時選取特定用戶端作業系統，才能提供這個值。 如果您選取 [預設（所有作業系統）]，請勿在查詢中指定這個值。</p>
<p>如果您在查詢中省略 <strong> ClientOS </strong> 參數，則只有已排序支援任何作業系統的套件才會出現在中繼資料中。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-syntax-view-pub-meta"></a>用於查看發佈中繼資料的查詢語法


下表提供語法和查詢範例。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">應用程式版本-V</th>
<th align="left">查詢語法</th>
<th align="left">參數描述</th>
<th align="left">範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 5.0 SP3 和 App-v 5。1</p></td>
<td align="left"><p><code>http://&lt;PubServer&gt;:&lt;Publishing Port#&gt;/?ClientVersion=&lt;AppvClientVersion&gt;&amp;ClientOS=&lt;OSStringValue&gt;</code></p></td>
<td align="left"><table>
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
<td align="left"><p>&lt;PubServer&gt;</p></td>
<td align="left"><p>App-v 發佈伺服器的名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;發佈埠#&gt;</p></td>
<td align="left"><p>移植到您在設定發佈伺服器時定義的 App-v 發佈伺服器。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ClientVersion = &lt; AppvClientVersion&gt;</p></td>
<td align="left"><p>App-v 用戶端的版本。 請參閱下表以取得正確的值以供使用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ClientOS = &lt; OSStringValue&gt;</p></td>
<td align="left"><p>執行 App-V 用戶端的電腦作業系統。 請參閱下表以取得正確的值以供使用。</p></td>
</tr>
</tbody>
</table>
<p> </p>
<p>若要從 App-v 用戶端取得發佈伺服器與埠號碼（HTTP:// &lt; PubServer &gt; ： &lt; 發佈埠 # &gt; ）的名稱，請查看 <strong> AppvPublishingServer PowerShell Cmdlet 的 URL 設定 </strong> 。</p></td>
<td align="left"><p><code><a href="http://pubsvr01:2718/?clientversion=5.0.10066.0&amp;clientos=WindowsClient_6.2_x64" data-raw-source="http://pubsvr01:2718/?clientversion=5.0.10066.0&amp;amp;clientos=WindowsClient_6.2_x64">http://pubsvr01:2718/?clientversion=5.0.10066.0&amp;clientos=WindowsClient_6.2_x64</a></code></p>
<p>在範例中：</p>
<ul>
<li><p>名為 "pubsvr01" 的 Windows Server 2012 R2 會託管發佈服務。</p></li>
<li><p>Windows 用戶端為 Windows 8.1 64 位。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 5.0 透過 App-v 5.0 SP2</p></td>
<td align="left"><p><code>http://&lt;PubServer&gt;:&lt;Publishing Port#&gt;/ </code></p>
<div class="alert">
<strong>注意</strong><br/><p><strong></strong> <strong> </strong> 只有在 app-v 5.0 SP3 和 app-v 5.1 中才支援 ClientVersion 和 ClientOS。</p>
</div>
<div>

</div></td>
<td align="left"><p>請參閱 App-v 5.0 SP3 與 App-v 5.1 的相關資訊。</p></td>
<td align="left"><p><code><a href="http://pubsvr01:2718" data-raw-source="http://pubsvr01:2718">http://pubsvr01:2718</a></code></p>
<p>在這個範例中，名為「pubsvr01」的 Windows Server 2012 R2 會託管管理和發佈服務。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-values-query-pub-meta"></a>用戶端作業系統與版本的查詢值


在發佈中繼資料查詢中，輸入與您所使用之用戶端作業系統及版本相對應的字串值。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">作業系統</th>
<th align="left">架構</th>
<th align="left">操作字串字串值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>WindowsClient_10. 0_x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>32 位元</p></td>
<td align="left"><p>WindowsClient_10. 0_x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 8.1</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>WindowsClient_6. 2_x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8.1</p></td>
<td align="left"><p>32 位元</p></td>
<td align="left"><p>WindowsClient_6. 2_x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows8</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>WindowsClient_6. 2_x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows8</p></td>
<td align="left"><p>32 位元</p></td>
<td align="left"><p>WindowsClient_6. 2_x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>WindowsServer 2012 R2</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>WindowsServer_6. 2_x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>WindowsServer 2012 R2</p></td>
<td align="left"><p>32 位元</p></td>
<td align="left"><p>WindowsServer_6. 2_x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>WindowsServer_6. 2_x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>32 位元</p></td>
<td align="left"><p>WindowsServer_6. 2_x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>WindowsClient_6. 1_x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>32 位元</p></td>
<td align="left"><p>WindowsClient_6. 1_x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>WindowsServer_6. 1_x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>32 位元</p></td>
<td align="left"><p>WindowsServer_6. 1_x86</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-whatis-pub-metadata"></a>發佈中繼資料的定義


當套件發佈至執行 App-v 用戶端的電腦時，會將中繼資料傳送至該電腦，指出要發佈哪些套件和連線組。 App-v 用戶端會針對下列兩個個別的要求進行：

-   擁有用戶端電腦資格的套件和連線群組。

-   擁有目前使用者資格的套件和連線群組。

發佈伺服器與管理伺服器進行通訊，以判斷申請者可以使用哪些套件和連線群組。 發佈伺服器必須在管理伺服器上註冊，才能產生中繼資料。

您可以使用特定使用者或電腦內容中的查詢，在網際網路瀏覽器中查看每個要求的中繼資料。






## 相關主題


[App-V 5.1 技術參考資訊](technical-reference-for-app-v-51.md)









