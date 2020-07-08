---
title: 部署 MBAM 1.0 伺服器基礎結構
description: 部署 MBAM 1.0 伺服器基礎結構
author: dansimp
ms.assetid: 90529379-b70e-4c92-b188-3d7aaf1844af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: de136db557233a097d95f47ef0a1bba5996798c5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811000"
---
# 部署 MBAM 1.0 伺服器基礎結構


您可以使用一到五台伺服器，在不同的設定中安裝 Microsoft BitLocker 管理和監控（MBAM）伺服器功能。 一般來說，您應該針對生產環境使用三到五台伺服器的配置，視您的可伸縮性需求而定。 如需 MBAM 和建議部署拓撲的效能伸縮性的詳細資訊，請參閱[MBAM 可伸縮性及高可用性指南白皮書](https://go.microsoft.com/fwlink/p/?LinkId=258314)。

## 在單一伺服器上部署所有 MBAM 1。0


在這個設定中，所有的 MBAM 功能都安裝在單一伺服器上。 此 MBAM server 基礎結構的部署拓朴會支援最多 21000 MBAM 用戶端電腦。

**重要** 這個設定是受支援的，但我們建議僅供測試。

 

本節中的程式說明在單一伺服器上完整安裝 MBAM 功能。

[如何在單一伺服器上安裝及設定 MBAM](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md)

## 在分散式伺服器上部署 MBAM 1。0


根據您的可伸縮性需求，MBAM 功能可以安裝在不同的設定中。 如需如何規劃 MBAM server 功能部署的詳細資訊，請參閱[規劃 MBAM 1.0 Server 部署](planning-for-mbam-10-server-deployment.md)。

本節中的程式說明分散式伺服器上的 MBAM 功能完整安裝。

### 三台電腦配置

下圖顯示適用于 MBAM 的三台電腦部署拓撲。 我們建議在支援最多 55000 MBAM 用戶端的生產環境中，進行這種拓撲。

![mbam 三台電腦部署拓朴](images/mbam-3-server.jpg)

在此設定中，MBAM 功能安裝在下列配置中：

1.  在伺服器上安裝了復原與硬體資料庫、合規性和審核資料庫，以及合規性和審核報告。

2.  系統會在伺服器上安裝 [管理和監控伺服器] 功能。

3.  MBAM 群組原則範本已安裝在能夠修改群群組原則物件（GPO）的電腦上。

### 四電腦配置

下圖顯示適用于 MBAM 的四電腦部署拓撲。 我們建議在支援最多 110000 MBAM 用戶端的生產環境中，使用此拓朴。

![mbam 四個電腦部署拓撲。](images/mbam-4-computer.jpg)

在此設定中，MBAM 功能安裝在下列配置中：

1.  在伺服器上安裝了復原與硬體資料庫、合規性和審核資料庫，以及合規性和審核報告。

2.  系統會在網路負載平衡（NLB）伺服器叢集中設定的伺服器上安裝 [管理和監控伺服器] 功能。

3.  MBAM 群組原則範本是安裝在能夠修改群組原則物件的電腦上。

### 五台電腦配置

下圖顯示適用于 MBAM 的五台電腦部署拓撲。 我們建議在支援最多 135000 MBAM 用戶端的生產環境中，進行這種拓撲。

![mbam 五台電腦部署拓撲。](images/mbam-5-computer.jpg)

在此設定中，MBAM 功能安裝在下列配置中：

1.  在伺服器上安裝復原和硬體資料庫。

2.  相容性與審計資料庫及合規性與審計報告都安裝在伺服器上。

3.  系統會在網路負載平衡（NLB）伺服器叢集中設定的伺服器上安裝 [管理和監控伺服器] 功能。

4.  MBAM 群組原則範本已安裝在能夠修改群組原則物件的電腦上。

[如何在分散式伺服器上安裝及設定 MBAM](how-to-install-and-configure-mbam-on-distributed-servers-mbam-1.md)

[如何針對 MBAM 設定網路負載平衡](how-to-configure-network-load-balancing-for-mbam.md)

## MBAM 1.0 Server 功能部署的其他資源


[部署 MBAM 1.0](deploying-mbam-10.md)

 

 





