---
title: 如何在相同電腦上部署 App-V 4.6 和 App-V 5.0 用戶端
description: 如何在相同電腦上部署 App-V 4.6 和 App-V 5.0 用戶端
ms.assetid: 5b7e27e4-4360-464c-b832-f1c7939e5485
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.date: 06/21/2016
ms.prod: w10
ms.openlocfilehash: f10f3d159c4724f3b486215b1169825bb029316d
ms.sourcegitcommit: 0132cd232b9c030820d95d91b71c4def0184400a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/19/2021
ms.locfileid: "11907226"
---
# <a name="how-to-deploy-the-app-v-46-and-the-app-v-50-client-on-the-same-computer"></a>如何在相同電腦上部署 App-V 4.6 和 App-V 5.0 用戶端

**注意：** App-V 4.6 已退出主流支援。 下列假設已安裝 App-V 4.6 SP3 用戶端。

請使用下列資訊在同一部電腦上安裝 App-V 5.0 用戶端 (最好使用最新的 Service Pack 和 hotfix) 和 App-V 4.6 SP3 用戶端。 有關支援的版本、需求及其他規劃資訊，請參閱規劃從先前版本的 [App-V 移移](planning-for-migrating-from-a-previous-version-of-app-v.md)。

**在同一部電腦上部署 App-V 5.0 用戶端和 App-V 4.6 用戶端**

1.  在執行 App-V 4.6 版本的用戶端電腦上安裝 App-V 5.0 SP3 用戶端。 為了獲得最佳結果，建議您將所有可用的更新安裝到 App-V 5.0 SP3 用戶端。

2.  逐漸轉換或重新排序套件。

    -   若要轉換套件，請使用 App-V 5.0 套件轉換程式，並將所需的套件轉換為 App-V 5.0 (**.appv**) 檔案格式。

    -   若要重新排序套件，請考慮使用最新版本的 Sequencer 以獲得最佳結果。

    若要進一步瞭解如何發佈套件，請參閱如何使用管理主控台 [發佈套件](how-to-publish-a-package-by-using-the-management-console-50.md)。

3.  將套件部署到用戶端電腦。

4.  依需要轉換延伸點。 如需詳細資訊，請參閱下列資源：

    -   [如何為特定電腦上的所有使用者，將擴充點從 App-V 4.6 封裝移轉至轉換的 App-V 5.0 封裝](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)

    -   [如何為特定使用者，將擴充點從 App-V 4.6 封裝移轉至 App-V 5.0](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md)

    -   [如何轉換在舊版 App-V 中建立的套件](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md)

5.  測試您的 App-V 5.0 套件是否成功，然後移除 4.6 套件。 若要檢查用戶端電腦的使用者狀態，建議您使用使用者體驗 [虛擬化](https://technet.microsoft.com/library/dn458947.aspx) 或其他使用者環境管理工具。

    **有 App-V 的建議嗎**？ 在這裡新增或投票支援 [建議](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)。 **有 App-V 問題嗎？** 使用 [App-V TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## <a name="related-topics"></a>相關主題


[規劃從舊版 App-V 移轉](planning-for-migrating-from-a-previous-version-of-app-v.md)

[部署 App-V 5.0 排序器和用戶端](deploying-the-app-v-50-sequencer-and-client.md)

 

 





