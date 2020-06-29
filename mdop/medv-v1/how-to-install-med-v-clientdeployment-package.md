---
title: 如何安裝 MED-V 用戶端
description: 如何安裝 MED-V 用戶端
author: dansimp
ms.assetid: bfac6de7-d96d-4b3e-bd8b-183e051e53c8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b2e4468b15c0c196bf605b1b5d129ab38678ec74
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812207"
---
# 如何安裝 MED-V 用戶端


在部署套件的案例中，MED-V 用戶端安裝包含在部署套件中，並直接從套件安裝。

**重要**  
使用不含影像的部署套件時，請務必先將影像上傳至網路，或是將它推到前階段資料夾，然後再安裝部署套件。



**若要安裝部署套件**

1.  執行下列其中一項：

    -   從網路下載 MED-V 套件。

    -   將部署 USB 或 DVD 插入主機磁片磁碟機。

2.  如果 MED-V 沒有自動啟動，請按兩下 [MED-VAutoInstaller.exe]。

    隨即會出現一個對話方塊，其中列出已安裝的元件，以及目前正在安裝的元件。

    **注意**  
    如果主機電腦上存在不支援的 Microsoft 虛擬電腦版本，則會顯示一則訊息，告訴您要卸載現有版本並再次執行安裝程式。



~~~
**Note**  
If an older version of the MED-V client exists, it will prompt you asking whether you want to upgrade.



Depending on the components that have been installed, you might need to reboot. If rebooting is necessary, a message appears notifying you that you must reboot.
~~~

3. 如有需要，請重新開機電腦。

   安裝完成後，MED-V 隨即啟動，並出現一則訊息，通知您安裝已完成。

4. 使用下列使用者名稱和密碼登入 MED-V：

   -   輸入網功能變數名稱稱和使用者名稱，後面接著允許在 MED-V 中使用之網域使用者的密碼。

       範例：「網域 \ _name \\user\ _name "，" password "

## 相關主題


[如何設定部署套件](how-to-configure-a-deployment-package.md)

[如何上傳 MED-V 映像至伺服器](how-to-upload-a-med-v-image-to-the-server.md)

[用戶端安裝命令列參考資料](client-installation-command-line-reference.md)









