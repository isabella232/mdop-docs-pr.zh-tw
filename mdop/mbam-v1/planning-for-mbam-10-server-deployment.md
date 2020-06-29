---
title: MBAM 1.0 伺服器部署規劃
description: MBAM 1.0 伺服器部署規劃
author: dansimp
ms.assetid: 3cbef284-3092-4c42-9234-2826b18ddef1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 76ff9c444ce3f9c39161341610fb0cd9a763dc6d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800091"
---
# MBAM 1.0 伺服器部署規劃


Microsoft BitLocker 管理與監視（MBAM）伺服器基礎結構，視您的企業需求而定，您可以在一或多台伺服器電腦上安裝一組伺服器功能。

## 規劃 MBAM Server 部署


下列 MBAM 功能代表 MBAM 伺服器部署的伺服器基礎結構：

-   恢復與硬體資料庫

-   合規性和審核資料庫

-   合規性與審計報告

-   管理和監控伺服器

您可以根據您的可伸縮性需求，在不同的設定中安裝 MBAM 伺服器資料庫和功能。 所有的 MBAM 伺服器功能都可以安裝在單一伺服器上，或是分佈在多個伺服器上。 一般來說，我們建議您針對生產環境使用三台伺服器或五台伺服器設定，不過，您也可以根據自己的計算需求，使用兩個或四個伺服器的配置。

**記事** 如需 MBAM 和建議部署拓撲的效能伸縮性的詳細資訊，請參閱 MBAM 可伸縮性及高可用性指南白皮書 <https://go.microsoft.com/fwlink/p/?LinkId=258314> 。

 

每個 MBAM 功能都有特定的先決條件。 如需伺服器功能必備元件和硬體及軟體需求的完整清單，請參閱[MBAM 1.0 部署先決條件](mbam-10-deployment-prerequisites.md)和[MBAM 1.0 支援](mbam-10-supported-configurations.md)的設定。

除了伺服器相關的 MBAM 功能之外，伺服器安裝應用程式還包含 MBAM 群組原則範本。 此範本可安裝在任何能夠執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）的電腦上。

## 部署 MBAM 伺服器功能的順序


當您部署 MBAM 伺服器功能時，請依照下列順序安裝這些功能：

1.  恢復與硬體資料庫

2.  合規性和審核資料庫

3.  合規性審核與報告

4.  管理和監控伺服器

5.  原則範本

**記事** 追蹤安裝每個功能的電腦名稱稱。 您將會在整個安裝過程中使用此資訊。 您可以列印並使用部署檢查清單來協助您完成安裝程式。 如需 MBAM 部署檢查清單的詳細資訊，請參閱[MBAM 1.0 部署檢查清單](mbam-10-deployment-checklist.md)。

 

## 相關主題


[規劃部署 MBAM 1.0](planning-to-deploy-mbam-10.md)

[部署 MBAM 1.0 伺服器基礎結構](deploying-the-mbam-10-server-infrastructure.md)

 

 





