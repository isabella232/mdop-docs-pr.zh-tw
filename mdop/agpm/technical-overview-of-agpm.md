---
title: AGPM 技術概觀
description: AGPM 技術概觀
author: dansimp
ms.assetid: 36bc0ab5-f752-474c-8559-721ea95169c2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0cc635f46c2aabb0c9fa1f472a258a3e65a07b55
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801761"
---
# AGPM 技術概觀


Microsoft 高級群組原則管理（AGPM）是用戶端/伺服器應用程式。 AGPM 服務器會將 [封存] 中的 [群組原則物件] （Gpo）離線，在伺服器的檔案系統上建立。 群組原則管理員使用群組原則管理主控台（GPMC）的 AGPM 管理單元來處理託管封存的伺服器上的 Gpo。 瞭解 AGPM 與相關專案的各個部分、如何將 Gpo 儲存在檔案系統中，以及許可權如何控制每個使用者角色的可用動作，以使用 AGPM 改善群組原則管理員的效能。

## 詞彙


下列說明基本的 AGPM 詞彙。

-   **AGPM 用戶端：** 針對群組原則管理主控台（GPMC）及從哪個群組原則管理員管理 Gpo 的 [AGPM] 管理單元執行的電腦。

-   **AGPM 管理單元：** 在 AGPM 用戶端上安裝的 AGPM 軟體元件，讓他們可以管理 Gpo。

-   **AGPM 服務器：** 執行 AGPM 服務並管理封存的伺服器。 每個 AGPM 服務器只能管理一個封存，但一個 AGPM 服務器可以在一個封存中管理多個網域的封存資料。 封存可以存放在 AGPM 服務器以外的電腦上。

-   **AGPM 服務：** 在 AGPM 服務器上執行的 AGPM 軟體元件（作為服務）。 此服務會管理封存中以及該目錄林中生產環境中的 Gpo。

-   封存 **：** 在 AGPM 中，包含相關聯的 AGPM 服務器所管理之受管理 Gpo 的中央存放區，除了每個 Gpo 的歷史記錄以外。 這包括每個 GPO 以前的所有受控制版本。 封存包含封存索引檔案和相關的封存資料，可能會在多個網域中包含 Gpo 的資料。 封存可以存放在 AGPM 服務器以外的電腦上。

-   **受控制的 GPO：** 由 AGPM 管理的 GPO。 AGPM 會管理受管理 Gpo 的記錄和許可權，並將其儲存在封存中。

-   無法**控制的 GPO：** 網域的生產環境中的 GPO，且不由 AGPM 管理。

## 要安裝、建立及影響的 AGPM


在 AGPM 服務器上，AGPM 安裝程式會安裝 AGPM 服務。 AGPM 不會變更 Active Directory®目錄服務或架構。 根據預設，AGPM Server 程式檔案會安裝在%ProgramFiles%\\Microsoft\\AGPM\\Server。 如果您需要的話，您可以在網網域控制站上安裝 AGPM 服務;不過，我們建議您在成員伺服器上安裝 AGPM 服務。

在 AGPM 用戶端上，AGPM 安裝程式會安裝 AGPM 管理單元，將**變更控制**資料夾新增至 GPMC 中出現的每個網域。 根據預設，AGPM 用戶端程式檔案會安裝在%ProgramFiles%\\Microsoft\\AGPM\\Client。

表格1說明 AGPM 所安裝或建立的專案，以及影響 AGPM 操作的作業系統部分。

**表格1：由 AGPM 安裝、建立或影響的專案**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">項目</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AGPM 服務</p></td>
<td align="left"><p>AGPM 服務會在 AGPM 服務器上執行。 此服務會管理包含在生產環境中的離線 Gpo 和受控 Gpo 的封存。 AGPM 服務的預設設定如下所示：</p>
<ul>
<li><p><strong>服務名稱： </strong> AGPM 服務</p></li>
<li><p><strong>顯示名稱： </strong> AGPM 服務</p></li>
<li><p><strong>可執行檔的路徑： </strong> % ProgramFiles% \Microsoft\AGPM\Server\Agpm.exe</p></li>
<li><p><strong>啟動： </strong> 自動</p></li>
<li><p><strong>在 </strong> 安裝 Agpm Server 期間指定的 Agpm 服務帳戶（可使用 <strong> </strong> [控制台] 中的 [程式和功能] 變更）來登入 <strong> </strong> 。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>AGPM 封存</p></td>
<td align="left"><p>根據預設，AGPM 會在 AGPM 服務器的%ProgramData%\Microsoft\AGPM 中建立封存。 封存可提供離線 Gpo 的儲存空間，而且可以儲存每個 GPO 的多個版本。 AGPM 對封存中的 Gpo 所做的變更不會影響生產環境，除非 AGPM 管理員或核准者將 GPO 部署到生產環境，並將 gpo 連結至組織單位（OU）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 防火牆</p></td>
<td align="left"><p>在安裝期間，AGPM 會啟用入站 Windows 防火牆規則，讓 AGPM 用戶端可以與 AGPM 服務器進行通訊。 預設的 Windows 防火牆規則如下所示：</p>
<ul>
<li><p><strong>名稱： </strong> AGPM 服務</p></li>
<li><p><strong>動作： </strong> 允許連線</p></li>
<li><p><strong>程式： </strong> 符合指定條件的所有程式</p></li>
<li><p><strong>通訊協定類型： </strong> TCP</p></li>
<li><p><strong>本機埠： </strong> 4600</p></li>
<li><p><strong>遠端埠： </strong> 所有埠</p></li>
<li><p><strong>本機 IP 位址： </strong> 任何</p></li>
<li><p><strong>遠端 IP 位址： </strong> 任何</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>電子郵件伺服器</p></td>
<td align="left"><p>AGPM 使用簡易郵件傳輸通訊協定（SMTP），將電子郵件要求傳送到 [ <strong> 網域委派] 索引標籤上設定的位址 </strong> 。例如，當編輯者要求建立新的 GPO 時，AGPM 會通知您在 [網域委派] 索引標籤上指定的每個電子郵件地址 <strong> </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AGPM 管理單元</p></td>
<td align="left"><p>GPMC 的 AGPM 管理單元是在 AGPM 用戶端上執行，由群組原則管理員用來管理 Gpo。 管理單元會出現在 GPMC 中，成為 <strong> 每個網域中的 [變更控制] </strong> 資料夾。</p></td>
</tr>
</tbody>
</table>

 

### 其他參考資料

如需有關 AGPM 所安裝之檔案的詳細資訊，請參閱[適用于 agpm 的規劃指南](https://go.microsoft.com/fwlink/?LinkId=160060)。

## Archive


根據預設，AGPM 服務器安裝程式會在%ProgramData%\\Microsoft\\AGPM. 中的 [AGPM 服務器] 本機硬碟上建立封存 不過，您可以在安裝期間變更路徑，甚至在 AGPM 服務器以外的伺服器上建立封存。

封存包含封存所包含每個版本之 GPO 的子資料夾。 每個子資料夾的名稱是可識別 GPO 版本的 GUID。

gpostate.xml 檔案會記錄封存中每個 GPO 的狀態。 檔案是描述封存內容的資訊清單。 例如，GPO 可以有許多版本，而每個版本都位於封存中自己的子資料夾中。 gpostate.xml 檔案會指出哪些子資料夾包含不同版本的單一 GPO。 此外，GPO 範本在封存中有子資料夾，但 gpostate.xml 指出這些是範本，而不是受控制的 Gpo。 同樣地，當群組原則管理員刪除 Gpo 時，AGPM 會在 gpostate.xml 中變更其狀態，以指出它們位於 [**回收站**] 中，但實際上並不會從封存中移除 gpo 的子資料夾。

**小心** 請勿手動編輯 gpostate.xml 或封存所包含的 Gpo。 提供這項資訊只是為了加強對 AGPM 封存的瞭解。 您可以改為使用 AGPM 管理單元來變更 Gpo。

 

當 AGPM 建立封存時，它會將 [完全控制] 提供給系統、系統管理員和 AGPM 服務帳戶（在 AGPM 服務器的設定中指定）。 使用 AGPM 管理單元的 AGPM 使用者介面變更許可權，不會改變封存的許可權，因為 AGPM 服務帳戶代表登入的使用者執行所有操作。

### 其他參考資料

如需有關如何備份封存、從備份還原封存，或移動 AGPM 服務器與封存的相關資訊，請參閱[適用于 agpm 的操作指南](https://go.microsoft.com/fwlink/?LinkId=160061)中的「執行 Agpm 系統管理員工作」一節。

## 角色和權限


角色簡化委派。 您可以將四個角色的其中一個角色指派給群組原則管理員，而不是指派詳細的許可權給群組原則系統管理員，以讓他們執行與該角色相關的工作：

-   **AGPM 系統管理員：** 指派給 AGPM 系統管理員（完全控制）角色的群組原則管理員，可以在 AGPM 中執行任何工作。 AGPM 系統管理員可以設定全域性選項，並委派其他群組原則管理員的許可權。

-   **核准者：** 指派核准者角色的群組原則系統管理員可以將 Gpo 部署到網域的生產環境。 核准者也可以建立和刪除 Gpo，以及核准或拒絕來自編輯者的要求。 核准者可以在網域中查看 Gpo 的清單、查看 Gpo 中的原則設定，以及建立及查看 GPO 中原則設定的報告。 他們無法編輯 Gpo 中的原則設定，除非它們也獲指派了 [編輯者] 角色。

-   **編輯器：** 指派「編輯者角色」的群組原則管理員可以在網域中查看 Gpo 的清單、查看 Gpo 中的原則設定、編輯 Gpo 中的原則設定，以及建立及查看 GPO 中原則設定的報告。 除非他們也指派給核准者角色，否則編輯者就無法建立、部署或刪除 Gpo。 不過，他們可以要求建立、部署或刪除 Gpo。

-   **檢閱者：** 指派檢閱者角色的群組原則管理員可以在網域中查看 Gpo 的清單，並在 GPO 中建立及查看原則設定的報告。 除非它們也獲指派編輯器角色，否則他們無法在 GPO 中編輯策略設定。

AGPM 可讓 AGPM 系統管理員利用 AGPM 管理單元，以比角色更詳細的層級來設定許可權。 Table 2 說明這些許可權，並指出預設情況下授予每個角色的許可權。

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
<th align="left">使用權限</th>
<th align="left">描述</th>
<th align="left">AGPM 系統管理員</th>
<th align="left">核准者</th>
<th align="left">編輯器</th>
<th align="left">審校</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>完全控制</strong></p></td>
<td align="left"><p>擁有擁有權限。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>建立 GPO</strong></p></td>
<td align="left"><p>在網域中建立 Gpo。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>清單內容</strong></p></td>
<td align="left"><p>列出網域中的 Gpo。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>讀取設定</strong></p></td>
<td align="left"><p>讀取 GPO 中的原則設定。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>編輯設定</strong></p></td>
<td align="left"><p>變更 GPO 中的原則設定。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>刪除 GPO</strong></p></td>
<td align="left"><p>刪除 GPO。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>修改安全性</strong></p></td>
<td align="left"><p>委派網域層級存取、委派單一 GPO 的存取權，以及委派對生產環境的存取權。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>部署 GPO</strong></p></td>
<td align="left"><p>將 GPO 從封存部署到生產環境。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>建立範本</strong></p></td>
<td align="left"><p>在 AGPM 中建立 GPO 範本。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>修改選項</strong></p></td>
<td align="left"><p>設定 AGPM 電子郵件通知，並限制儲存在封存中的 GPO 版本。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>匯出 GPO</strong></p></td>
<td align="left"><p>將 GPO 匯出至檔案。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>匯入 GPO</strong></p></td>
<td align="left"><p>從檔案匯入 GPO。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

**記事** 
在 AGPM 3.0 或2.5 中無法使用**匯出 gpo**和匯**入 gpo**許可權。

在 AGPM 2.5 中，您無法委派對網域生產環境中 Gpo 的存取權，以及限制儲存之 GPO 版本數的能力。

 

### 其他參考資料

如需有關指派特定角色的群群組原則系統管理員或關於執行特定工作所需的許可權的相關資訊，請參閱適用于 AGPM 的[操作指南](https://go.microsoft.com/fwlink/?LinkId=160061)。

 

 





