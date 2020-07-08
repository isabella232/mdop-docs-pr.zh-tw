---
title: 如何建立限時復原映像
description: 如何建立限時復原映像
author: dansimp
ms.assetid: d2e29cac-c24c-4239-997f-0320b8a830ae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a11891753f80d41f0089311771b906865950337c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800142"
---
# 如何建立限時復原映像


您可以建立一個只能在產生特定天數後使用的 DaRT 恢復影像。 若要這樣做，您必須在命令提示字元執行**DaRT 復原映射嚮導**，並指定天數。

**建立具有時間限制的復原影像**

1.  使用系統管理員認證開啟命令提示字元。

2.  將目錄變更為 ERDC.exe 程式的位置。

3.  使用下列語法，執行 DaRT 復原**影像嚮導**。 *Numberofdays 後*是一個正整數，代表 DaRT 復原影像可使用的天數。

    ``` syntax
    ERDC /e NumberOfDays
    ```

## 相關主題


[建立 DaRT 7.0 復原映像](creating-the-dart-70-recovery-image-dart-7.md)

 

 





