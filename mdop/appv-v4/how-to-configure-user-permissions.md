---
title: 如何設定使用者權限
description: 如何設定使用者權限
author: dansimp
ms.assetid: 54e69f46-b028-4ad1-9b80-f06ef5c8f559
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 3c2581a9f9dddcbc63682d356c777a24222dd62f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801534"
---
# 如何設定使用者權限


您可以在**許可權**登錄機碼（HKEY _LOCAL \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\client\\permissions）底下編輯金鑰值，為沒有系統管理許可權的使用者啟用和停用某些動作。 此金鑰主要是用來協助避免使用者由於具有管理許可權的使用者可以編輯這些金鑰值，而不是為了提供任何特殊安全性而進行錯誤。 下列程式是如何變更鍵值的範例。 如需應用程式虛擬化（App-v）用戶端登錄機碼和值的詳細資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkId=121528> 。

**變更使用者許可權**

1.  若要讓使用者選擇以離線模式執行用戶端，請將下列鍵值設定為1：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Permissions\\ToggleOfflineMode

2.  若要讓使用者能夠透過使用者介面查看所有應用程式，請將下列金鑰值設定為1。 將此值設定為0（零）後，就可以讓使用者只看到可供他們使用的應用程式。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Permissions\\ViewAllApplications

## 相關主題


[如何使用命令列設定 App-V 用戶端登錄設定](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

[Application Virtualization Client 中的使用者存取權限](user-access-permissions-in-application-virtualization-client.md)

 

 





