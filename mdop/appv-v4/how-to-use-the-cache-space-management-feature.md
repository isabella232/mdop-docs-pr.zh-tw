---
title: 如何使用快取空間管理功能
description: 如何使用快取空間管理功能
author: dansimp
ms.assetid: 60965660-c015-46a8-88ac-54cbc050fe33
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fcb9cc4bc076e1acf52fb1c03797384c45b82f7b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801013"
---
# 如何使用快取空間管理功能


FileSystem 快取空間管理功能使用最新使用的（LRU）演算法，且預設為啟用。 如果新套件所需的空間超過快取中的可用空間，應用程式虛擬化（App-v）用戶端會使用這項功能來判斷它可以從快取中刪除的現有套件（如果有的話），為新套件騰出空間。 用戶端會刪除最舊的最近存取日期的套件（如果它比 MinPkgAge 註冊表值中指定的值還舊）。 使用 [FileSystem 快取空間管理] 功能也可協助避免較低的快取空間問題。

如有需要，則會刪除一個以上的套件。 鎖定的套件不會被刪除。

**記事** 若要確保快取已為所有已部署套件指派足夠的空間，請使用設定用戶端時使用的 [**可用磁碟空間閾值**] 設定，讓快取視需要增加。 或者，您可以在安裝期間預先決定需要多少磁碟空間，並在安裝時設定快取大小。

 

[快取空間管理] 功能是由 UnloadLeastRecentlyUsed 登錄值所控制。 如果值為1，則會啟用此功能，而值0（零）則會停用它。

**啟用或停用緩衝空間管理功能**

-   將下列登錄值設定為1，以啟用 LRU 演算法。 將它設定為0（零）以停用此功能。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\UnloadLeastRecentlyUsed

**控制可放棄哪些套件**

-   若要判斷何時可以選取要捨棄的套件，請將下列登錄值設為等於自上次存取套件後所要經過的最小天數。 您最近使用的套件將不會遭到捨棄。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\MinPkgAge

    **小心** 此登錄機碼的最大值為0x00011111。 較大的值會使快取磁片管理功能的操作無法正常運作。

     

## 相關主題


[如何使用命令列設定 App-V 用戶端登錄設定](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





