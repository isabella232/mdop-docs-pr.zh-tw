---
title: 部署 MBAM 1.0 群組原則物件
description: 部署 MBAM 1.0 群組原則物件
author: dansimp
ms.assetid: 2129291e-d2b2-41ed-b643-1e311c49fee7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8d14123f1d5b197146e425cba063e8ce4c180641
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808624"
---
# 部署 MBAM 1.0 群組原則物件


若要成功部署 Microsoft BitLocker 管理和監控（MBAM），您必須先決定將在您的 MBAM 中使用的群組原則。 如需各種可用原則的詳細資訊，請參閱[規劃 MBAM 1.0 群組原則需求](planning-for-mbam-10-group-policy-requirements.md)。 當您決定要使用的原則之後，您必須使用 MBAM 1.0 群組原則範本來建立及部署一個或多個包含 MBAM 原則設定的群組原則物件（GPO）。

## 安裝 MBAM 1.0 群組原則範本


除了提供 MBAM 的伺服器相關功能之外，伺服器安裝應用程式還包含 MBAM 群組原則範本。 您可以在任何能夠執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）的電腦上安裝此範本。

[如何安裝 MBAM 1.0 群組原則範本](how-to-install-the-mbam-10-group-policy-template.md)

## 部署 MBAM 1.0 群組原則設定


在您建立必要的 Gpo 之後，您必須將 MBAM 群組原則設定部署到貴組織的用戶端電腦。

[如何編輯 MBAM 1.0 GPO 設定](how-to-edit-mbam-10-gpo-settings.md)

## 在 Windows 中顯示 [MBAM] 控制台


因為 MBAM 提供自訂的 MBAM 控制台，可以取代預設的 Windows BitLocker 控制台，您也可以選擇透過使用群組原則來隱藏使用者的預設 BitLocker 控制台。

[如何在 Windows 控制台中隱藏預設 BitLocker 加密](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel.md)

## 部署 MBAM 1.0 群組原則物件的其他資源


[部署 MBAM 1.0](deploying-mbam-10.md)

 

 





