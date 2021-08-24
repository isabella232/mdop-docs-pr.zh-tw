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
ms.openlocfilehash: 63099d425b51bfde52eac59771007b1c765acf05
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910418"
---
# <a name="deploying-the-mbam-10-server-infrastructure"></a>部署 MBAM 1.0 伺服器基礎結構


您可以使用一到五 (，以不同的 (安裝 MICROSOFT BitLocker 系統管理) 管理與監控功能。 一般而言，您應該根據您的擴充能力需求，針對生產環境使用三到五個伺服器組。 For more information about performance scalability of MBAM and recommended deployment topologies, see the [MBAM Scalability and High-Availability Guide White Paper](https://go.microsoft.com/fwlink/p/?LinkId=258314).

## <a name="deploy-all-mbam-10-on-a-single-server"></a>在單一伺服器上部署所有 IBMM 1.0


在此配置中，所有 IBMM 功能都安裝在單一伺服器上。 此部署拓撲適用于 ：適用于 IBMM 伺服器基礎結構，最多支援 21，000 部 IBMM 用戶端電腦。

**重要**  
支援此組配置，但我們建議您僅測試。

 

本節中的程式描述在單一伺服器上完整安裝的 IBMM 功能。

[如何在單一伺服器上安裝及設定 MBAM](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md)

## <a name="deploy-mbam-10-on-distributed-servers"></a>在分散式伺服器上部署 IBMM 1.0


根據您的擴充能力需求，可依您的不同配置安裝 。。 若要瞭解如何規劃適用于 IBMM 伺服器功能部署的資訊，請參閱[規劃適用于 IBMM 1.0 伺服器部署 。](planning-for-mbam-10-server-deployment.md)

本節中的程式描述在分散式伺服器上完整安裝 IBMM 功能。

### <a name="three-computer-configuration"></a>三部電腦群組組

下圖顯示三部電腦部署拓撲的 ：適用于 我們建議此拓撲適用于支援多達 55，000 個的 55，000 個管理用戶端的生產環境。

![管理三種電腦部署拓撲。](images/mbam-3-server.jpg)

在此組配置中，以下組配置中已安裝了 ：：

1.  修復與硬體資料庫、合規性和稽核資料庫，以及合規性和稽核報告會安裝在伺服器上。

2.  系統伺服器上已安裝系統管理與監控伺服器功能。

3.  在能夠修改 GPO 或 GPO 的群組原則物件的電腦上， (群組原則) 。

### <a name="four-computer-configuration"></a>四電腦群組

下圖顯示適用于該電腦的四電腦部署拓撲。 我們針對可支援多達 110，000 個的 110，000 個

![管理四種電腦部署拓撲。](images/mbam-4-computer.jpg)

在此組配置中，以下組配置中已安裝了 ：：

1.  修復與硬體資料庫、合規性和稽核資料庫，以及合規性和稽核報告會安裝在伺服器上。

2.  系統管理與監控伺服器功能會安裝在網路負載平衡與 NLB (伺服器) 伺服器上。

3.  在能夠修改群組原則物件的電腦上，會安裝一個可修改群組原則物件的電腦上。。

### <a name="five-computer-configuration"></a>五部電腦群組組

下圖顯示適用于 5 台電腦的部署拓撲。 我們建議此拓撲適用于支援多達 135，000 個的 135，000 個管理用戶端的生產環境。

![5 台電腦部署拓撲。](images/mbam-5-computer.jpg)

在此組配置中，以下組配置中已安裝了 ：：

1.  修復和硬體資料庫已安裝在伺服器上。

2.  合規性與稽核資料庫及合規性與稽核報告會安裝在伺服器上。

3.  系統管理與監控伺服器功能會安裝在網路負載平衡與 NLB (伺服器) 伺服器上。

4.  在能夠修改群組原則物件的電腦上，會安裝一個可修改群組原則物件的電腦上。。

[如何在分散式伺服器上安裝及設定 MBAM](how-to-install-and-configure-mbam-on-distributed-servers-mbam-1.md)

[如何針對 MBAM 設定網路負載平衡](how-to-configure-network-load-balancing-for-mbam.md)

## <a name="other-resources-for-mbam-10-server-features-deployment"></a>適用于 IBMM 1.0 Server 功能部署的其他資源


[部署 MBAM 1.0](deploying-mbam-10.md)

 

 





