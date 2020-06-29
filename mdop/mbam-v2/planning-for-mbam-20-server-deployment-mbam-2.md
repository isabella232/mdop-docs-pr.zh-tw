---
title: MBAM 2.0 伺服器部署規劃
description: MBAM 2.0 伺服器部署規劃
author: dansimp
ms.assetid: b57f1a42-134f-4997-8697-7fbed08e2fc4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 57e6510556522dce029c958172bd89a361e06b83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800137"
---
# MBAM 2.0 伺服器部署規劃


Microsoft BitLocker 管理與監視（MBAM）伺服器基礎結構，視企業的需求而定，可以安裝在一或多台伺服器電腦上的一組伺服器功能。 如果您是使用 Configuration Manager 拓撲進行 Microsoft BitLocker 管理和監視，請參閱[規劃使用 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md)。

**記事** 建議在單一伺服器上安裝 Microsoft BitLocker 管理和監控，只適用于測試環境。

 

## 規劃 MBAM Server 部署


MBAM 伺服器部署的基礎結構包括下列功能：

-   復原資料庫

-   合規性和審核資料庫

-   合規性與審計報告

-   自助服務入口網站

-   管理和監控伺服器

-   MBAM 群組原則範本

您可以根據您的可伸縮性需求，在不同的設定中安裝 MBAM 伺服器資料庫和功能。 所有的 MBAM 伺服器功能都可以安裝在單一伺服器上，或是分佈在多個伺服器上。 我們建議您在生產環境中使用雙伺服器設定，不過，您也可以根據自己的計算需求，使用兩個伺服器的配置。

每個 MBAM 功能都有特定的先決條件。 如需伺服器功能必備元件和硬體及軟體需求的完整清單，請參閱[MBAM 2.0 部署先決條件](mbam-20-deployment-prerequisites-mbam-2.md)和[MBAM 2.0 支援](mbam-20-supported-configurations-mbam-2.md)的設定。

除了伺服器相關的 MBAM 功能之外，伺服器安裝應用程式還包含 MBAM 群組原則範本。 範本包含您設定的群群組原則物件（GPO）設定，以管理企業中的 BitLocker 磁碟機加密。 您可以在任何可執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）的電腦上安裝此範本。

在您規劃 MBAM 伺服器部署時，請考慮 MBAM 中的 BitLocker 復原金鑰僅供單一使用，在修復金鑰到期後。 若要讓金鑰在使用之後過期，必須透過服務台入口網站或自助入口網站進行檢索。

## 部署 MBAM 伺服器功能的順序


若要在多個伺服器上部署 MBAM 功能，您必須以下列順序安裝這些功能：

1.  復原資料庫

2.  合規性和審核資料庫

3.  合規性審核與報告

4.  自助服務入口網站

5.  管理和監控伺服器

6.  MBAM 群組原則範本

**記事** 追蹤安裝每個功能的電腦名稱稱。 您必須在整個安裝過程中使用此資訊。 您可以列印並使用部署檢查清單來協助進行這項工作。 如需 MBAM 部署檢查清單的詳細資訊，請參閱[MBAM 2.0 部署檢查清單](mbam-20-deployment-checklist-mbam-2.md)。

 

## 相關主題


[規劃部署 MBAM 2.0](planning-to-deploy-mbam-20-mbam-2.md)

[部署 MBAM 2.0 伺服器基礎結構](deploying-the-mbam-20-server-infrastructure-mbam-2.md)

 

 





