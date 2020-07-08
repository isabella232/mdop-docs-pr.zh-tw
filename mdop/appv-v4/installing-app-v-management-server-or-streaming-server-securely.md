---
title: 安全地安裝 App-V Management Server 或 Streaming Server
description: 安全地安裝 App-V Management Server 或 Streaming Server
author: dansimp
ms.assetid: d2a51a81-a80f-427c-a727-611e1eb74f02
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0150f4dc7f489731c4a818fed9780ebb25dbd24f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800997"
---
# 安全地安裝 App-V Management Server 或 Streaming Server


本節中的主題提供安裝應用程式 V 管理伺服器或 App-v 流式處理伺服器的增強安全版本的相關資訊。

**記事** 安裝或設定應用程式 V 管理或流式伺服器以使用增強的安全性（例如，傳輸層安全性或 TLS），需要將 x.509 V3 憑證預配至 App-v 伺服器。

 

當您準備安裝或設定安全管理或流式處理伺服器時，請考慮下列技術需求：

-   憑證必須是有效的。 如果憑證無效，用戶端就會結束連線。

-   憑證必須包含正確的*增強型金鑰用法*（EKU），即伺服器驗證（OID 1.3.6.1.5.5.7.3.1）。 如果憑證不包含此 EKU，用戶端就會結束連線。

-   證書的完整功能變數名稱（FQDN）必須與安裝它的伺服器相符。 例如，如果用戶端正在撥號， `RTSPS://Myserver.mycompany.com/content/MyApp.sft` 且 [**頒發給**] 欄位的 [頒發給] 欄位設定為 `Server1.mycompany.com` []，則用戶端將無法連線至伺服器，且會話結束。 該失敗會報告給使用者。

    **記事** 如果您是在網路負載平衡群集中使用 App-v，您必須使用 Subject 替代名稱（San）來設定憑證以支援 RTSPS。 如需有關設定憑證授權單位（CA）及使用 San 建立憑證的詳細資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkId=133228> 。

     

-   用戶端和伺服器需要根信任 CA，即向應用程式連線的 CA 必須受用戶端連線到伺服器的信任。 如果不是，用戶端會結束連線。

-   憑證的私人金鑰必須變更許可權，才能允許 App-v 服務帳戶存取證書。 根據預設，App-v 會使用網路服務帳戶，而且根據預設，網路服務帳戶不具有存取私密金鑰的許可權，這將會防止安全連線。

## 本節內容


<a href="" id="configuring-certificates-to-support-secure-streaming"></a>[支援憑證以支援安全串流](configuring-certificates-to-support-secure-streaming.md)  
提供有關取得、設定及安裝憑證以支援安全資料流程的資訊。

<a href="" id="how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server"></a>[如何修改私密金鑰權限以支援管理伺服器或串流伺服器](how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server.md)  
提供您可以用來在 Windows Server2003 和 Windows Server2008 中修改金鑰的程式。

<a href="" id="configuring-certificates-to-support-app-v-management-server-or-streaming-server"></a>[設定憑證以支援 APP-V Management Server 或 Streaming Server](configuring-certificates-to-support-app-v-management-server-or-streaming-server.md)  
提供有關針對 App V 管理或流式處理伺服器設定憑證的相關資訊，包括為網路負載平衡環境設定憑證的相關資訊。

 

 





