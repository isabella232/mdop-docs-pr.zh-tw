---
title: 規劃 Application Virtualization Client 部署
description: 規劃 Application Virtualization Client 部署
author: dansimp
ms.assetid: a352f80f-f0f9-4fbf-ac10-24c510b2d6be
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6c9fc4f29020af83a8606827015947e78761f4d7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800922"
---
# 規劃 Application Virtualization Client 部署


決定如何將虛擬應用程式套件發佈並部署到您的最終使用者電腦之後，您應該規劃應用程式虛擬化用戶端軟體的部署。

應用程式虛擬化用戶端是實際執行虛擬應用程式的元件。 應用程式虛擬化用戶端可讓使用者與圖示互動，並按兩下檔案類型來啟動虛擬應用程式。 它也會從流式處理伺服器處理應用程式內容的資料流程，並在啟動應用程式之前先將其進行緩衝。 應用程式內容的結構化，即啟動應用程式及處理初始使用者互動所需的所有內容都會先以資料流程傳送給最終使用者的電腦。 應用程式虛擬化用戶端軟體有兩種不同的類型：遠端桌面服務（舊稱終端服務）的應用程式虛擬化用戶端，用於遠端桌面工作階段主機（RDSession 主機）伺服器系統，以及適用于所有其他電腦的應用程式虛擬化桌面用戶端。

應用程式虛擬化用戶端應該在安裝期間以應用程式虛擬化管理主控台或透過安裝程式命令列來設定，包括下列各項：

-   所有應用程式之圖示的位置。

-   包含套件定義資訊的 OSD 檔案位置。

-   應用程式內容來源。

-   檢索前面的專案時要使用的通訊通訊協定。

-   要使用的快取大小與快取大小管理方法。

若要在使用電子軟體發佈（ESD）方案時，加速應用程式虛擬化用戶端軟體的部署，必須事先謹慎定義前面的設定。 當您的電腦位於不同的辦公室，且需要將其用戶端設定為使用不同的來源位置時，這一點尤為重要。

**注意**  
-   在選擇發佈方法時（無論是使用 Windows Installer 或 SFTMIME），圖示位置和 OSD 檔案值都是要考慮的重要因素。 應用程式內容來源的設定是由您選擇的流式處理方法所定義。

-   若要確保快取已為所有已部署套件指派足夠的空間，請使用設定用戶端時使用的 [**可用磁碟空間閾值**] 設定，讓快取視需要增加。 或者，您可以在安裝期間預先決定需要多少磁碟空間，並在安裝時設定快取大小。 如需有關緩衝空間管理功能的詳細資訊，請參閱如何使用 Microsoft Application Virtualization （App-v）操作指南中的快取**空間管理功能**。

-   在發佈與 HTTP （S）資料流程作業期間，App-v 4.5 SP1 用戶端會使用在使用者電腦上的 Internet Explorer 中設定的 proxy 伺服器設定。

如需有關設定用戶端安裝參數的詳細資訊，請參閱[應用程式虛擬化用戶端安裝程式命令列參數](application-virtualization-client-installer-command-line-parameters.md)。

 

最後，您必須決定如何為桌面用戶端部署 Application Virtualization 桌面用戶端軟體。 雖然您可以在每個電腦上手動部署應用程式虛擬化桌面用戶端，但大多陣列織必須透過一些自動化程式來執行此操作。 中型或大型組織可能會有 ESD 系統在運作中，這是部署用戶端的理想方式。 如果不存在 ESD 系統，您可以使用您在組織中安裝軟體的標準方法。 選項包括群組原則或各種腳本技術。 視您擁有的辦公室數量和規模而定，此部署程式可能很複雜，而且您必須使用結構化的方法，以確保所有電腦都能以正確的設定來取得安裝的用戶端。

## 相關主題


[規劃 Application Virtualization 系統部署](planning-for-application-virtualization-system-deployment.md)

[如何使用命令列安裝用戶端](how-to-install-the-client-by-using-the-command-line-new.md)

[如何在用戶端上發佈虛擬應用程式](how-to-publish-a-virtual-application-on-the-client.md)

[如何升級 Application Virtualization Client](how-to-upgrade-the-application-virtualization-client.md)

[如何解除安裝 App-V Client](how-to-uninstall-the-app-v-client.md)

 

 





