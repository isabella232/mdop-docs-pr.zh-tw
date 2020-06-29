---
title: 如何使用命令列新增封裝
description: 如何使用命令列新增封裝
author: dansimp
ms.assetid: e75af49e-811a-407a-a7f0-6de8562b9188
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ab418017a075300f308d4ef4c6eceb4f623a05c7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808738"
---
# 如何使用命令列新增封裝


下列程式會列出將虛擬應用程式套件新增到特定電腦上的應用程式虛擬化（app-v）用戶端所需的步驟。

**為特定使用者新增虛擬應用程式套件**

-   在要取得套件的人員的使用者帳戶下，執行下列命令。 該命令會為該使用者新增併發布套件。

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path>`

**為所有使用者新增虛擬應用程式套件**

-   在具有系統管理員許可權的帳戶下，執行下列命令。 此套件是針對電腦上的所有使用者新增併發布。

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path> /GLOBAL`

**使用電子軟體發佈系統新增套件**

1.  如果您使用的是電子軟體發佈系統，它會在電腦的**系統**帳戶下執行命令，除非您使用/GLOBAL 開關，否則只會針對該帳戶發佈套件。 執行下列命令，為電腦上的所有使用者新增及發佈套件：

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path> /GLOBAL`

2.  

    如果您只想要為特定使用者新增套件，請執行 [**新增套件**] 命令，然後在每個人員的使用者帳戶下執行下列 [**發佈套件**] 命令，為每位使用者明確發佈套件：

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path>`

    `SFTMIME PUBLISH PACKAGE:”name” /MANIFEST <manifest-path>`

    發佈不含全域參數的套件時，系統會授與使用者對套件中應用程式的存取權，並將資訊清單中所列的檔案類型和快速鍵發佈至使用者的設定檔。 所需的許可權為「管理檔案類型關聯」（**ManageTypes**）和「發佈快捷方式」（**PublishShortcut**）。

## 相關主題


[如何使用命令列刪除所有虛擬應用程式](how-to-delete-all-virtual-applications-by-using-the-command-line.md)

[如何使用命令列來移除封裝](how-to-remove-a-package-by-using-the-command-line.md)

 

 





