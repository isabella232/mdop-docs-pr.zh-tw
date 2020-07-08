---
title: 如何設定部署套件
description: 如何設定部署套件
author: dansimp
ms.assetid: 748272a1-6af2-476e-a3f1-87435b8e94b1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aba5e91a4da92f9e51a5ccc70502658ae724d76f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811462"
---
# 如何設定部署套件


打包嚮導會在您的本機電腦上建立資料夾，並將所有必要的安裝檔案傳輸到單一資料夾，以引導您完成套件的建立。 然後，您可以將資料夾的內容移至多個卸除式媒體磁碟機以進行發佈。

**注意**  
單一套件不能包含 x86 和 x64 系統的安裝檔。



## 如何建立部署套件


**建立部署套件**

1. 在**影像**模組中確認您已建立至少一個本機打包的影像。

2. 在 [**工具**] 功能表上，選取 [**打包嚮導]**。

3. 在 [**打包嚮導]** 歡迎頁面上，按一下 **[下一步]**。

4. 在 [**工作區圖像**] 頁面上，選取 [在**套件中包含影像**] 核取方塊，以在套件中包含影像。

   [**影像**] 欄位已啟用。

   **注意**  
   在 MED-V 套件中不需要影像;您可以建立不含影像的套件。 在這種情況下，應該將影像上傳到伺服器，以便稍後透過網路將它下載到用戶端，或是將它推入影像的暫存資料夾。



5. 按一下**影像**清單，即可查看所有可用的影像。 選取要複製到套件的影像。 按一下 **[** 重新整理] 以重新整理可用影像的清單。

6. 按 **\[下一步\]**。

7. 在 [ **Med-v 安裝設定**] 頁面上，執行下列其中一項來選取 med-v 安裝檔：

   -   在 [ **med-v 安裝**檔案] 欄位中，輸入安裝檔案所在目錄的完整路徑。

   -   按一下 [ **...** ] 以流覽至安裝檔案所在的目錄。

   **注意**  
   此欄位是強制性的，而且在沒有有效檔案名的情況下，嚮導將無法繼續。



8. 在 [ **server address] （伺服器位址**）欄位中，輸入伺服器名稱或 IP 位址。

9. 在 [ **server port] （伺服器埠**）欄位中，輸入伺服器埠。

10. 選取 [**使用 HTTPs 存取伺服器**] 核取方塊，即可需要 HTTPs 連線才能連線到伺服器。

11. 執行下列其中一項：

    -   按一下 [**預設安裝設定**]，然後按一下 **[下一步]** 繼續並保留預設設定。

    -   按一下 [**自訂安裝設定**]，然後按一下 **[下一步]** 以自訂安裝設定。

        1.  在 [ **Med-v 安裝自訂設定**] 頁面上的 [**安裝資料夾**] 欄位中，輸入將在主機電腦上安裝 med-v 檔案的資料夾路徑。

            **注意**  
            建議您在路徑中使用變數，而不是常數，這可能會與電腦有所不同。

            例如，使用 *%ProgramFiles%\\MED-V*而不是*c:\\MED-V*。



    ~~~
    2.  In the **Virtual machines images folder** field, type the path of the folder where the virtual images files will be installed on the host computer.

        **Note**  
        If you are using image pre-staging, this is the image pre-stage folder where the image is located.



    3.  In the **Minimal required RAM** field, enter the RAM required to install a MED-V package. If the user installing the MED-V package does not have the minimal required RAM, the installation will fail.

    4.  Select the **Install the MED-V management application** check box to include the MED-V management console application in the installation.

    5.  Select the **Create a shortcut to MED-V on the desktop** check box to create a shortcut to MED-V on the host's desktop.

    6.  Select the **Start automatically on computer startup** check box to start MED-V automatically on startup.

    7.  Click **Next**.
    ~~~

12. 在 [**其他安裝**] 頁面上，選取 [**包括虛擬化軟體的安裝**] 核取方塊，以包含套件中的虛擬電腦安裝。

    [**安裝檔**] 欄位已啟用。 輸入虛擬化軟體安裝檔案的完整路徑，或按一下 [ **...** ] 以流覽至該目錄。

13. 選取 [**包括虛擬電腦 QFE 的安裝**] 核取方塊，以包含套件中的虛擬電腦更新安裝。

    [**安裝檔**] 欄位已啟用。 輸入虛擬電腦更新安裝檔案的完整路徑，或按一下 [ **...** ] 以流覽至該目錄。

14. 選取 [**包括安裝 microsoft .Net framework 2.0** ] 核取方塊，以將 Microsoft .net framework 2.0 安裝包含在套件中。

    [**安裝檔**] 欄位已啟用。 輸入 Microsoft .NET Framework 2.0 安裝檔案的完整路徑，或按一下 [ **...** ] 以流覽至該目錄。

15. 按 **\[下一步\]**。

16. 在 [**完成**] 頁面上，請執行下列其中一項動作，選取要儲存套件的位置：

    -   在 [**套件目的地**] 欄位中，輸入要儲存套件的目錄完整路徑。

    -   按一下 [ **...** ] 以流覽至要儲存安裝盤案的目錄。

    **注意**  
    建立套件可能會佔用比實際套件大小更多的空間。 因此，建議您在硬碟上建立套件。 建立套件之後，就可以將它複製到 USB。



17. 在 [**套件名稱**] 欄位中，輸入套件的名稱。

18. 按一下 **[完成]** 來建立套件。

    套件即建立完畢。 這可能需要幾分鐘的時間。

    建立套件之後，會出現一則訊息，通知您已成功完成。

**注意**  
如果您在本機儲存了所有檔案，而不是直接在移除的媒體上儲存，請確定您只將資料夾內容（而非資料夾本身）複製到卸除式媒體中。



**注意**  
卸除式媒體的大小必須足夠大，才能讓套件內容只佔用最多三個季度的卸除式媒體記憶體。



**注意**  
建立套件時，在完成組建後，可能需要最多兩倍的實際套件大小。



## 相關主題


[建立 MED-V 映像](creating-a-med-v-image.md)









