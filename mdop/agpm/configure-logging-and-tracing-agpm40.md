---
title: 設定記錄和追蹤
description: 設定記錄和追蹤
author: dansimp
ms.assetid: 2418cb6a-7189-4080-8fe2-9c8d47dec62c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bfc56d418ae83cbc5db24246bfac057305629df7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802029"
---
# 設定記錄和追蹤


您可以使用 [系統管理範本] 來集中設定選用記錄和追蹤。 在診斷任何與高級群組原則管理（AGPM）相關的問題時，這可能會很有説明。

具有 AGPM 系統管理員（完全控制）角色的使用者帳戶、在這些程式中建立群組原則物件（GPO）的核准者使用者帳戶，或是在 AGPM 中有必要許可權的使用者帳戶完成這些程式。 此外，必須擁有 AGPM 服務器存取權的使用者帳戶才能在 AGPM 服務器上開機記錄。 請參閱本主題中的「其他注意事項」中的詳細資料。

**設定 AGPM 的記錄和追蹤功能**

1.  在 [**群組原則管理] 主控台**樹狀結構中，針對您要開啟記錄和追蹤的所有群組原則管理員，編輯已套用的 GPO。 （如需詳細資訊，請參閱[編輯 GPO](editing-a-gpo-agpm40.md)）。

2.  按一下 [**群組原則管理編輯器**] 視窗中的 [**電腦**設定]、[**原則**]、[系統**管理範本**]、[ **Windows 元件**] 和 [ **AGPM**]

3.  在 [詳細資料] 窗格中，按兩下 [ **AGPM：設定記錄**]。

4.  在 [**屬性**] 視窗中，按一下 [**啟用**]，然後設定記錄中要記錄的詳細資料層級。

5.  按一下 \[確定\] ****。

6.  關閉 [**群組原則管理編輯器**] 視窗。 （如需詳細資訊，請參閱[部署 GPO](deploy-a-gpo-agpm40.md)）。更新群組原則之後，您必須重新開機 AGPM 服務，才能啟動、修改或停止 AGPM 服務器上的記錄。 群組原則管理員必須關閉並重新啟動 GPMC，才能啟動、修改或停止在他們的電腦上記錄。

    **追蹤檔案位置**：

    -   用戶端：%LocalAppData%\\Microsoft\\AGPM\\agpm.log

    -   伺服器：%ProgramData%\\Microsoft\\AGPM\\agpmserv.log

### 其他考量

-   您必須能夠編輯和部署 GPO，才能設定 AGPM 記錄和追蹤功能。 如需更多詳細資料，請參閱[編輯 gpo](editing-a-gpo-agpm40.md)及[部署 gpo](deploy-a-gpo-agpm40.md) 。

### 其他參考資料

-   [設定進階群組原則管理](configuring-advanced-group-policy-management-agpm40.md)

 

 





