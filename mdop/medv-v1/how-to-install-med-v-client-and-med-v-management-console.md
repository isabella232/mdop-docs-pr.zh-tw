---
title: 如何安裝 MED-V 用戶端及 MED-V 管理主控台
description: 如何安裝 MED-V 用戶端及 MED-V 管理主控台
author: dansimp
ms.assetid: 8a5f3010-3a50-487e-99d8-e352e5cb51c6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 24a486cc7cf5534171f80b08dc93742e03cd4a0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812081"
---
# 如何安裝 MED-V 用戶端及 MED-V 管理主控台


用戶端 .msi 套件包含下列 MED-V 元件：

-   MED-V 用戶端：必須在用戶端電腦上安裝 MED-V-V 工作區的 MED-V 軟體。

-   MED-V 管理主控台-系統管理員可用來建立及維護影像、MED-V 工作區及原則的管理工具。

MED-V 管理主控台和 MED-V 用戶端都是從 MED-V 用戶端的 .msi 套件進行安裝。 不過，您可以在安裝期間清除 [**安裝 Med-v 管理應用程式**] 核取方塊，以在沒有 med-v 管理主控台的情況下獨立安裝 med-v 用戶端。

**注意**  
MED-V 用戶端和 MED-V 管理主控台只能安裝在 Windows 7、Windows Vista 和 Windows XP 的電腦上。 無法在伺服器產品上安裝它們。



**注意**  
請勿使用 Windows **runas**命令安裝 med-v 用戶端。



**安裝 MED-V 用戶端**

1.  以擁有本機系統管理員許可權的使用者身分登入本機電腦。

2.  執行 MED-V 封裝。

    會呼叫 MED-V 封裝*MED-V\_x.msi*，其中*x*是版本號碼。

    例如， *MED-V\_1.0.65.msi*。

3.  出現**InstallShield 嚮導歡迎**畫面時，請按 **[下一步]**。

4.  在 [**授權合約**] 畫面上，閱讀 [授權合約]，按一下 [**我接受授權合約中的條款**]，然後按 **[下一步]**。

    [**目的地資料夾**] 畫面隨即出現，並顯示預設安裝資料夾。

    預設的 [安裝] 資料夾是安裝作業系統的目錄。

    -   若要變更要安裝 MED-V 的資料夾，請按一下 [**變更**]，然後流覽至現有的資料夾。

5.  按 **\[下一步\]**。

6.  在**med-v [設定**] 畫面上，設定 med-v 安裝，如下所示：

    -   選取 [**安裝 med-v 管理應用程式**] 核取方塊，以在安裝中包含管理元件。

        **注意**  
        企業桌面虛擬化管理員應該安裝 MED-V 管理應用程式。 這個應用程式是設定桌面影像和 MED-V 工作區所必需的。



~~~
-   Select the **Load MED-V when Windows starts** check box to start MED-V automatically on startup.

-   Select the **Add a MED-V shortcut to my desktop** check box to create a MED-V shortcut on your desktop.

-   In the **Server address** field, type the server address.

-   In the **Server port** field, type the server's port.

-   Select the **Server requires encrypted connections (https)** check box to work with https.

-   The default virtual machine images folder is displayed. The default installation folder is *%systemdrive%\\MED-V Images\\*. To change the folder where MED-V should be installed, click **Change**, and browse to an existing folder.
~~~

7. 按 **\[下一步\]**。

8. 在 [**準備好安裝程式**] 畫面中，按一下 [**安裝**]。

   MED-V 用戶端安裝隨即啟動。 這可能需要幾分鐘的時間，而且螢幕可能不會顯示文字。 在安裝期間，會出現幾個進度畫面。 如果出現訊息，請依照提供的指示進行。

   成功安裝後，就會出現 [ **InstallShield 嚮導完成]** 畫面。

9. 按一下 **[完成**] 以關閉嚮導。

## 相關主題


[支援的設定](supported-configurationsmedv-orientation.md)

[安裝和升級檢查清單](installation-and-upgrade-checklists.md)









