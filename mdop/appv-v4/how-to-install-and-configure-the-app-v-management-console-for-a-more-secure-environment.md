---
title: 如何安裝及設定 APP-V 管理主控台以用於更安全的環境
description: 如何安裝及設定 APP-V 管理主控台以用於更安全的環境
author: dansimp
ms.assetid: 9d89ef09-cdbf-48fc-99da-b24fc987ef8f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9887787d1e203410b5517439d897260305d7526e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801390"
---
# 如何安裝及設定 APP-V 管理主控台以用於更安全的環境


App V 管理主控台的預設安裝包含對安全通訊的支援。 當您第一次啟動或連線到其他 App-v Web 管理服務時，系統會針對每個連接設定每個管理主控台。 預設設定會在 TCP 埠443上使用 SSL。 如果伺服器上的埠號碼已修改，您可以變更埠號碼。 您可以使用下列程式，透過安全連線來連線到 App-v Web 管理服務。

**如何使用 SSL 連線連線到 App V 管理服務**

1.  啟動應用程式虛擬化管理主控台。

2.  在主控台的 [動作] 窗格中，按一下 [**設定**連線]。

3.  輸入**Web 服務主機名稱**，並確認已選取 [**使用安全**連線]。

    **重要** 在 Web 服務主機名稱中提供的名稱必須與憑證上的通用名稱相符，否則連線將會失敗。

     

4.  選取適當的登入認證，然後按一下 **[確定]**。

## 相關主題


[設定憑證以支援 APP-V Web 管理服務](configuring-certificates-to-support-the-app-v-web-management-service.md)

 

 





