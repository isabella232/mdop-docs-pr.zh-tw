---
title: 設定 IIS 以用於安全串流
description: 設定 IIS 以用於安全串流
author: dansimp
ms.assetid: 9a80a703-4642-4bec-b7af-dc7cb6b76925
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 724fd247d98c265421cea13f4b91c97049a2b4d4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809021"
---
# 設定 IIS 以用於安全串流


在發行 Microsoft Application Virtualization （App-v）版本4.5 時，您可以使用 HTTP 和 HTTPS 做為應用程式套件的通訊協定，以傳送到 App-v 用戶端。 這個選項可讓組織利用 IIS 通常提供的其他可伸縮性。 當您使用 IIS 作為流式處理伺服器時，您可以使用 HTTPS （而不是 HTTP），協助保護用戶端與伺服器之間的通訊安全。

**記事** 如果您想要從檔案伺服器對流進行應用程式，您應該加強與應用程式套件通訊的安全性。 這可以使用 IPsec 來實現。 如需詳細資訊，請參閱 TechNet 文件庫中的下列主題：

-   針對 Windows Server2003， <https://go.microsoft.com/fwlink/?LinkId=133226>

-   針對 Windows Server 2008， <https://go.microsoft.com/fwlink/?LinkId=133227>

 

## MIME 類型


當您使用 IIS 以 HTTP 或 HTTPS 流式處理虛擬應用程式時，若要支援 App-v，必須在 IIS 伺服器中新增下列 MIME 類型：

-   .OSD = TXT

-   .SFT = Binary

使用下列 KB 文章做為新增 MIME 類型的指導方針：

IIS 6.0： <https://go.microsoft.com/fwlink/?LinkId=151973>

IIS 7.0： <https://go.microsoft.com/fwlink/?LinkId=151977>

## Kerberos 驗證


當您使用 HTTP 或 HTTPS 與 Kerberos 驗證來資料流 .ICO、OSD 或 SFT 檔案時，您將會增強環境的安全性。 不過，若要讓 IIS 支援 Kerberos 驗證，您必須設定適當的服務主體名稱（SPN）。 `setspn.exe`從安裝 CD 的支援工具中，Windows Server2003 提供此工具，而且它是內建的 Windows Server2008。

若要建立 SPN，請在以 `setspn.exe` 網域管理員成員身分登入命令提示字元的情況下，執行該 SPN （例如，） `setspn.exe –A HTTP/FQDN of Server ServerName` 。

## 相關主題


[設定管理或串流伺服器以供安裝後續安全通訊](configuring-management-or-streaming-server-for-secure-communications-post-installation.md)

 

 





