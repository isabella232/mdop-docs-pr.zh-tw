---
title: 如何使用命令列來移除封裝
description: 如何使用命令列來移除封裝
author: dansimp
ms.assetid: 47697ec7-20e5-4258-8865-a0a710d41d5a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b282830802f34bfb0670ddfdb8e2852d3559e3f7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801170"
---
# 如何使用命令列來移除封裝


您可以使用下列命令列程式，從特定電腦上的應用程式虛擬化（App-v）用戶端刪除虛擬應用程式套件。

**刪除所有使用者的虛擬應用程式套件**

-   如果先前是使用/GLOBAL 開關為所有使用者新增套件，請使用下列命令刪除套件和通用檔案類型及快速鍵。 需要系統管理員許可權。 在這種情況下，不需要/GLOBAL 切換，因為命令會永遠執行套件的全域刪除。

    `SFTMIME DELETE PACKAGE:”name”`

**刪除先前針對個別使用者新增的套件**

1.  如果先前已為個別使用者新增套件，您有幾個選項。

    在發行套件的每位使用者帳戶下，執行下列命令。 這會在應用程式漫遊至另一部電腦時，拒絕使用者存取。 它會從設定檔中刪除特定使用者的設定、快速鍵和檔案類型，並停止在使用者的內容下進行背景載入。

    `SFTMIME UNPUBLISH PACKAGE:”name”`

2.  或者，您也可以在發行套件的每位使用者帳戶下執行下列命令。

    `SFTMIME UNPUBLISH PACKAGE:”name”`

    然後對套件執行此命令。

    `SFTMIME DELETE PACKAGE:”name”`

    這會完全移除套件，並刪除其設定檔中的所有使用者設定、快速鍵和檔案類型。 如果隨後重新新增套件，則使用者將必須再次指定其設定。 只有「刪除應用程式」（**DeleteApp**）許可權才需要執行這個命令。

3.  第三個替代方案是，您可以直接執行 [**刪除套件**] 命令，而不使用 [**取消發佈套件**] 命令。 在這種情況下，每個使用者的檔案類型和快速鍵都會隱藏而不是刪除，而且使用者設定會保留下來。 這表示如果隨後針對使用者重新新增套件，則會還原檔案類型和快速鍵，並重新應用使用者設定。

## 相關主題


[如何使用命令列新增封裝](how-to-add-a-package-by-using-the-command-line.md)

[如何使用命令列刪除所有虛擬應用程式](how-to-delete-all-virtual-applications-by-using-the-command-line.md)

 

 





