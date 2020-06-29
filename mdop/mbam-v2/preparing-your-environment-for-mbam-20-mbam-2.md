---
title: MBAM 2.0 的環境準備
description: MBAM 2.0 的環境準備
author: dansimp
ms.assetid: 5fb01da9-620e-4992-9e54-2ed3fb69e6af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f1be989112d456064db302952d50159d00b5597a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811258"
---
# MBAM 2.0 的環境準備


開始進行 Microsoft BitLocker 管理與監控（MBAM）安裝之前，您應該確定您已滿足安裝產品的先決條件。 當您知道必備的先決條件之後，您就可以高效地部署產品並啟用其功能，讓它能更有效率地支援貴組織的業務目標。

如果您是使用 Microsoft System Center Configuration Manager 2007 或 MicrosoftSystemCenter2012 ConfigurationManager 部署 Microsoft BitLocker 管理和監視，請參閱[規劃以使用 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md)。

## 評審 MBAM 2.0 部署先決條件


MBAM 用戶端和每個 MBAM 伺服器功能都有特定的先決條件，必須先滿足才能成功安裝。

為了確保成功安裝 MBAM 用戶端和 MBAM 伺服器功能，請確定針對 MBAM 用戶端或 MBAM Server 功能安裝指定的電腦已正確準備好進行 MBAM 設定。

**記事** MBAM 安裝程式會在安裝開始前檢查是否已滿足所有先決條件。 如果不符合所有先決條件，安裝程式將會失敗。

 

[MBAM 2.0 部署必要條件](mbam-20-deployment-prerequisites-mbam-2.md)

## 規劃 MBAM 2.0 群組原則需求


在 MBAM 可以管理企業中的用戶端之前，您必須針對環境的加密需求定義群組原則。

**重要** MBAM 將無法與獨立的 BitLocker 磁片磁碟機加密原則搭配使用。 必須針對 MBAM 定義群組原則設定，否則 BitLocker 加密和強制執行將會失敗。

 

[MBAM 2.0 群組原則需求規劃](planning-for-mbam-20-group-policy-requirements-mbam-2.md)

## 規劃 MBAM 2.0 系統管理員角色


MBAM 系統管理員角色是由在您安裝 BitLocker 管理和監視伺服器、合規性和審核報告功能，以及合規性和審核狀態資料庫時，由 MBAM 安裝程式所建立的本機群組所管理。

您可以在 ActiveDirectoryDomainServices 中建立安全性群組，將適當的管理員帳戶新增至那些群組，然後將這些安全性群組新增至 BitLocker 管理和監視本機群組，以進行管理，以取得 Microsoft BitLocker 管理和監視角色的成員資格。 如需詳細資訊，請參閱[如何管理 MBAM 管理員角色](how-to-manage-mbam-administrator-roles-mbam-2.md)。

## MBAM 規劃的其他資源


[MBAM 2.0 規劃](planning-for-mbam-20-mbam-2.md)

[MBAM 2.0 支援的組態](mbam-20-supported-configurations-mbam-2.md)

 

 





