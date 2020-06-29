---
title: 設定叢集模式的 MED-V 伺服器
description: 設定叢集模式的 MED-V 伺服器
author: dansimp
ms.assetid: 41f0b2a3-4ce9-48e1-a6fb-4c13c4228515
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ddb7dd5af65d8a465c5c1884bb27a3027621bac1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811924"
---
# 設定叢集模式的 MED-V 伺服器


您可以在 [群集模式] 中設定 MED-V 伺服器。 在群集模式中，會使用兩個伺服器，並將兩個伺服器標示為共有的所有檔案都放在檔案系統上。 伺服器會從檔案系統存取檔案，而不是將檔案儲存在本機。

## <a href="" id="bkmk-howtoconfigurethemedvserverinclustermode"></a>


**若要在群集模式中設定 MED-V 伺服器**

1.  在其中一個伺服器上安裝並設定 MED-V。

2.  在所有伺服器都可以存取的中央位置建立共用網路。

3.  將 [ * &lt; InstallDir &gt; /Servers/ConfigurationServer* ] 資料夾的內容複寫到共用的網路上。

4.  在所有指定的伺服器上安裝 MED-V 伺服器。

5.  在共用的網路上，指派所有 MED-V 伺服器系統帳戶的完整存取權。

6.  在每個伺服器上，執行下列動作：

    1.  在* &lt; InstallDir &gt; /Servers/ServerConfiguration.xml*檔案中，將* &lt; StorePath &gt; *的值設為共用的網路路徑。

    2.  從原始伺服器將* &lt; InstsallDir &gt; /Servers/KeyPair.xml*檔案複製到所有的 med-v 伺服器。

    3.  重新開機 MED-V 服務。

**記事** 如果所有伺服器都有相同的本機設定（例如，偵聽埠、IIS server、管理許可權、報表資料庫等），則所有伺服器也都可以共用* &lt; InstallDir &gt; /Servers/ServerSettings.xml* 。

 

## 相關主題


[MED-V 基礎結構規劃和設計](med-v-infrastructure-planning-and-design.md)

 

 





