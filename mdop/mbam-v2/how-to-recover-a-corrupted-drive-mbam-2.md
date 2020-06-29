---
title: 如何修復損毀的磁碟機
description: 如何修復損毀的磁碟機
author: dansimp
ms.assetid: b0457a00-f72e-4ad8-ab3b-7701851ca87e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5bbd4c2a1f5ef3fde78a9f72c1f77ccb0cdea377
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809615"
---
# 如何修復損毀的磁碟機


若要復原受 BitLocker 保護的損毀磁片磁碟機，Microsoft BitLocker 管理與監控（MBAM）技術支援服務使用者將需要建立復原金鑰套件檔案。 這個套件檔案可以複製到包含損毀磁片磁碟機的電腦，然後用來復原磁片磁碟機。 使用下列程式執行此動作所需的步驟。

**重要** 為了避免潛在的資料遺失，強烈建議您閱讀「repair-manage-bde」說明，並清楚瞭解如何使用命令，然後再完成下列指示。

 

**復原損壞的磁片磁碟機**

1.  若要建立復原損壞的磁片磁碟機所需的復原金鑰套件，請啟動網頁瀏覽器，然後開啟 MBAM 管理和監控網站。

2.  從左側流覽窗格中選取 [**磁片磁碟機**復原]。 輸入使用者的功能變數名稱、使用者名稱、解除磁片鎖定的原因，以及使用者的復原密碼識別碼。

    **記事** 如果您是技術支援中心系統管理員角色的成員，則不需要輸入使用者的功能變數名稱或使用者名稱。

     

3.  按一下 **\[提交\]**。 隨即會顯示覆原金鑰。

4.  按一下 [**儲存**]，然後選取 [復原**金鑰套件**]。 系統會在您的電腦上建立復原金鑰套件。

5.  將復原金鑰套件複製到有損毀磁片磁碟機的電腦。

6.  開啟提升權限的命令提示字元。 若要這樣做，請按一下 [**開始**]，然後 `cmd` 在 [**搜尋程式及**檔案] 方塊中輸入。 以滑鼠右鍵按一下**cmd.exe** ，然後選取 [**以系統管理員身分執行**]。

7.  在命令提示字元中，輸入下列內容：

    `repair-bde <corrupted drive> <fixed drive> -kp <location of keypackage> -rp <recovery password>`

    **記事** &lt;將固定磁碟機更換 &gt; 為可用的硬碟磁片磁碟機，其可用空間等於或大於損壞的磁片磁碟機上的資料。 已損壞的磁片磁碟機上的資料會復原並移至指定的硬碟。

     

## 相關主題


[使用 MBAM 執行 BitLocker 管理](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





