---
title: 如何使用命令列設定 App-V 用戶端登錄設定
description: 如何使用命令列設定 App-V 用戶端登錄設定
author: dansimp
ms.assetid: 3e3d873f-13d2-402f-97b4-f62d0c399171
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c424f39c8209ca641f6073838ebcb8726acc9e25
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801601"
---
# 如何使用命令列設定 App-V 用戶端登錄設定


使用命令列在安裝期間部署並設定應用程式虛擬化（App-v）用戶端之後，可能需要變更一或多個用戶端設定。 如此一來，您可以使用下列其中一種方法編輯適當的登錄機碼來完成：

-   直接使用登錄編輯程式

-   使用 .reg 檔案

-   使用「VBScript」或「Windows PowerShell」等指令碼語言

您也可以使用 [ADM] 範本。 如需 ADM 範本的詳細資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkId=121835> 。

**小心** 當您編輯登錄時請小心，因為錯誤可能會使電腦處於無法使用的狀態。 請務必遵循與編輯註冊表有關的標準商務慣例。 在部署到生產電腦之前，請先在測試環境中徹底測試所有提議的變更。

 

## 本節內容


**重要** 在64位電腦上，下列各節中所述的金鑰和值將會位於 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\Client。

 

<a href="" id="how-to-reset-the-filesystem-cache"></a>[如何重設 FileSystem 快取](how-to-reset-the-filesystem-cache.md)  
提供重設 FileSystem 快取所需的資訊。

<a href="" id="how-to-change-the-size-of-the-filesystem-cache"></a>[如何變更 FileSystem 快取的大小](how-to-change-the-size-of-the-filesystem-cache.md)  
說明如何變更快取的大小。

<a href="" id="how-to-use-the-cache-space-management-feature"></a>[如何使用快取空間管理功能](how-to-use-the-cache-space-management-feature.md)  
說明如何設定快取空間管理功能。

<a href="" id="how-to-configure-the-client-log-file"></a>[如何設定用戶端記錄檔](how-to-configure-the-client-log-file.md)  
描述控制用戶端記錄檔的各種登錄專案值，以及您可以如何變更它們。

<a href="" id="how-to-configure-user-permissions"></a>[如何設定使用者權限](how-to-configure-user-permissions.md)  
識別控制使用者許可權的登錄機碼，並提供如何變更某些許可權的範例。

<a href="" id="how-to-configure-the-client-for-application-package-retrieval"></a>[如何設定應用程式封裝擷取的用戶端](how-to-configure-the-client-for-application-package-retrieval.md)  
說明如何將用戶端設定為從不同來源中檢索套件內容、圖示及檔案類型關聯，並提供幾個正確路徑格式的範例。

<a href="" id="how-to-configure-the-client-for-disconnected-operation-mode"></a>[如何設定中斷連線的操作模式的用戶端](how-to-configure-the-client-for-disconnected-operation-mode.md)  
提供有關如何設定與中斷式作業模式相關聯之各種設定的資訊。

<a href="" id="how-to-configure-shortcut-and-file-type-association-behavior"></a>[如何設定捷徑和檔案類型關聯行為](how-to-configure-shortcut-and-file-type-association-behavior-46-only.md)  
描述在 App-v 用戶端中控制快速鍵與檔案類型關聯的登錄項值，並提供如何進行設定的詳細資訊。

## 相關主題


[Application Virtualization Client](application-virtualization-client.md)

 

 





