---
title: 安全性與保護概觀
description: 安全性與保護概觀
author: dansimp
ms.assetid: a43e1c53-7936-4d48-a110-0be26c8e9d97
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b08b7dcb3defa8a01a4fd8a3e7234b5ac2956c4e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800863"
---
# 安全性與保護概觀


Microsoft Application Virtualization 4.5 提供下列增強的安全性功能，可協助您規劃及執行更安全的部署策略：

-   應用程式虛擬化現在支援使用 x.509 V3 憑證的傳輸層安全性（TLS）。 如果您已將伺服器憑證預配至規劃的應用程式虛擬化管理或流式處理伺服器，則安裝將預設為使用 RTSPS 通訊協定，透過埠322進行保護。 使用 RTSPS 可確保應用程式虛擬化伺服器與應用程式虛擬化用戶端之間的通訊已簽署並加密。 如果未在應用程式虛擬化伺服器安裝期間將憑證指派給伺服器，通訊將會設定為經由埠554的 RTSP。

    **安全性注意事項：**

    若要協助提供伺服器的安全設定，您必須先確定 RTSP 埠已停用，即使您已將所有套件設定為使用 RTSPS。

    如果您在安裝伺服器之後在伺服器中新增安全性憑證，伺服器可能無法偵測到憑證。 若要協助確保安全性憑證偵測，請在新增憑證後重新開機伺服器。

-   用戶端必須設定為使用與伺服器相同的通訊協定和埠，否則就不能與伺服器通訊。 用戶端也必須信任憑證的 issuer，並隨附在其受信任的根存放區中的幾個主要提供者。 您可以使用自我簽署的憑證，但是您需要更新用戶端。

-   將 IIS 伺服器設定為使用 HTTPS 通訊協定進行流式處理時，您必須在 IIS 伺服器上設定安全通訊端層（SSL），並為伺服器提供憑證。 用戶端也必須設定為信任頒發伺服器憑證的根憑證授權單位。

-   已將 Kerberos 驗證新增至 Microsoft Application Virtualization 作為預設驗證機制。 早期版本依賴于 NTLM V2 進行驗證。 使用 Kerberos 驗證能增強用戶端與應用程式虛擬化伺服器之間通訊的安全性。 從用戶端啟動連線時，應用程式虛擬化伺服器會使用金鑰發佈中心（KDC）來驗證會話票證。

-   由於支援使用伺服器憑證以及使用 RTSPS 或 HTTPS 通訊協定，您現在可以支援公司網路以外的用戶端。 這可協助您在啟動應用程式虛擬化設定的應用程式之前，避免行動使用者設定安全連線至公司網路（VPN、RAS 等）的需求。

考慮的其他重要安全考慮事項包括下列各項：

-   永遠保持伺服器完全更新並受到保護。

-   若要新增憑證以啟用更安全的與應用程式虛擬化管理伺服器通訊，必須符合下列準則：

    -   要新增憑證的使用者，必須是憑證存放所在伺服器的系統管理員。

    -   必須啟動伺服器服務。

    -   管理伺服器上的埠139必須開啟至 Web 服務 server'sIP。

-   使用存取控制清單（Acl），以確保應用程式套件和所有套件檔案受到保護且無法被篡改。 Acl 會限制對儲存套件之位置或資料夾的存取權，只允許存取特定帳戶。

-   確定應用程式虛擬化管理伺服器與資料庫之間的通道是安全的，例如，使用 IPsec。

-   如果套件儲存在 SAN 或 NAS 上，請確定中央存放裝置與應用程式虛擬化伺服器之間的連線已受到保護。

-   用戶端的所有通訊通道都應該受到保護，包括與發佈伺服器的連線、應用程式虛擬化伺服器，以及 OSD 與 .ICO 檔案的路徑，方法是使用 HTTPS 或 IPsec 等通訊協定。 

-   應該設定用戶端許可權，以協助確保使用者無法篡改套件。 您不會在與多個使用者共用的系統（例如遠端桌面工作階段主機（RDSession 主機）伺服器）上，給予使用者新增或更新套件的許可權，特別重要。

-   若要讓伺服器管理主控台能正常運作，必須跨網域或林環境允許 Kerberos 驗證。

-   這個版本的軟體不支援在相同的電腦上託管 Kerberos 式 RTSP 伺服器和僅限 Microsoft NTLM 的 IIS 伺服器。 若要在同一部電腦上託管 RTSP 伺服器和 IIS 伺服器，請從 IIS 伺服器移除 SPN，然後使用 NTLM 驗證。

## 相關主題


[規劃 Application Virtualization 系統部署](planning-for-application-virtualization-system-deployment.md)

 

 





