---
title: 以電子軟體發佈為基礎的案例概觀
description: 以電子軟體發佈為基礎的案例概觀
author: dansimp
ms.assetid: e9e94b8a-6cba-4de8-9b57-73897796b6a0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cfbdf40f5ac0f61721c05d0da5cd49e910b16154
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808852"
---
# 以電子軟體發佈為基礎的案例概觀


如果您打算使用電子軟體發佈（ESD）方案來部署虛擬應用程式，請務必瞭解該決策所要進入並受到影響的因素。 本主題描述使用 ESD 式案例的優點，並提供發佈與套件流式處理方法的相關資訊，在您繼續進行部署時，您將需要考慮這些資訊。

**重要** 無論您使用的是哪一種 ESD 方案，您都必須熟悉特定解決方案的需求。 如果您使用的是 Microsoft 端點設定管理員，請參閱位於的 Configuration Manager 檔 <https://go.microsoft.com/fwlink/?LinkId=66999> 。

 

使用現有的 ESD 系統會為您提供下列好處：

-   消除雙管理基礎結構

-   減少額外硬體的成本

-   減少額外作業系統和資料庫授權的成本

## 發佈方法


使用 ESD 案例時，您可以選擇將應用程式發佈到用戶端的下列選項：

-   **獨立 Windows 安裝程式。** Windows Installer 檔案包含用戶端用來設定套件的資訊清單和 OSD 及 .ICO 檔案。 Windows 安裝程式檔案也會將 SFT 檔案複製到用戶端，因為這個案例不使用伺服器。

-   **包含套件資訊清單的 Windows 安裝程式。** Windows Installer 檔案包含用戶端用來設定套件的資訊清單和 OSD 及 .ICO 檔案。 SFT 檔案會儲存在伺服器上。 命令列參數會將用戶端導向到 SFT 檔案的位置。

-   **SFTMIME 命令。** SFTMIME 命令會與資訊清單、OSD、.ICO 及 SFT 檔案搭配使用，以將套件新增到用戶端。 資訊清單檔案必須在用戶端電腦上，或必須可透過 UNC 路徑進行存取。 根據用戶端設定與命令列選項，OSD、.ICO 和 SFT 檔案可以位於用戶端電腦或伺服器上。

如需上述發佈方法的詳細資訊，請參閱[決定發佈方法](determine-your-publishing-method.md)。

## 套件流式處理方法


您必須判斷您的應用程式虛擬化系統會用來從伺服器將虛擬應用程式套件（或 SFT 檔案）資料流到用戶端的方法。 下列資料流程選項可供使用：

-   **應用程式虛擬化資料流程伺服器。** 如果您在設定中使用應用程式虛擬化資料流程伺服器，則會使用 RTSP 或 RTSPS 通訊協定，將 SFT 檔案從該伺服器流入用戶端。 您必須在電腦上安裝伺服器軟體，而且您必須透過登錄進行設定，但此設定不會依賴于 SQL 或 Active Directory 網域服務等服務。 SFT 檔案會儲存在伺服器上用戶端可存取的位置。 發佈資訊可透過任何散佈機制分發給用戶端。 不過，當設定時，用戶端會自動接收套件升級，且支援進行中的升級。

-   **應用程式虛擬化管理伺服器。** 如果您在設定中使用應用程式虛擬化管理伺服器，則會使用 RTSP 或 RTSPS 通訊協定，將 SFT 檔案從該伺服器流入用戶端。 您可以透過應用程式虛擬化管理主控台來管理此伺服器。 此設定會使用 SQL 資料庫和 Active Directory 服務。 伺服器可將發佈資訊散佈到用戶端，因此不需要額外的發佈機制。

-   **檔案伺服器。** 如果您在設定中使用檔案伺服器，則會使用 SMB 通訊協定，將 SFT 檔案流式處理到其他用戶端電腦。 此設定中使用的檔案伺服器是透過在檔案共用和 SFT 檔案上建立存取控制清單（Acl）來管理。 請務必小心，將用戶端引導至檔案伺服器上的正確檔案。

-   **IIS 伺服器。** 如果您在設定中使用 IIS 伺服器，則會使用 HTTP 或 HTTPS 通訊協定，將 SFT 檔案從該伺服器流入用戶端。 IIS 伺服器很容易設定和管理。 請務必小心，將用戶端引導至 IIS 伺服器上的正確檔案。

如需上述流式處理方法的詳細資訊，請參閱[判斷您的流式處理方法](determine-your-streaming-method.md)。

## 相關主題


[Application Virtualization Client 安裝程式命令列參數](application-virtualization-client-installer-command-line-parameters.md)

[以 Application Virtualization 伺服器為基礎的案例](application-virtualization-server-based-scenario.md)

[決定您的發佈方法](determine-your-publishing-method.md)

[決定您的串流方法](determine-your-streaming-method.md)

[以電子軟體發佈為基礎的案例](electronic-software-distribution-based-scenario.md)

[SFTMIME 命令參考](sftmime--command-reference.md)

 

 





