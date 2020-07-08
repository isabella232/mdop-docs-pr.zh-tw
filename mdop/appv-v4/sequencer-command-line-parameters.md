---
title: 排序器命令列參數
description: 排序器命令列參數
author: dansimp
ms.assetid: 28fb875a-c302-4d95-b2e0-8dc0c5dbb0f8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ecfa269de04cf3dcba30cbb4a40f9176f03f6571
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800842"
---
# 排序器命令列參數


您可以使用下列應用程式虛擬化（App-v） Sequencer 參數來排序應用程式，並使用命令列來升級現有的虛擬應用程式。 如需使用命令列來排序應用程式的詳細資訊，請參閱[如何使用命令列來排序新的應用程式](how-to-sequence-a-new-application-by-using-the-command-line.md)。

## 排序器命令列參數


<a href="" id="-help-or---"></a>**/HELP 或/？**  
顯示可使用命令列來排序應用程式之參數的相關資訊。

<a href="" id="-installpackage-or--i"></a>**/INSTALLPACKAGE 或/I**  
指定要用來安裝應用程式的 Windows Installer 或批次處理檔案，以便進行排序。

<a href="" id="-installpath-or--p"></a>**/INSTALLPATH 或/P**  
指定應用程式的套件根目錄。

<a href="" id="-outputfile-or--o"></a>**/OUTPUTFILE 或/O**  
指定將產生的 SPRJ 檔案的路徑和檔案名。

<a href="" id="-fullload-or--f"></a>**/FULLLOAD 或/F**  
指定是否將所有檔案包含在主要功能區塊中。 如果 **/FULLLOAD**參數是在命令列上指定，則所有相關聯的應用程式資料都會新增到主要功能區塊。 如果未在命令列上指定 **/FULLLOAD**參數，則不會在主要功能區塊中新增任何相關聯的應用程式資料。

<a href="" id="-packagename-or--k"></a>**/PACKAGENAME 或/K**  
指定將指派給序列化應用程式的套件名稱。

<a href="" id="-blocksize"></a>**/BLOCKSIZE**  
指定將用來將套件資料流程封裝至用戶端電腦的 SFT 檔案區塊大小。 您可以選取下列其中一個值：

-   4 KB

-   16 KB

-   32 KB

-   64 KB

當您指定區塊大小時，您應該考慮 SFT 檔案的大小。 區塊大小較小的檔案需要較長的時間，才能在網路上傳輸，但較少佔用頻寬。 區塊大小較大的檔案會使用更多的網路頻寬。

<a href="" id="-compression"></a>**/COMPRESSION**  
指定壓縮要傳送到用戶端的 SFT 檔案的方法。

<a href="" id="-msi-or--m"></a>**/MSI 或/M**  
指定是否應建立已排序之應用程式的 Windows 安裝程式。

<a href="" id="-default"></a>**/DEFAULT**  
指定建立虛擬應用程式套件時將使用的預設 SPRJ 檔案。 當應用程式第一次排序時，此檔案會當作 sprj 範本使用。

<a href="" id="-upgrade"></a>**/UPGRADE**  
指定將升級之 SPRJ 檔案的路徑和檔案名。

<a href="" id="-decodepath"></a>**/DECODEPATH**  
指定排序電腦上已安裝與序列化應用程式套件相關聯之檔案的目錄。 指定目錄時，請使用下列其中一種格式：

-   /decodepath：問：

-   /decodepath:Q:.

-   /decodepath:"Q:."

-   /decodepath： "Q："

## 相關主題


[Application Virtualization Sequencer](application-virtualization-sequencer.md)

[排序器命令列錯誤碼](sequencer-command-line-error-codes.md)

 

 





