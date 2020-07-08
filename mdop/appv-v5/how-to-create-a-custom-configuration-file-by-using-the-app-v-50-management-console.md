---
title: 如何使用 App-V 5.0 Management Console 建立自訂設定檔案
description: 如何使用 App-V 5.0 Management Console 建立自訂設定檔案
author: dansimp
ms.assetid: 0d1f6768-be30-4682-8eeb-aa95918b24c3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d54e68caa380025b2ff6f3ea79d30f275b589b30
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800566"
---
# 如何使用 App-V 5.0 Management Console 建立自訂設定檔案


您可以使用動態設定來自訂特定使用者的 app-v 5.0 套件。 不過，您必須先建立動態使用者配置（.xml）檔案或動態部署設定檔，才能使用這些檔案。 建立檔案是一個高級的手動操作。 如需有關動態使用者設定檔的一般資訊，請參閱[關於 app-v 5.0 動態](about-app-v-50-dynamic-configuration.md)設定。

使用下列程式來建立使用 App-v 5.0 管理主控台的動態使用者設定檔。

**建立動態使用者設定檔**

1.  以滑鼠右鍵按一下您想要查看之套件的名稱，然後選取 [**編輯 active directory 存取**]，以查看指派給特定使用者群組的配置。 或者，選取套件，然後按一下 [**編輯**]。

2.  在**Ad 實體**清單中使用 Access，選取您要自訂的廣告群組。 從下拉式清單中選取 [**自訂**] （如果尚未選取）。 隨即會顯示名為 [**編輯**] 的連結。

3.  按一下**編輯**。 隨即會顯示已指派給 AD 群組的動態使用者設定。

4.  按一下 [**高級**]，然後按一下 [**匯出配置**]。 輸入檔案名，然後按一下 [**儲存**]。 現在，您可以編輯檔案，為使用者設定套件。

    您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[App-V 5.0 作業](operations-for-app-v-50.md)

 

 





