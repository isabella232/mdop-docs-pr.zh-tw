---
title: 如何重設 FileSystem 快取
description: 如何重設 FileSystem 快取
author: dansimp
ms.assetid: 7777259d-8c21-4c06-9384-9599b69f9828
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 680634d98f8aac048af605c62029a0ee6b20af03
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801126"
---
# 如何重設 FileSystem 快取


重設 FileSystem 快取並不是通常應該需要的操作。 不過，如果您需要完全重設 FileSystem 快取，可能是出於疑難排解目的，您可以使用下列程式。 需要系統管理許可權才能執行此動作。

**重設 FileSystem 快取**

1.  將下列登錄值設定為0（零）：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\State

2.  重新開機電腦。

## 相關主題


[如何使用命令列設定 App-V 用戶端登錄設定](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





