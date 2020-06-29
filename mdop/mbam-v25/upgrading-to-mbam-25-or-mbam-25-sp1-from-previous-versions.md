---
title: 從舊版升級至 MBAM 2.5 或 MBAM 2.5 SP1
description: 從舊版升級至 MBAM 2.5 或 MBAM 2.5 SP1
author: dansimp
ms.assetid: a9edb4b8-5d5e-42ab-8db6-619db2878e50
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 07a03ebbbfce45f7f69a85000e18ddf1a58e53ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800172"
---
# 從舊版升級至 MBAM 2.5 或 MBAM 2.5 SP1


本主題描述升級 Microsoft BitLocker 管理和監控（MBAM）伺服器以及舊版 MBAM 的 MBAM 用戶端的程式。

**記事** 您可以從任何舊版的 MBAM 直接升級至 MBAM 2.5 或 MBAM 2.5 SP1。

 

## 開始升級前


在您開始升級前，請先查看下列資訊。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">開始前的須知</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>如果您要在一台伺服器上安裝 MBAM 網站，並在另一部伺服器上執行 web 服務，您必須使用 Windows PowerShell Cmdlet 來進行設定。</p></td>
<td align="left"><p>MBAM Server 設定向導不支援在另一台伺服器上設定網站，也不支援在其他伺服器上設定 web 服務。</p></td>
</tr>
<tr class="even">
<td align="left"><p>如果您要升級至 MBAM 2.5 或 2.5 SP1 （從 Windows Server2008 R2 中的 MBAM 2.0 或 2.0 SP1）：</p>
<p>如果您在已安裝 Internet Information Services （IIS）之後安裝所需的 .NET Framework 4.5 軟體，管理和監控網站和自助服務入口網站將無法運作。</p>
<p>發生此問題的原因是，如果在安裝 IIS 之後安裝 .NET Framework，則無法正確註冊 ASP.NET。</p></td>
<td align="left"><p><strong>若要解決此問題：</strong></p>
<p><strong>從下列位置執行 aspnet_regiis – i </strong> ：</p>
<p>C:\windows\microsoft.net\Framework\v4.0.30319</p>
<p>如需詳細資訊，請參閱： <a href="https://go.microsoft.com/fwlink/?LinkId=393272" data-raw-source="[ASP.NET IIS Registration Tool](https://go.microsoft.com/fwlink/?LinkId=393272)"> ASP.NET IIS 註冊工具 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>如果符合下列所有條件，請在應用程式池帳戶上註冊 SPN：</p>
<ul>
<li><p>您要從舊版的 MBAM 升級。</p></li>
<li><p>目前您不是在負載平衡或分散式設定中執行 MBAM 網站，但是當您升級至 MBAM 2.5 或 2.5 SP1 時，您會想要這麼做。</p></li>
</ul></td>
<td align="left"><p>如需相關指示，請參閱 <a href="planning-how-to-secure-the-mbam-websites.md#bkmk-registerspn" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md#bkmk-registerspn)"> 規劃如何保護 MBAM 網站的安全 </a> 。</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>我們建議的專案</strong></p></td>
<td align="left"><p>登錄應用程式池帳戶的服務主體名稱（SPN），即使您可能已經為電腦帳戶註冊了 Spn 也一樣。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>我們建議的原因</strong></p></td>
<td align="left"><p>您必須在應用程式池帳戶上註冊 SPN，才能在負載平衡或散佈配置中設定網站。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>如果已在電腦帳戶上設定 Spn，會發生什麼情況？</strong></p></td>
<td align="left"><p>MBAM 會使用您已註冊的 Spn，而且您不需要設定其他 Spn，但您無法在負載平衡或散佈配置中設定網站。</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 

## 升級 MBAM Server 基礎結構的步驟


使用下列各節中的步驟來升級獨立拓撲或 System Center Configuration Manager 整合拓撲的 MBAM。

**若要升級獨立拓朴的 MBAM 伺服器基礎結構**

1.  從 [**程式和功能**] 和 [web 伺服器] 卸載舊版 MBAM，以確保資訊不會從 MBAM 用戶端寫入 MBAM 基礎結構。 如需相關指示，請參閱[移除 MBAM Server 功能或軟體](removing-mbam-server-features-or-software.md#bkmk-removeserverfeatures)。

2.  備份您的資料庫。

3.  使用**程式和功能**從 sql Server 卸載舊版的 MBAM，包括透過 Sql Server Reporting SERVICES 託管 MBAM 報告的 sql server。 從資料庫伺服器和 reporting services 移除任何剩餘的 MBAM 伺服器臨時檔案或資料夾。

    **記事** 資料庫將不會移除，而且所有合規性和復原資料都會保留在資料庫中。

     

4.  依照該順序安裝及設定 MBAM 2.5 或 2.5 SP1 資料庫、報表及 web 應用程式。 資料庫已就地升級。

5.  使用 MBAM 2.5 範本更新群組原則物件（Gpo），以利用 MBAM 中的新功能，例如強制加密。 如果您沒有更新 Gpo，且 MBAM 用戶端無法 MBAM 2.5，舊版的 MBAM 用戶端將會繼續針對您目前的 Gpo 提供精簡功能的報告。 瞭解[如何取得您的 MDOP 群組原則（admx）範本](https://www.microsoft.com/download/details.aspx?id=41183)，以下載最新的 admx 範本。

    在您升級 MBAM 伺服器基礎結構之後，現有的用戶端電腦會繼續成功地向 MBAM 2.5 或 2.5 SP1 伺服器進行報告，並繼續儲存恢復資料。

6.  安裝最新的 MBAM 2.5 或 2.5 SP1 用戶端。 部署之後，用戶端電腦不需要重新開機。

**若要升級 System Center Configuration Manager 整合拓朴的 MBAM 基礎結構**

1.  從 [**程式和功能**] 和 [web 伺服器] 卸載舊版 MBAM，以確保資訊不會從 MBAM 用戶端寫入 MBAM 基礎結構。 如需相關指示，請參閱[移除 MBAM Server 功能或軟體](removing-mbam-server-features-or-software.md#bkmk-removeserverfeatures)。

2.  備份您的資料庫。

3.  使用**程式和功能**從 sql Server 卸載舊版的 MBAM，包括透過 Sql Server Reporting SERVICES 託管 MBAM 報告的 sql server。 從資料庫伺服器和 reporting services 移除任何剩餘的 MBAM 伺服器臨時檔案或資料夾。

4.  從 Configuration Manager 伺服器卸載 MBAM。

    **記事** 資料庫與 Configuration Manager 物件（比較基準、MBAM 支援的電腦集合及報告）不會被移除，而且所有合規性和復原資料都會保留在資料庫中。

     

5.  更新 mof 檔案。

6.  安裝並設定 MBAM 2.5 或 2.5 SP1 資料庫、報表、web 應用程式及 Configuration Manager 整合（依順序）。 資料庫與 Configuration Manager 物件已就地升級。

7.  或者，您也可以更新群組原則物件（Gpo），如果您想要在 MBAM 中執行新功能（例如強制加密），請編輯設定。 如果您沒有更新 Gpo，MBAM 將會繼續針對您目前的 Gpo 進行報告。 瞭解[如何取得您的 MDOP 群組原則（admx）範本](https://docs.microsoft.com/microsoft-desktop-optimization-pack/solutions/how-to-download-and-deploy-mdop-group-policy--admx--templates)，以下載最新的 admx 範本。

    在您升級 MBAM 伺服器基礎結構之後，現有的用戶端電腦會繼續成功地向 MBAM 2.5 或 2.5 SP1 伺服器進行報告，並繼續儲存恢復資料。

8.  安裝最新的 MBAM 2.5 或 2.5 SP1 用戶端。 部署之後，用戶端電腦不需要重新開機。

## MBAM 用戶端的升級支援


MBAM 支援從任何舊版的 MBAM 用戶端升級至 MBAM 2.5 用戶端。

**安裝 MBAM 用戶端的方法：**

-   在安裝 MBAM 2.5 伺服器基礎結構之後，立即或逐步升級執行 MBAM 用戶端的電腦。

-   透過電子軟體發佈系統或透過工具（例如 Active Directory 網域服務或 System Center Configuration Manager）來安裝 MBAM 用戶端。



## 相關主題


[部署 MBAM 2.5](deploying-mbam-25.md)

[部署 MBAM 2.5 用戶端](deploying-the-mbam-25-client.md)

[設定 MBAM 2.5 伺服器功能](configuring-the-mbam-25-server-features.md)

 

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





