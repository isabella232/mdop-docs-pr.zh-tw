---
title: 如何設定網域使用者或群組
description: 如何設定網域使用者或群組
author: dansimp
ms.assetid: 055aba81-a9c9-4b98-969d-775e603becf3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c51da13808df657c1341572767c24860d9d5e8b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812212"
---
# 如何設定網域使用者或群組


部署設定可讓您控制哪些使用者或群組可以存取 MED-V 工作區，以及可以使用 MED-V 工作區的時間長度，以及它是否可離線使用。 您也可以設定其他規則來控制 MED-V 工作區與主機之間的存取。

所有的 MED-V 工作區許可權都在 [**部署**] 索引標籤上的 [**原則**] 模組中設定。

若要允許使用者使用 MED-V 工作區，您必須先將網域使用者或群組新增至 MED-V 工作區許可權。 接著，您可以為每個使用者或群組設定許可權。

## 如何新增網域使用者或群組


**新增網域使用者或群組**

1.  在 [**使用者/群組**] 視窗中，按一下 [**新增]。**

2.  在 [**輸入使用者或組名**] 對話方塊中，執行下列其中一項動作，選取 [網域使用者] 或 [群組]：

    -   在 [**輸入使用者或組名**] 欄位中，輸入網域或電腦上的本機使用者或群組中存在的使用者或群組。 然後按一下 [**檢查名稱**]，將它解析成完整的名稱。

    -   按一下 [**尋找**] 以開啟 [標準**選取使用者或群組**] 對話方塊。 然後選取 [網域使用者] 或 [群組]。

3.  按一下 \[確定\] ****。

    新增網域使用者或群組。

    **注意**  
    信任網域中的使用者應該手動新增。



~~~
**Warning**  
Do not run the management application from a computer that is part of a domain that is not trusted by the domain the server is installed on.
~~~



## 如何移除網域使用者或群組


**移除網域使用者或群組**

1.  在 [**使用者/群組**] 視窗中，選取一個使用者或群組。

2.  按一下 [**移除**]。

    已刪除使用者或群組。

## 如何設定使用者或群組的許可權


**若要設定使用者或群組的許可權**

1.  按一下您要設定許可權的使用者或群組。

2.  按照下表所述，設定 MED-V 工作區屬性。

3.  在 [**原則**] 功能表上，選取 [**確認**]。

**工作區部署屬性**

*一般*屬性描述

啟用 &lt; 使用者或群組的工作區&gt;

選取此核取方塊以啟用此使用者或群組的 MED-V 工作區。

工作區在此日期到期

選取此核取方塊，為此使用者或群組指派許可權集的到期日。

選取此選項時，即會啟用 [日期] 方塊。 設定日期和許可權會在指定日期結束時到期。

[離線工作] 限制為

選取此核取方塊，指派必須針對此使用者或群組重新整理原則的時段。 選取此選項時，即會啟用 [時間週期] 方塊。 設定天數或小時數，並在指定的時間期限結束時，如果原則沒有重新整理，使用者或群組就無法連線。

工作區刪除選項

按一下以設定 MED-V 工作區刪除選項。 如需詳細資訊，請參閱[如何設定 Med-v 工作區刪除選項](how-to-set-med-v-workspace-deletion-options.md)。

*資料傳輸*

在主機和工作區之間支援剪貼簿

選取此核取方塊可在主機與 MED-V 工作區之間啟用複製與貼上。

主機與工作區之間的支援檔案傳輸

選取此核取方塊以啟用在 host 與 MED-V 工作區之間傳輸檔案。 從 [檔案**傳輸**] 方塊中選取下列其中一個選項：

-   **兩者皆**可讓您在主機和 med-v 工作區之間傳送檔案。

-   **主機至工作區**-可讓您從主機傳送檔案至 med-v 工作區。

-   **主機工作區**-啟用從 med-v 工作區傳送檔案至主機。

**注意**  
如果沒有許可權的使用者嘗試傳輸檔案，系統會顯示一個視窗，提示他輸入擁有執行檔案傳輸許可權的使用者認證。



**重要**  
若要在 Windows XP SP3 中支援檔案傳輸，您必須透過編輯登錄來停用離線檔案同步處理，如下所示：

`REG ADD HKLM\software\microsoft\windows\currentversion\netcache /V Enabled /T REG_DWORD /F /D 0`



進階

按一下以設定高級檔案傳輸選項。 如需詳細資訊，請參閱[如何設定高級檔案傳輸選項](how-to-set-advanced-file-transfer-options.md)。

*裝置控制*

啟用列印至連線至主機的印表機

選取此核取方塊可讓使用者使用主機印表機從 MED-V 工作區列印。

**注意**  
列印是由主機上定義的印表機所執行。



啟用 CD/DVD 存取

選取此核取方塊以允許從這個 MED-V 工作區存取 CD 或 DVD 光碟機。



**多個成員資格**

1.  如果使用者是群組的一部分，且許可權會套用至使用者以及其所屬的群組，則會套用擁有權限。

2.  如果使用者是兩個不同群組的成員，則會套用限制性最低的許可權。

## 相關主題


[使用 MED-V 管理主控台使用者介面](using-the-med-v-management-console-user-interface.md)

[建立 MED-V 工作區](creating-a-med-v-workspacemedv-10-sp1.md)

[如何設定 MED-V 工作區刪除選項](how-to-set-med-v-workspace-deletion-options.md)

[如何設定進階檔案傳輸選項](how-to-set-advanced-file-transfer-options.md)









