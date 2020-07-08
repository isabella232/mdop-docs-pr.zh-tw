---
title: 如何修改私密金鑰權限以支援管理伺服器或串流伺服器
description: 如何修改私密金鑰權限以支援管理伺服器或串流伺服器
author: dansimp
ms.assetid: 1ebe86fa-0fbc-4512-aebc-0a5da991cd43
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2e35c2df518f22ba81a070d2c40ad3862f376a6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801253"
---
# 如何修改私密金鑰權限以支援管理伺服器或串流伺服器


若要支援更安全的 App-v 安裝，您可以使用下列程式來修改 Windows Server2003 或 Windows Server2008 中的私人金鑰。 若要修改私用金鑰的許可權，您可以使用 Windows Server2003 資源套件工具 `WinHttpCertCfg.exe` 。

針對 Windows Server2003，程式需要符合本檔所列先決條件的憑證，才會安裝在您要安裝 App V 管理或流式處理伺服器的電腦上。 您可以在使用此工具的其他相關資訊 `WinHttpCertCfg.exe` <https://go.microsoft.com/fwlink/?LinkId=151981> 。

在 Windows Server2008 中，變更私人金鑰上的 Acl 的程式會更簡單。 證書的使用者介面可用於管理私密金鑰許可權。

**記事** 預設的安全性內容是 [網路服務];不過，您可以改為使用網域帳戶。

 

**在 Windows Server2003 中管理私人金鑰**

1.  在將成為 App V 管理或流式處理伺服器的電腦上，于命令提示字元中輸入下列命令，以列出指派給特定憑證的目前許可權：

    `winhttpcertcfg -l -c LOCAL_MACHINE\My -s Name_of_cert`

2.  如有必要，請修改憑證的許可權，以便提供對將用於管理或流式處理服務之安全內容的讀取存取：

    `winhttpcertcfg -g -c LOCAL_MACHINE\My -s Name_of_cert -a NetworkService`

3.  列出憑證上的許可權，確認已正確新增安全性內容：

    `winhttpcertcfg –l –c LOCAL_MACHINE\My –s Name_of_cert`

**在 Windows Server2008 中管理私人金鑰**

1.  使用以*本機電腦*憑證存放的*憑證*管理單元來建立 MICROSOFT 管理主控台（MMC）。

2.  展開 MMC，然後選取 [**管理私人金鑰**]。

3.  在 [**安全性**] 索引標籤上，將 [**網路服務**] 帳戶新增為 [**讀取**存取]。

## 相關主題


[設定憑證以支援 APP-V Management Server 或 Streaming Server](configuring-certificates-to-support-app-v-management-server-or-streaming-server.md)

[支援憑證以支援安全串流](configuring-certificates-to-support-secure-streaming.md)

 

 





