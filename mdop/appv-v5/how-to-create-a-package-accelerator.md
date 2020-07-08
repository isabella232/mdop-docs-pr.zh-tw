---
title: 如何建立封裝加速器
description: 如何建立封裝加速器
author: dansimp
ms.assetid: dfe305e5-7cf8-498f-9581-4805ffc722bd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0710bff5e5ea420119ac3c395c2e8917f7c582dd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800553"
---
# 如何建立封裝加速器


App-v 5.0 套件加速器會自動產生新的虛擬應用程式套件。

**注意**  
您可以使用 PowerShell 建立套件加速器。 如需詳細資訊，請參閱[如何使用 PowerShell 建立套件加速器](how-to-create-a-package-accelerator-by-using-powershell.md)。



使用下列程式建立套件加速器。

**重要**  
套件加速器可以包含密碼和使用者專用的資訊。 因此，您必須將套件加速器與關聯安裝媒體儲存在安全的位置，而且您應該在建立套件加速器之後進行數位簽章，以便在套用 app-v 5.0 套件加速器時驗證發行者。



**重要**  
開始進行下列程式前，您應該執行下列步驟：

-   複製您將用來在執行排序器的電腦上將用來建立套件加速器的虛擬應用程式套件。

-   將與虛擬應用程式套件相關的所有必要安裝檔案複製到執行排序器的電腦上。



**建立套件加速器**

1.  **重要**  
    App-v 5.0 Sequencer 不會將任何您用來建立套件加速器之軟體應用程式的授權權利授與。 您必須遵守所使用之應用程式的所有使用者授權合約。 您有責任確認軟體應用程式的授權條款可讓您使用 App-v 5.0 排序器來建立套件加速器。



~~~
To start the App-V 5.0 sequencer, on the computer that is running the sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.
~~~

2. 若要啟動 app-v 5.0 [**建立套件加速器**] 嚮導，請在 app-v 5.0 排序器主控台中，按一下 [**工具**  /  **建立加速器**]。

3. 在 [**選取套件**] 頁面上，若要指定要用來建立套件加速器的現有虛擬應用程式套件，請按一下 **[流覽]**，然後找出現有的虛擬應用程式套件（appv 檔案）。

   **提示**  
   將與您計畫要在本機使用的虛擬應用程式套件相關聯的檔案複製到執行排序器的電腦上。



~~~
Click **Next**.
~~~

4. 在 [**安裝**檔案] 頁面上，若要指定包含您用來建立原始虛擬應用程式套件之安裝檔案的資料夾，請按一下 **[流覽]**，然後選取包含安裝檔的目錄。

   **提示**  
   在執行排序器的電腦上，複製包含所需安裝檔案的資料夾。



5. 如果應用程式已安裝在執行排序器的電腦上，若要指定安裝檔案，請選取 [**本機系統上已安裝的**檔案]。 若要使用此選項，應用程式必須已安裝在預設安裝位置。

6. 在 [**收集資訊**] 頁面上，查看在此嚮導的 [**安裝**檔案] 頁面上指定的位置中找不到的檔案。 如果不需要顯示的檔案，請選取 [**移除這些**檔案]，然後按一下 **[下一步]**。 如果檔案是必要的，請按一下 [**上一步**]，然後將所需的檔案複製到 [**安裝**檔案] 頁面上指定的目錄。

   **注意**  
   您必須移除 unrequired 檔案，或按一下 [**上一**步]，然後找出所需的檔案，以移至此嚮導的下一個頁面。



7. 在 [**選取**檔案] 頁面上，仔細查看已偵測到的檔案，並清除任何應從套件加速器移除的檔案。 只選取應用程式成功執行所需的檔案，然後按一下 **[下一步]**。

8. 在 [**驗證應用程式**] 頁面上，確認已顯示組建套件所需的所有安裝檔案。 當套件加速器用來建立新的套件時，在 [**應用程式**] 窗格中顯示的所有安裝檔案都是建立套件所需的專案。

   如有需要，若要新增其他安裝程式檔案，請按一下 [**新增**]。 若要移除不必要的安裝檔，請選取安裝程式檔案，然後按一下 [**刪除**]。 若要編輯與安裝程式相關聯的屬性，請按一下 [**編輯**]。 當您使用套件加速器建立新的虛擬應用程式套件時，系統會要求在此步驟中指定的安裝檔案。 確認顯示的資訊後，請按 **[下一步]**。

9. 在 [**選取指導**者] 頁面上，若要指定包含套件加速器之相關資訊的檔案，請按一下 **[流覽]**。 例如，此檔案可以包含執行排序器的電腦配置、目的電腦的應用程式必備資訊，以及一般筆記的相關資訊。 您應該提供套件加速器所需的所有必要資訊，才能成功套用。 您所選取的檔案必須是 rtf （.rtf）或文字檔（.txt）格式。 按 **\[下一步\]**。

10. 在 [**建立套件加速器**] 頁面上，若要指定要儲存套件加速器的位置，請按一下 **[流覽]** ，然後選取目錄。

11. 在**完成**頁面上，若要關閉 [**建立套件快速鍵**嚮導]，請按一下 [**關閉**]。

   **重要**  
   為了協助確保套件加速器盡可能安全，且在套用套件加速器時可驗證發行者，您應該必須以數位方式簽署套件加速器。



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 相關主題


[App-V 5.0 作業](operations-for-app-v-50.md)

[如何使用 App-V 封裝加速器建立虛擬應用程式套件](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator.md)









