---
title: 如何保護 MBAM 網站的規劃
description: 如何保護 MBAM 網站的規劃
author: dansimp
ms.assetid: aea1d137-62cf-4da4-9989-541e0b5ad8d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 223c9397ad7933e11051c289c3dbcab63940fbc5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810905"
---
# 如何保護 MBAM 網站的規劃


本主題描述下列方法，以保護 Microsoft BitLocker 管理與監控（MBAM）2.5 的管理與監控網站與自助式入口網站：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">必要或選擇性嗎？</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>使用憑證來保護 MBAM 網站</p></td>
<td align="left"><p>選擇性，但強烈建議</p></td>
</tr>
<tr class="even">
<td align="left"><p>註冊應用程式池帳戶的服務主體名稱（SPN）</p></td>
<td align="left"><p>必要</p></td>
</tr>
</tbody>
</table>



如需如何保護 MBAM 部署的詳細資訊，請參閱[MBAM 2.5 安全考慮](mbam-25-security-considerations.md)。

## 使用憑證來保護 MBAM 網站


我們建議您使用憑證來保護下列各專案間的通訊：

-   MBAM 用戶端和 web 服務

-   瀏覽器以及管理和監控網站與自助入口網站

如需有關要求及安裝憑證的資訊，請參閱設定[網際網路伺服器憑證](https://technet.microsoft.com/library/cc731977.aspx)。

**注意**  
只有在您使用 Windows PowerShell 時，才能在不同的伺服器上設定網站和 web 服務。 如果您使用 MBAM 伺服器設定向導來設定網站，您必須在同一個伺服器上設定網站和 web 服務。



為了保護 web 服務與資料庫之間的通訊，我們也建議您在 SQL Server 中強制執行加密。 如需加強所有連線至 SQL Server 連線的相關資訊（包括 web 服務與 SQL Server 之間的通訊），請參閱[MBAM 2.5 安全性考慮](mbam-25-security-considerations.md#bkmk-secure-databases)。

## 為應用程式池帳戶註冊 Spn


若要讓 MBAM 伺服器從管理和監控網站和自助服務入口網站驗證通訊，您必須在您用於 web 應用程式池的網域帳戶下，為主機名稱註冊服務主要名稱（SPN）。

本主題包含如何針對下列類型的主機名稱註冊 Spn 的指示：

-   完全合格的功能變數名稱

-   NetBIOS 名稱

-   虛擬名稱

### 在建立初始 MBAM 安裝的 Spn 之前

開始建立 Spn 之前，請先查看下表中的資訊。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任務或專案</th>
<th align="left">詳細資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在 Active Directory 網域服務（AD DS）中建立服務帳戶。</p></td>
<td align="left"><p>服務帳戶是您在 AD DS 中建立的使用者帳戶，可提供 MBAM 網站的安全性。 MBAM 網站會在應用程式池中執行，其身分識別為服務帳戶的名稱。 然後，系統會在應用程式池帳戶中註冊 Spn。</p>
<div class="alert">
<strong>注意</strong><br/><p>您必須針對所有的 web 伺服器使用相同的應用程式池帳戶。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>確認 IIS IUSRS 群群組帳戶或應用程式池帳戶已獲授與所需的權利。</p></td>
<td align="left"><p>若要檢查這一點，請遵循下列步驟：</p>
<ol>
<li><p>開啟 [ <strong> 本機安全性原則編輯器] </strong> ，然後展開 [ <strong> 本機原則] </strong> 節點。</p></li>
<li><p>選取 [ <strong> 使用者權利指派] </strong> 節點，然後按兩下 [在 <strong> 驗證之後類比用戶端 </strong> ]，然後 <strong> </strong> 在右窗格中以批次工作群組原則設定登入。</p></li>
</ol></td>
</tr>
<tr class="odd">
<td align="left"><p>如果您使用網域系統管理帳戶來設定 MBAM 網站，MBAM 會為您建立 Spn。</p></td>
<td align="left"><p>如果您使用網域系統管理帳戶來設定 MBAM 網站，請依照本主題中的步驟，手動登錄您所使用之主機名稱類型的 Spn。</p></td>
</tr>
</tbody>
</table>



### 當您使用完整的網域主機名稱稱時，註冊 Spn

如果您在設定 MBAM 時使用完整的功能變數名稱主機名稱，就必須只註冊一個 SPN，如下列範例所示。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">您需要執行的動作</th>
<th align="left">範例及詳細資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>針對完全合格的功能變數名稱註冊 SPN。</p></td>
<td align="left"><p><code>Setspn -s http/mybitlockerrecovery.contoso.com contoso\mbamapppooluser</code></p>
<p>完整的主機名稱是 <strong> mybitlockerrecovery.contoso.com </strong> ，而用於 web 應用程式池的網域帳戶是 <strong> contoso\mbamapppooluser </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>針對您針對應用程式池帳戶所註冊的 SPN，設定受限制的委派。</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=394335" data-raw-source="[Configuring Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=394335)">設定受限制的委派</a></p>
<p>這個需求只適用于 MBAM 2.5;MBAM 2.5 SP1 中並無需這麼做。</p></td>
</tr>
</tbody>
</table>



### 當您使用 NetBIOS 主機名稱時，註冊 Spn

如果您在設定 MBAM 時使用 NetBIOS 主機名稱，請為 NetBIOS 名稱註冊一個 SPN，然後針對完整功能變數名稱登錄另一個 SPN，如下列範例所示。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">您需要執行的動作</th>
<th align="left">範例及詳細資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>針對 NetBIOS 主機名稱註冊 SPN。</p></td>
<td align="left"><p><code>Setspn -s http/nbname01 contoso\mbamapppooluser</code></p>
<p>NetBIOS 主機名稱是 <strong> nbname01 </strong> ，而用於 web 應用程式池的網域帳戶是 <strong> contoso\mbamapppooluser </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>針對完全合格的功能變數名稱註冊 SPN。</p></td>
<td align="left"><p><code>Setspn –s http/nbname01.corp.contoso.com contoso\mbamapppooluser</code></p>
<p>完整的功能變數名稱是 <strong> nbname01.contoso.com </strong> ，而用於 web 應用程式池的網域帳戶是 <strong> contoso\mbamapppooluser </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>針對您為應用程式池帳戶所註冊的 Spn，設定受限制的委派。</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=394335" data-raw-source="[Configuring Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=394335)">設定受限制的委派</a></p>
<p>這個需求只適用于 MBAM 2.5;MBAM 2.5 SP1 中並無需這麼做。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-regvirtualspn"></a>當您使用虛擬主機名稱稱時，註冊 Spn

如果您使用是完整功能變數名稱的虛擬主機名稱來設定 MBAM，請只針對虛擬主機名稱註冊一個 SPN。 如果您設定的虛擬主機名稱不是完整的功能變數名稱，您必須建立第二個 SPN 來指定完整的功能變數名稱，如下列範例所述。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">您需要執行的動作</th>
<th align="left">範例及詳細資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>如果您的虛擬主機名稱是完整的功能變數名稱，就像在這個範例中一樣，只註冊一個 SPN。</p></td>
<td align="left"><p><code>Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></p>
<p>在這個範例中，虛擬主機名稱是 <strong> mbamvirtual.contoso.com </strong> ，而用於 web 應用程式池的網域帳戶是 <strong> contoso\mbamapppooluser </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>如果您的虛擬主機名稱不是完整的功能變數名稱，請註冊這個額外的 SPN。</p></td>
<td align="left"><p><code>Setspn -s http/mbamvirtual contoso\mbamapppooluser</code></p>
<p>在這個範例中，虛擬主機名稱是 <strong> mbamvirtual </strong> ，而用於 web 應用程式池的網域帳戶是 <strong> contoso\mbamapppooluser </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>如果您的虛擬主機名稱不是完整的功能變數名稱，請註冊這個額外的 SPN。</p></td>
<td align="left"><p><code>Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></p>
<p>在這個範例中，虛擬主機名稱是 <strong> mbamvirtual.contoso.com </strong> ，而用於 web 應用程式池的網域帳戶是 <strong> contoso\mbamapppooluser </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在功能變數名稱伺服器（DNS）伺服器上，建立自訂主機名稱的 "A 記錄"，並將其指向 web 伺服器或負載平衡器。</p></td>
<td align="left"><p>請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=394337" data-raw-source="[Configure DNS Host Records](https://go.microsoft.com/fwlink/?LinkId=394337)"> 設定 Dns 主機記錄中的「設定 Dns 主機 A 記錄」一節 </a> 。</p>
<p>我們建議您使用記錄，而不是 CNAMES。 如果您使用 CNAMES 指向網域位址，您也必須在應用程式池帳戶中註冊 web 伺服器名稱的 Spn。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>針對您為應用程式池帳戶所註冊的 Spn，設定受限制的委派。</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=394335" data-raw-source="[Configuring Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=394335)">設定受限制的委派</a></p>
<p>這個需求只適用于 MBAM 2.5;MBAM 2.5 SP1 中並無需這麼做。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-registerspn"></a>從舊版 MBAM 升級時註冊 SPN

只有在您想要的情況下，才能完成本節中的步驟：

-   從舊版本的 MBAM 升級。

-   在負載平衡或分散式設定中執行 MBAM 2.5 中的網站，而且您目前正在執行的設定不是負載平衡。

如果您已在電腦帳戶上註冊 Spn，而不是在應用程式池帳戶中登錄，MBAM 會使用現有的 Spn，而且您無法在負載平衡或散佈配置中設定網站。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">您需要執行的動作</th>
<th align="left">範例及詳細資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在 Active Directory 網域服務（AD DS）中建立應用程式池帳戶。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>移除目前已安裝的網站和 web 服務。</p></td>
<td align="left"><p><a href="removing-mbam-server-features-or-software.md" data-raw-source="[Removing MBAM Server Features or Software](removing-mbam-server-features-or-software.md)">移除 MBAM 伺服器功能或軟體</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>從電腦帳戶移除 Spn。</p></td>
<td align="left"><p><code>Setspn –d http/mbamwebserver mbamwebserver</code></p>
<p><code>Setspn –d http/mbamwebserver.contoso.com mbamwebserver</code></p></td>
</tr>
<tr class="even">
<td align="left"><p>在應用程式池帳戶中註冊 Spn。</p></td>
<td align="left"><p><a href="#bkmk-regvirtualspn" data-raw-source="[Registering SPNs when you use a virtual host name](#bkmk-regvirtualspn)">當您使用虛擬主機名稱稱時，請遵循註冊 spn 的步驟 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>重新設定 web 應用程式和 web 服務。</p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)">如何設定 MBAM 2.5 Web 應用程式</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>視您用於設定的方法而定，請執行下列其中一項操作：</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>MBAM Server 設定精靈</strong></p></td>
<td align="left"><p>在 [ <strong> Web 服務應用程式池] 的 [網域帳戶] 欄位中，輸入應用程式池帳戶 </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><code>Enable-MbamWebApplication</code> Windows PowerShell Cmdlet</p></td>
<td align="left"><p>在參數中輸入帳戶 <code>WebServiceApplicationPoolCredential</code> 。</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
<td align="left"><div class="alert">
<strong>重要</strong><br/><p>您輸入的主機名稱必須與您要為其建立 Spn 的虛擬主機名稱名稱相同。 此外，在您的網路群中，主機名稱和應用程式池認證在您要設定的每個伺服器上都必須是相同的。</p>
</div>
<div>

</div>
<p>當 MBAM 設定 web 應用程式時，它會嘗試為您註冊 Spn，但只有在您要安裝 MBAM 的伺服器上有網域系統管理員許可權時，才能這麼做。 如果您沒有這些許可權，您可以完成設定，但您必須在設定 MBAM 之前或之後設定 Spn。</p></td>
</tr>
</tbody>
</table>

## 必要的要求篩選設定

 應用程式需要「允許未列出的檔案名副檔名」才能正常運作。  若要找到此功能，請流覽至 [Microsoft BitLocker 管理與監視]-> 要求篩選-> 編輯功能設定]。


## 相關主題


[MBAM 2.5 的環境準備](preparing-your-environment-for-mbam-25.md)

[MBAM 2.5 部署必要條件](mbam-25-deployment-prerequisites.md)





## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。



