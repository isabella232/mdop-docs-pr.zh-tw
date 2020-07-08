---
title: 使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能
description: 使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能
author: dansimp
ms.assetid: 826429fd-29bb-44be-b47e-5f5c7d20dd1d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: f350a9eb96a20f50644cfdc1965b7f72741a2c29
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809596"
---
# 使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能


在您安裝 MBAM 2.5 Server 軟體之後，您可以使用 Windows PowerShell Cmdlet 或 [MBAM 伺服器設定] 嚮導，使用 [設定 MBAM 2.5 伺服器功能]。 本主題描述如何使用 Windows PowerShell Cmdlet 來設定 MBAM 2.5。 若要改為使用嚮導，請參閱設定[MBAM 2.5 伺服器功能](configuring-the-mbam-25-server-features.md)。

## 本主題內容


本主題包含下列關於使用 Windows PowerShell 來設定 MBAM 的資訊：

-   [如何載入 MBAM 2.5 的 Windows PowerShell 說明](#bkmk-load-posh-help)

-   [如何取得有關 MBAM Windows PowerShell Cmdlet 的說明](#bkmk-help-specific-cmdlet)

-   [您只能在 Windows PowerShell 中執行的設定，而不能使用 MBAM Server 設定精靈進行](#bkmk-config-only-posh)

-   [使用 Windows PowerShell 設定 MBAM Server 功能的先決條件及需求](#bkmk-prereqs-posh-mbamsvr)

-   [使用 Windows PowerShell 來設定遠端電腦上的 MBAM](#bkmk-remote-config)

-   [必要的帳戶和對應的 Windows PowerShell Cmdlet 參數](#bkmk-reqd-posh-accts)

如需可用於管理 MBAM 之**MbamBitLockerRecoveryKey**和**MbamTPMOwnerPassword** Windows powershell Cmdlet 的詳細資訊，請參閱[使用 Windows PowerShell 管理 MBAM 2.5](using-windows-powershell-to-administer-mbam-25.md)。

## <a href="" id="bkmk-load-posh-help"></a>如何載入 MBAM 2.5 的 Windows PowerShell 說明


如需 TechNet 上的 Windows PowerShell Cmdlet 清單，請參閱適用[于 Windows powershell 的 Microsoft 桌面優化套件自動化](https://go.microsoft.com/fwlink/?LinkId=392816)。

**若要在安裝 MBAM 伺服器軟體後載入 Windows PowerShell Cmdlet 的 MBAM 2.5 說明**

1.  開啟 Windows PowerShell 或 Windows PowerShell 整合式腳本環境（ISE）。

2.  類型**更新-說明-MODULE MBAM**。

## <a href="" id="bkmk-help-specific-cmdlet"></a>如何取得有關 MBAM Windows PowerShell Cmdlet 的說明


MBAM 的 Windows PowerShell 說明提供下列格式：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Windows PowerShell 說明格式</th>
<th align="left">詳細資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在 Windows PowerShell 命令提示字元中，輸入 <strong> get-help </strong> &lt; <em> Cmdlet</em>&gt;</p></td>
<td align="left"><p>若要上傳最新的 Windows PowerShell Cmdlet，請按照上一節中如何載入 MBAM 的 Windows PowerShell 說明一節中的指示進行。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在 TechNet 上做為網頁</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393498" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393498">https://go.microsoft.com/fwlink/?LinkId=393498</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>以單字 .docx 檔案的形式在下載中心</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393497" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393497">https://go.microsoft.com/fwlink/?LinkId=393497</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>以 .pdf 檔案的形式在下載中心</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393499" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393499">https://go.microsoft.com/fwlink/?LinkId=393499</a></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-config-only-posh"></a>您只能在 Windows PowerShell 中執行的設定，而不能使用 MBAM Server 設定精靈進行


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">只能使用 Windows PowerShell 執行的設定</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>從 web 應用程式在不同的電腦上安裝 web 服務。</p></td>
<td align="left"><p>您必須在同一部電腦上安裝 web 服務和 web 應用程式，才能使用此嚮導。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在個別的報表服務點啟用報表，而不安裝所有 Configuration Manager 物件。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>從 Configuration Manager 刪除所有物件。</p></td>
<td align="left"><p>刪除物件時，會從 Configuration Manager 刪除所有合規性資料。</p></td>
</tr>
<tr class="even">
<td align="left"><p>為資料庫輸入自訂的連線字串。</p></td>
<td align="left"><p>範例：若要將 web 應用程式設定為搭配鏡像使用，您必須使用 <strong> Enable-MbamWebApplication </strong> Cmdlet，在連線字串中指定適當的容錯移轉合作夥伴語法。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>[略過驗證] 和 [設定功能]，即使必備項檢查失敗也一樣。</p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

 

**記事** 您無法使用 Windows PowerShell Cmdlet 或 MBAM 伺服器設定向導停用 MBAM 資料庫。 若要防止意外移除您的合規性和審核資料，資料庫管理員必須手動移除資料庫。

 

## <a href="" id="bkmk-prereqs-posh-mbamsvr"></a>使用 Windows PowerShell 設定 MBAM Server 功能的先決條件及需求


開始設定之前，請先完成下列先決條件。

**與客戶相關的先決條件**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必備</th>
<th align="left">詳細資料或其他資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>建立必要的帳戶。</p></td>
<td align="left"><p>請參閱 <strong> 本主題稍後的所需帳戶和對應的 Windows PowerShell Cmdlet 參數一節 </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>您傳遞為 Windows PowerShell Cmdlet 之參數的使用者帳戶和群組，在網域中必須是有效的帳戶。</p></td>
<td align="left"><p>您無法使用本機帳戶。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>指定底層格式的帳戶。</p></td>
<td align="left"><p>範例：</p>
<p>domainNetBiosName\userdomainNetBiosName\group</p></td>
</tr>
</tbody>
</table>

 

**許可權相關的先決條件**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必備</th>
<th align="left">詳細資料或其他資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>您必須是本機電腦的系統管理員，才能設定 MBAM 功能。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>使用提升許可權的 Windows PowerShell 命令提示字元來執行所有的 Windows PowerShell Cmdlet。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>僅適用于 <strong> Enable-MbamDatabase </strong> Cmdlet：</p>
<p>您必須 &quot; &quot; 在目標 Microsoft SQL Server 資料庫的實例上擁有 [建立任何資料庫] 許可權。</p>
<p>這個使用者帳戶必須是本機管理員群組的一部分，或 [備份操作員] 群組，才能註冊 MBAM Volume Shadow 複製服務（VSS）寫入程式。</p></td>
<td align="left"><p>根據預設，資料庫系統管理員或系統管理員必須 &quot; 建立任何資料庫 &quot; 許可權。</p>
<p></p>
<p>如需 VSS 寫入程式的詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=392814" data-raw-source="[Volume Shadow Copy Service](https://go.microsoft.com/fwlink/?LinkId=392814)"> Volume Shadow 複製服務 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>僅限 System Center Configuration Manager 整合 </strong> 功能：</p>
<p>啟用此功能的使用者必須在 Configuration Manager 中擁有下列許可權：</p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Configuration Manager 中的許可權類型</th>
<th align="left">所需的許可權</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Configuration Manager 網站許可權：</p></td>
<td align="left"><p>- 讀取</p></td>
</tr>
<tr class="even">
<td align="left"><p>Configuration Manager 集合許可權：</p></td>
<td align="left"><p>- 建立-刪除-已讀-修改-部署設定項目</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Configuration Manager 設定項目許可權：</p></td>
<td align="left"><p>- 建立-刪除-已讀取</p></td>
</tr>
</tbody>
</table>
<p> </p>
<p></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-remote-config"></a>使用 Windows PowerShell 來設定遠端電腦上的 MBAM


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>使用此功能的時機</strong></p></td>
<td align="left"><p>當您想要設定遠端電腦上的 MBAM 2.5 伺服器功能時。 Windows PowerShell Cmdlet 是在一部電腦上執行，您是在不同的遠端電腦上設定功能。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>您必須執行的動作</strong></p></td>
<td align="left"><p>若要使用 Windows PowerShell 來設定遠端電腦上的 MBAM 2.5 伺服器功能，您必須：</p>
<ul>
<li><p>確認已在遠端電腦上安裝 MBAM 2.5 Server 軟體。</p></li>
<li><p>使用認證安全支援提供者（CredSSP）通訊協定來開啟 Windows PowerShell 會話。</p></li>
<li><p>啟用 Windows 遠端系統管理（WinRM）。 如果您無法啟用 WinRM 並正確設定， <strong> </strong> 此表格中所述的新 PSSession Cmdlet 會顯示錯誤，並說明如何修正問題。 如需有關 WinRM 的詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=393064" data-raw-source="[Using Windows Remote Management](https://go.microsoft.com/fwlink/?LinkId=393064)"> 使用 Windows 遠端系統管理 </a> 。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>為什麼要這麼做</strong></p></td>
<td align="left"><p>這個通訊協定可讓 Windows PowerShell Cmdlet 使用使用者的管理認證來連線至 Active Directory 網域服務。 如果您在沒有這個通訊協定的情況下啟動 Windows PowerShell 會話，您可能會收到驗證錯誤。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>如何使用 CredSSP 通訊協定啟動 Windows PowerShell 會話</strong></p></td>
<td align="left"><p>在 Windows PowerShell 提示中輸入下列程式碼：</p>
<p><code>$s = New-PSSession -ComputerName xxx -Authentication Credssp -Credential xxx</code></p>
<p>下列程式碼顯示一個範例。</p>
<p><code>$session = New-PSSession -ComputerName &lt;MBAM_server_name&gt; -Authentication Credssp -Credential (Get-Credential)</code></p>
<p><code>Enter-PSSession $session</code></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-reqd-posh-accts"></a>必要的帳戶和對應的 Windows PowerShell Cmdlet 參數


下表說明設定 MBAM 2.5 伺服器功能所需的帳戶。 它也會列出對應的 Windows PowerShell Cmdlet 和參數，您必須在設定期間指定該帳戶。

Cmdlet 參數類型（使用者或群組） Description Enable-MBAMDatabase

AccessAccount

使用者或群組

指定擁有此資料庫讀/寫許可權的網域使用者或群組，以讓 web 應用程式存取此資料庫中的資料和報表。 如果該值是網域使用者，則執行**Enable MbamWebApplication** Cmdlet 時所使用的**WebServiceApplicationPoolCredential**參數必須使用相同的使用者帳戶。 如果該值是 [網域使用者] 群組，則**WebServiceApplicationPoolCredential**參數所使用的網域帳戶必須是此群組的成員。

ReportAccount

使用者或群組

指定擁有此資料庫唯讀許可權的網域使用者或使用者群組，以提供 MBAM 報告對合規性和審核資料的存取權。 如果該值是網域使用者， **Enable-MbamReport** Cmdlet 的**ComplianceAndAuditDBCredential**參數必須使用相同的使用者帳戶。 如果該值是 [網域使用者] 群組，則**ComplianceAndAuditDBCredential**參數所使用的網域帳戶必須是此群組的成員。

Enable-MbamReport

ComplianceAndAuditDBCredential

使用者

指定本機 SSRS 實例用來連線到 MBAM 合規性和審核資料庫的管理認證。 系統管理認證中的網域使用者必須與執行**ReportAccount**參數時所使用的使用者帳戶相同，這會在執行**Enable-MbamDatabase** Cmdlet 時使用。 如果網域使用者群組是與**ReportAccount**參數搭配使用，這個帳戶應該是該群組的成員。

**重要** 系統管理認證中指定的帳號應該擁有有限的使用者許可權，以提高安全性。 此外，帳戶的密碼應該設定為 [未過期]。

 

ReportsReadOnlyAccessGroup

群組

指定擁有報告 [讀取] 許可權的網域使用者群組。 指定的群組必須是在**Enable-MbamWebApplication** Cmdlet 中用於**ReportsReadOnlyAccessGroup**參數的同一個群組。

Enable-MBAMWebApplication

AdvancedHelpdeskAccessGroup

群組

指定 [網域使用者] 群組，該群組有權存取管理和監控網站的所有區域（[報告] 區域除外）。

HelpdeskAccessGroup

群組

指定可存取管理和監控網站之 [**管理 TPM** ] 和 [**磁片磁碟機**] 區域的 [網域使用者] 群組。

ReportsReadOnlyAccessGroup

群組

指定擁有 [管理] 和 [監視] 網站 [**報告**] 區域之 [讀取] 許可權的 [網域使用者] 群組。 指定的群組必須是在**Enable-MbamReport** Cmdlet 中用於**ReportsReadOnlyAccessGroup**參數的同一個群組。

WebServiceApplicationPoolCredential

使用者

指定要供 MBAM web 應用程式的應用程式池使用的網域使用者。 它必須是在**Enable-MbamDatabase** Cmdlet 的**AccessAccount**參數中所指定的相同網域使用者帳戶。 如果**AccessAccount**參數是在執行**Enable MbamDatabase** Cmdlet 時使用網域使用者群組，則此處指定的網域使用者必須是該群組的成員。 如果您沒有指定管理認證，則會使用任何先前啟用的 web 應用程式所指定的管理認證。 所有的 web 應用程式都使用相同的應用程式池身分識別。 如果多次指定，則會使用最近指定的值。

**重要** 若要提高安全性，請將管理認證中指定的帳號設定為受限制的使用者權利。 此外，將帳戶的密碼設定為永不過期。 請確定已將內建的 IIS \ _IUSRS 帳戶或用於**WebServiceApplicationPoolCredential**參數的帳戶新增至 [在驗證本機安全性**之後類比用戶端**] 設定。

若要查看 [本機安全性] 設定，請開啟 [**本機安全性原則編輯器**]，然後展開 [**本機原則**] 節點，選取 [**使用者權利指派**] 節點，然後按兩下 [在**驗證之後類比用戶端**]，然後在詳細資料窗格中以**批次工作**群組原則設定登入。

 

 




## 相關主題


[設定 MBAM 2.5 伺服器功能](configuring-the-mbam-25-server-features.md)

[驗證 MBAM 2.5 伺服器功能設定](validating-the-mbam-25-server-feature-configuration.md)

[使用 Windows PowerShell 管理 MBAM 2.5](using-windows-powershell-to-administer-mbam-25.md)

 
## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
 





