---
title: 應用程式虛擬化屬性 [一般] 索引標籤
description: 應用程式虛擬化屬性 [一般] 索引標籤
author: dansimp
ms.assetid: be7449d9-171a-4a11-9382-83b7008ccbdd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6ee00bfc7f70ee7b17da42aad61356540a7a0be0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802317"
---
# Application Virtualization 內容：一般索引標籤


使用 [**應用程式虛擬化屬性**] 對話方塊的 **[一般**] 索引標籤來修改記錄設定和資料位置。

此索引標籤包含下列元素。

<a href="" id="log-level"></a>**記錄層級**  
從下拉式清單中選取等級。 預設等級為 [**資訊**]。

<a href="" id="reset-log"></a>**重設記錄**  
按一下此按鈕以備份目前的記錄檔，並立即開始新的記錄檔。

<a href="" id="location"></a>**位置**  
輸入或流覽至您要儲存記錄檔 sftlog.txt 的位置。 預設位置如下所示：

-   針對 WindowsXP、Windows Server2003-*C:\\Documents 與 Settings\\All Users\\Application Data\\Microsoft\\Application Virtualization 用戶端*

-   Windows Vista、Windows 7、Windows Server2008-*C:\\ProgramData\\Microsoft\\Application Virtualization 用戶端*

<a href="" id="system-log-level"></a>**系統記錄層級**  
從下拉式清單中選取等級。 預設的層級為 [**警告**]。

**記事** **系統記錄層級**設定控制傳送至系統事件記錄條的訊息層級。 記錄的訊息與記錄在用戶端事件日誌中的訊息相同，但它們儲存在不同的位置，而不具備用戶端事件記錄的空間限制。 因為系統事件記錄檔沒有空間限制，所以特別適合在需要詳細記錄的情況下。

 

<a href="" id="global-data-directory"></a>**全域資料目錄**  
輸入或流覽至記錄檔目錄的位置。 預設位置如下所示：

-   針對 WindowsXP、Windows Server2003-*C:\\Documents 與 Settings\\All Users\\Application Data\\Microsoft\\Application Virtualization 用戶端*

-   Windows Vista、Windows 7、Windows Server2008-*C:\\ProgramData\\Microsoft\\Application Virtualization 用戶端*

<a href="" id="user-data-directory"></a>**使用者資料目錄**  
輸入或流覽至儲存使用者特定資料之目錄的位置。 預設值為% APPDATA%。 此路徑必須是用戶端電腦上的有效環境變數。

## 相關主題


[用戶端管理主控台：Application Virtualization 內容](client-management-console-application-virtualization-properties.md)

 

 





