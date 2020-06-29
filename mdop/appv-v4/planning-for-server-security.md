---
title: 規劃伺服器安全性
description: 規劃伺服器安全性
author: dansimp
ms.assetid: c7cd8227-b359-41e7-a8ae-d0d5718a76a2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9bea1bd8287a15385200bbfb425ed8e00fbcdb02
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800912"
---
# 規劃伺服器安全性


若要加強環境的安全性，您必須在環境中查看是否有任何可能的威脅。 提供 App-v 基礎結構的安全性需要您使用特定的 App V 安全性功能，以及基礎基礎結構的安全做法和功能。 針對 Internet 資訊服務（IIS）、Active Directory 網域服務與 SQL Server 等服務，保護基礎基礎結構的安全，將會改善 App V 系統的整體安全性。

伺服器安裝的預設設定會提供最高的安全性等級。 不過，某些元件依賴的基礎基礎結構並未設定為安裝的一部分。 依照安裝後的步驟進行後續步驟，將加強 App-v 基礎結構的安全性。

內容目錄包含要流入用戶端的所有套件。 這些資源必須盡可能安全，才能消除許多可能的安全性威脅。 下列清單提供一些其他指導方針：

-   UNC 式發佈和/或資料流程：此專案的許可權在環境中應該是最嚴格的限制式。 使用 NTFS 許可權來針對內容目錄執行最嚴格限制的存取控制清單（Acl）（使用者 = 讀取，系統管理員 = 讀取和寫入）。

-   用於發佈和/或資料流程的 IIS —將 IIS 設定為僅支援 Windows 整合式驗證。 移除 IIS 伺服器的匿名存取，並以 NTFS 許可權限制對目錄的存取權。

-   RTSP/RTSPS 以串流應用程式套件-將 App-v 提供者原則設定為需要驗證、強制進行存取許可權，並僅允許必要的群組存取提供者原則。 在資料庫中使用適當的許可權來設定應用程式。

將具有管理許可權的使用者數保持在最小，以減少資料存放區中的資料可能威脅，並避免將惡意的應用程式發佈到基礎結構中。

## 應用程式虛擬化安全性


App-V 在基礎結構的各個元件之間使用數種通訊方式。 規劃 app-v 基礎結構時，保護伺服器間的通訊可能會降低現有網路上可能已經存在的安全性風險。

### 資料存放區

應用程式虛擬化管理伺服器與應用程式虛擬化管理服務會透過 TCP 埠1433使用 SQL 連線來與資料存放區進行通訊。 管理伺服器使用資料存放區來取得應用程式和設定資料，並將使用資訊寫入資料庫。 管理服務代表設定 App-v 基礎結構的管理員，與資料儲存區進行通訊。 因為資料存放區包含重要資訊，所以請務必將此資料的威脅降至最低。

建議在 App-v 管理伺服器、管理服務與資料存放區之間的通訊使用網際網路通訊協定安全性（IPsec）加以保護。 具體說來，建立可保護資料存放區（SQL）與管理伺服器以及資料存放區與管理服務之間通訊通道的原則。 您也可以使用 [IPsec] 來部署伺服器與網域隔離，以確保所有 App-v 基礎結構元件只與安全通道進行通訊。 如需有關實施 IPsec 的資訊，請參閱下列檔：

-   若是 Windows Server2003，請參閱 <https://go.microsoft.com/fwlink/?LinkId=133226> （） https://go.microsoft.com/fwlink/?LinkId=133226) 。

-   若是 Windows Server2008，請參閱 <https://go.microsoft.com/fwlink/?LinkId=133227> （） https://go.microsoft.com/fwlink/?LinkId=133227) 。

### 內容目錄

App-v Management Server 安裝會設定內容目錄的位置。 此目錄是虛擬化應用程式套件的儲存位置。 這個位置可以是伺服器的本地位置，也可以放在遠端網路共用上。 因此，請實現 IPsec 以協助保護與內容目錄的遠端位置進行通訊。

您也可以使用 IIS 伺服器上的虛擬目錄，將套件傳輸到用戶端。 如果為內容建立的虛擬目錄位於遠端來源，請使用 IPsec 來協助保護 IIS 伺服器與遠端儲存位置之間的通訊。

內容目錄包含所有流入用戶端的套件。 這些資源必須盡可能安全，才能消除許多可能的安全性威脅。

### 安全性協定

您可以使用 RTSPS 或 HTTPS 來加強安全通訊。 RTSPS 是應用程式 V 伺服器所使用的通訊協定，而 HTTPS 是 IIS 伺服器所使用的通訊協定。 從伺服器將應用程式發佈到應用程式虛擬化桌面用戶端時，會用到這些通訊協定。 在您決定想要的通訊協定後，請新增使用該通訊協定的發佈伺服器。

### <a href="" id="configuring-app-v-servers-for-rtsps-"></a>設定 RTSPS 的 App-v 伺服器

安裝或設定 App V 管理伺服器或流式伺服器若要使用 [增強的安全性（例如 TLS）]，必須將 x.509 V3 憑證預配至 App-v 伺服器。 當您準備安裝或設定伺服器的安全性時，必須履行一些特定需求。 針對更安全的 App-v 管理伺服器或流式伺服器部署和設定憑證的技術需求包括下列各項：

-   憑證必須是有效的。 否則，用戶端會終止連線。

-   憑證必須包含正確的增強型金鑰用法（EKU）-伺服器驗證（OID 1.3.6.1.5.5.7.3.1）。 否則，用戶端會終止連線。

-   證書的完整功能變數名稱（FQDN）必須與安裝它的伺服器相符。 例如，如果用戶端正在通話 `RTSPS://Myserver.mycompany.com/content/MyApp.sft` ，但 [**頒發給**] 欄位的憑證包含 `Myserver1.mycompany.com` ，用戶端就不會連線到伺服器，而且會話會終止，即使 `Myserver.mycompany.com` 並 `Myserver1.mycompany.com` 解析為相同的 IP 位址也一樣。

    **記事** 如果您在網路負載平衡群集中使用 App-v，則必須使用*Subject 替代名稱*（san）來設定憑證以支援 RTSPS。 如需有關設定憑證授權單位（CA）及使用 San 建立憑證的詳細資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkId=133228> （ https://go.microsoft.com/fwlink/?LinkId=133228) 。

     

-   將憑證頒發給 App-v server 的 CA 必須受用戶端連線到伺服器的信任。 否則，用戶端會終止連線。

-   您必須變更*證書私密金鑰*的許可權，才能透過伺服器 app-v 服務來啟用存取。 根據預設，應用程式 V 管理伺服器與流式處理伺服器服務會在網路服務帳戶下執行。 當在伺服器上產生 PKCS \ #10 時，就會建立一個私用金鑰。 只有 [本機系統] 和 [管理員] 群組有權存取此金鑰。 這些預設 Acl 會防止 App-v 伺服器接受安全連線。

    **記事** 如需有關設定公開金鑰基礎結構（PKI）的資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkId=133229> （ https://go.microsoft.com/fwlink/?LinkId=133229) 。

     

### 使用 HTTPS 設定 IIS 伺服器

App-v 可能會在某些基礎結構設定中使用 IIS 伺服器。 如需有關設定 IIS 伺服器的詳細資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkId=133230> （） https://go.microsoft.com/fwlink/?LinkId=133230) 。

**記事** 如果您使用 IIS 來發佈 .ICO 和 OSD 檔案，請設定 OSD = TXT 的 MIME 類型;否則，IIS 將拒絕將 .ICO 和 OSD 檔案提供給用戶端。

 

### 應用程式層級安全性

您可以將伺服器設定為將特定應用程式資料流至使用者的桌面。 不過，實際是在封裝層級，而不是在應用程式層級授與存取許可權。 雖然特定應用程式可能無法發佈至使用者的桌面，但如果使用者有權新增應用程式或用戶端電腦上的系統管理員，則使用者可以在用戶端上建立並使用快捷方式來執行套件中的所有應用程式。

## 設定分散式環境的 App-V 系統管理


針對您的特定組織設計基礎結構時，您可以在安裝 App-v Management Server 的電腦以外的電腦上安裝 App-v Management Web 服務。 分隔這些 App V 元件的常見原因包括下列各項：

-   效能

-   可靠性

-   可用性

-   延展性

若要讓基礎結構正常運作，請在應用程式 V 管理主控台、管理伺服器與管理 Web 服務之間分隔，需要進行額外的設定。 如需如何設定伺服器的詳細資訊，請參閱[如何將伺服器設定為信任委派](how-to-configure-the-server-to-be-trusted-for-delegation.md)。

## 相關主題


[規劃安全性與保護](planning-for-security-and-protection.md)

 

 





