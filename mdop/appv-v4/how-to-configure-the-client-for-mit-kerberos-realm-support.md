---
title: 如何設定用戶端以支援 MIT Kerberos 領域
description: 如何設定用戶端以支援 MIT Kerberos 領域
author: dansimp
ms.assetid: 46102f4c-270c-4115-8eb4-7ff5ae3be32d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ae5cd73d00f340bc50070fdd0a5fd3e038cc3789
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801566"
---
# 如何設定用戶端以支援 MIT Kerberos 領域


在應用程式虛擬化（App-v） 4.5 SP1 中，針對 MIT Kerberos 領域新增了支援。 本主題提供如何啟用該支援的詳細資訊。

**若要啟用 MIT Kerberos 領域支援**

-   建立名為 DWORD 類型**UseMitKerberos**的新登錄機碼，如下所示，然後將它設定為1的值。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\UseMitKerberos

 

 





