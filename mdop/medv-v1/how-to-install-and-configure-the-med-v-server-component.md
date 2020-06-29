---
title: 如何安裝和設定 MED-V 伺服器元件
description: 如何安裝和設定 MED-V 伺服器元件
author: dansimp
ms.assetid: 2d3c5b15-df2c-4ab6-bf78-f47ef8ae7418
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4fb0cc5c9ffe76e987e316d0285f172dd0b76578
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812080"
---
# 如何安裝和設定 MED-V 伺服器元件


本節說明如何[安裝](#bkmk-howtoinstallthemedvserver)和[設定](#bkmk-howtoconfigurethemedvserver)med-v 伺服器。

## <a href="" id="bkmk-howtoinstallthemedvserver"></a>如何安裝 MED-V 伺服器


**若要安裝 MED-V 伺服器**

1.  安裝 MED-V Server .msi 封裝。

    會呼叫 MED-V Server .msi 封裝*MED-V\_Server\_x.msi*，其中 x 是版本號碼。

    例如， *MED-V\_Server\_1.0.65.msi*。

2.  出現**InstallShield 嚮導歡迎**畫面時，請按 **[下一步]**。

3.  在 [**授權合約**] 畫面上，閱讀 [授權合約]，按一下 **[我接受授權合約中的條款**]，然後按 **[下一步]**。

    [**目的地資料夾**] 畫面隨即出現，並顯示預設安裝資料夾。

    預設安裝資料夾為 *%Systemdrive%\\Program Files\\Microsoft Enterprise Desktop Virtualization\\*。

    -   若要變更要安裝 MED-V 的資料夾，請按一下 [**變更**]，然後流覽至現有的資料夾。

4.  按 **\[下一步\]**。

5.  在 [**準備好安裝程式**] 畫面中，按一下 [**安裝**]。

    MED-V 伺服器安裝隨即啟動。 這可能需要幾分鐘的時間，而且螢幕可能不會顯示文字。 在安裝期間，會出現幾個進度畫面。 如果出現訊息，請依照提供的指示進行。

6.  當 [ **InstallShield 嚮導完成]** 畫面出現時，請按一下 **[完成**] 以完成嚮導。

**注意**  
如果您是透過 Microsoft 遠端桌面安裝 MED-V 伺服器，請使用下列語法： **mstsc/admin**。確定您的 RDP 會話已定向至主機。



## <a href="" id="bkmk-howtoconfigurethemedvserver"></a>如何設定 MED-V 伺服器


下列伺服器設定可以設定：

-   [連線](#bkmk-configuringconnections)

-   [Images](#bkmk-configuringimages)

-   [權限](#bkmk-configuringpermissions)

-   [報告](#bkmk-configuringreports)

### <a href="" id="bkmk-configuringconnections"></a>設定連接

**若要設定連接**

1.  在 Windows [開始] 功能表上，選取 [**所有程式] &gt; med-v-v &gt; Med-v Server Configuration Manager**。

    **注意**  
    注意：如果您在伺服器安裝期間選取了 [**啟動 med-v-v Server Configuration Manager** ] 核取方塊，則在伺服器安裝完成後，med-v Server configuration manager 會自動啟動。



~~~
The MED-V Server Configuration Manager appears.
~~~

2. **在 [連線**] 索引標籤上，設定下列用戶端連線設定：

   -   **[啟用未加密的連線（HTTP），使用埠**]：選取此核取方塊，以使用指定的埠啟用未加密的連接。 在 [埠] 方塊中，輸入要接受未加密連線的伺服器埠（HTTP）。

   -   **[啟用加密連線（HTTPs），使用埠**]：選取此核取方塊以啟用使用指定埠的加密連線。 在 [埠] 方塊中，輸入要接受加密連線的伺服器埠（HTTPs）。

       Https 是一個選用的設定，可以設定以確保 MED-V 伺服器與 MED-V 用戶端之間的安全事務。 若要設定 HTTPs，您必須執行下列程式：

       -   在伺服器上設定證書。

       -   將伺服器憑證與使用 netsh 指定的埠建立關聯。 如需詳細資訊，請參閱下列內容：

           -   [超文字傳輸通訊協定（HTTP）的 Netsh 命令](https://go.microsoft.com/fwlink/?LinkId=183314)

           -   [操作方法：使用 SSL 憑證設定埠](https://go.microsoft.com/fwlink/?LinkID=183315)

           -   [操作方法：使用 SSL 憑證設定埠](https://msdn.microsoft.com/library/ms733791.aspx)

3. 按一下 \[確定\] ****。

### <a href="" id="bkmk-configuringimages"></a>配置影像

**若要設定影像**

1.  按一下 [**影像**] 索引標籤。

2.  設定下列影像管理設定：

    -   **Vm 目錄**：虛擬機器目錄（儲存影像的目錄）。 此欄位包含影像發佈伺服器上影像目錄的 UNC 路徑，該路徑應該可從 MED-V 伺服器存取。

    -   **VM URL**-儲存影像的伺服器位置。

3.  按一下 \[確定\] ****。

### <a href="" id="bkmk-configuringpermissions"></a>設定許可權

**若要設定許可權**

1.  按一下 [**許可權**] 索引標籤。

2.  提供可以登入的所有使用者清單。 若要將讀取和寫入權限套用至使用者，請選取使用者旁邊的核取方塊。 若要將唯讀許可權套用至使用者，請清除該核取方塊。

3.  若要新增網域使用者或群組，請按一下 [**新增**]。

    [**輸入使用者或組名**] 對話方塊隨即出現。

    1.  選取 [網域使用者] 或 [群組]，方法是執行下列其中一項操作：

        -   在 [**輸入使用者或組名**] 欄位中，輸入網域中的使用者或群組，或以本機使用者或群組的形式存在於電腦上。 然後按一下 [**檢查名稱**]，將它解析成完整的名稱。

        -   按一下 [**尋找**] 以開啟 [標準**選取使用者或群組**] 對話方塊。 然後選取 [網域使用者] 或 [群組]。

    2.  按一下 \[確定\] ****。

4.  若要移除網域使用者或群組，請選取使用者或群組，然後按一下 [**移除**]。

5.  按一下 \[確定\] ****。

### <a href="" id="bkmk-configuringreports"></a>配置報表

**若要設定報表**

1.  按一下 [**報告**] 索引標籤。

2.  若要支援報表，請選取 [**啟用報表**]。

3.  在 [**連接字串**] 方塊中，輸入 MSSQL 資料庫的連線字串。

    -   在遠端伺服器上安裝 SQL Server 時，請使用下列連接字串：

        `Data Source=<ServerName>;Initial Catalog=<DBName>;uid=sa;pwd=<Password>;`

        **注意**  
        注意：若要連接至 SQL Express，請使用： `Data Source=<ServerName>\sqlexpress.`



4.  若要建立資料庫，請按一下 [**建立資料庫**]。

5.  若要測試連線，請按一下 [**測試**連線]。

6.  若要設定資料庫清除選項，請按一下 [**清除選項**]。

    [**清除資料庫選項**] 對話方塊隨即出現。

    1.  選擇下列其中一個選項：

        -   **清除較舊的資料**：清除超過指定天數的所有資料。在 [數值] 方塊中，輸入天數。

        -   **清除資料庫中的所有資料**—清除資料庫中所有現有的資料。

        -   [**刪除資料庫**]：刪除資料庫。

    2.  按一下 **[確定]** 以套用變更並關閉對話方塊。

7.  按一下 **[確定]** 儲存變更，或按一下 [**取消**] 關閉對話方塊，不儲存變更。

8.  如果出現提示，請重新開機 MED-V 伺服器服務，以將變更套用至網路設定。

## 相關主題


[支援的設定](supported-configurationsmedv-orientation.md)

[設計 MED-V 伺服器基礎結構](design-the-med-v-server-infrastructure.md)









