---
title: 如何設定 VM 電腦名稱模式內容
description: 如何設定 VM 電腦名稱模式內容
author: dansimp
ms.assetid: ddf79ace-8cc3-4ee6-be5a-5940b4df5c36
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aa171712b6624b73fb5e0756aaf56277baa4c8cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812140"
---
# 如何設定 VM 電腦名稱模式內容


您可以針對 revertible 和持續性的 MED-V 工作區，指派虛擬機器電腦名稱稱模式。

-   Revertible-管理員可以為每個 Revertible 的 MED-V 工作區實例指派唯一名稱，以在多部電腦上使用相同的 MED-V 工作區來區分。

-   Persistent：在持久的 MED-V 工作區中，管理員可以將電腦設定為在安裝程式腳本中重新命名。

## 如何將虛擬電腦的電腦名稱稱模式指派給 Revertible MED-V-V 工作區


**將虛擬電腦電腦名稱稱模式指派給 revertible MED-V 工作區**

1.  按一下要設定的 revertible MED-V 工作區。

2.  在 [ **REVERTIBLE VM 設定**] 區段中，選取 [**根據電腦名稱稱模式重新命名 VM** ] 核取方塊。

3.  在 [ **VM 電腦名稱稱模式**] 區段中，輸入要用來命名虛擬機器影像的模式，使用下列選項：

    -   **常數**-在使用 med-v 工作區的所有電腦上輸入完全不變的文字。

    -   [**變數**]：輸入變數，請按一下 [**插入變數**]，然後選取下列其中一項：

        -   **使用者名稱**

        -   **網域名稱 (Domain name)**

        -   **主機名稱**

        -   **工作區名稱**

        -   **虛擬機器名稱**

        選取的變數會與使用 MED-V 工作區的電腦相關。 例如，如果已選取 [**功能變數名稱**]，則每個電腦的唯一名稱將會包含電腦的功能變數名稱。

    -   **隨機字元**：針對要包含在模式中的每個隨機字元輸入 "\ #"。 使用 MED-V 工作區的每個電腦將會有指定長度的尾碼（隨機產生）。

    **注意**  
    電腦名稱稱的長度限制為15個字元。 如果模式超過限制，將會被截斷。



4.  在 [**原則**] 功能表上，選取 [**確認**]。

    **注意**  
    已核取根據電腦名稱稱模式（在 [ **REVERTIBLE VM 設定**] 區段）中的 **[重新命名 vm** ] 時，可以指派 revertible VM 電腦名稱稱模式。



~~~
**Note**  
A unique computer name can be assigned only if it is configured prior to MED-V workspace setup. Changing the name will not affect MED-V workspaces that were already set up.
~~~



## 如何將虛擬電腦電腦名稱稱模式指派給持久的 MED-V 工作區


**將虛擬電腦電腦名稱稱模式指派至持久的 MED-V 工作區**

1.  按一下要設定的持久 MED-V 工作區。

2.  在 [**永久 VM 設定**] 區段中，按一下 [**腳本編輯器**]。

3.  在 [**腳本動作**] 對話方塊中，按一下 [**新增**]，然後在子功能表上，按一下 [**重新命名電腦**]。

4.  按一下 **[確定]** 以關閉 [**腳本動作**] 對話方塊。

5.  在 [ **Vm 設定**] 索引標籤上，于 [ **Vm 電腦名稱稱模式**] 區段中，輸入要用來重新命名電腦的模式，使用下列程式：

    -   [**固定**]：輸入電腦名稱稱中將包含的自由文字。

    -   [**變數**]：輸入變數，請按一下 [**插入變數**]，然後選取下列其中一項：

        -   **使用者名稱**

        -   **網域名稱 (Domain name)**

        -   **主機名稱**

        -   **工作區名稱**

        -   **虛擬機器名稱**

        已選取的變數會針對要重新命名的電腦而定。 例如，如果已選取 [**功能變數名稱**]，電腦名稱稱將會包含電腦的功能變數名稱。

    -   **隨機字元**：針對要包含在模式中的每個隨機字元輸入 "\ #"。 電腦將會有指定長度的尾碼（隨機產生）。

    **注意**  
    電腦名稱稱的長度限制為15個字元。 如果模式超過限制，將會被截斷。



6.  在 [**原則**] 功能表上，選取 [**確認**]。

    **注意**  
    只有在 [**腳本動作**] 對話方塊中將其設定為動作時，才會重新命名電腦。 如需詳細資訊，請參閱[如何設定腳本動作](how-to-set-up-script-actions.md)。



## 相關主題


[使用 MED-V 管理主控台使用者介面](using-the-med-v-management-console-user-interface.md)

[建立 MED-V 工作區](creating-a-med-v-workspacemedv-10-sp1.md)

[如何設定指令碼動作](how-to-set-up-script-actions.md)

[虛擬機器設定的範例](examples-of-virtual-machine-configurationsv2.md)









