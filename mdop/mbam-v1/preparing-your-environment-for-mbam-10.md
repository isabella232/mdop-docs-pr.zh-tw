---
title: MBAM 1.0 的環境準備
description: MBAM 1.0 的環境準備
author: dansimp
ms.assetid: 915f7c3c-70ad-4a90-a434-73e7fba97ecb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9a2de4e825d5c89aeabcf57d78dc856bacb03e11
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809807"
---
# MBAM 1.0 的環境準備


開始進行 Microsoft BitLocker 管理與監控（MBAM）安裝之前，請確定您已滿足安裝產品所需的先決條件。 如果您事先知道先決條件，您就可以高效地部署產品並啟用其功能，以便更有效率地支援貴組織的業務目標。

## 評審 MBAM 1.0 部署先決條件


MBAM 用戶端和每個 MBAM 伺服器功能都有特定的先決條件，必須先滿足才能成功安裝。

若要確保成功安裝 MBAM 用戶端和 MBAM 伺服器功能，您應該規劃確保針對 MBAM 用戶端或 MBAM Server 功能安裝所指定的電腦已正確準備好進行 MBAM 設定。

**記事** MBAM 安裝程式會在安裝開始前驗證是否已滿足所有先決條件。 如果不符合，安裝程式將會失敗。

 

[MBAM 1.0 部署必要條件](mbam-10-deployment-prerequisites.md)

## 規劃 MBAM 1.0 群組原則需求


在 MBAM 可以管理企業中的用戶端之前，您必須針對環境的加密需求定義群組原則。

**重要** MBAM 將無法與獨立的 BitLocker 磁片磁碟機加密原則搭配使用。 必須針對 MBAM 定義群群組原則;否則，BitLocker 加密和強制將會失敗。

 

[MBAM 1.0 群組原則需求規劃](planning-for-mbam-10-group-policy-requirements.md)

## 規劃 MBAM 1.0 系統管理員角色


MBAM 系統管理員角色是由在您安裝下列各項時由 MBAM 安裝程式所建立的本機群組所管理： BitLocker 管理與監視伺服器、合規性和審核報告功能，以及合規性與審核狀態資料庫。

如果您在 ActiveDirectoryDomainServices 中建立安全性群組，就能更有效地管理 MBAM 角色的成員資格，將適當的管理員帳戶新增到這些群組，然後將這些安全性群組新增至 MBAM 本機群組。 如需詳細資訊，請參閱[如何管理 MBAM 管理員角色](how-to-manage-mbam-administrator-roles-mbam-1.md)。

[MBAM 1.0 系統管理員角色規劃](planning-for-mbam-10-administrator-roles.md)

## MBAM 規劃的其他資源


[MBAM 1.0 規劃](planning-for-mbam-10.md)

 

 





