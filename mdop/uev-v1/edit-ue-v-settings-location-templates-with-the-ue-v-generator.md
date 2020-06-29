---
title: 使用 UE-V 產生器編輯 UE-V 設定位置範本
description: 使用 UE-V 產生器編輯 UE-V 設定位置範本
author: dansimp
ms.assetid: da78f9c8-1624-4111-8c96-79db7224bd0b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7b90cd58761e6ac40c089f3afeade3c445a52ea6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812159"
---
# 使用 UE-V 產生器編輯 UE-V 設定位置範本


使用 Microsoft 使用者經驗虛擬化（UE-V）發生器編輯設定位置範本。 當使用 UE-V 發生器將修訂的設定新增到範本時，範本內的版本資訊會自動更新，以確保企業中部署的任何現有範本都能正確更新。

**如何使用 UE-V 發生器編輯 UE-V 設定位置範本**

1.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **microsoft 使用者體驗虛擬化**]，然後按一下 [ **microsoft 使用者體驗虛擬化發生器**]。

2.  按一下 [**編輯設定位置範本**]。

3.  在最近使用的範本清單中，選取要編輯的範本。 或者，**流覽**至 [設定] 範本檔案。 按 \[**下一步**\] 繼續。

4.  查看設定範本的**屬性** **、登錄**位置**及檔案**位置。 視需要編輯。

    -   [**屬性**] 索引標籤可讓您查看及編輯下列屬性：

        -   **應用程式名稱**：寫入程式檔案屬性描述的應用程式名稱。

        -   **程式名稱**：從程式檔案屬性中取得的程式名稱。 這個名稱通常具有 .exe 副檔名。

        -   **產品版本**：應用程式 .exe 檔案的產品版本號碼。 這個屬性與檔案**版本**，可協助判斷設定位置範本所針對的是哪些應用程式。 這個屬性接受主要版本號碼。 如果此屬性為空白，則會將設定位置範本套用至所有版本的產品。

        -   **檔版本**：應用程式 the.exe 檔案的檔案版本號碼。 這個屬性和**產品版本**，可協助判斷設定位置範本所針對的是哪些應用程式。 這個屬性接受主要版本號碼。 如果這個屬性是空的，設定位置範本會套用至所有版本的程式。

        -   **範本作者名稱**（選用）：設定範本作者的名稱。

        -   **範本作者電子郵件**（選用）：設定位置範本作者的電子郵件地址。

    -   [**登錄] 索引**標籤會列出 [設定位置] 範本中所包含的登錄位置**金鑰**和**範圍**。 您可以使用 [**任務**] 下拉式功能表來編輯登錄位置。 工作包括新增金鑰、編輯現有金鑰的名稱或範圍、刪除金鑰，以及流覽金鑰所在的註冊表。 當您定義註冊表的範圍時，您可以使用**All 設定**範圍，將所有的登錄設定都包含在指定的索引鍵底下。 使用 [**所有設定**] 和 [子機] **，將所有**的登錄設定都包含在指定的索引鍵、子機和子項設定底下。

    -   [**檔案] 索引**標籤會列出 [設定位置] 範本中所包含之檔案位置的檔案路徑和檔案遮罩。 您可以使用 [**任務**] 下拉式功能表來編輯檔案位置。 檔案位置的工作包括新增檔案或資料夾位置、編輯現有檔案或資料夾的範圍、刪除檔案或資料夾，以及在 Windows 資源管理器中開啟所選的位置。 若要包含指定資料夾中的所有檔案，請將檔案遮罩保留為空白。

5.  按一下 [**儲存**]，將變更儲存到 [設定位置] 範本。

6.  按一下 [**關閉**]，關閉 [設定範本] 嚮導。 退出 UE-V 發生器應用程式。

    在編輯應用程式的設定位置範本之後，您應該測試範本。 在實驗室環境中部署已修改的設定位置範本，然後將它放入企業中的生產環境。

**如何手動編輯設定位置範本**

1.  建立 [設定位置] 範本（.xml 檔案）的本機複本。 UE-V 設定位置範本是 .xml 檔案，可識別應用程式儲存設定值的位置。

2.  使用 XML 編輯器開啟 [設定位置] 範本檔。

3.  編輯設定位置範本檔。 所有變更必須符合 SettingsLocationTempate 中定義的 UE-V 架構檔案。 Xsd 檔案的複本預設位於中 `\ProgramData\Microsoft\UEV\Templates` 。

4.  儲存 [設定位置] 範本檔案，然後關閉 [XML 編輯器]。

5.  使用 UE-V 發生器驗證已修改的設定位置範本檔。 如需使用 UE-V 發生器驗證的詳細資訊，請參閱[使用 Ue-v 發生器驗證 Ue-v 設定位置範本](validate-ue-v-settings-location-templates-with-ue-v-generator.md)。

## 相關主題


[使用自訂 UE-V 範本與 UE-V 產生器](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

[UE-V 1.0 作業](operations-for-ue-v-10.md)

 

 




