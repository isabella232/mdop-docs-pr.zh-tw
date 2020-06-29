---
title: 如何發佈與取消發佈 MED-V 工作區上的應用程式
description: 如何發佈與取消發佈 MED-V 工作區上的應用程式
author: dansimp
ms.assetid: fd5a62e9-0577-44d2-ae17-61c0aef78ce8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cc8f9579d800aa0e5da0d67e0cd71bcae5e912a0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812045"
---
# 如何發佈與取消發佈 MED-V 工作區上的應用程式


即使應用程式已安裝在 MED-V 工作區中，您也可能還必須先發佈應用程式，才能供使用者使用。 根據預設，大部分的應用程式會在安裝時發佈，並建立並啟用快速鍵。

在某些情況下，您可能會想要在 MED-V 工作區上安裝應用程式，而不讓最終使用者使用，例如病毒掃描軟體。 同樣地，您還是想要發佈的應用程式是已安裝在由使用者先前無法使用的 MED-V 工作區。 例如，如果安裝沒有在 [**開始**] 功能表上自動建立快捷方式，您可能必須發佈已安裝的應用程式。

**重要** 如果您發佈的應用程式不支援 UNC 路徑，我們建議您將應用程式對應至磁片磁碟機。

 

您可以執行下列其中一項任務，將應用程式發佈或取消發佈到已部署的 MED-V 工作區：

**發佈或取消發佈已安裝的應用程式**

1.  若要在已部署的 MED-V 工作區發佈應用程式，請將該應用程式的快捷方式複製到虛擬機器上的下列資料夾：

    [C:\\Documents] 和 [Settings\\All Users\\Start] 功能表

    如有需要，請使用 [群組原則] 或 [ESD 系統] 來部署腳本，將該應用程式的快捷方式複製到 [全部 Users\\Start] 功能表資料夾中。

2.  若要在已部署的 MED-V 工作區上取消發佈應用程式，請從虛擬機器上的下列資料夾中刪除該應用程式的快捷方式：

    [C:\\Documents] 和 [Settings\\All Users\\Start] 功能表

    如有需要，請使用 [群組原則] 或 [ESD 系統] 來部署腳本，從 [所有 Users\\Start] 功能表資料夾中刪除該應用程式的快捷方式。

    **記事** 在您卸載應用程式時，會經常從主機電腦的 [**開始**] 功能表刪除快捷方式。 不過，在某些情況下（例如針對共用電腦的所有使用者所設定的 MED-V 工作區），您可能必須在卸載應用程式後，手動刪除 [**開始**] 功能表上的快捷方式。 最終使用者可以用滑鼠右鍵按一下快捷方式，然後選取 [**刪除**] 來執行此動作。

     

若要測試應用程式是否已發佈或未發佈，請在 MED-V 工作區中驗證是否有對應的快速鍵可供使用。

**記事** Windows XP SP3 中包含且位於 [虛擬機器開始] 功能表資料夾中的應用程式不會自動發佈到主機。 它們是由封鎖自動發佈的註冊表設定所控制。 如需詳細資訊，請參閱[Windows 虛擬電腦應用程式排除清單](windows-virtual-pc-application-exclude-list.md)。

 

**發佈 [控制台] 專案**

1.  在目標為專案名稱的虛擬機器上建立快捷方式，例如 [C:\\WINDOWS\\system32\\appwiz.cpl]。

    快捷方式必須在 [%ALLUSERSPROFILE%\\Start Menu\\] 資料夾或其中一個子資料夾中建立或移至它。

    該專案將會發佈到主機 [開始] 功能表資料夾中相對應位置的主機電腦。

2.  在主機中啟動專案的快捷方式。

**小心** 當您建立快捷方式時，請不要指定% SystemRoot% \\control.exe。 此應用程式將不會發佈，因為它包含在封鎖自動發佈的註冊表設定中。

 

**MED-V 如何處理自動應用程式發佈**

1.  在應用程式發佈期間，MED-V 會嘗試與來賓中存在的資料夾階層相符，以將來賓虛擬機器的快速鍵複製到主機電腦。 如此一來，MED-V 會按照下列步驟，將來賓的快速鍵複製到主機：

    1.  MED-V 會嘗試在名為「開始 Menu\\Programs」的主機電腦中，找到與快捷方式所在之來賓中的資料夾相同的資料夾。

    2.  如果沒有相符的資料夾，MED-V 會嘗試在主機 [開始] 功能表資料夾中找出名稱與快捷方式所在之來賓中的資料夾相同的資料夾。

    3.  如果沒有相符的資料夾，MED-V 會將快捷方式複製到主機上的預設資料夾，即 [開始 Menu\\Programs] 資料夾。

2.  應用程式發佈程式範例：

    1.  如果應用程式快捷方式發佈至來賓中的 [開始 Menu\\Programs\\AppShortcuts] 資料夾，則 MED-V 會在主機電腦中尋找 [開始 Menu\\Programs\\ AppShortcuts] 資料夾，如果找到，就會將快捷方式複製到該資料夾。

    2.  如果找不到資料夾，則 MED-V 會在主機電腦中尋找開始 Menu\\AppShortcuts 資料夾，如果有找到，就會將快捷方式複製到該資料夾。

    3.  如果找不到資料夾，則 MED-V 會將快捷方式複製到 [開始] Menu\\Programs 資料夾。

**記事** 該資料夾必須已經存在於 MED-V 中的主機電腦的 [開始] 功能表資料夾中，才能複製快捷方式。 如果資料夾不存在，MED-V 就不會建立該資料夾。

 

## 相關主題


[安裝和移除 MED-V 工作區上的應用程式](installing-and-removing-an-application-on-the-med-v-workspace.md)

[管理 MED-V 工作區的軟體更新](managing-software-updates-for-med-v-workspaces.md)

[Windows Virtual PC 應用程式排除清單](windows-virtual-pc-application-exclude-list.md)

 

 





