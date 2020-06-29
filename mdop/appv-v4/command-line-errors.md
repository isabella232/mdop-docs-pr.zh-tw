---
title: 命令列錯誤
description: 命令列錯誤
author: dansimp
ms.assetid: eea62568-4e90-4877-9cc7-e27ef5c05068
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ab29a77dc15a8c7bd3590b918a7ca8c1ca6e8c0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802205"
---
# 命令列錯誤


使用下列錯誤清單來找出命令列排序次序無法正常運作的原因。 您也可以透過查看排序器記錄檔，查看這些錯誤。

**記事** 排序時可能會顯示一個以上的錯誤。 此外，顯示的錯誤碼可能是兩個錯誤代碼的總和。 例如，如果 */InstallPath*和 */outputfile*參數遺失，Microsoft System Center 應用程式虛擬化排序器將會傳回96（兩個錯誤碼的總和）。

 

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
指定的區塊大小（/BLOCKSIZE <em> ） </em> 無效。

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


[關於使用排序器命令列](about-using-the-sequencer-command-line.md)

[命令列參數](command-line-parameters.md)

 

 





