---
title: App-V 5.0 的版本資訊
description: App-V 5.0 的版本資訊
author: dansimp
ms.assetid: 68a6a5a1-4b3c-4c09-b00c-9ca4237695d5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e49f6072d738b45afe25de24f2ee9a2d09d64a2e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800314"
---
# App-V 5.0 的版本資訊


**若要在這些版本筆記中搜尋特定問題，請按 CTRL + F。**

安裝 App-v 5.0 之前，請先閱讀這些版本資訊。

這些版本資訊包含成功安裝 App-v 5.0 所需的資訊。 版本資訊中也包含產品檔中不提供的資訊。 如果這些版本資訊與其他 App-v 5.0 檔有差異，最新的變更應該視為權威性。 這些版本資訊取代本產品隨附的內容。

## 關於產品檔


如需 App-V 5.0 檔的相關資訊，請參閱 Microsoft TechNet 上的 app-v 5.0 首頁。

## 提供意見反應


我們對 App-v 5.0 的意見反應感興趣。 您可以將意見反應傳送給您 <mdopdocs@microsoft.com> 。

**記事** 此電子郵件地址不是支援頻道，但您的意見反應將協助我們規劃我們的檔和產品版本中的未來變更。

 

如需 MDOP 及其他學習資源的最新資訊，請參閱[Mdop 資訊體驗](https://go.microsoft.com/fwlink/p/?LinkId=236032)頁面。

如需新更新或提供意見反應的詳細資訊，請在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上關注我們。

## App-v 5.0 的已知問題


本節包含有關 App-V 5.0 已知問題的版本資訊。

### 使用伺服器 PowerShell Cmdlet 時無法終止新增套件

使用 PowerShell 新增套件時，沒有任何方法可結束新增套件。

因應措施：若要停止新增套件，請在新增最終套件後按**enter** 。

### <a href="" id="-------------app-v-5-0-client-rejects-packages-from-servers-whose-ssl-certificate-has-been-revoked"></a> App-V 5.0 用戶端拒絕從已吊銷 SSL 憑證的伺服器套件

使用 HTTPS 通訊協定時，App-v 5.0 用戶端預設會拒絕來自已吊銷 SSL 憑證的伺服器的套件。 您可以透過修改**VerifyCertificateRevocationList**設定，將此行為關閉。 將 App-v 5.0 服務重新開機之後，才會將此設定的新設定套用到應用程式。

解決方法：重新開機 App-v 5.0 服務。

## 版本資訊版權資訊


Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、MicrosoftIntune 和 WindowsPowerShell 是 Microsoft 公司群組的商標。 所有其他商標都是其各自擁有者的財產。








## 相關主題


[關於 App-V 5.0](about-app-v-50.md)

 

 





