---
title: 如何使用 PowerShell 來建立封裝加速器
description: 如何使用 PowerShell 來建立封裝加速器
author: dansimp
ms.assetid: 0cb98394-4477-4193-8c5f-1c1773c7263a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 347572343cff058a7494574035464d66c4d61be4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800554"
---
# 如何使用 PowerShell 來建立封裝加速器


App-v 5.1 套件加速器會自動序列化大型、複雜的應用程式。 此外，當您套用 app-v 5.1 套件加速器時，您不一定必須手動安裝應用程式，才能建立虛擬化套件。

**建立套件加速器**

1.  安裝 App-v 5.1 排序器。 如需有關安裝排序器的詳細資訊，請參閱[如何安裝排序](how-to-install-the-sequencer-51beta-gb18030.md)器。

2.  若要開啟 PowerShell 主控台，請按一下 [**開始**]，然後輸入**powershell**。 以滑鼠右鍵按一下 **Windows PowerShell**，並選取 **\[以系統管理員身分執行\]**。 使用**AppvPackageAccelerator** Cmdlet。

3.  若要建立套件加速器，請確定您有要從中建立加速器的 appv 套件、安裝媒體或安裝檔案，以及可供加速器使用的使用者選擇 [讀我檔案]。 下列參數是使用封裝快速鍵 Cmdlet 所需的：

    -   **InstalledFilesPath** -指定應用程式的安裝路徑。

    -   **安裝**程式–指定應用程式安裝程式媒體的路徑

    -   **InputPackagePath** –指定 appv 包的路徑

    -   **Path** -指定套件的輸出目錄。

    下列範例顯示如何使用 appv 封裝與安裝媒體來建立套件加速器：

    **AppvPackageAccelerator-InputPackagePath &lt; 路徑，到 &gt; 安裝程式可執行檔的 appv 檔案安裝程式 &lt; 路徑（ &gt; &lt; 輸出路徑的路徑目錄）&gt;**

    您可以在下列清單中顯示可搭配使用**AppvPackageAccelerator** Cmdlet 的其他可選參數：

    -   **AcceleratorDescriptionFile** -指定使用者建立的套件快速鍵指示路徑。 封裝快速鍵指示是使用 [套件加速器] 建立的套件所封裝的 **.txt**或 **.rtf**描述檔。

    您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[使用 PowerShell 管理 App-V 5.1](administering-app-v-51-by-using-powershell.md)

 

 





