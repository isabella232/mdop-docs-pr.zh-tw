---
title: 排序器命令列錯誤碼
description: 排序器命令列錯誤碼
author: dansimp
ms.assetid: 3d491314-4923-45fd-9839-c541c5e620bd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 74f5bd0c1b66656ac6891dcc1c019254fa36fdac
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800843"
---
# 排序器命令列錯誤碼


使用下列清單，協助您使用命令列來識別與順序應用程式相關的錯誤。 您也可以透過查看關聯的 App-v 排序器記錄檔來查看此資訊。

**記事** 在排序期間，可能會發生多個錯誤，如果發生這種情況，則顯示的錯誤碼可能是兩個錯誤碼的總和。 例如，如果 */InstallPath*和 */outputfile*參數遺失，app-v 會傳回**96**，即兩個錯誤碼的總和。

 

<a href="" id="01"></a>01  
出現未指定的錯誤。

<a href="" id="02"></a>2002  
指定的安裝目錄（/INSTALLPACKAGE）無效。

<a href="" id="04"></a>年  
指定的套件根目錄（/INSTALLPATH）無效。

<a href="" id="08"></a>下半年  
指定的 */outputfile*參數無效。

<a href="" id="16"></a>位  
未指定安裝目錄（/INSTALLPACKAGE）。

<a href="" id="32"></a>32  
未指定套件根目錄（/INSTALLPATH）。

<a href="" id="64"></a>64  
未指定 */outputfile*參數。

<a href="" id="128"></a>128  
指定的應用程式虛擬化磁片磁碟機無效。

<a href="" id="256"></a>256  
安裝程式失敗。

<a href="" id="512"></a>512  
排序應用程式失敗。

<a href="" id="1024"></a>1024  
評估已安裝的快速鍵失敗。

<a href="" id="2048"></a>2048  
已排序的應用程式套件無法儲存。

<a href="" id="4096"></a>4096  
指定的套件名稱（/PACKAGENAME）無效。

<a href="" id="8192"></a>8192  
指定的區塊大小（/BLOCKSIZE）無效。

<a href="" id="16384"></a>16384  
指定的壓縮類型（/COMPRESSION）無效。

<a href="" id="32768"></a>32768  
指定的專案路徑無效。

<a href="" id="65536"></a>65536  
指定的升級參數無效。

<a href="" id="131072"></a>131072  
指定的升級專案參數無效。

<a href="" id="262144"></a>262144  
指定的 [解碼路徑] 參數無效。

<a href="" id="525288"></a>525288  
未指定套件名稱。

## 相關主題


[Application Virtualization Sequencer 參考資料](application-virtualization-sequencer-reference.md)

[排序器命令列參數](sequencer-command-line-parameters.md)

 

 





