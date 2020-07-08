---
title: 關於 Microsoft Application Virtualization 4.6 SP2
description: 關於 Microsoft Application Virtualization 4.6 SP2
author: dansimp
ms.assetid: 1429e314-9c38-472b-8687-3bed6cf0015c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 16303380782a086cfd750c7a8b2f99bf4f4c8b5d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802449"
---
# 關於 Microsoft Application Virtualization 4.6 SP2


Microsoft Application Virtualization （App-v） 4.6 SP2 提供幾項增強功能及新功能，如本主題所述。

**小心** 本主題說明如何使用 [登錄編輯程式] 變更 Windows 登錄。 如果您不正確地變更 Windows 登錄，可能會導致嚴重的問題，可能需要重新安裝 Windows。 變更登錄前，您應該先製作一份登錄檔案（系統 .dat 和使用者 .dat）的備份複本。 Microsoft 不能保證變更註冊表時可能會發生的問題，可以解決。 變更註冊表的風險由您自行承擔。

 

**Windows 8 和 Windows Server 2012 的支援**

App-V 4.6 SP2 新增 Windows 8 和 Windows Server 2012 遠端桌面服務的支援。

**支援 App-V 5.0 用戶端的共存**

App-V 4.6 SP2 提供與 Microsoft Application Virtualization 5.0 用戶端共存的支援。 請參閱 App-v 5.0 檔，以取得如何設定 App-v 5.0 用戶端與 App-v 4.6 SP2 用戶端共存的相關指示。 如需 App-V 5.0 的詳細資訊，請參閱 TechNet 上的[應用程式虛擬化 5](https://go.microsoft.com/fwlink/?LinkId=267599) 。

**能夠虛擬化 Adobe Reader X 與受保護的模式**

您可以使用下列程式，將 Adobe Reader X 虛擬化，並開啟其受保護的模式功能。 先前您必須停用受保護的模式，才能虛擬化 Adobe Reader X。

啟動 App-v 排序器之前，請先在 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE \\Microsoft\\SoftGrid\\4.5\\SystemGuard\\Overrides 中建立下列登錄值：

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>名稱</p></td>
<td align="left"><p>類型</p></td>
<td align="left"><p>資料</p></td>
<td align="left"><p>描述</p></td>
</tr>
<tr class="even">
<td align="left"><p>EnableVFSPassthrough</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>sr-1</p></td>
<td align="left"><p>將此值設定為 <strong> 1， </strong> 即可在啟動階段中，以 [受保護模式] 啟動 Adobe Reader X。</p></td>
</tr>
</tbody>
</table>

 

**記事** 在執行64位作業系統的電腦上，在 [HKEY \] 下建立登錄值 _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\Overrides。

 

針對您 Adobe Reader X 套件中的每個 OSD 檔案，請在 [原則] 元素底下新增下列專案 &lt; &gt; ：

`<VIRTUAL_FILE_SYSTEM_PASS_THROUGH>TRUE</VIRTUAL_FILE_SYSTEM_PASS_THROUGH>`

`<VIRTUAL_REGISTRY_PASS_THROUGH>TRUE</VIRTUAL_REGISTRY_PASS_THROUGH>`

`<ENFORCE_ACLS_ON_VREG_MODIFY>TRUE</ENFORCE_ACLS_ON_VREG_MODIFY>`

**新的 Sequencer 命令列參數**

當您透過排序器 GUI 建立套件加速器（PA）時，您可以選取 RTF 或 TXT 檔案，為將套用套件加速器的管理員提供封裝與部署指導方針。 此功能現在可使用排序器 CLI 使用。

`/ACCELERATORDESCRIPTIONFILE:PathToDescriptionFile`

指定 RTF 或 TXT 檔案的路徑，以便在建立套件加速器時提供封裝與部署指導方針。

**不再需要安裝 Microsoft 應用程式錯誤報表**

當您使用 setup.msi 安裝 App V 4.6 SP2 用戶端時，您不再需要安裝 Microsoft 應用程式錯誤報表（dw20shared.msi）。 App-v 4.6 SP2 現在使用 Microsoft 錯誤報表。 如需詳細資訊，請參閱[如何使用 Setup.msi安裝 App-V 用戶端](https://go.microsoft.com/fwlink/?LinkId=267237)。

**客戶意見反應與修補程式匯總**

App-V 4.6 SP2 包括自 App-v 4.6 SP1 發行以來發現問題的修正程式匯總。 App-V 4.6 SP2 包含最新的修正程式，包括 Microsoft Application Virtualization 4.6 SP1 修正程式6。

## 本節內容


<a href="" id="app-v-4-6-sp2-release-notes"></a>[App-V 4.6 SP2 版本資訊](https://go.microsoft.com/fwlink/?LinkId=267600)  
提供 App-V 4.6 SP2 已知問題的最新資訊。

 

 





