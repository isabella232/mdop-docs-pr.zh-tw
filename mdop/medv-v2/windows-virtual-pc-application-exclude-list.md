---
title: Windows Virtual PC 應用程式排除清單
description: Windows Virtual PC 應用程式排除清單
author: dansimp
ms.assetid: 7715f198-f5ed-421e-8740-0cec2ca4ece3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/28/2017
ms.openlocfilehash: 190049ce99865ef237d8d26e14a8279def7da521
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810107"
---
# Windows Virtual PC 應用程式排除清單


在某些情況下，您可能不想將 MED-V 工作區中安裝的應用程式發佈到主機電腦的 [**開始**] 功能表。 您可以按照指示在[Med-v 工作區中發佈及取消發佈應用程式](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)的指示，以取消發佈這些應用程式。 不過，如果程式自動更新，也可能會自動重新發佈。 這會讓您再次取消發佈應用程式。

Windows 虛擬電腦包含稱為「排除清單」的功能，可讓您指定一些您不想發佈到主機 [**開始**] 功能表的已安裝應用程式。 [排除清單] 位於 HKLM\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Virtual Machine\\VPCVAppExcludeList 金鑰中的來賓登錄，並列出那些未發佈至主機 [**開始**] 功能表的應用程式。 您可以將「排除清單」視為永久取消發佈指定的應用程式，因為所列出之應用程式的任何自動更新將不會自動重新發佈。

## 使用 Windows 虛擬電腦中的排除清單管理應用程式


****

1.  以全螢幕開啟 MED-V 工作區。

    如需使用 MED-V 管理工具組以全螢幕模式開啟 MED-V 工作區的相關資訊，請參閱[查看 Med-v 工作區](viewing-med-v-workspace-configurations.md#bkmk-fullscreen)設定。 或者，您可以按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **windows 虛擬電腦**]，按一下 [ **WINDOWS 虛擬電腦**]，然後按兩下 med-v 工作區，以全螢幕方式手動開啟。

2.  在 MED-V 工作區 Windows 虛擬電腦視窗中，開啟 [登錄編輯程式]。

    按一下 [**開始**]，按一下 [**執行**]，然後輸入 regedit。 然後按一下 **[確定]**。

3.  在 [登錄編輯程式] 中，找出 HKLM\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Virtual Machine\\VPCVAppExcludeList 登錄機碼。

4.  針對您不想將其發佈到主機電腦 [**開始**] 功能表的已安裝應用程式，建立新的登錄值。 例如，如果您想要取消發佈自動發佈的程式 Microsoft Silverlight，請遵循下列步驟：

    1.  在 VPCVAppExcludeList 登錄機碼醒目提示時，按一下 [**編輯**]，按一下 [**新增**]，然後按一下 [**字串值**]。

    2.  輸入新註冊值的名稱。 例如，在 Microsoft Silverlight 中，您可以輸入 sllauncher.exe。

    3.  按兩下新的註冊表值，然後輸入值資料。

        [值資料] 是您要取消發佈之命令的完整路徑。 您可以在不想要發行之應用程式的 [**開始**] 功能表上，以滑鼠右鍵按一下快捷方式，然後按一下 [**屬性**]，找到完整路徑。 完整路徑會列于 [**目標**] 底下的 [**快捷方式**] 索引標籤中。

        例如，對於程式 Microsoft Silverlight，完整路徑可能是「C:\\program files Files\\Microsoft Silverlight\\4.0.50917.0\\Silverlight.Configuration.exe」。

        **重要** 如果適用的話，請在 [值資料] 欄位中，移除完整路徑中的引號。

         

5.  關閉 [登錄編輯程式]，然後重新開機 MED-V 工作區虛擬機器。

    應用程式仍安裝在 MED-V 工作區中，但現在已從主機電腦的 [**開始**] 功能表中移除。

您也可以從 VPCVAppExcludeList 鍵中刪除對應的值，將排除的應用程式重新發佈至主機 [**開始**] 功能表。 例如，若要重新發佈 Microsoft Silverlight，請以滑鼠右鍵按一下註冊表值 sllauncher.exe 然後選取 [**刪除**]。

## 相關主題


[MED-V 技術參考資料](technical-reference-for-med-v.md)

[如何發佈與取消發佈 MED-V 工作區上的應用程式](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)

 

 





