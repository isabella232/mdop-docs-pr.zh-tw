---
title: 如何測試 URL 重新導向
description: 如何測試 URL 重新導向
author: dansimp
ms.assetid: 38d80088-da1d-4098-b27e-76f9e78f81dc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: d964cf9d0114d3085d7e8952eebc82486b7b76cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810562"
---
# 如何測試 URL 重新導向


在您第一次設定完成測試之後，您可以執行下列工作，以驗證 URL 重新導向功能是否如期運作。

**重要** MED-V 主機代理程式必須執行，URL 重新導向才能正常運作。

<a href="" id="bkmk-urlredir"></a>**測試 URL 重新導向**

1.  在主機電腦中開啟 Internet Explorer 瀏覽器，然後輸入您指定要重新導向的 URL。

2.  確認網頁已在來賓虛擬機器上的 Internet Explorer 中開啟。

3.  針對您要測試的每個 URL，重複此程式。

**若要測試可以新增或移除 URL**

1.  從 MED-V 工作區新增或移除 URL。

    如需有關如何在 MED-V 工作區上新增和移除重新導向 Url 的相關資訊，請參閱[管理 med-v-v URL](manage-med-v-url-redirection.md)重新導向。

2.  如果您已在重新導向清單中新增 URL，請重複上述步驟[來測試 URL](#bkmk-urlredir)重新導向，以確認新的 URL 會以預期方式重新導向。

3.  如果您從 [重新導向] 清單中移除 URL，請遵循下列步驟，確認已移除 URL：

    1.  在主機電腦中開啟 Internet Explorer 瀏覽器，然後輸入您從重新導向清單中移除的 URL。

    2.  確認網頁已在主機電腦上的 Internet Explorer 中開啟，而不是在來賓虛擬機器上開啟。

        **記事** 可能需要幾秒鐘的時間，URL 重新導向變更才會發生。

**記事** 如果您在驗證 URL 重新導向設定時遇到任何問題，請參閱[操作疑難排解](operations-troubleshooting-medv2.md)。

在 MED-V 工作區中測試完 URL 重新導向之後，您可以測試其他設定，以驗證它們正常運作。

完成您的 MED-V 工作區套件測試並確認它已正常運作之後，您就可以將 MED-V 工作區部署到您的企業。

## 相關主題

[如何測試應用程式發佈](how-to-test-application-publishing.md)

[如何驗證第一次安裝設定](how-to-verify-first-time-setup-settings.md)

[部署 MED-V 工作區套件](deploying-the-med-v-workspace-package.md)

 

 





