---
title: Application Virtualization 伺服器的疑難排解資訊
description: Application Virtualization 伺服器的疑難排解資訊
author: dansimp
ms.assetid: e9d43d9b-84f2-4d1b-bb90-a13740151e0c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7c98ad42a00e20900263d0598822a6381e2df1ef
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800769"
---
# Application Virtualization 伺服器的疑難排解資訊


本主題包含一些資訊，您可以用來針對應用程式虛擬化（App-v）伺服器上的各種問題進行疑難排解。

## 安裝伺服器後，在安裝程式記錄中出現警告訊息25017


安裝之後，您可能會在伺服器安裝程式記錄中找到下列訊息。

*警告25017。 安裝程式無法為伺服器建立 Active Directory 標記物件。 用於安裝的帳戶沒有足夠的許可權寫入 Active Directory 或 Active Directory 無法使用。*

App-V 管理或流式伺服器安裝程式會在 Active Directory 網域服務（新增）中的電腦物件底下建立服務連接點專案，而如果用來執行安裝程式的帳戶具有適當的許可權，就會在安裝伺服器的電腦上建立對應。 無法建立此專案，不會導致安裝失敗，而且應該不會影響產品的運作。 發生任何失敗的可能原因是，用來執行安裝的使用者帳戶沒有足夠的許可權來寫入。 雖然在新增中註冊 app-v server 是選擇性的，但這樣做有一個優點，就能讓集中式管理工具找到適用于庫存與管理目的的 App-v 伺服器。

## 相關主題


[Application Virtualization 伺服器](application-virtualization-server.md)

 

 





