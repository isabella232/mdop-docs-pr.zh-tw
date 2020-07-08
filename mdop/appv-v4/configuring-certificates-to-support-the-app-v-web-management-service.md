---
title: 設定憑證以支援 APP-V Web 管理服務
description: 設定憑證以支援 APP-V Web 管理服務
author: dansimp
ms.assetid: b7960161-2c19-4cbf-a98a-d4b06f547dce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 23839e6fad79c1f10eb2416941396ad3c6f04d26
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809026"
---
# 設定憑證以支援 APP-V Web 管理服務


App-v Web 管理服務必須設定為支援以 SSL 為基礎的連線，以協助保護通訊。 這個程式要求安裝管理服務的 Web 服務器或電腦已將憑證頒發給服務或電腦。

下列案例說明如何取得憑證以達到此目的：

1.  公司基礎結構已經有一個將憑證自動頒發給電腦的公開金鑰基礎結構（PKI）。

2.  公司基礎結構已經有一個 PKI，雖然它不會自動將憑證頒發給電腦。

3.  公司基礎結構沒有正確的 PKI。

在上述每個案例中，取得憑證的方法會有所不同，但最終結果是一樣的。 系統管理員必須將憑證指派給 IIS 預設的網站，並將 App-V Web 管理服務設定為需要安全通訊。

**重要** 憑證名必須符合伺服器的名稱。 最佳做法是針對憑證的通用名稱使用完整的功能變數名稱（Fqdn）。

 

App-v 可以使用 IIS 伺服器來支援不同的基礎結構配置。 如需有關設定 IIS 伺服器以支援 HTTPS 的詳細資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkId=151972> 。

## 相關主題


[如何安裝及設定 APP-V 管理主控台以用於更安全的環境](how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment.md)

 

 





