---
title: 如何修改現有的虛擬應用程式封裝 (App-V 4.6 SP1)
description: 如何修改現有的虛擬應用程式封裝 (App-V 4.6 SP1)
author: dansimp
ms.assetid: f43a9927-4325-4b2d-829f-3068e4e84349
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f0e9d45a32afa240ce7f6fb2ee5dfbc51889c1fa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801257"
---
# 如何修改現有的虛擬應用程式封裝 (App-V 4.6 SP1)


使用下列程式來修改現有的虛擬應用程式套件。 您可以使用這些程式來執行下列動作：

-   更新屬於現有虛擬應用程式套件的應用程式。 若要執行這項工作，請使用這份檔中的「**更新現有應用程式套件中的應用程式」程式**。

-   修改與現有虛擬應用程式套件相關聯的屬性。 若要執行這項工作，請使用這份檔中的「**修改現有虛擬應用程式套件所關聯的屬性**」程式。

-   將新的應用程式新增至現有的虛擬應用程式套件。 若要執行這項工作，請使用這份檔中的 [**將新的應用程式新增至現有的虛擬應用程式套件]** 程式。

您必須已安裝 App-v 排序器，才能修改虛擬應用程式套件。 如需安裝 App-v 排序器的詳細資訊，請參閱[如何安裝 Sequencer （app-v 4.6 SP1）](how-to-install-the-sequencer---app-v-46-sp1-.md)。

**更新現有虛擬應用程式套件中的應用程式**

1.  若要啟動 app-v 排序器，請在執行 app-v 排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization 排序**器。

2.  在 App-v 排序器中，按一下 [**修改現有的虛擬應用程式套件**]，然後按一下 **[下一步]**。

3.  在 [**選取**工作] 頁面上，按一下 [**在現有套件中更新應用程式**]，然後按一下 **[下一步]**。

4.  在 [**選取套件**] 頁面上，按一下 **[流覽]** ，找出包含您要更新之應用程式的虛擬應用程式套件，然後按一下 **[下一步]**。

5.  在 [**準備電腦**] 頁面上，查看可能導致應用程式更新失敗的問題，或應用程式更新包含不必要的資料。 我們強烈建議您在繼續進行之前先解決所有潛在問題。 修正衝突之後，若要更新所顯示的資訊，**請按一下 [** 重新整理]。 解決所有可能的問題之後，請按 **[下一步]**。

    **重要** 如果您需要停用病毒掃描軟體，請掃描執行 sequencer 的電腦，以確保不會在套件中新增不需要的或惡意的檔案。

     

6.  在 [**選取安裝程式**] 頁面上，按一下 **[流覽]** ，然後指定應用程式的更新安裝檔案。 如果更新沒有關聯的安裝程式檔案，且您打算手動執行所有安裝步驟，請選取 [**選取此選項以執行自訂安裝**] 核取方塊，然後按一下 [**下一步]**。

7.  在 [**安裝**] 頁面上，當排序器和應用程式安裝程式準備好時，請安裝應用程式更新，讓排序器可以監視安裝程式。 如果安裝時必須執行其他安裝檔案，請按一下 [**執行**]，然後找出並執行其他安裝檔案。 完成安裝後，請選取 [**我已完成安裝**]。 按 **\[下一步\]**。

    **記事** 排序器會監視執行排序器的電腦所做的所有變更和安裝，包括在順序嚮導之外執行的變更和安裝。

     

8.  在 [**安裝報告**] 頁面上，您可以查看您剛更新之虛擬應用程式的相關資訊。 如需**其他資訊**所顯示之資訊的詳細說明，請按兩下該事件。 審閱資訊之後，請按 **[下一步]**。

9.  在 [**流式處理**] 頁面上，執行每個程式，讓它能在目的電腦上優化並更有效率地執行。 可能需要幾分鐘的時間，所有應用程式才會執行。 在所有應用程式都已執行之後，請關閉每個應用程式，然後按 **[下一步]**。

    **記事** 如果您想要在此步驟中停止載入應用程式，請在 [**應用程式啟動**] 對話方塊中，按一下 [**停止**]，然後按一下下列其中一個選項： [**停止所有應用程式**] 或 [**僅停止此應用程式**]，視您想要的專案而定。

     

10. 在 [**建立套件**] 頁面上，若要修改套件但不儲存，請選取 [**繼續使用套件編輯器來修改套件但不儲存**] 核取方塊。 當您選取此選項時，會開啟 Sequencer 視窗中的套件，讓您可以在儲存套件之前加以修改。 按 **\[下一步\]**。

    若要立即儲存套件，請選取 [**立即儲存套件**] 的預設值。 新增將與套件相關聯的選擇性**批註**。 若要識別套件的版本及其他資訊，可以使用 [批註]。 也會顯示預設的**儲存位置**。 若要變更預設位置，請按一下 **[流覽]** ，然後指定新的位置。 隨即會顯示未壓縮的套件大小。 如果套件大小超過 4 GB （未壓縮），且您打算將套件資料流程資料流至目的電腦，您必須選取 [**壓縮套件**]，然後按一下 [**建立**]。

11. 在**完成**頁面上，按一下 [**關閉**] 以關閉嚮導。 套件現在可在 sequencer 中取得。

**修改與現有虛擬應用程式套件相關聯的屬性**

1.  若要啟動 app-v 排序器，請在執行 app-v 排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization 排序**器。

2.  在 App-v 排序器中，按一下 [**修改現有的虛擬應用程式套件**]，然後按一下 **[下一步]**。

3.  在 [**選取**工作] 頁面上，按一下 [**編輯套件**]，然後按一下 **[下一步]**。

4.  在 [**選取套件**] 頁面上，按一下 **[流覽]** ，找出包含您要修改之應用程式屬性的虛擬應用程式套件，然後按一下 [**編輯**]。

5.  在 Sequencer 主控台中，您可以執行下列任何一項工作：

    -   [查看套件屬性]。

    -   [查看套件變更歷程記錄]。

    -   [查看關聯的套件檔案]。

    -   編輯註冊表設定。

    -   查看其他套件設定（除了作業系統檔案屬性之外）。

    -   建立相關聯的 Windows Installer （MSI）。

    -   [修改 OSD 檔案]。

    -   壓縮和解壓縮套件。

    -   新增檔案類型關聯。

    -   設定虛擬化登錄機碼的狀態（覆寫或合併）。

    -   設定虛擬化資料夾的狀態。

    -   編輯虛擬檔案系統對應。

6.  當您完成修改套件屬性時，**請按一下 [**  /  **儲存**] 以儲存套件。

**將新的應用程式新增至現有的虛擬應用程式套件**

1.  若要啟動 app-v 排序器，請在執行 app-v 排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization 排序**器。

2.  在 App-v 排序器中，按一下 [**修改現有的虛擬應用程式套件**]，然後按一下 **[下一步]**。

3.  在 [**選取**工作] 頁面上，按一下 [新增**應用程式**]，然後按一下 **[下一步]**。

4.  在 [**選取套件**] 頁面上，按一下 **[流覽]** ，找出您要新增應用程式的虛擬應用程式套件，然後按一下 **[下一步]**。

5.  在 [**準備電腦**] 頁面上，查看可能導致套件建立失敗的問題，或更新以包含不必要的資料。 我們強烈建議您在繼續進行之前先解決所有潛在問題。 修正衝突之後，若要更新所顯示的資訊，**請按一下 [** 重新整理]。 解決所有可能的問題之後，請按 **[下一步]**。

    **重要** 如果您需要停用病毒掃描軟體，請掃描執行 sequencer 的電腦，以確保不會在套件中新增不需要的或惡意的檔案。

     

6.  在 [**選取安裝程式**] 頁面上，按一下 **[流覽]** ，然後指定應用程式的安裝檔。 如果應用程式沒有關聯的安裝程式檔案，且您打算手動執行所有安裝步驟，請選取 [**選取此選項以執行自訂安裝**] 核取方塊，然後按一下 [**下一步]**。

7.  在 [**安裝**] 頁面上，當排序器和應用程式安裝程式準備好時，請安裝應用程式，讓排序器可以監視安裝程式。 如果安裝時必須執行其他安裝檔案，請按一下 [**執行**]，然後找出並執行其他安裝檔案。 完成安裝後，請選取 [**我已完成安裝**]。 按 **\[下一步\]**。 在 [**流覽資料夾**] 對話方塊中，指定將安裝應用程式的主要目錄。 這應該是新的位置，因此您不會覆寫現有的虛擬應用程式套件版本。

    **記事** 排序器會監視執行排序器的電腦的所有變更和安裝，包括在順序嚮導之外執行的變更和安裝。

     

8.  在 [**設定軟體**] 頁面上，選擇性地執行套件中包含的程式。 此步驟可協助您完成在您部署並在目的電腦上執行套件之前，執行應用程式所需的任何相關授權或配置工作。 若要同時執行所有程式，請選取至少一個程式，然後按一下 [**全部執行**]。 若要執行特定程式，請選取您要執行的程式或程式，然後按一下 [**執行選取**的專案]。 完成所需的配置工作，然後關閉應用程式。 所有程式都可能需要幾分鐘的時間才能執行。 按 **\[下一步\]**。

9.  在 [**安裝報告**] 頁面上，您可以查看您剛更新之虛擬應用程式的相關資訊。 如需**其他資訊**所顯示之資訊的詳細說明，請按兩下該事件。 審閱資訊之後，請按 **[下一步]**。

10. 如果您已完成安裝並設定虛擬應用程式，請在 [**自訂**] 頁面上選取 [**立即停止**]，然後跳至此程式的步驟14。 如果您想要自訂以下清單中的任何專案，請按一下 [**自訂**]。

    -   編輯與應用程式相關聯的檔案類型關聯。

    -   準備虛擬套件以進行流式處理。 [資料流程] 可改善虛擬應用程式套件在目的電腦上執行時的體驗。

    按 **\[下一步\]**。

11. 在 [**編輯快速鍵**] 頁面上，您可以選擇性地設定將與套件中各種應用程式相關聯的檔案類型關聯（FTA）。 若要建立新的 FTA，請在左窗格中選取並展開您要自訂的應用程式，然後按一下 [**新增**]。 在 [**新增檔案類型關聯**] 對話方塊中，為新的 FTA 提供必要的資訊。 若要查看與應用程式相關聯的快捷方式資訊，請選取 [**快捷方式**] 核取方塊，然後在 [**位置**] 窗格中，您可以查看圖示檔資訊。 若要編輯現有的 FTA，請按一下 [**編輯**]。 若要移除 FTA，請選取 FTA，然後按一下 [**移除**]。 按 **\[下一步\]**。

12. 在 [**流式處理**] 頁面上，執行每個程式，讓它能在目的電腦上優化並更有效率地執行。 可能需要幾分鐘的時間，所有應用程式才會執行。 在所有應用程式都已執行之後，請關閉每個應用程式，然後按 **[下一步]**。

    **記事** 如果您想要在此步驟期間停止載入應用程式，請在 [**應用程式啟動**] 對話方塊中，按一下 [**停止**]，然後選取 [**停止所有應用程式**] 或 [**僅停止此應用程式**] 核取方塊（視您想要的專案而定）。

     

13. 在 [**建立套件**] 頁面上，選取 [**繼續使用套件編輯器來修改套件但不儲存**] 核取方塊，即可修改套件而不儲存。 當您選取此選項時，會開啟 sequencer 視窗中的套件，讓您可以在儲存套件之前加以修改。 按 **\[下一步\]**。

    選取 [**立即儲存套件**]，立即儲存套件。 新增將與套件相關聯的選擇性**批註**。 若要識別套件的版本及其他資訊，可以使用 [批註]。 也會顯示預設的**儲存位置**。 若要變更預設位置，請按一下 **[流覽]** ，然後指定新的位置。 隨即會顯示未壓縮的套件大小。 如果套件大小超過 4 GB （未壓縮），且您打算將套件資料流程資料流至目的電腦，您必須選取 [**壓縮套件**]。 按一下 \[建立\]****。

14. 在**完成**頁面上，按一下**關閉**。 套件現在可在 sequencer 中取得。

## 相關主題


[Application Virtualization Sequencer 的工作 (App-V 4.6 SP1)](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

 

 




