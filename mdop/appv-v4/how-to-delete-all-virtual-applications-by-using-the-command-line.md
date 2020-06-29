---
title: 如何使用命令列刪除所有虛擬應用程式
description: 如何使用命令列刪除所有虛擬應用程式
author: dansimp
ms.assetid: bfe13b5c-825a-4eb1-a979-6c4b8d8b2a9c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 55c809df31fa5c19f2f1a56c143d492b092156c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801457"
---
# 如何使用命令列刪除所有虛擬應用程式


您可以使用下列程式來刪除特定電腦中的所有虛擬應用程式。

**記事** 從套件中刪除所有應用程式時，應用程式虛擬化（App-v）用戶端也會刪除套件。

 

**刪除所有應用程式**

-   執行下列命令，以刪除執行命令之使用者帳戶的所有應用程式。 如果您使用具有管理許可權的帳戶來執行命令與選用的/GLOBAL 開關，所有的使用者都會刪除所有的應用程式。

    `SFTMIME DELETE OBJ:APP [/GLOBAL]`

    **記事** 從套件中刪除所有應用程式時，應用程式虛擬化（App-v）用戶端也會刪除套件。

     

## 相關主題


[如何使用命令列新增封裝](how-to-add-a-package-by-using-the-command-line.md)

[如何使用命令列來移除封裝](how-to-remove-a-package-by-using-the-command-line.md)

 

 





