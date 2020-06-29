---
title: 如何使用 App-V 封裝加速器建立虛擬應用程式套件
description: 如何使用 App-V 封裝加速器建立虛擬應用程式套件
author: dansimp
ms.assetid: eae1e4f8-f14f-4bc8-9867-052561c37297
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 15376ae52a19b2d220f9ea0031f3ad5649ca487d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800552"
---
# 如何使用 App-V 封裝加速器建立虛擬應用程式套件


**重要**  
App-v 5.1 Sequencer 不會授與您用來建立套件加速器之軟體應用程式的任何授權許可權。 您必須遵守您所使用之應用程式的所有使用者授權合約。 您有責任確認軟體應用程式的授權條款可讓您使用 App-v 5.1 排序器建立套件加速器。



使用下列程式來建立含有 App-v 5.1 套件加速器的虛擬應用程式套件。

**注意**  
開始此程式之前，請先將所需的套件加速器複製到執行 App-v 5.1 排序器的電腦上。 您也應該將套件的所有必要安裝檔案，複製到執行排序器的電腦上的本機目錄。 這是您必須在此程式步驟5中指定的目錄。



**若要使用 App-v 5.1 套件加速器建立虛擬應用程式套件**

1.  若要啟動 app-v 排序器，請在執行 app-v 5.1 排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  。**microsoft application virtualization**  /  **microsoft application virtualization 排序**器。

2.  若要啟動 [**建立新套件] 嚮導**，請按一下 [**建立新的虛擬應用程式套件**]。 若要建立套件，請選取 [**使用套件加速器建立套件**] 核取方塊，然後按一下 **[下一步]**。

3.  若要指定將用來建立新的虛擬應用程式套件的套件加速器，請在 [**選取套件加速器**] 頁面上按一下 **[流覽]** 。 按 **\[下一步\]**。

    **重要**  
    如果無法驗證套件加速器的發行者，且不包含有效的數位簽章，請在您按一下 [**執行**] 前，確認您是否信任套件加速器的來源。 在 [**安全性警告**] 對話方塊中確認您的選擇。



4.  在 [**指導**方針] 頁面上，查看 [資訊] 窗格中顯示的發佈指導資訊。 此資訊是在建立套件加速器時新增，且包含如何建立及發佈套件的相關指導方針。 若要將指南資訊匯出至文字（.txt）檔案，請按一下 [**匯出**] 並指定要儲存檔案的位置，然後按 **[下一步]**。

5.  在 [**選取安裝**檔案] 頁面上，按一下 [**建立新資料夾**]，以建立一個本機資料夾，其中包含套件所需的所有安裝檔案，並指定該資料夾的儲存位置。 您也必須指定要指派給資料夾的名稱。 接著，您必須將所有所需的安裝檔案複製到您指定的位置。 如果包含安裝檔的資料夾已經存在於執行排序器的電腦上，請按一下 **[流覽]** 以選取該資料夾。

    或者，如果您已將安裝檔案複製到此電腦上的目錄，請按一下 [**建立新資料夾**]，流覽到包含安裝檔案的資料夾，然後按 **[下一步]**。

    **注意**  
    您可以指定下列支援的安裝檔案類型：

    -   Windows Installer 檔案（**.msi**）

    -   Cabinet 檔案（.cab）

    -   副檔名為 .zip 的壓縮檔案

    -   實際的應用程式檔案

    下列檔案類型不受支援： **.msp**與 **.exe**檔案。 如果您指定 **.exe**檔案，您必須手動解壓縮安裝檔案。



~~~
If the package accelerator requires an application to be installed before you apply the Package Accelerator, and if you have already installed the required application, select **I have installed all applications**, and then click **Next** on the **Local Installation** page.
~~~

6. 在 [**套件名稱**] 頁面上，指定將與套件建立關聯的名稱。 您指定的名稱會在 App V 管理主控台中識別套件。 按 **\[下一步\]**。

7. 在 [**建立套件**] 頁面上，提供將與套件相關聯的批註。 批註應該包含您正在建立之套件的識別資訊。 若要確認建立套件的位置，請查看 [**儲存位置**] 中顯示的資訊。 若要壓縮套件，請選取 [**壓縮套件**]。 如果套件將在網路上流動，或者套件大小超過 4 GB，請選取 [**壓縮套件**] 核取方塊。

   若要建立套件，請按一下 [**建立**]。 建立套件後，請按 **[下一步]**。

8. 在 [**設定軟體**] 頁面上，若要啟用排序器來設定套件中包含的應用程式，請選取 [**設定軟體**]。 在此步驟中，您可以設定任何必須完成才能在目的電腦上執行應用程式的相關工作。 例如，您可以設定任何相關的授權協定。

   如果您選取 [**設定軟體**]，則可以使用 Sequencer 來設定下列專案，做為此步驟的一部分：

   -   **載入套件**。 Sequencer 會載入與套件相關聯的檔案。 解碼套件可能需要數秒到1小時的時間。

   -   **執行每個程式**。 您也可以選擇執行套件中包含的程式。 在您部署並在目的電腦上執行套件之前，請先完成執行應用程式所需的任何相關授權或配置工作，才能執行此步驟。 若要一次執行所有程式，請選取至少一個程式，然後按一下 [**全部執行**]。 若要執行特定程式，請選取您要執行的程式或程式，然後按一下 [**執行選取**的專案]。 完成所需的設定任務，然後關閉應用程式。 所有程式都可能需要幾分鐘的時間才能執行。 按 **\[下一步\]**。

   -   [**儲存套件**]。 Sequencer 會儲存套件。

   -   **主要功能區塊**。 排序器透過重建主要功能區塊來優化資料流程套件。

   如果您不想要設定應用程式，請按一下 [**略過此步驟**]，然後移至此程式的步驟9，然後按 **[下一步]**。

9. 在 [**完成**] 頁面上，檢查 [**虛擬應用程式套件報告**] 窗格中顯示的資訊後，按一下 [**關閉**]。

   套件現在可在 Sequencer 中取得。 若要編輯套件屬性，請按一下 **[編輯 \ [套件名稱 \]]**。 如需如何修改套件的詳細資訊，請參閱[如何修改現有的虛擬應用程式套件](how-to-modify-an-existing-virtual-application-package-beta.md)。

   您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[App-V 5.1 作業](operations-for-app-v-51.md)








