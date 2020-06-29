---
title: 設定分散式環境的 App-V 系統管理
description: 設定分散式環境的 App-V 系統管理
author: dansimp
ms.assetid: 53971fa9-8319-435c-be74-c37feb9af1da
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c1a638d6afde9270859c8aa98fc9f421c39cfc72
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809039"
---
# 設定分散式環境的 App-V 系統管理


針對您的特定組織設計基礎結構時，您可以在安裝 App-v Management Server 的電腦以外的電腦上安裝 App-v Management Web 服務。 分隔這些 App V 元件的常見原因包括下列各項：

-   效能

-   可靠性

-   可用性

-   延展性

若要將管理伺服器與管理 Web 服務分開，需要基礎結構的其他配置才能正常運作。 當您將這兩個功能分開，但沒有完成本主題中所述的程式時，系統會將管理主控台連線至管理 Web 服務，但無法正確驗證資料存放區。 系統不會正確載入管理主控台，而且管理員將無法完成任何管理作業。

之所以會發生此行為，是因為管理 Web 服務無法使用從管理主控台傳給它的認證來存取資料存放區。 解決方案是將管理 Web 服務伺服器設定為「信任委派」。

## 正在設定 Active Directory 網域服務


您也必須設定 Active Directory 網域服務，才能正確地在分散式環境中運作。 本節包含您設定 Active Directory 網域服務所需的資訊。

### SQL 服務使用本機系統帳戶時

若要設定 SQL 服務使用本機系統帳戶的環境，請將管理 Web 服務的電腦帳戶的屬性變更為信任委派。 如需如何執行此動作的詳細程式，請參閱[如何將伺服器設定為信任委派](how-to-configure-the-server-to-be-trusted-for-delegation.md)

### SQL 服務使用網域帳戶時

若要設定 SQL Server 使用網域服務帳戶的環境，您必須考慮是否要套用各種不同的因素，包括下列各項：

-   SQL Server 群集

-   複寫

-   自動化工作

-   連結伺服器

如需在 SQL 服務使用網域帳戶時設定 Active Directory 網域服務的相關資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkId=151968> 。

 

 





