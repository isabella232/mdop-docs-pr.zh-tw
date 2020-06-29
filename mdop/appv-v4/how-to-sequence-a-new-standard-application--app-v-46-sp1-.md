---
title: 如何排序新的標準應用程式 (App-V 4.6 SP1)
description: 如何排序新的標準應用程式 (App-V 4.6 SP1)
author: dansimp
ms.assetid: c4a2eb33-def8-4535-b93a-3d2de21ce29f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 47c93b4880d0095c87a98292fda743acc1659e81
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801106"
---
# 如何排序新的標準應用程式 (App-V 4.6 SP1)


使用下列程式，透過應用程式虛擬化（App-v） Sequencer 來建立新的標準虛擬應用程式套件。 此程式適用于您所排序的大部分應用程式。 如需有關您可以排序之應用程式類型的詳細資訊，請參閱[如何判斷要順序的應用程式類型（app-v 4.6 SP1）](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)。 您必須使用具有系統管理員許可權的帳戶來執行 sequencer （**SFTSequencer.exe**），因為排序器對本機系統所做的變更。 這些變更可以包括將檔案寫入**C:\\program files files**目錄、進行登錄、啟動及停止服務、更新檔案的安全性描述項，以及變更許可權。

**重要**  
在排序期間，如果執行 Sequencer 的電腦是執行 Windows Vista 或 Windows 7，且在虛擬環境之外啟動重新開機，例如**開始**  /  **關閉**，則當系統提示您關閉阻礙 Windows vista 或 windows 關閉的程式時，您必須按一下 [**取消**]。 如果您按一下 [**強制關閉**]，套件建立就會失敗。 當您按一下 [**取消**] 時，Sequencer 會在應用程式排序時成功記錄重新開機。



**注意**  
在安全模式中執行 App-v 排序器不受支援。



**為新的標準應用程式排序**

1.  若要啟動 app-v 排序器，請在執行 app-v 排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization 排序**器。

2.  若要啟動 [**建立新套件] 嚮導**，請按一下 [**建立新的虛擬應用程式套件**]。 若要建立套件，請選取 [**建立套件（預設）**]，然後按一下 **[下一步]**。

3.  在 [**準備電腦**] 頁面上，查看可能導致套件建立失敗的問題，或針對套件包含不必要的資料。 我們強烈建議您在繼續進行之前先解決所有潛在問題。 修正衝突之後，若要更新所顯示的資訊，**請按一下 [** 重新整理]。 解決所有可能的問題之後，請按 **[下一步]**。

    **重要**  
    如果您需要停用病毒掃描軟體，請掃描執行 Sequencer 的電腦，以確保無法在套件中新增不需要的或惡意的檔案。



4.  在 [**應用程式類型**] 頁面上，按一下 [**標準應用程式（預設）** ] 核取方塊，然後按一下 **[下一步]**。

    如需可排序之應用程式類型的詳細資訊，請參閱[如何判斷要順序的應用程式類型（app-v 4.6 SP1）](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)。

5.  在 [**選取安裝程式**] 頁面上，按一下 **[流覽]** ，然後指定應用程式的安裝檔。 如果應用程式沒有關聯的安裝程式檔案，且您打算手動執行所有安裝步驟，請選取 [**執行自訂安裝**] 核取方塊，然後按一下 **[下一步]**。

6.  在 [**套件名稱**] 頁面上，指定將與套件建立關聯的名稱。 名稱可協助識別已新增到套件中之應用程式的用途和版本。 套件名稱也會顯示在 App V 管理主控台中。 **主要虛擬應用程式目錄**會顯示應用程式虛擬化路徑，應用程式將會安裝在目的電腦上。 若要編輯此位置，請選取 **[編輯] （[高級]）**。

    **重要**  
    編輯應用程式虛擬化路徑是一個高級的配置工作。 您應該完全瞭解變更路徑的意義。 在大部分的應用程式中，建議使用預設路徑。



~~~
Click **Next**.
~~~

7. 在 [**安裝**] 頁面上，當排序器和應用程式安裝程式準備好時，請安裝應用程式，讓排序器可以監視安裝程式。 使用應用程式的安裝程式來執行安裝。 如果安裝時必須執行其他安裝檔案，請按一下 [**執行**]，找出並執行其他安裝檔案。 完成安裝後，請選取 [**我已完成安裝**]。 按 **\[下一步\]**。

8. 在 [**安裝**] 頁面上，請稍候，Sequencer 會設定虛擬應用程式套件。

9. 在 [**設定軟體**] 頁面上，選擇性地執行套件中包含的程式。 此步驟可協助您完成在您部署並在目的電腦上執行套件之前，執行應用程式所需的任何相關授權或配置工作。 若要一次執行所有程式，請選取至少一個程式，然後按一下 [**全部執行**]。 若要執行特定程式，請選取您要執行的程式或程式，然後按一下 [**執行選取**的專案]。 完成所需的配置工作，然後關閉應用程式。 所有程式都可能需要幾分鐘的時間才能執行。 按 **\[下一步\]**。

10. 在 [**安裝報告**] 頁面上，您可以查看您剛剛排序的虛擬應用程式套件的相關資訊。 如需**其他資訊**所顯示之資訊的詳細說明，請按兩下該事件。 審閱資訊之後，請按 **[下一步]**。

11. 在 [**自訂**] 頁面上，如果您已完成安裝並設定虛擬應用程式，請選取 [**立即停止**]，然後跳至此程式的步驟15。 如果您想要自訂以下清單中的任何專案，請選取 [**自訂**]。

    -   編輯檔案類型關聯及與應用程式相關聯的圖示。

    -   準備虛擬套件以進行流式處理。 [資料流程] 可改善虛擬應用程式套件在目的電腦上執行時的體驗。

    -   指定可以執行此套件的作業系統。

    按 **\[下一步\]**。

12. 在 [**編輯快速鍵**] 頁面上，您可以選擇性地設定檔案類型關聯（FTA），以及將與套件中各種應用程式相關聯的快捷方式位置。 若要建立新的 FTA，請在左窗格中，選取並展開您要自訂的應用程式，然後按一下 [**新增**]。 在 [**新增檔案類型關聯**] 對話方塊中，為新的 FTA 提供必要的資訊。 若要查看與應用程式相關聯的快捷方式資訊，請在應用程式底下選取 [**快速鍵**]，然後在 [**位置**] 窗格中，您可以編輯圖示檔資訊。 若要編輯現有的 FTA，請按一下 [**編輯**]。 若要移除 FTA，請選取 FTA，然後按一下 [**移除**]。 按 **\[下一步\]**。

13. 在 [**流式處理**] 頁面上，執行每個程式，讓它能在目的電腦上優化並更有效率地執行。 可能需要幾分鐘的時間，所有應用程式才會執行。 在所有應用程式都已執行之後，請關閉每個應用程式，然後按 **[下一步]**。

   **注意**  
   如果您想要在此步驟中停止載入應用程式，請在 [**應用程式啟動**] 對話方塊中，按一下 [**停止**]，然後選取其中一個核取方塊、[**停止所有應用程式**] 或 [**僅停止此應用程式**] （視您的需求而定）。



14. 在 [**目標作業系統**] 頁面上，指定可執行此套件的作業系統。 若要在您的環境中啟用所有受支援的作業系統來執行這個套件，請選取 [**允許此套件在任何作業系統上執行**]。 若要將這個套件設定為只在特定作業系統上執行，請選取 [**只允許此套件在下列作業系統上**執行]，並指定可執行此套件的作業系統。 按 **\[下一步\]**。

   **重要**  
   此步驟中指定的作業系統會反映已啟用可執行套件的目的電腦作業系統。 您必須確保您所排序的應用程式支援所指定的作業系統。



15. 在 [**建立套件**] 頁面上，若要修改套件但不儲存，請選取 **[繼續]，不使用 [封裝編輯器] 儲存來修改套件**。 選取此選項會在 Sequencer 視窗中開啟套件，讓您可以在儲存套件之前加以修改。 按 **\[下一步\]**。

   若要立即儲存套件，請選取 [**立即儲存套件**] 的預設值。 新增將與套件相關聯的選擇性**批註**。 若要識別套件的版本及其他資訊，可以使用 [批註]。 也會顯示預設的**儲存位置**。 若要變更預設位置，請按一下 **[流覽]** ，然後指定新的位置。 隨即會顯示未壓縮的套件大小。 如果套件大小超過 4 GB （未壓縮），且您打算將套件資料流程資料流至目的電腦，您必須選取 [**壓縮套件**]。 按一下 \[建立\]****。

16. 在 [**完成**] 頁面上，檢查 [**虛擬應用程式套件報告**] 窗格中顯示的資訊後，按一下 [**關閉**]。 在 [**虛擬應用程式套件報告**] 窗格中顯示的資訊，也可在此程式的步驟15中指定的目錄中取得，在名為**Report.xml**的檔案中提供。

    套件現在可在 Sequencer 中取得。 若要編輯套件屬性，請按一下 **[編輯 \ [套件名稱 \]]**。 如需有關修改套件的詳細資訊，請參閱[如何修改現有的虛擬應用程式套件（app-v 4.6 SP1）](how-to-modify-an-existing-virtual-application-package--app-v-46-sp1-.md)

    **重要**  
    成功建立虛擬應用程式套件之後，您就無法在執行排序器的電腦上執行虛擬應用程式套件。



## 相關主題


[Application Virtualization Sequencer 的工作 (App-V 4.6 SP1)](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

[如何判斷要順序的應用程式類型（App-v 4.6 SP1）](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)








