---
title: MBAM 2.0 用戶端部署規劃
description: MBAM 2.0 用戶端部署規劃
author: dansimp
ms.assetid: 3a92cf29-092f-4cad-bdfa-d5f6aafe554b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c3a7383188d4064247d8e493c8e6125fc24a1d2b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800139"
---
# MBAM 2.0 用戶端部署規劃


根據您部署 Microsoft BitLocker 管理與監視（MBAM）用戶端的時間，您可以在您組織中的電腦上啟用 BitLocker 磁碟機加密，您必須先在使用者接收到電腦或之後進行。 針對 MBAM 獨立版與 Configuration Manager 拓撲結構，您必須設定 MBAM 的群組原則設定。

如果您使用的是 MBAM 獨立拓朴，建議您使用企業軟體部署系統，將 MBAM 用戶端軟體部署到終端使用者電腦。

如果您使用 Configuration Manager 拓撲部署 MBAM，您可以使用 Configuration Manager 將 MBAM 用戶端軟體部署到終端使用者電腦。 在 Configuration Manager 中，MBAM 安裝會建立 MBAM 可管理的電腦集合。 此集合包含的工作站和裝置沒有受信任的平臺模組（TPM），但執行的是 Windows 8。

**記事** 如果您使用的是 Configuration Manager 2007，則 MBAM 整合式 Configuration Manager 安裝不支援 Windows To Go。

 

## 部署 MBAM 用戶端以在電腦發佈至最終使用者之後啟用 BitLocker 加密


在您設定群組原則之後，您可以使用企業軟體部署系統產品（例如 Microsoft System Center Configuration Manager 或 Active Directory 網域服務（AD DS）），將 MBAM 用戶端安裝的 Windows Installer 檔案部署至目的電腦。 若要部署 MBAM 用戶端，您可以使用32位或64位 MbamClientSetup.exe 檔案或 MBAMClient.msi 檔案（隨附于 MBAM 軟體）。

當您在將電腦發佈到用戶端電腦之後部署 MBAM 用戶端時，系統會提示使用者將電腦加密。 這可讓 MBAM 收集資料（包括 PIN 和密碼），然後開始加密程式。

**記事** 在這個方法中，電腦擁有 TPM 晶片的使用者會收到啟動並初始化 TPM 晶片（如果此晶片尚未啟用）。

 

## 使用 MBAM 用戶端在電腦發佈至最終使用者之前啟用 BitLocker 加密


在已集中接收和設定電腦的組織中，以及電腦擁有相容的 TPM 晶片的位置，您可以安裝 MBAM 用戶端，在每個電腦上管理 BitLocker 加密，然後再寫入任何使用者資料。 此程式的優點是，每個電腦都會成為符合 BitLocker 加密規範的功能。 這個方法不依賴使用者的動作，因為系統管理員已經將電腦加密。 這個案例的主要假設是，在電腦傳送給使用者之前，組織的原則會安裝公司的 Windows 影像。

如果您的組織想要使用 TPM 晶片來加密電腦，系統管理員會新增 TPM 保護程式來加密電腦的作業系統磁片。 如果您的組織想要使用 TPM 晶片及 PIN 保護器，系統管理員會使用 TPM 保護程式來加密作業系統的磁片，然後在使用者第一次登入時選取 PIN。 如果您的組織決定只使用 PIN 保護器，系統管理員就不需要先加密標籤。 當使用者登入時，Microsoft BitLocker 管理和監控會提示他們提供 PIN，或在稍後的電腦重新開機時要使用的 PIN 與密碼。

**記事** TPM 保護器選項需要系統管理員在將電腦傳送給使用者之前，先接受 BIOS 提示，才能啟動並初始化 TPM。

 

## 相關主題


[規劃部署 MBAM 2.0](planning-to-deploy-mbam-20-mbam-2.md)

[部署 MBAM 2.0 用戶端](deploying-the-mbam-20-client-mbam-2.md)

 

 





