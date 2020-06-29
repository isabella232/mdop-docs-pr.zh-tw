---
title: 如何修復損毀的磁碟機
description: 如何修復損毀的磁碟機
author: dansimp
ms.assetid: 715491ae-69c0-4fae-ad3f-3bd19a0db2f2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 545ff5c7e6bea29d5f89cce1cf18212b7d0e2870
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800220"
---
# 如何修復損毀的磁碟機


若要復原受 BitLocker 保護的已損壞的磁片磁碟機，Microsoft BitLocker 管理與監視（MBAM）技術支援服務使用者必須建立復原金鑰套件檔案。 這個套件檔案可以複製到包含損壞之磁片磁碟機的電腦，然後用來復原磁片磁碟機。 若要完成這項作業，請使用下列程式。

**復原損壞的磁片磁碟機**

1.  開啟 [MBAM 管理] 網站。

2.  從 [功能窗格] 中選取 [**磁片磁碟機**復原]。 輸入使用者的網功能變數名稱稱和使用者名稱、解除磁片磁碟機鎖定的原因，以及使用者的復原密碼識別碼。

    **記事** 如果您是技術支援中心系統管理員角色的成員，則不需要輸入使用者的功能變數名稱或使用者名稱。

     

3.  按一下 **\[提交\]**。 隨即會顯示覆原金鑰。

4.  按一下 [**儲存**]，然後選取 [復原**金鑰套件**]。 系統會在您的電腦上建立復原金鑰套件。

5.  將復原金鑰套件複製到有損毀磁片磁碟機的電腦。

6.  開啟提升權限的命令提示字元。 若要這樣做，請按一下 [**開始**]，然後 `cmd` 在 [**搜尋程式及**檔案] 方塊中輸入。 在搜尋結果清單中，以滑鼠右鍵按一下**cmd.exe**然後選取 [以**系統管理員身分執行**]。

7.  在命令提示字元中，輸入下列內容：

    `repair-bde <fixed drive> <corrupted drive> -kp <location of keypackage> -rp <recovery password>`

    **記事** 針對 &lt; 命令中的固定磁片磁碟機 &gt; ，指定可用的儲存空間，該裝置的可用空間等於或大於損壞的磁片磁碟機上的資料。 已損壞的磁片磁碟機上的資料會復原並移至指定的固定磁片磁碟機。

     

## 相關主題


[使用 MBAM 執行 BitLocker 管理](performing-bitlocker-management-with-mbam.md)

 

 





