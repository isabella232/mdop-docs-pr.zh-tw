---
title: 如何測試應用程式發佈
description: 如何測試應用程式發佈
author: dansimp
ms.assetid: 17ba2e12-50a0-4f41-8300-f61f09db9f6c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 8dffb4f79ac89c7d419b27640f4f05364bd69e5d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812039"
---
# 如何測試應用程式發佈


在您第一次設定完成測試之後，您可以執行下列工作，以驗證應用程式發佈功能是否如期運作。

<a href="" id="bkmk-apppub"></a>**測試應用程式發佈**

1.  確認您指定要發佈的應用程式是可見的。

    按一下 [**開始**]，然後按一下 [**所有程式**]，然後搜尋指定的應用程式。

    在某些情況下，您可能會安裝兩次相同的應用程式，一次是在主機電腦上，一次是在訪客上。 如果發佈的應用程式具有相同的名稱，發佈到主機 [**開始**] 功能表上的同一個位置，則會將虛擬機器名稱新增至快捷方式名稱，以區別主機應用程式快捷方式。 例如，對於名為 "MEDVHost1" 的虛擬機器，主機應用程式可能會是 "Notepad"，而已發佈的應用程式可能是 "Notepad （MEDVHost1）"。

2.  確認應用程式正常運作。

    在主機電腦上，啟動您發佈的應用程式，並確認它們已在來賓上的 Windows XP SP3 中開啟。 應用程式必須出現在主機電腦桌面上的 Windows XP 樣式視窗中。

3.  如果適用，請確認檔重新導向正常運作。

    如果來賓上已發佈的應用程式必須開啟主機系統磁碟機上的資料夾，請確定它可以開啟指定的資料夾。

    **重要** 因為 Windows Virtual 電腦不支援從已共用的資料夾建立共用，所以從共用資料夾開啟的任何檔（例如位於網路上的 [我的文件] 資料夾），都不會發生重新導向。 如需詳細資訊，請參閱[操作疑難排解](operations-troubleshooting-medv2.md)。

確認已發佈的應用程式安裝正常且正常運作之後，您可以測試是否可以在 MED-V 工作區中新增或移除應用程式。

**測試是否可以新增或移除應用程式**

1.  從 MED-V 工作區新增或移除應用程式。

    如需如何從 MED-V 工作區新增及移除應用程式的相關資訊，請參閱[管理部署至 Med-v 工作區的應用程式](managing-applications-deployed-to-med-v-workspaces.md)。

2.  如果您新增了應用程式，請重複上述步驟，[以測試應用程式發佈](#bkmk-apppub)，以確認新的應用程式正常運作。

3.  如果您移除應用程式，請按一下 [**開始**]，然後按一下 [**所有程式**]，確認您移除的任何應用程式都已不再列出。

**記事** 如果您在驗證應用程式發佈設定時遇到任何問題，請參閱[操作疑難排解](operations-troubleshooting-medv2.md)。

測試完應用程式發佈之後，您可以測試其他的 MED-V 工作區設定，以確認其正常運作。

完成您的 MED-V 工作區套件測試並確認它已正常運作之後，您就可以將 MED-V 工作區部署到您的企業。

## 相關主題

[如何測試 URL 重新導向](how-to-test-url-redirection.md)

[如何驗證第一次安裝設定](how-to-verify-first-time-setup-settings.md)

[部署 MED-V 工作區套件](deploying-the-med-v-workspace-package.md)

 

 





