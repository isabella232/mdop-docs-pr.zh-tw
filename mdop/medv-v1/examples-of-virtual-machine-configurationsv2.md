---
title: 虛擬機器設定的範例
description: 虛擬機器設定的範例
author: dansimp
ms.assetid: 5937601e-41ab-4ca2-8fa1-3c9154710cd6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6b9fc7b1f88b2b30ea149fe73a387826fdbb2a66
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810646"
---
# 虛擬機器設定的範例


下列是典型的虛擬機器配置範例：一個是在持久性的 MED-V 工作區，另一個是在 revertible MED-V 工作區中。

**記事** 這些範例不適合在所有環境中使用。 根據您的環境調整設定。

 

**在持久的 MED-V 工作區中設定一般的網域設定**

1.  在基本映射上設定 Sysprep，以建立唯一的 SID。 如需詳細資訊，請參閱[建立 med-v 的虛擬電腦影像](creating-a-virtual-pc-image-for-med-v.md#bkmk-howtoconfiguresysprepformedvimages)。

2.  在 [ **VM 設定**] 索引標籤上，選取 [**執行 VM 設定**] 核取方塊。

3.  在 [ **VM 電腦名稱稱模式**] 區段中，設定電腦影像名稱的模式。 如需詳細資訊，請參閱[如何設定 VM 電腦名稱稱模式屬性](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)。

4.  按一下 [**腳本編輯器**]，然後在 [ **VM 設定腳本編輯器**] 對話方塊中，設定下列動作：

    1.  **重新命名電腦**

    2.  **重新開機 Windows**

    3.  **檢查連線性**

    4.  **加入網域**

    5.  **停用自動登入**

    如需詳細資訊，請參閱[如何設定腳本動作](how-to-set-up-script-actions.md)。

5.  按一下 [**原則**] 功能表上的 [**確認**]。

**在 revertible 工作區中設定典型設定**

1.  在 [ **VM 設定**] 索引標籤上，選取 [**根據電腦名稱稱模式重新命名 VM** ] 核取方塊。

2.  在 [ **VM 電腦名稱稱模式**] 區段中，設定電腦影像名稱的模式。 如需詳細資訊，請參閱[如何設定 VM 電腦名稱稱模式屬性](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)。

3.  按一下 [**原則**] 功能表上的 [**確認**]。

## 相關主題


[如何設定 MED-V 工作區的虛擬機器設定](how-to-configure-the-virtual-machine-setup-for-a-med-v-workspacemedvv2.md)

[如何設定 VM 電腦名稱模式內容](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)

[如何設定指令碼動作](how-to-set-up-script-actions.md)

 

 





