---
title: 疑難排解憑證權限問題
description: 疑難排解憑證權限問題
author: dansimp
ms.assetid: 06b8cbbc-93fd-44aa-af39-2d780792d3c3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 728c35b9f51c8f2e18db8acd63708c70bb5d3100
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800773"
---
# 疑難排解憑證權限問題


安裝 App-v 4.5 之後，如果尚未針對網路服務的適當 ACL 設定私密金鑰，則會在 NT 事件記錄檔中記錄一個事件，並在檔案中放入一個專案 `Sft-server.log` 。

## 錯誤訊息


### Windows Server2003

事件識別碼 36870-嘗試存取 SSL 伺服器認證私密金鑰時發生致命錯誤。 從加密模組傳回的錯誤碼是0x80090016。

### Windows Server2008

事件識別碼 36870-嘗試存取 SSL 伺服器認證私密金鑰時發生致命錯誤。 從加密模組傳回的錯誤碼是0x8009030d。

## Sft-server 記錄


下列錯誤會放在 `sft-server.log` 位於目錄中的檔案中 `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\logs` ：

無法載入憑證。 錯誤碼 \ [-2146893043 \]。 確認 [網路服務] 帳戶具有正確的憑證存取權和其對應的私密金鑰檔案。

 

 





