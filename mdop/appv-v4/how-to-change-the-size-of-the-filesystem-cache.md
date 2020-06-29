---
title: 如何變更 FileSystem 快取的大小
description: 如何變更 FileSystem 快取的大小
author: dansimp
ms.assetid: 6ed17ba3-293b-4482-b3fa-31e5f606dad6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d63c98d53ccb31e8eb64bc70d3d79b2198c506e2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801642"
---
# 如何變更 FileSystem 快取的大小


您可以使用命令列來變更 FileSystem 快取的大小。 此動作需要完整的快取重設，且需要管理許可權。

**變更 FileSystem 快取的大小**

1.  將下列登錄值設定為0（零）：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\State

2.  將下列登錄值設定為包含套件所需的大小上限（以 MB 為單位），例如，8192 MB：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\FileSize

3.  重新開機電腦。

## 相關主題


[如何使用命令列設定 App-V 用戶端登錄設定](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





