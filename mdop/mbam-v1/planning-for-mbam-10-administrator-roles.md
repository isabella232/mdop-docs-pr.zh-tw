---
title: MBAM 1.0 系統管理員角色規劃
description: MBAM 1.0 系統管理員角色規劃
author: dansimp
ms.assetid: 95be0eb4-25e9-43ca-a8e7-27373d35544d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 104d650824330ea990881c520a7811511f496dd1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811426"
---
# MBAM 1.0 系統管理員角色規劃


本主題包含並說明 Microsoft BitLocker 管理和監控（MBAM）中可用的系統管理員角色，以及建立本機群組的伺服器位置。

## MBAM 管理員角色


<a href="" id="---------------mbam-system-administrators"></a> **MBAM 系統管理員**  
這個角色的管理員可以存取所有的 MBAM 功能。 此角色的本機群組已安裝在管理和監視伺服器上。

<a href="" id="---------------mbam-hardware-users"></a> **MBAM 硬體使用者**  
此角色的系統管理員可以存取 MBAM 中的硬體功能功能。 此角色的本機群組已安裝在管理和監視伺服器上。

<a href="" id="---------------mbam-helpdesk-users"></a> **MBAM 支援人員的使用者**  
此角色的系統管理員可從 MBAM 存取技術支援人員的功能。 此角色的本機群組已安裝在管理和監視伺服器上。

<a href="" id="---------------mbam--report-users"></a> **MBAM 報表使用者**  
此角色的管理員可從 MBAM 存取合規性和審核報告功能。 此角色的本機群組已安裝在管理和監控伺服器、合規性與審核資料庫，以及託管合規性與審核報告的伺服器上。

<a href="" id="---------------mbam--advanced-helpdesk-users"></a> **MBAM 高級支援人員的使用者**  
此角色的系統管理員已提升從 MBAM 到技術支援人員功能的存取權。 此角色的本機群組已安裝在管理和監視伺服器上。 如果使用者是 MBAM 技術支援人員的成員，且 MBAM 高級技術支援人員的使用者，則 MBAM [高級技術支援人員] 的許可權會覆寫 MBAM 的 [支援人員] 使用者許可權。

**重要** 若要查看報表，系統管理使用者必須是 [管理與監控伺服器]、[合規性] 和 [審核資料庫] 中的**MBAM 報表使用者**安全性群組成員，以及託管合規性與報告功能的伺服器。 最佳做法是在 Active Directory 中建立一個安全性群組，並在 [管理] 和 [監視] 伺服器以及託管合規性與報告的伺服器上，以許可權在 [管理員] 和 [監視] 伺服器上的 [**使用者**安全性群組] 中建立。

 

## 相關主題


[MBAM 1.0 的環境準備](preparing-your-environment-for-mbam-10.md)

 

 





