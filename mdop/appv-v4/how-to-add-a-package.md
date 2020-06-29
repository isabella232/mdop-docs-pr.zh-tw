---
title: 如何新增封裝
description: 如何新增封裝
author: dansimp
ms.assetid: 5407fdbe-e658-44f6-a9b8-a566b81dedce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c580d7d131017c52e278adda0208ffcb2e86ccf2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808732"
---
# 如何新增封裝


您可以透過下列方式從應用程式虛擬化伺服器管理主控台新增套件：

-   匯入應用程式，這會在程式中自動建立套件。

-   手動新增套件。

建議您匯入應用程式，而不是手動新增。 如需有關匯入應用程式的詳細資訊，請參閱[如何匯入應用程式](how-to-import-an-applicationserver.md)。

**手動新增套件**

1.  在應用程式虛擬化伺服器管理主控台中，以滑鼠右鍵按一下左窗格中的 [**套件**] 節點，然後選擇 [**新增套件**]。

2.  在 [**新增套件**] 對話方塊中，于 [**套件名稱**] 欄位中輸入名稱。

3.  在 [封裝檔案] 欄位的 [**完整路徑**] 中流覽或輸入路徑名稱。 這必須是 SFT 檔案。

    **記事** 如果您流覽到 SFT 檔案，請以伺服器的靜態主機名稱或 IP 位址取代本機路徑（例如，C:\\program files Files\\User\ _Apps \\Virtual\ _App \ _Server \\content）。 使用變數 *% SFT \ _SOFTGRIDSERVER%* 需要每用戶端電腦設定。

    在參照虛擬應用程式伺服器的對話方塊中，您必須使用使用者可以存取的網路位置（例如伺服器的靜態主機名稱或 IP 位址）。 應用程式的開啟軟體描述項（OSD）檔案可以使用伺服器的靜態主機名稱或 IP 位址來取代預留位置變數 *% SFT \ _SOFTGRIDSERER%* 。 如果您保留預留位置變數，就必須在每一個要存取該伺服器的用戶端電腦上設定這個變數。 在 SFT \ _SOFTGRIDSERVER 的每台電腦上設定使用者或系統變數。 變數值必須是伺服器的靜態主機名稱或 IP 位址。 如果您設定了變數，請結束用戶端會話、登出並返回 Microsoft Windows，然後在執行會話且已設定變數的每一部電腦上重新開機會話。

     

4.  按 **\[下一步\]**。

5.  [**摘要**] 對話方塊會顯示檔案位置，並會提示您將檔案複製到該位置（如果您尚未這麼做的話）。 驗證資訊之後，按一下 **[完成]** 。

    **記事** 如果您要管理遠端伺服器上的應用程式，請在 [下一步] 對話方塊中，輸入相對於伺服器內容根目錄的檔案路徑。

     

## 相關主題


[如何匯入應用程式](how-to-import-an-applicationserver.md)

[如何在伺服器管理主控台中管理封裝](how-to-manage-packages-in-the-server-management-console.md)

 

 





