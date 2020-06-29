---
title: 設定記錄和追蹤
description: 設定記錄和追蹤
author: dansimp
ms.assetid: 419231f9-e9db-4f91-a7cf-a0a73db25256
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa3dfa71edb25f6641ade595cd4469e846410ac2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802030"
---
# 設定記錄和追蹤


您可以使用系統管理範本來集中設定 [高級群組原則管理（AGPM）] 的 [選用記錄] 和 [追蹤]。

具有 AGPM 系統管理員（完全控制）角色的使用者帳戶、在這些程式中建立 GPO 所使用的核准者使用者帳戶，或是必須具備高級群組原則管理中所需許可權的使用者帳戶才能完成這些程式。 此外，必須擁有 AGPM 服務器存取權的使用者帳戶才能在 AGPM 服務器上開機記錄。 請參閱本主題中的「其他注意事項」中的詳細資料。

**設定 AGPM 的記錄和追蹤功能**

1.  在 [**群組原則管理] 主控台**樹狀結構中，針對您要開啟記錄和追蹤的所有群組原則管理員，編輯已套用的 GPO。 （如需詳細資訊，請參閱[編輯 GPO](editing-a-gpo.md)）。

2.  在 [**群組原則物件編輯器**] 中，按一下 [電腦設定]、[**系統****管理範本**] 和 [ **Windows 元件**]。

3.  如果 [ **Windows 元件**] 下並未列出 [ **AGPM** ]：

    1.  以滑鼠右鍵按一下 [**管理範本**]，然後按一下 [**新增/移除範本**]。

    2.  按一下 [**新增**]，選取 [ **agpm** ] 或 [ **agpm] .adm**，按一下 [**開啟**]，然後按一下 [**關閉**]。

4.  在 [ **Windows 元件**] 底下，按兩下 [ **AGPM**]。

5.  在 [詳細資料] 窗格中，按兩下 [ **AGPM 記錄**]。

6.  在 [ **AGPM 記錄屬性**] 視窗中，按一下 [**啟用**]，然後設定記錄中要記錄的詳細資料層級。

7.  按一下 \[確定\] ****。

8.  關閉 [**群組原則物件編輯器**]。 （如需詳細資訊，請參閱[部署 GPO](deploy-a-gpo.md)）。更新群組原則之後，您必須重新開機 AGPM 服務，才能在 AGPM 服務器上開始記錄。 群組原則管理員必須關閉並重新啟動 GPMC，才能開始記錄其電腦。

    **追蹤檔案位置**：

    -   用戶端：%LocalAppData%\\Microsoft\\AGPM\\agpm.log

    -   伺服器：%ProgramData%\\Microsoft\\AGPM\\agpmserv.log

### 其他考量

-   您必須能夠編輯和部署 GPO，才能設定 AGPM 記錄和追蹤功能。 如需更多詳細資料，請參閱[編輯 gpo](editing-a-gpo.md)及[部署 gpo](deploy-a-gpo.md) 。

### 其他參考資料

-   [執行 AGPM 系統管理員工作](performing-agpm-administrator-tasks.md)

 

 





