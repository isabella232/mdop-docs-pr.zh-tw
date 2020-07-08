---
title: App-V 5.0 伺服器部署規劃
description: App-V 5.0 伺服器部署規劃
author: dansimp
ms.assetid: fd89b324-3961-471a-ad90-c8f9ae7a8155
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 06c7c17fd081b89337bbecd31f20f6796338f697
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800348"
---
# App-V 5.0 伺服器部署規劃


Microsoft Application Virtualization （App-v） 5.0 server 基礎結構包含一組專用功能，可根據企業的需求，在一或多台伺服器電腦上安裝。

## 規劃 app-v 5.0 Server 部署


App-V 5.0 伺服器包含下列功能：

-   管理伺服器-提供 App-V 5.0 基礎結構的整體管理功能。

-   管理資料庫–可協助 App-v 5.0 管理的資料庫 predeployments。

-   發佈伺服器-提供虛擬應用程式的託管與流式處理功能。

-   報表伺服器–提供 App-v 5.0 reporting services。

-   報告資料庫–協助 App-v 5.0 報告的資料庫 predeployments。

下列清單顯示安裝 App-V 5.0 伺服器基礎結構的建議方法：

-   安裝 App-V 5.0 伺服器。 如需詳細資訊，請參閱[如何部署 app-v 5.0 伺服器](how-to-deploy-the-app-v-50-server-50sp3.md)。

-   在不同的電腦上安裝資料庫、報告和管理功能。 如需詳細資訊，請參閱[如何從管理和報表服務在不同的電腦上安裝管理和報告資料庫](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services.md)。

-   使用電子軟體發佈（ESD）。 如需詳細資訊，請參閱[如何使用電子軟體發佈部署 app-v 5.0 套件](how-to-deploy-app-v-50-packages-using-electronic-software-distribution.md)。

-   在一部電腦上安裝所有伺服器功能。

## <a href="" id="---------app-v-5-0-server-interaction"></a> App-v 5.0 Server 互動


本節包含各個 App-v 5.0 伺服器角色彼此互動的相關資訊。

App-v 5.0 管理伺服器包含套件的儲存庫及其指派的設定。 針對已在管理伺服器註冊的發佈伺服器，在執行 App-v 5.0 用戶端的電腦收到發佈重新整理要求時，就會提供與發佈伺服器搭配使用的相關中繼資料。 由單一管理伺服器所管理的 app-v 5.0 發佈伺服器可提供不同的用戶端，而且可以有不同的網站名稱和埠系結。 此外，同一個管理伺服器所管理的所有發佈伺服器都是彼此的複本。

**記事** 管理伺服器不會執行任何負載平衡。 關聯的中繼資料只會傳遞到發佈伺服器，以供處理用戶端要求時使用。

 

## 伺服器相關通訊協定與外部功能


下列顯示 App-v 5.0 伺服器所使用的伺服器相關通訊協定的相關資訊。 此表格也包含每個伺服器類型的報告機制。

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
<th align="left">需要外部功能</th>
<th align="left">報告</th>
<th align="left"></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>IIS 伺服器</p></td>
<td align="left"><p>HTTP</p>
<p>HTTPS</p></td>
<td align="left"><p>這個伺服器通訊協定組合需要一種機制來同步處理管理伺服器與流式處理伺服器之間的內容。 使用 HTTP 或 HTTPS 時，請使用 IIS 伺服器和防火牆來保護伺服器，避免暴露在網際網路上。</p></td>
<td align="left"><p>內部</p></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><p>檔案</p></td>
<td align="left"><p>SMB</p></td>
<td align="left"><p>此伺服器通訊協定組合需要支援，才能同步處理管理伺服器與流式處理伺服器之間的內容。 使用用戶端電腦進行檔案共用或流式處理功能。</p></td>
<td align="left"><p>內部</p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

 






## 相關主題


[規劃部署 App-V](planning-to-deploy-app-v.md)

[部署 App-V 5.0 伺服器](deploying-the-app-v-50-server.md)

 

 





