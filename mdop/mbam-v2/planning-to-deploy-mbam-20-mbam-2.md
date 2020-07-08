---
title: 規劃部署 MBAM 2.0
description: 規劃部署 MBAM 2.0
author: dansimp
ms.assetid: 2dc05fcd-aed9-4315-aeaf-92aaa9e0e955
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c7f065e52655212261dfe8b6b3f081f697142473
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811271"
---
# 規劃部署 MBAM 2.0


在建立 Microsoft BitLocker 管理與監控（MBAM）的部署方案之前，您應該先考慮幾個不同的部署設定和先決條件。 本節包含可協助您收集必要資訊的資訊，以闡明最符合您的業務需求的部署方案。 如果您是使用 Configuration Manager 拓撲安裝 MBAM，請參閱[規劃使用 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md) ，以取得額外的規劃資訊。

## 查看 MBAM 2.0 支援的設定


為 MBAM Server 和用戶端功能安裝準備好您的計算環境之後，請務必查看支援的設定，以確認您要安裝 MBAM 的電腦符合最低硬體與作業系統需求。 如需 MBAM 部署必備元件的詳細資訊，請參閱[MBAM 2.0 部署必備元件](mbam-20-deployment-prerequisites-mbam-2.md)。

[MBAM 2.0 支援的組態](mbam-20-supported-configurations-mbam-2.md)

## 規劃 MBAM 2.0 Server 和用戶端部署


MBAM 伺服器基礎結構視企業的需求而定，可以安裝在一或多台伺服器電腦上的一組伺服器功能上。 您可以在多個伺服器上以分散式配置來安裝這些功能。

**記事** 只有在實驗室環境中，才建議在單一伺服器上進行 MBAM 安裝。

 

MBAM 用戶端可讓系統管理員在企業中的電腦上強制執行及監視 BitLocker 磁片磁碟機加密。 您可以透過企業軟體傳送系統部署用戶端，或在用戶端電腦上安裝用戶端代理程式（作為初始影像處理常式的一部分），來將 BitLocker 用戶端整合到組織中。

有了 MBAM，您就可以在最終使用者接收電腦之前或使用 [群組原則] 之後，在您組織中的電腦上加密。

[MBAM 2.0 伺服器部署規劃](planning-for-mbam-20-server-deployment-mbam-2.md)

[MBAM 2.0 用戶端部署規劃](planning-for-mbam-20-client-deployment-mbam-2.md)

## <a href="" id="other-resources-for-mbam-planning-"></a>MBAM 規劃的其他資源


[MBAM 2.0 規劃](planning-for-mbam-20-mbam-2.md)

 

 





