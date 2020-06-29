---
title: 如何使用差異 SFT 檔案
description: 如何使用差異 SFT 檔案
author: dansimp
ms.assetid: 607e30fd-2f0e-4e2f-b669-0b3f010aebb0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 85cc45f9665569d77fcf275db6dbc080eb919229
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801009"
---
# 如何使用差異 SFT 檔案


當您將應用程式排序時，Microsoft Application Virtualization （App-v） Sequencer 會建立 SFT 檔案（SFT），以儲存虛擬應用程式的所有檔案內容和配置資訊。 在 App-v 的4.5 版本中，引入了差異 SFT （dsft）檔案。 使用 Sequencer 建立現有套件的升級之後，您可以選擇產生此檔案，只儲存原始已排序的應用程式套件與新版本之間的差異。 因此，它比完整的 SFT 檔案要小得多，就是針對新版本的應用程式，並減少在低頻寬網路連線中傳送套件更新的影響。 不過，只有在某些受限制的情況下，才支援使用。 此功能是專門用來在您使用電子軟體發佈（ESD）系統管理一組使用者，並在低頻寬連線中使用本機檔案伺服器來管理使用者，而不是使用 App-v 流式處理伺服器。

如果您使用的是 [配置 Manager2007] 來管理使用者，則不需要使用差異 SFT 檔案，因為 Configuration Manager 支援已內建的低頻寬部署。 如果您使用的是應用程式虛擬化（App-v）管理或流式伺服器（含作用中升級），則也不需要它，因為用戶端只會檢索舊版本與新套件版本之間的差異。

下列程式說明如何使用 Sequencer 安裝中包含的 mkdiffpkg.exe 來建立差異 SFT 檔案、完成虛擬應用程式套件升級之後，以及部署差異 SFT 檔案。 完成這個程式有助於確保如果套件是以某種方式從用戶端電腦上卸載，則在使用者下次嘗試執行該應用程式時，用戶端會回到覆寫 URL，該 URL 已設定為從本機檔案共用中傳送完整套件 V2。 sft。 這將避免啟動應用程式時的使用者任何失敗。 如果整個用戶端遭到損毀或卸載，建議將 ESD 系統設定為將升級套件的完整版本（V2）部署到用戶端。

如需升級套件的詳細資訊，請參閱 App-V 4.5 操作指南中的「如何升級現有的虛擬應用程式」 <https://go.microsoft.com/fwlink/?LinkId=133129>

**記事** 作為先決條件，ESD 所針對的所有使用者電腦都必須將 V1 檔案完全載入到其本機快取中，而且必須在所有電腦上啟用檔案資料流程。

 

**使用差異 SFT 檔案**

1.  使用具有系統管理員許可權的帳戶登入 Sequencer 電腦。 在 Sequencer 中開啟原始套件（V1）以進行升級，然後將套件升級為新的版本（V2），並將其儲存為新的 V2. sft。

2.  在 App-V 4.5 排序器安裝資料夾中開啟命令視窗，然後執行下列命令：

    `“mkdiffpkg.exe V2.sft V2.dsft”`

3.  使用 ESD 系統或其他檔案複製程式，將完整的 V2 套件內容檔案（V2）複製到本機檔案共用，以供使用者電腦在連線良好的網路連線時存取。

4.  使用 ESD 系統，將差異 SFT 檔案（dsft）的複本放在每個使用者電腦上。

5.  若要匯入 dsft 檔案，請在每個使用者電腦上執行下列 SFTMIME 命令：

    `“SFTMIME load package:<package name> /SFTPATH <path to V2.dsft>”`

6.  在每個使用者電腦上執行下列 SFTMIME 命令，以將覆寫 URL 設定為指向 V2 盤案：

    `“SFTMIME configure package:<package name> /OverrideURL FILE://<network path to V2.sft>”`

**注意**  
-   差異 SFT 檔案必須按照正確的順序套用到用戶端。 例如，dsft 必須套用至 V1 應用程式後，才會套用 V3. dsft。

-   Sequencer 中的 [**產生 Microsoft Windows Installer （MSI）] 套件**功能無法與差異 SFT 檔案搭配使用。

 

## 相關主題


[如何使用 App-v 排序器建立或升級虛擬應用程式](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)

 

 





