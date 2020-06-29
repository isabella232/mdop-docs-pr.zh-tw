---
title: MBAM 2.5 用戶端部署規劃
description: MBAM 2.5 用戶端部署規劃
author: dansimp
ms.assetid: 23c89976-af24-4753-9412-ce0ea42d1964
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ff03b58da0985b2f57308c99a9bc15f4a0554623
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811487"
---
# MBAM 2.5 用戶端部署規劃


根據您部署 Microsoft BitLocker 管理和監視（MBAM）用戶端軟體的時間，您可以在使用者接收電腦之前或之後，在組織中的電腦上啟用 BitLocker 磁碟機加密。 針對 MBAM 獨立版和 System Center Configuration Manager 整合拓朴，您必須設定 MBAM 的群組原則設定。

如果您使用的是 MBAM 獨立拓朴，建議您使用企業軟體部署系統，將 MBAM 用戶端軟體部署到終端使用者電腦。

如果您使用 Configuration Manager 整合拓朴來部署 MBAM，您可以使用 Configuration Manager 將 MBAM 用戶端軟體部署到最終使用者的電腦。 在 Configuration Manager 中，MBAM 安裝會建立 MBAM 可管理的電腦集合。 此集合包含的工作站和裝置沒有受信任的平臺模組（TPM），但執行的是 Windows 8、Windows 8.1 或 Windows 10。

**記事** 當您使用 Configuration Manager 2007 時，Configuration Manager 整合拓撲安裝不支援 Windows To Go。

 

## 部署 MBAM 用戶端以在電腦發佈至最終使用者之後啟用 BitLocker 磁碟機加密


在您設定群組原則之後，您可以使用企業軟體部署系統產品（例如 Microsoft System Center Configuration Manager 或 Active Directory 網域服務（AD DS）），將 MBAM 用戶端安裝的 Windows Installer 檔案部署至目的電腦。 若要部署 MBAM 用戶端，您可以使用32位或64位 MbamClientSetup.exe 檔案或 MBAMClient.msi 檔案，這些檔案是由 MBAM 用戶端軟體所提供。

**記事** 從 MBAM 2.5 SP1 開始，MBAM 產品不再隨附個別的 MSI。 不過，您可以從隨附于產品的可執行檔（.exe）中解壓縮 MSI。

 

當您在將電腦發佈到用戶端電腦之後部署 MBAM 用戶端時，系統會提示使用者將電腦加密。 此動作可讓 MBAM 收集資料，其中包含 PIN 及密碼（如果原則需要的話），然後開始加密程式。

**記事** 在這個方法中，電腦擁有 TPM 晶片的使用者會在尚未啟用晶片的情況下，提示您啟用並初始化 TPM 晶片。

 

## 使用 MBAM 用戶端在電腦發佈至最終使用者之前啟用 BitLocker 磁碟機加密


在已集中接收和設定電腦的組織中，以及電腦擁有相容的 TPM 晶片的位置，您可以使用 MBAM 用戶端在每個電腦上管理 BitLocker 磁碟機加密，然後再寫入任何使用者資料。 此程式的優點是，每個電腦都符合規範。 這個方法不依賴使用者的使用者動作，因為系統管理員已經將電腦加密。 這個案例的主要假設是，在將電腦傳送給使用者之前，組織的原則會安裝公司的 Windows 影像。

如果您的組織想要使用 TPM 晶片來加密電腦，系統管理員會新增 TPM 保護程式來加密電腦的作業系統磁片。 如果您的組織想要使用 TPM 晶片及 PIN 保護器，系統管理員會使用 TPM 保護程式來加密作業系統的磁片，然後在使用者第一次登入時選取 PIN。 如果您的組織決定只使用 PIN 保護器，系統管理員就不需要先加密標籤。 當使用者登入時，Microsoft BitLocker 管理和監控會提示他們提供 PIN，或在稍後的電腦重新開機時要使用的 PIN 與密碼。

**記事** TPM 保護器選項需要系統管理員在將電腦傳送給最終使用者之前，先接受 BIOS 提示，才能啟動並初始化 TPM。

 

## MBAM 加密硬碟的用戶端支援


MBAM 支援針對 Opal 和 IEEE 1667 標準提供 TCG 規格需求的加密硬碟磁碟機上的 BitLocker。 在這些裝置上啟用 BitLocker 時，它會在加密的磁片磁碟機上產生金鑰並執行管理功能。 如需詳細資訊，請參閱[加密的硬碟](https://technet.microsoft.com/library/hh831627.aspx)。


## 相關主題


[規劃部署 MBAM 2.5](planning-to-deploy-mbam-25.md)

[部署 MBAM 2.5 用戶端](deploying-the-mbam-25-client.md)

 

 
## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




