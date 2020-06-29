---
title: 如何解除安裝 MED-V 元件
description: 如何解除安裝 MED-V 元件
author: dansimp
ms.assetid: c121dd27-6b2f-4d41-a21a-c6e8608c5c41
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 514ec8227b858b34289ca2330f7cfb038bc4f00e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800241"
---
# 如何解除安裝 MED-V 元件


在某些情況下，您可能會想要從您的企業卸載全部或部分的 Microsoft 企業版桌面虛擬化（MED-V）2.0 元件。 例如，您已解決所有應用程式作業系統相容性問題，或您想要在企業中部署不同的 MED-V 工作區。

通常，您可以使用 Windows 的安裝程式，將您的電子軟體發佈（ESD）系統設定為卸載 MED-V 元件。 或者，您也可以手動卸載全部或部分的 MED-V 元件。

**重要** 在您可以卸載 MED-V 主機代理程式之前，您必須先卸載任何已安裝的 MED-V 工作區。

 

使用下列程式從您的企業卸載 MED-V 元件。

**使用電子軟體發佈系統卸載 MED-V**

1.  使用您的 ESD 系統發佈腳本來針對您要卸載的每個 MED-V 工作區，都叫用這個 uninstall.exe 的可執行程式。 檔案位於 C:\\ProgramData\\Microsoft\\Medv\\Workspace。 您可以設定標誌來自動執行卸載可執行程式，讓使用者不知道卸載。

2.  建立套件，將 MED-V 主機代理程式安裝檔發佈到已卸載 MED-V 工作區的每一部電腦。 將套件設定為在安靜模式下執行卸載。

ESD 用戶端會辨識新套件何時可用，並開始根據定義和需求來卸載套件。

**若要手動卸載 MED-V 工作區**

1.  在主機電腦上，按一下 [**開始**]，按一下 [**控制台**]，然後按一下 [**程式和功能**]。

2.  在 [**程式和功能**] 視窗中，選取您要移除的 med-v 工作區，然後按一下 [**卸載**]。 （MED-V 工作區命名為「MED-V-V 工作區- &lt;*工作區 \ _name* &gt; "）。 &lt;隨即會開啟 [*工作區 \ _name* &gt; **設定] 嚮導**。

3.  在 [**設定] 嚮導**中，按一下 **[下一步]**，然後按一下 [**移除**]。

4.  如果您想要的話，請選取核取方塊以刪除由 MED-V 建立的主 VHD 磁片與差異磁片。 這不是必要的，但會在卸載完成後釋放磁碟空間。

5.  按一下 [**移除**]。

    **記事** 如果 MED-V 目前正在執行，會出現一個對話方塊，詢問您是否要將它關閉。 按一下 **[是]** 以繼續卸載。 按一下 [**否**]，取消卸載。

     

或者，您也可以執行檔案 `uninstall.exe` （通常位於 C:\\ProgramData\\Microsoft\\Medv\\Workspace. 上）來移除 med-v 工作區

**若要手動卸載 MED-V 主機代理程式**

1.  在 Windows 7 主機電腦上，按一下 [**開始**]，按一下 [**控制台**]，然後按一下 [**程式和功能**]。

2.  在 [**程式和功能**] 視窗中，選取 [ **Med-v 主機代理程式**]，然後按一下 [**卸載**]。

    Windows 安裝程式會移除 MED-V 主機代理程式。

    **記事** 如果您在卸載 MED-V 工作區之前嘗試卸載 MED-V 主機代理，會出現一個對話方塊，指出您必須先卸載 MED-V 工作區。 按一下**確定**繼續。

     

**若要手動卸載 MED-V 工作區包裝程式**

1.  在主機電腦上，按一下 [**開始**]，按一下 [**控制台**]，然後按一下 [**程式和功能**]。

2.  在 [**程式和功能**] 視窗中，選取 [ **Med-v-V 工作區包裝程式**]，然後按一下 [**卸載**]。

    Windows 安裝程式會移除 MED-V-V 工作區包裝程式。

    **記事** 您可以隨時卸載 MED-V 工作區包裝程式，而不會影響任何已部署的 MED-V 工作區。

     

## 相關主題


[部署 MED-V 元件](deploy-the-med-v-components.md)

 

 





