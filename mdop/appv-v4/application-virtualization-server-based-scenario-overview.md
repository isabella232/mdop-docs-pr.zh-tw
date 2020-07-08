---
title: 以 Application Virtualization 伺服器為基礎的案例概觀
description: 以 Application Virtualization 伺服器為基礎的案例概觀
author: dansimp
ms.assetid: 2d91392b-5085-4a5d-94f2-15eed1ed2928
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7b3ac3f10a5b7c7705e6d72c122d52be801a6d50
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809147"
---
# 以 Application Virtualization 伺服器為基礎的案例概觀


如果您打算針對您的 Microsoft 應用程式虛擬化環境使用以伺服器為基礎的部署案例，請務必瞭解*應用程式虛擬化管理伺服器*與*應用程式虛擬化資料流程伺服器*之間的差異。 本主題描述這些差異，並提供封裝傳遞方法、傳輸通訊協定和外部元件的相關資訊，在您繼續進行部署時，您將需要考慮。

## 應用程式虛擬化管理伺服器


應用程式虛擬化管理伺服器會執行發佈功能與流式處理函數。 伺服器會將應用程式圖示、快速鍵及檔案類型關聯發佈到適用于已授權使用者的 App-v 用戶端。 當使用者要求應用程式要求時，系統會使用 RTSP 或 RTSPS 通訊協定，將資料按需求傳送給授權的使用者。 在使用這個伺服器的大部分配置中，一或多個管理伺服器會共用一個常見的資料存放區，以取得設定和封裝資訊。

應用程式虛擬化管理伺服器使用 Active Directory 群組來管理使用者的授權。 除了 Active Directory 網域服務之外，這些伺服器還安裝 SQL Server 來管理資料庫和資料存放區。 管理伺服器是透過應用程式虛擬化管理主控台（由 Microsoft 管理主控台的一個快照）來控制。

由於應用程式虛擬化管理伺服器會根據需求將應用程式流式處理應用程式，因此這些伺服器非常適合擁有可靠、高頻寬局域網的系統組態。

## 應用程式虛擬化資料流程伺服器


應用程式虛擬化資料流程伺服器會提供管理伺服器所提供的相同資料流程與套件升級功能，但不含其 Active Directory 或 SQL Server 的需求。 不過，流式處理伺服器沒有發佈服務，也沒有授權或測定功能。 個別的 App-v 管理伺服器的發佈服務會與 App-v 資料流程伺服器搭配使用。 App-v 流式處理伺服器可滿足在多個位置使用應用程式虛擬化的企業需求，以及傳統伺服器設定的資料流程功能，但在每個位置中可能不會有支援 App-v 管理伺服器的基礎結構。

應用程式虛擬化資料流程伺服器也可以在具備現有電子軟體發佈系統（ESD）的環境中使用。 您使用 ESD 來管理流式處理應用程式。 與應用程式虛擬化管理伺服器不同，流式處理伺服器不使用 SQL 或管理主控台。 這些伺服器使用存取控制清單（Acl）來授與使用者的授權。

## 封裝傳送方法


如果您打算使用應用程式虛擬化伺服器作為發佈傳送方法，您必須判斷您的案例會採用下列哪一種套件傳遞方法：

-   *動態套件遞送*

-   *從檔案套件傳送中載入*

### 動態套件遞送

在動態套件遞送期間，伺服器（應用程式虛擬化管理伺服器、應用程式虛擬化資料流程伺服器或 IIS 伺服器）透過隨選部署將虛擬化的應用程式傳送給最終使用者。 只有在使用者第一次嘗試啟動應用程式時（根據需求），伺服器才會將虛擬化的應用程式和套件傳送到用戶端電腦。 伺服器只會資料流程啟動應用程式所需的區塊（主要功能區塊）。 在主要功能區區塊轉送到用戶端之後，應用程式會執行;用戶端不會收到完整的應用程式（增量式部署），除非用戶端需要存取不在主要功能區塊中的部分應用程式。 發生這種情況時，用戶端會執行順序外的要求，而次要功能區塊則會以資料流程傳送給用戶端。 動態套件傳遞可讓應用程式快速啟動。

### 從檔案套件傳送中載入

若要從檔案套件傳送載入，伺服器會在使用者啟動應用程式之前，將整個虛擬化的應用程式套件傳送到用戶端電腦。 在這種情況下，虛擬化的應用程式是以完整套件的形式傳送，而不是透過動態傳遞模型所使用的動態、增量方法來傳送。

**記事** 針對每個傳遞方法，初始的虛擬應用程式傳遞程式和虛擬應用程式更新程式都相同;已更新的虛擬應用程式套件會取代原始應用程式套件。

 

下表比較每個套件傳送方法的優點與缺點。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">優點</th>
<th align="left">缺點</th>
<th align="left">註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>動態套件遞送</p></td>
<td align="left"><p>應用程式會根據需求傳送並更新。</p>
<p>應用程式會以遞增的方式進行傳遞並更新，以優化啟動時間。</p>
<p>更新會自動傳送到用戶端桌面。</p></td>
<td align="left"><p>由於伺服器需求，企業拓朴中的需求量較大。</p>
<p>應用程式資料流程應該在局域網上;WAN 上的部署案例或在伺服器與用戶端之間使用不可靠或間歇性連接的情況，可能無法使用。</p></td>
<td align="left"><p>需要流式處理基礎結構。</p>
<p>用來將應用程式虛擬化桌面用戶端軟體部署到終端使用者電腦的 Windows 安裝程式。</p>
<p>大型企業應該使用應用程式虛擬化資料流程伺服器作為發佈點。</p></td>
</tr>
<tr class="even">
<td align="left"><p>從檔案套件傳送中載入</p></td>
<td align="left"><p>與典型的企業管理做法一致。</p>
<p>支援獨立的配置案例。</p>
<p>提供對 office 的微分支問題的解決方案。</p></td>
<td align="left"><p>應用程式傳遞與更新不可能隨選。</p>
<p>應用程式傳遞與更新不是增量式的;它會增加相對於動態傳遞的資源使用量。</p></td>
<td align="left"><p>IT 組織通常負責管理應用程式授權、使用者授權和驗證。</p></td>
</tr>
</tbody>
</table>

 

## 伺服器相關通訊協定與外部元件


下表列出可在應用程式虛擬化伺服器案例中使用的伺服器類型，以及其對應的傳輸通訊協定，以及支援特定伺服器設定所需的外部元件。 此表格也包含每個伺服器類型的報告機制及作用中升級機制。 因為這些案例都使用應用程式虛擬化管理伺服器，所以您可以使用系統內建的內部報告功能。 如果您使用應用程式虛擬化管理或應用程式虛擬化資料流程伺服器來傳送套件給用戶端，則在使用者登入用戶端時，伺服器上的套件會自動升級;如果您使用 IIS 伺服器或檔案將套件傳送到用戶端，則用戶端上的套件必須手動升級。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">伺服器類型</th>
<th align="left">通訊協定</th>
<th align="left">需要外部元件</th>
<th align="left">報告</th>
<th align="left">活動升級</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>應用程式虛擬化管理伺服器</p></td>
<td align="left"><p>RTSP</p>
<p>RTSPS</p></td>
<td align="left"><p>使用 HTTPS 時，請使用 IIS 伺服器下載 [.ICO] 和 [OSD] 檔案和防火牆，以保護伺服器不暴露在網際網路上。</p></td>
<td align="left"><p>內部</p></td>
<td align="left"><p>支援</p></td>
</tr>
<tr class="even">
<td align="left"><p>應用程式虛擬化資料流程伺服器</p></td>
<td align="left"><p>RTSP</p>
<p>RTSPS</p></td>
<td align="left"><p>使用機制來同步處理管理伺服器與流式處理伺服器之間的內容。 使用 HTTPS 時，請使用 IIS 伺服器下載 [.ICO] 和 [OSD] 檔案，並使用防火牆來保護伺服器不暴露在網際網路上。</p></td>
<td align="left"><p>內部</p></td>
<td align="left"><p>支援</p></td>
</tr>
<tr class="odd">
<td align="left"><p>IIS 伺服器</p></td>
<td align="left"><p>HTTP</p>
<p>HTTPS</p></td>
<td align="left"><p>使用機制來同步處理管理伺服器與流式處理伺服器之間的內容。 使用 HTTP 或 HTTPS 時，請使用 IIS 伺服器下載 [.ICO] 和 [OSD] 檔案和防火牆，以保護伺服器不暴露在網際網路上。</p></td>
<td align="left"><p>內部</p></td>
<td align="left"><p>不支援</p></td>
</tr>
<tr class="even">
<td align="left"><p>檔案</p></td>
<td align="left"><p>SMB</p></td>
<td align="left"><p>您需要在管理伺服器與流式處理伺服器之間同步處理內容的方式。 您需要具有檔案共用或流式處理功能的用戶端電腦。</p></td>
<td align="left"><p>內部</p></td>
<td align="left"><p>不支援</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[以電子軟體發佈為基礎的案例](electronic-software-distribution-based-scenario.md)

[如何針對以伺服器為基礎的部署設定伺服器](how-to-configure-servers-for-server-based-deployment.md)

[如何安裝伺服器和系統元件](how-to-install-the-servers-and-system-components.md)

 

 





