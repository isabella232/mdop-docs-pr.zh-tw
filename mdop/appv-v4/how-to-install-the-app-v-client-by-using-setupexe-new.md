---
title: 如何使用 Setup.exe 安裝 App-V Client
description: 如何使用 Setup.exe 安裝 App-V Client
author: dansimp
ms.assetid: 106a5d97-b5f6-4a16-bf52-a84f4d558c74
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 60f79a2d2f74848ab121ba13cdf8c215088d54db
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801377"
---
# 如何使用 Setup.exe 安裝 App-V Client


本主題描述如何使用 setup.exe 程式來安裝 App-v 用戶端。 當您使用 setup.exe 程式安裝 App-V 用戶端時，安裝程式會決定需要哪些必備軟體，並在安裝用戶端之前自動安裝。

**使用 Setup.exe 安裝應用程式虛擬化用戶端**

1.  確認您是以在電腦上擁有系統管理員許可權的帳戶登入。

2.  開啟命令提示字元視窗，然後將目錄變更為內含安裝程式檔案的資料夾。 在安裝版本4.6 或更新版本的 App-v 用戶端時，您必須針對電腦的作業系統、32位或64位使用正確的安裝程式。 如果您使用的是錯誤的安裝程式，安裝將會失敗，並會顯示錯誤訊息。

3.  在命令提示字元中輸入安裝命令字串。 或者，您可以建立命令檔，然後從命令提示字元執行它。 您也可以使用「VBScript」或「Windows PowerShell」等指令碼語言來執行命令。

4.  下列命令列範例會說明如何將 setup.exe 用於許多選用的參數。 如需這些參數的詳細資訊，請參閱[應用程式虛擬化用戶端安裝程式命令列參數](application-virtualization-client-installer-command-line-parameters.md)。

    **"setup.exe"/s/v "/qn SWICACHESIZE = \ \" 10240 \\ "SWIPUBSVRDISPLAY = \\" = \ "HTTP SWIPUBSVRTYPE"/SECURE\\ = \ "SWIPUBSVRHOST" PRODSYS\\ = \\ "443 \\" SWIPUBSVRPATH = \ "/AppVirt/appsntype.xml \ [SWIPUBSVRREFRESH = \ \" on\\ "SWIGLOBALDATA = \ \" D:\\AppVirt\\Global\\ "SWIUSERDATA = \\" ^% LOCALAPPDATA ^%\\Windows\\Application 虛擬化 Client\\ "SWIFSDRIVE = \ \" Q\\ ""**

    **重要**  
    -   出現在 [**/v**] 區段中的引號必須被視為特殊字元，並以前面的 " **\\** " 輸入。 只有在值包含空格時，才需要使用引號;不過，在一致性中，前面範例中的所有實例都會顯示為引號。

    -   " **%** **% HomeDrive%**" 中的 "" 字元前面必須是 " **^** " 逸出字元。 否則，Windows 命令 shell 會將值設定為執行安裝的使用者。

    -   需要**InstallShield**開關 **/s**和 **/qn** ，才能讓它成為無訊息安裝。 **/Qn**開關必須跟在 **/v**開關之後，並以不含空格的引號字元分隔。

    -   **SWIGLOBALDATA**值中指定的資料夾必須已經存在。

     

5.  安裝完成後，建議您執行 Microsoft 更新掃描，以確保已安裝最新的更新。

## 相關主題


[如何使用命令列安裝用戶端](how-to-install-the-client-by-using-the-command-line-new.md)

 

 





