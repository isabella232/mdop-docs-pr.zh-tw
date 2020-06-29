---
title: 壓縮 MED-V 虛擬硬碟
description: 壓縮 MED-V 虛擬硬碟
author: dansimp
ms.assetid: 5e6122d1-9847-4b33-adab-594919eec3c5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f71aefb1e4e901078b4d0a421065b7bd5acdf0ee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809860"
---
# 壓縮 MED-V 虛擬硬碟


雖然它是選擇性的，但您可以壓縮虛擬硬碟（VHD）來回收空白磁碟空間，並在設定 Windows 虛擬電腦影像之前減少 VHD 大小。

**重要** 在您繼續進行之前，請先建立 Windows XP 映射的備份複本。

 

**準備虛擬硬碟**

1.  開啟您的 Windows XP 影像。

    按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **windows 虛擬電腦**]，按一下 [ **windows 虛擬電腦**]，然後按兩下您的 Windows XP 影像。

2.  清除 DLL 快取。

    1.  在虛擬機器的命令提示字元中，輸入**sfc/cachesize = 1**。

    2.  重新開機虛擬機器。

    3.  在虛擬機器的命令提示字元中，輸入**sfc/purgecache**。

3.  刪除不必要的檔案，例如 uninstallers、temp 檔案、記錄檔、頁面檔案、共用資料夾等。

4.  關閉系統還原。 您也可以在 Sysprep.inf 檔案中指定此步驟。

    1.  在 [**控制台**] 中，按兩下 [**系統**]，然後選取 [**系統還原**] 索引標籤。

    2.  選取 [**關閉系統還原**]，然後按一下 **[確定]**。

5.  設定最大事件記錄大小並清除所有事件。

    1.  開啟 [事件檢視器]。

        按一下 [**開始**]，按一下 [**控制台**]，按兩下 [系統**管理工具**]，然後按兩下 [**事件檢視器**]。

    2.  以滑鼠右鍵按一下 [**應用程式**]，然後按一下 [**屬性**]。

    3.  在 [**記錄大小**] 區域中，將 [**最大記錄大小**] 設定為512kb，然後選取 [**視需要覆寫事件**]。

    4.  按一下 [**清除記錄**]。 在出現的 [**事件檢視器**] 對話方塊中，按一下 [**否**]。

    5.  按一下 [**屬性**] 視窗中的 **[確定]**。

    6.  針對**安全性**與**系統**記錄，重複步驟 a 至 e。

6.  執行磁片清理工具。

    按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**附件**]，按一下 [**系統工具**]，然後按一下 [**磁片清理**]。

7.  視需要為您的應用程式設定頁面檔案。

    1.  在 [**控制台**] 中，按兩下 [**系統**]，然後選取 [**高級**] 索引標籤。

    2.  在 [**效能**] 區域中，按一下 [**設定**]。

    3.  在 [**虛擬記憶體**] 區域中，按一下 [**變更**]。

    4.  設定您的頁面檔案設定。

8.  關閉 Windows XP 影像。

**整理並預先壓縮虛擬硬碟**

1.  在執行 Windows 7 的主機電腦的 [**控制台**] 中，按一下 [**管理工具**]，按兩下 [**電腦管理**]，然後按一下 [**磁片管理**]。

2.  使用磁片管理主控台，附加（裝載）虛擬硬碟，然後整理磁片磁片。

3.  使用 ISO 解壓縮工具，解壓縮位於 \\Program Files\\Windows Virtual PC\\Integration 元件資料夾中的 precompact。

4.  使用 precompact.exe 程式來壓縮 Windows XP 虛擬硬碟。

5.  使用磁片管理主控台，分離虛擬硬碟。

**壓縮虛擬硬碟**

1.  開啟 Windows 虛擬電腦。

    按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **windows 虛擬電腦**]，然後按一下 [ **windows 虛擬電腦**]。

2.  以滑鼠右鍵按一下您的 Windows XP 影像，然後選取 [**設定**]。

3.  針對您的 Windows XP 映射，按一下 [**硬碟**]，然後按一下 [**修改**]。

4.  按一下 [**壓縮虛擬硬碟**]。

5.  按一下 [**壓縮**]，然後按一下 **[確定]**。

建立壓縮虛擬硬碟的備份複本。

## 相關主題


[設定 MED-V 的 Windows 虛擬電腦映像](configuring-a-windows-virtual-pc-image-for-med-v.md)

[MED-V 技術參考資料](technical-reference-for-med-v.md)

 

 





