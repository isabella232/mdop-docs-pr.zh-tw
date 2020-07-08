---
title: MBAM 2.0 系統管理員角色規劃
description: MBAM 2.0 系統管理員角色規劃
author: dansimp
ms.assetid: 6f813297-6479-42d3-a21b-896d54466b5b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a89a04c0ef074407dc3cd081d351d44023e65e70
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810827"
---
# MBAM 2.0 系統管理員角色規劃


本主題列出並說明 Microsoft BitLocker 管理和監控（MBAM）中可用的系統管理員角色，以及建立本機群組的伺服器位置。

## MBAM 管理員角色


<a href="" id="---------------mbam-system-administrators"></a> **MBAM 系統管理員**  
此角色的管理員可以存取所有 Microsoft BitLocker 管理和監控功能。 此角色的本機群組已安裝在管理和監視伺服器上。

<a href="" id="---------------mbam-helpdesk-users"></a> **MBAM 支援人員的使用者**  
此角色的管理員可從 MBAM 存取技術支援人員的功能。 此角色的本機群組已安裝在管理和監視伺服器上。

<a href="" id="---------------mbam-report-users"></a> **MBAM 報表使用者**  
此角色的管理員可以存取 MBAM 的合規性和審核報告。 此角色的本機群組已安裝在管理和監控伺服器、合規性與審核資料庫，以及託管合規性與審核報告的伺服器上。

<a href="" id="---------------mbam-advanced-helpdesk-users"></a> **MBAM 高級支援人員的使用者**  
此角色的系統管理員已增加從 MBAM 存取服務台功能的許可權。 此角色的本機群組已安裝在管理和監視伺服器上。 如果使用者是 MBAM 技術支援人員的成員，且 MBAM 高級技術支援人員的使用者，則 MBAM [高級技術支援人員] 的許可權會覆寫 MBAM 的 [支援人員] 使用者許可權。

**重要** 若要查看報表，系統管理使用者必須是管理和監控伺服器、合規性和審核資料庫，以及託管合規性和審核報告功能之伺服器上的**MBAM Report 使用者**安全性群組的成員。 最佳做法是在 Active Directory 網域服務中使用本機**MBAM 報表**上的許可權，在管理與監視伺服器以及託管合規性和審核報告的伺服器上，建立具有許可權的使用者安全性群組。

 

## 相關主題


[MBAM 2.0 的環境準備](preparing-your-environment-for-mbam-20-mbam-2.md)

 

 





