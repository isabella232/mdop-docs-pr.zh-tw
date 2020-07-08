---
title: App-V 4.6 SP3 版本資訊
description: App-V 4.6 SP3 版本資訊
author: dansimp
ms.assetid: 206fadeb-59cc-47b4-836f-191ab1c27ff8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: dd0b82c5e12cbe161066a7f4a4e0932cb92cca42
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802358"
---
# App-V 4.6 SP3 版本資訊


若要搜尋這些版本筆記，請按 CTRL + F。

安裝 Microsoft Application Virtualization （App-v）管理系統之前，請先閱讀這些版本資訊。 這些版本資訊包含可協助您成功安裝應用程式虛擬化（App-v） 4.6 SP3 的資訊。 此檔包含產品檔中不提供的資訊。 如果這些版本資訊與其他 App-v 檔之間有差異，最新變更應視為權威性。 這些版本資訊取代本產品隨附的內容。

## 防範安全性漏洞與病毒


若要協助防範安全性漏洞和病毒，請務必為任何要安裝的新軟體安裝最新的可用安全更新。 如需詳細資訊，請參閱[Microsoft 安全性網站](https://go.microsoft.com/fwlink/?LinkId=3482)（ https://go.microsoft.com/fwlink/?LinkId=3482) 。

## Application Virtualization 4.6 SP3 的已知問題


本節提供有關 Microsoft Application Virtualization （App-v） 4.6 SP3 之問題的最新資訊。 這些問題不會出現在產品檔中，某些情況下，可能會矛盾現有的產品檔。 如果可能的話，這些問題將會在稍後的版本中解決。

### 無法在虛擬環境中使用網際網路 Explorer11 在 Microsoft Windows 8.1 上開啟超連結

在使用 Internet Explorer 11 的 Windows 8.1 上，嘗試從虛擬環境中開啟超連結時，將會失敗。 這是因為 Internet Explorer 11 現已隨附預設啟用的增強保護模式（EPM），因此這會導致 App-v 無法存取必要的登錄機碼、檔案和通訊埠物件。

因應措施：在開啟 App-V 套件前，停用 [網際網路 Explorer11] 中的 EPM。 這可讓您從虛擬環境中開啟 Internet Explorer。

## 相關主題


[關於 Microsoft Application Virtualization 4.6 SP3](about-microsoft-application-virtualization-46-sp3.md)

 

 





