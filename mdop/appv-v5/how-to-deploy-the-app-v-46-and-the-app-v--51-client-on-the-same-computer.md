---
title: 如何在同一部電腦上部署 app-v 4.6 和 App-v 5.1 用戶端
description: 如何在同一部電腦上部署 app-v 4.6 和 App-v 5.1 用戶端
ms.assetid: 498d50c7-f13d-4fbb-8ea1-b959ade26fdf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 354db96223e623a7cd0416cb49ad67eb4d8f7162
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800527"
---
# 如何在同一部電腦上部署 app-v 4.6 和 App-v 5.1 用戶端

**注意：** App-V 4.6 已退出主流支援。

使用下列資訊來安裝 Microsoft Application Virtualization （App-v）5.1 用戶端（最好是使用最新的 Service Pack 和熱修復程式），以及在同一部電腦上使用 app-v 4.6 SP2 用戶端或應用程式 V 4.6 S3 用戶端。 如需支援的版本、需求及其他規劃資訊，請參閱[規劃從繼承應用程式遷移（V](planning-for-migrating-from-a-previous-version-of-app-v51.md)）。

**在同一部電腦上部署 app-v 5.1 用戶端和 App-v 4.6 用戶端**

1.  在執行 App-v 4.6 的電腦上，安裝下列版本的 App-v 用戶端。

    -   [Microsoft Application Virtualization 4.6 Service Pack 3](https://www.microsoft.com/download/details.aspx?id=41187)

2.  在執行 App-V 4.6 SP3 版本用戶端的電腦上，安裝 app-v 5.1 用戶端。 為了獲得最佳結果，建議您將所有可用的更新安裝到 App-v 5.1 用戶端。

3.  逐步轉換或重新排列套件。

    -   若要轉換套件，請使用 App-v 5.1 套件轉換器，並將所需的套件轉換成 App-v 5.1 （**appv**）檔案格式。

    -   若要重新排列套件，請考慮使用最新版本的 Sequencer 來取得最佳結果。

    如需發佈套件的詳細資訊，請參閱[如何使用管理主控台發佈套件](how-to-publish-a-package-by-using-the-management-console-51.md)。

4.  將套件部署到用戶端電腦。

5.  視需要轉換延伸點。 如需詳細資訊，請參閱下列資源：

    -   [如何為特定電腦上的所有使用者，將擴充點從 App-V 4.6 封裝移轉至轉換的 App-V 5.1 封裝](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-51-package-for-all-users-on-a-specific-computer.md)

    -   [如何為特定使用者，將擴充點從 App-V 4.6 封裝移轉至 App-V 5.1](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md)

    -   [如何轉換在舊版 App-V 中建立的套件](how-to-convert-a-package-created-in-a-previous-version-of-app-v51.md)

6.  測試您的 App-v 5.1 套件是否成功，然後移除4.6 套件。 若要檢查用戶端電腦的使用者狀態，建議您使用[使用者體驗虛擬化](https://technet.microsoft.com/library/dn458947.aspx)或其他使用者環境管理工具。

    您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[規劃從舊版 App-V 移轉](planning-for-migrating-from-a-previous-version-of-app-v51.md)

[部署 App-V 5.1 排序器和用戶端](deploying-the-app-v-51-sequencer-and-client.md)

 

 





