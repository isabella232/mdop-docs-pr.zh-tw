---
title: App-V 5.0 容量規劃
description: App-V 5.0 容量規劃
author: dansimp
ms.assetid: 56f48b00-cd91-4280-9481-5372a0e2e792
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9e828457a286f6f686c227a935828679514d87ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800697"
---
# App-V 5.0 容量規劃


下列建議可以用來做為比較基準，以協助判斷適合您組織的 app-v 5.0 基礎結構的容量規劃資訊。

**重要** 此區段中的資訊只能做為規劃 App-v 5.0 部署的一般指南。 您的系統容量需求將取決於您的硬體和應用程式環境的特定詳細資料。 此外，此檔中顯示的績效數位是範例，而您的結果可能會有所不同。

 

## 判斷專案範圍


設計 App-v 5.0 基礎結構之前，您必須判斷專案的範圍。 範圍包括判斷哪些應用程式將會真正可用，以及識別目標使用者及其位置。 這項資訊將協助您判斷應該要實施哪種類型的 App-v 5.0 基礎結構。 專案範圍的相關決策必須以貴組織的特定需求為基礎。

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
<td align="left"><p>決定應用程式範圍</p></td>
<td align="left"><p>根據要虛擬化的應用程式而定，App-v 5.0 基礎結構可以以不同的方式加以設定。 第一個工作是定義您想要虛擬化的應用程式。</p></td>
</tr>
<tr class="even">
<td align="left"><p>判斷位置範圍</p></td>
<td align="left"><p>[位置範圍] 是指您計畫執行虛擬化應用程式的物理位置（例如，企業範圍或特定地理位置）。 它也可以參照使用者群體（例如，單一部門），他們將會執行虛擬應用程式。 您應該會取得包含連接路徑以及使用虛擬化應用程式及 WAN 連結速度的使用者數目的網狀圖。</p></td>
</tr>
</tbody>
</table>

 

## 判斷需要 App-v 5.0 基礎結構


**重要** 下列兩種模型都需要在您計畫執行虛擬應用程式的電腦上安裝 App-v 5.0 用戶端。

您也可以使用電子軟體發佈（ESD）方案（例如 Microsoft 系統中心設定管理員），管理您的 App-v 5.0 環境。 如需詳細資訊，請參閱[使用電子軟體發佈（ESD）部署 app-v 5.0 套件](deploying-app-v-50-packages-by-using-electronic-software-distribution--esd-.md)。

 

-   **獨立模型**-獨立模型可讓虛擬應用程式在 Windows 安裝程式啟用，以便在沒有資料流程的情況下發布。 在獨立模式中，app-v 5.0 是由排序器和用戶端所組成;不需要額外的元件。 應用程式準備好使用稱為 [排序] 的程式來進行虛擬化。 如需詳細資訊，請參閱[應用程式-V 5.0 排序器與用戶端部署的規劃](planning-for-the-app-v-50-sequencer-and-client-deployment.md)。 針對下列案例，建議使用獨立模型：

    -   無法連線到 app-v 5.0 基礎結構的中斷遠端使用者使用。

    -   當您執行的是軟體管理系統（例如 Configuration Manager 2012）時。

    -   當網路頻寬限制抑制電子軟體發佈時。

-   **完整的基礎結構模型**-完整的基礎結構模型可提供軟體發佈、管理和報告功能;它也包含跨網路的應用程式資料流程。 App-v 5.0 完整基礎結構模型是由一或多個 App-v 5.0 管理伺服器所組成。 管理伺服器可以用來將應用程式發佈到所有用戶端。 發佈程式會將虛擬應用程式圖示和快速鍵放在目的電腦上。 它也可以將應用程式流式資料流程給本機使用者。 如需安裝管理伺服器的詳細資訊，請參閱[規劃 app-v 5.0 Server 部署](planning-for-the-app-v-50-server-deployment.md)。 針對下列案例，建議使用完整的基礎結構模型：

    **重要** App-v 5.0 完整基礎結構模型需要 Microsoft SQL Server 來儲存配置資料。 如需詳細資訊，請參閱[app-v 5.0 支援的](app-v-50-supported-configurations.md)設定。

     

    -   當您想要使用管理伺服器將應用程式發佈至目的電腦時。

    -   可快速提供目的電腦的應用程式。

    -   當您想要使用 App-v 5.0 報表時。

## 端對端伺服器規模調整指南


下列章節提供有關端對端 App-V 5.0 大小及規劃的資訊。 如需詳細資訊，請參閱後續章節。

**記事** 用戶端上的往返行程回應時間是執行 App-V 5.0 用戶端以接收發布伺服器成功通知的時間。 發佈伺服器上的往返行程回應時間是電腦執行發佈伺服器時所花費的時間，可從管理伺服器接收成功的套件中繼資料更新。

 

-   20000用戶端可以以單一發布伺服器為目標，以在可接受的往返行程時間內取得套件更新。 （ &lt; 3 秒）

-   單一管理伺服器最多可支援50發佈伺服器，以便在可接受的往返行程期間更新套件中繼資料。 （ &lt; 5 秒）

## <a href="" id="---------app-v-5-0-management-server-capacity-planning-recommendations"></a> App-V 5.0 管理伺服器容量規劃建議


App-v 5.0 發佈伺服器需要管理伺服器來更新套件重新整理要求和套件重新整理回應。 然後，管理伺服器會將資訊傳送給管理資料庫以取得資訊。 如需 App-V 5.0 管理伺服器支援的設定的詳細資訊，請參閱[app-v 5.0 支援](app-v-50-supported-configurations.md)的設定。

**記事** App-v 5.0 發佈伺服器上的預設重新整理時間為10分鐘。

 

當多個同時發佈伺服器與單一管理伺服器連線以進行套件中繼資料更新時，下列三個因素會影響發佈伺服器上的往返行程回應時間：

1.  同時要求進行的發佈伺服器數量。

2.  管理伺服器上設定的連線群組數目。

3.  管理伺服器上設定的存取組數目。

下表顯示影響往返行程時間之每個因素的詳細資訊。

**記事** 往返行程回應時間是電腦執行 App-v 5.0 發佈伺服器以從管理伺服器接收成功的套件中繼資料更新所花費的時間。

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">影響往返行程回應時間的因素</th>
<th align="left">其他資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>同時要求封裝中繼資料重新整理的發佈伺服器數目。</p></td>
<td align="left"><p></p>
<ul>
<li><p>單一管理伺服器可以同時回應多達320發佈的發佈伺服器（要求同時發佈中繼資料）。</p></li>
<li><p>320 pub 伺服器的往返行程回應時間是大約40秒。</p></li>
<li><p>針對 &lt; 50 同時要求中繼資料的發佈伺服器，往返行程回應時間為 &lt; 5 秒。</p></li>
<li><p>從50到320發佈伺服器，回應時間會線性增加（約2x）。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>管理伺服器上設定的連線群組數目。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>最多100個連線群組，發佈伺服器的往返行程回應時間不會有顯著的變更。</p></li>
<li><p>針對 100-400 連線群組，往返行程回應時間有輕微的線性增加。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>管理伺服器上設定的存取組數目。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>在最多40存取群組中，發佈伺服器的往返行程回應時間有一個線性（大約3倍）的增加。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

下表顯示上述每個因素的範例值。 在每個變化中，120套件都會從 App-v 5.0 管理伺服器進行重新整理。

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">案例</th>
<th align="left">變化</th>
<th align="left">連線群組數目</th>
<th align="left">存取群組的數目</th>
<th align="left">發佈伺服器數</th>
<th align="left">網路連線類型發佈伺服器/管理伺服器</th>
<th align="left">發佈伺服器上的往返行程回應時間（以秒為單位）</th>
<th align="left">管理伺服器上的 CPU 利用率</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>同時發佈伺服器與管理伺服器一起發佈中繼資料。</p></td>
<td align="left"><p>發佈伺服器數</p></td>
<td align="left"><p></p>
<ul>
<li><p>0</p></li>
<li><p>0</p></li>
<li><p>0</p></li>
<li><p>0</p></li>
<li><p>0</p></li>
<li><p>0</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>sr-1</p></li>
<li><p>sr-1</p></li>
<li><p>sr-1</p></li>
<li><p>sr-1</p></li>
<li><p>sr-1</p></li>
<li><p>sr-1</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>50</p></li>
<li><p>100</p></li>
<li><p>200</p></li>
<li><p>300</p></li>
<li><p>315</p></li>
<li><p>320</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>500</p></li>
<li><p>第</p></li>
<li><p>合</p></li>
<li><p>32</p></li>
<li><p>為期</p></li>
<li><p>37</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>11x17</p></li>
<li><p>11x17</p></li>
<li><p>11x17</p></li>
<li><p>工資</p></li>
<li><p>11x17</p></li>
<li><p>工資</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>發佈中繼資料包含連接群組</p></td>
<td align="left"><p>連線群組數目</p></td>
<td align="left"><p></p>
<ul>
<li><p>第</p></li>
<li><p>50</p></li>
<li><p>100</p></li>
<li><p>150</p></li>
<li><p>300</p></li>
<li><p>400</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>sr-1</p></li>
<li><p>sr-1</p></li>
<li><p>sr-1</p></li>
<li><p>sr-1</p></li>
<li><p>sr-1</p></li>
<li><p>sr-1</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>100</p></li>
<li><p>100</p></li>
<li><p>100</p></li>
<li><p>100</p></li>
<li><p>100</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>第</p></li>
<li><p>11</p></li>
<li><p>11</p></li>
<li><p>位</p></li>
<li><p>22</p></li>
<li><p>位</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>11x17</p></li>
<li><p>合</p></li>
<li><p>22</p></li>
<li><p>合</p></li>
<li><p>20</p></li>
<li><p>20</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>發佈中繼資料包含存取群組</p></td>
<td align="left"><p>存取群組的數目</p></td>
<td align="left"><p></p>
<ul>
<li><p>0</p></li>
<li><p>0</p></li>
<li><p>0</p></li>
<li><p>0</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>sr-1</p></li>
<li><p>第</p></li>
<li><p>20</p></li>
<li><p>40</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>100</p></li>
<li><p>100</p></li>
<li><p>100</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>第</p></li>
<li><p>43</p></li>
<li><p>153</p></li>
<li><p>535</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>11x17</p></li>
<li><p>26</p></li>
<li><p>24</p></li>
<li><p>24</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

執行管理伺服器之電腦的 CPU 利用率會接近25%，而不考慮以目標為目標的發佈伺服器數量而定。 Microsoft SQL Server 資料庫事務/秒、批次要求/秒和使用者連線，與發佈伺服器數量無關。 例如：交易/秒是 ~ 30，批次要求 ~ 200，而使用者則會連接 ~ 6。

使用地理位置分散的部署（管理伺服器 & 發佈伺服器）使用低速連結網路時，發佈伺服器的往返行程回應時間是在可接受的時間限制內（ &lt; 5 秒），即使是在單一管理伺服器上同時進行100的要求也是如此。

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">案例</th>
<th align="left">變化</th>
<th align="left">連線群組數目</th>
<th align="left">存取群組的數目</th>
<th align="left">發佈伺服器數</th>
<th align="left">網路連線類型發佈伺服器/管理伺服器</th>
<th align="left">發佈伺服器上的往返行程回應時間（以秒為單位）</th>
<th align="left">管理伺服器上的 CPU 利用率</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>發佈伺服器與管理伺服器之間的網路連線</p></td>
<td align="left"><p>1.5 Mbps 低速連結網路</p></td>
<td align="left"><p></p>
<ul>
<li><p>0</p></li>
<li><p>0</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>sr-1</p></li>
<li><p>sr-1</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>50</p></li>
<li><p>100</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>1.5 mbps 纜線 DSL</p></li>
<li><p>1.5 mbps 纜線 DSL</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>4</p></li>
<li><p>500</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>sr-1</p></li>
<li><p>pplx-2</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>發佈伺服器與管理伺服器之間的網路連線</p></td>
<td align="left"><p>局域網/WIFI 網路</p></td>
<td align="left"><p></p>
<ul>
<li><p>0</p></li>
<li><p>0</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>sr-1</p></li>
<li><p>sr-1</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>200</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>Wifi</p></li>
<li><p>Wifi</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>11</p></li>
<li><p>20</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>工資</p></li>
<li><p>11x17</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

無論管理伺服器和發佈伺服器是以低速連結網路或高速網路連線，管理伺服器都可以在30分鐘內處理大約15000套件重新整理要求。

## <a href="" id="---------app-v-5-0-reporting-server-capacity-planning-recommendations"></a> App-V 5.0 報表伺服器容量規劃建議


App-v 5.0 用戶端會將報告資料傳送到報表伺服器。 然後，報表伺服器會在 Microsoft SQL Server 資料庫中記錄資訊，並將成功的通知傳回執行 App-v 5.0 用戶端的電腦上。 如需 App-V 5.0 報表服務器支援之設定的詳細資訊，請參閱[app-v 5.0 支援](app-v-50-supported-configurations.md)的設定。

**記事** 往返行程回應時間是執行 App-v 5.0 用戶端的電腦用來傳送報告資訊至報表伺服器並接收來自報表伺服器的成功通知的時間。

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">案例</th>
<th align="left">摘要</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>多個 App-V 5.0 用戶端會同時將報告資訊傳送到報表伺服器。</p></td>
<td align="left"><p></p>
<ul>
<li><p>來自報表服務器的往返行程回應時間是500用戶端的2.6 秒。</p></li>
<li><p>來自報表服務器的往返行程回應時間是1000用戶端的5.65 秒。</p></li>
<li><p>隨著用戶端數量而定，往返行程回應時間會線性增加。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>報表服務器每秒處理的要求。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>單一報表伺服器與單一資料庫，最多可處理每秒139個要求。 平均值為121個要求/秒。</p></li>
<li><p>使用兩個報表伺服器來報告相同的 Microsoft SQL Server 資料庫，平均要求/秒數與單一報表服務器 = ~ 127，最多可有278個要求/秒。</p></li>
<li><p>單一報表服務器可以處理500併發/活動連線。</p></li>
<li><p>單一報表服務器可以處理最大1500併發連接。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>報告資料庫。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>執行 Microsoft SQL Server 的電腦上的鎖爭用是要求/秒的限制因素。</p></li>
<li><p>輸送量與回應時間是獨立于資料庫大小的。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**計算隨機延遲**：

隨機延遲指定將資料傳送到報表伺服器的最大延遲（以分鐘為單位）。 當排程的任務開始時，用戶端會在**0**與**ReportingRandomDelay**之間產生隨機延遲，並在傳送資料之前等待指定的持續時間。

隨機延遲 = 4 \ * 用戶端數目/每秒平均請求數。

範例：針對500用戶端（每秒含120個要求），隨機延遲是，4 \ * 500/120 = ~ 17 分鐘。

## <a href="" id="---------app-v-5-0-publishing-server-capacity-planning-recommendations"></a> App-V 5.0 發佈伺服器容量規劃建議


執行 App-V 5.0 用戶端的電腦會連線至 App-v 5.0 發佈伺服器，以傳送發佈重新整理要求並接收回應。 在執行 App-v 5.0 用戶端的電腦上測量往返行程回應時間。 處理器時間是在發佈伺服器上測量。 如需 App-V 5.0 發佈伺服器支援之設定的詳細資訊，請參閱[app-v 5.0 支援](app-v-50-supported-configurations.md)的設定。

**重要** 下列清單顯示設定 App-v 5.0 發佈伺服器時要考慮的主要因素：

-   同時連接到單一發布伺服器的用戶端數量。

-   每次重新整理中的套件數目。

-   用戶端與 app-v 5.0 發佈伺服器之間的環境中的可用網路頻寬。

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">案例</th>
<th align="left">摘要</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>多個 App-V 5.0 用戶端同時連線到單一發布伺服器。</p></td>
<td align="left"><p></p>
<ul>
<li><p>執行雙核心處理器的發佈伺服器最多可以在要求同時進行重新整理的5000用戶端上回應。</p></li>
<li><p>針對5000-10000 用戶端，發佈伺服器需要最低的四核核心。</p></li>
<li><p>針對10000-20000 用戶端，發佈伺服器應該有雙四核，以獲得更有效率的回應時間。</p></li>
<li><p>含四核的發佈伺服器在3秒內可以重新整理至10000套件。 （支援10000併發用戶端）</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>每次重新整理中的套件數目。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>數量增加的套件會增加大約40% （最多1000個套件）的回應時間。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>App-V 5.0 用戶端與發佈伺服器之間的網路。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>在慢速網路（1.5 Mbps 頻寬）中，回應時間會隨著局域網（最高達1000使用者）而增加97%。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**記事** 發佈伺服器的 CPU 使用量在必須處理同時要求的時間間隔期間（ &gt; 在大多數情況下，會有90%）。 發佈伺服器可以在1秒內處理 ~ 1500 用戶端要求。

 

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">案例</th>
<th align="left">變化</th>
<th align="left">App-v 5.0 用戶端的數目</th>
<th align="left">套件數目</th>
<th align="left">發佈伺服器上的處理器配置</th>
<th align="left">網路連線類型發佈 server/App-v 5.0 用戶端</th>
<th align="left">App-v 5.0 用戶端上的往返時間（以秒為單位）</th>
<th align="left">發佈伺服器上的 CPU 利用率（以%）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-V 5.0 用戶端傳送發佈更新要求 &amp; 接收回應，每個包含120套件的要求</p></td>
<td align="left"><p>用戶端數目</p></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>1000</p></li>
<li><p>5000</p></li>
<li><p>10000</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>120</p></li>
<li><p>120</p></li>
<li><p>120</p></li>
<li><p>120</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>雙核</p></li>
<li><p>雙核</p></li>
<li><p>四核</p></li>
<li><p>四核</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>sr-1</p></li>
<li><p>pplx-2</p></li>
<li><p>pplx-2</p></li>
<li><p>3</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>99</p></li>
<li><p>89</p></li>
<li><p>77</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>每次重新整理中有多個套件</p></td>
<td align="left"><p>套件數目</p></td>
<td align="left"><p></p>
<ul>
<li><p>1000</p></li>
<li><p>1000</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>500</p></li>
<li><p>1000</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>四核</p></li>
<li><p>四核</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>pplx-2</p></li>
<li><p>3</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>92</p></li>
<li><p>91</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>用戶端與發佈伺服器之間的網路</p></td>
<td align="left"><p>1.5 Mbps 低速連結網路</p></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>500</p></li>
<li><p>1000</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>120</p></li>
<li><p>120</p></li>
<li><p>120</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>四核</p></li>
<li><p>四核</p></li>
<li><p>四核</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>1.5 Mbps 的大陸內部網路</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>3</p></li>
<li><p>10（含0.2% 失敗率）</p></li>
<li><p>17（1% 失敗率）</p></li>
</ul></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="---------app-v-5-0-streaming-capacity-planning-recommendations"></a> App-v 5.0 流式處理容量規劃建議


執行 App-V 5.0 用戶端的電腦會從流式處理伺服器對流執行虛擬應用程式套件。 往返行程回應時間是在執行 App-v 5.0 用戶端的電腦上測量，且是處理整個套件所需的時間。

**重要** 下列清單說明設定 App-v 5.0 流式處理伺服器時要考慮的主要因素：

-   從單一流式處理伺服器同時流式處理應用程式套件的用戶端數量。

-   要流入的套件大小。

-   用戶端與流式處理伺服器之間的環境中的可用網路頻寬。

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">案例</th>
<th align="left">摘要</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>多個 App-v 5.0 用戶端會同時從單一資料流程伺服器資料流程應用程式。</p></td>
<td align="left"><p></p>
<ul>
<li><p>如果同時從同一個伺服器同時流式處理的用戶端數量增加，就會有與套件下載/資料流程時間相對應的線性關聯。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>要流入的套件大小。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>套件大小對於大小約為1GB 的大型套件，只會對資料流程/下載時間產生很大的影響。 對於從 3 MB 到 100 MB 的封裝大小，資料流程時間的範圍是從20秒到100秒，以及100併發的用戶端。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>App-V 5.0 用戶端與流式處理伺服器之間的網路。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>在慢速網路（1.5 Mbps 頻寬）中，回應時間會隨著局域網（最高達100使用者）而增加70-80%。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

下表顯示前面清單中每個因素的範例值：

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">案例</th>
<th align="left">變化</th>
<th align="left">App-v 5.0 用戶端的數目</th>
<th align="left">每個套件的大小</th>
<th align="left">網路連線類型流式處理伺服器/App-v 5.0 用戶端</th>
<th align="left">App-v 5.0 用戶端上的往返時間（以秒為單位）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>多個 App-V 5.0 用戶端從流式處理伺服器流式處理虛擬應用程式套件。</p></td>
<td align="left"><p>用戶端數量。</p></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>200</p></li>
<li><p>1000</p></li>
<li><p></p></li>
<li><p>100</p></li>
<li><p>200</p></li>
<li><p>1000</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>3.5 MB</p></li>
<li><p>3.5 MB</p></li>
<li><p>3.5 MB</p></li>
<li><p></p></li>
<li><p>5 MB</p></li>
<li><p>5 MB</p></li>
<li><p>5 MB</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p></p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>5</p></li>
<li><p>39</p></li>
<li><p>391</p></li>
<li><p></p></li>
<li><p>35</p></li>
<li><p>68</p></li>
<li><p>461</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>正在進行資料流程處理的每個套件大小。</p></td>
<td align="left"><p>每個套件的大小。</p></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>200</p></li>
<li><p></p></li>
<li><p>100</p></li>
<li><p>200</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>21 MB</p></li>
<li><p>21 MB</p></li>
<li><p></p></li>
<li><p>109</p></li>
<li><p>109</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p></p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
</ul></td>
<td align="left"><p></p>
<p>33</p>
<p>83</p>
<p></p>
<p>100</p>
<p>160</p></td>
</tr>
<tr class="odd">
<td align="left"><p>用戶端與 App-v 5.0 流式處理伺服器之間的網路連線。</p></td>
<td align="left"><p>1.5 Mbps 低速連結網路。</p></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p></p></li>
<li><p>100</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>3.5 MB</p></li>
<li><p></p></li>
<li><p>5 MB</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>1.5 Mbps 的大陸內部網路</p></li>
</ul></td>
<td align="left"><p></p>
<p>102</p>
<p></p>
<p>121</p></td>
</tr>
</tbody>
</table>

 

每個應用程式 V 5.0 流式處理伺服器都應該能夠處理同時流式處理的虛擬化應用程式最少的200個用戶端。

**記事** 資料流程的實際時間是由同時流式處理的用戶端數、套件數目、套件大小、伺服器的網路活動和網路狀況決定。

 

例如，當100同步處理的用戶端從伺服器傳送時，一般的使用者可以將 100 MB 套件資料流程傳輸在2分鐘以內。 不過，大小為 1 GB 的套件可能需要長達30分鐘的時間。 在大部分實際環境中，資料流程需求不會均勻分佈，您必須瞭解環境中所提供的大約峰值流量需求，才能正確地調整所需的流式處理伺服器數目。

如果您已預先快取您的應用程式，可能會大幅增加流式處理伺服器支援的用戶端數目，並減少峰值流量需求。 您也可以使用點播流式傳遞和資料流程優化套件，增加流式處理伺服器可支援的用戶端數量。

## 結合 app-v 5.0 伺服器角色


折扣調整比例與容錯需求，與 Active Directory 連通的位置所需的伺服器數量最少為1。 此伺服器將託管管理伺服器、管理伺服器服務及 Microsoft SQL Server 角色。 因此，伺服器角色可以依任何所需的組合來排列，因為它們不會相互衝突。

忽略縮放需求，提供容錯實現所需的伺服器數量最少為4個。 管理伺服器以及 Microsoft SQL Server 角色支援將其放在容錯設定中。 管理伺服器服務可以與任何角色結合，但仍會保持單一失敗點。

雖然有許多容錯策略和技術可供使用，但並非所有都適用于特定的服務。 此外，如果結合 app-v 5.0 角色，則某些容錯選項可能會因為不相容而不再適用。






## 相關主題


[App-V 5.0 支援的組態](app-v-50-supported-configurations.md)

[App-V 5.0 高可用性規劃](planning-for-high-availability-with-app-v-50.md)

[規劃部署 App-V](planning-to-deploy-app-v.md)

 

 





