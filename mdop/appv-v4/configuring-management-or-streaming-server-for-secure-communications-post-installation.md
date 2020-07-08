---
title: 設定管理或串流伺服器以供安裝後續安全通訊
description: 設定管理或串流伺服器以供安裝後續安全通訊
author: dansimp
ms.assetid: 1062a213-470b-4ae2-b12f-b3e28a6ab745
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2a2713f130809c431b7444f3e928a523838597a6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809020"
---
# 設定管理或串流伺服器以供安裝後續安全通訊


如果在安裝應用程式 V 管理伺服器或 App-v 流式處理伺服器之前未預配過適當的憑證，App-v 可以設定為在初始安裝之後加強安全性。 您可以透過應用程式 V 管理主控台來設定 App-v 管理伺服器。 不過，App-v 流式處理伺服器是透過登錄來管理。 不論是哪一種情況，憑證都必須包含正確的伺服器驗證*擴展金鑰用法*（EKU），而且網路服務必須擁有私密金鑰的讀取存取權。

## 本節內容


<a href="" id="how-to-configure-management-server-security-post-installation"></a>[如何設定安裝後續管理伺服器安全性](how-to-configure-management-server-security-post-installation.md)  
提供可使用 App-v 管理主控台執行安裝後的程式，以新增憑證並設定 App-v Management Server 以增強安全性。

<a href="" id="how-to-configure-streaming-server-security-post-installation"></a>[如何設定安裝後續串流伺服器安全性](how-to-configure-streaming-server-security-post-installation.md)  
提供可在安裝後執行的程式，以新增憑證並設定 App-v 資料流程伺服器以增強安全性。

<a href="" id="troubleshooting-certificate-permission-issues"></a>[疑難排解憑證權限問題](troubleshooting-certificate-permission-issues.md)  
提供針對網路服務的適當 ACL 沒有設定私密金鑰的疑難排解指南。

 

 





