---
title: 命令列參數
description: 命令列參數
author: dansimp
ms.assetid: d90a0591-f1ce-4cb8-b244-85cc70461922
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 31d6ca1215648e2519e9818817ab5cc779a746d0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802202"
---
# 命令列參數


使用下列應用程式虛擬化排序器參數來排序應用程式，並在命令提示字元中升級順序化的應用程式套件。 在 Microsoft Application Virtualization Sequencer 目錄中，您可以輸入**SFTSequencer**，後面接著適當的參數。

<a href="" id="-help-or---"></a>*/Help*或 */？*  
用來顯示命令列順序的可用參數清單。

<a href="" id="-installpackage-or--i"></a>*/INSTALLPACKAGE*或 */i*  
用來指定要排序之應用程式的安裝程式或批次檔案。

<a href="" id="-installpath-or--p"></a>*/INSTALLPATH*或 */p*  
用來指定套件根目錄。

<a href="" id="-outputfile-or--o"></a>*/Outputfile*或 */o*  
用來指定將產生的 SPRJ 檔案的路徑和檔案名。

**重要** 開啟您不想升級的套件時，無法使用 */outputfile*參數。

 

<a href="" id="-fullload-or--f"></a>*/FULLLOAD*或 */f*  
用來指定是否要將所有專案放在主要功能區塊中。

<a href="" id="-packagename-or--k"></a>*/Packagename*或 */k*  
用來指定已排序之應用程式的套件名稱。

<a href="" id="-blocksize"></a>*/BLOCKSIZE*  
指定將用來將套件資料流程封裝至用戶端電腦的 SFT 檔案區塊大小。 您可以選取下列其中一個值：

-   4 KB

-   16 KB

-   32 KB

-   64 KB

當您指定區塊大小時，您應該考慮 SFT 檔案的大小。 區塊大小較小的檔案需要較長的時間，才能在網路上傳輸，但較少佔用頻寬。 區塊大小較大的檔案會使用更多的網路頻寬。

<a href="" id="-compression"></a>*/COMPRESSION*  
用來指定在將 SFT 檔案傳送到用戶端時壓縮該檔案的方法。

<a href="" id="-msi-or--m"></a>*/MSI*或 */m*  
用來指定產生已排序之應用程式的 Microsoft Windows 安裝程式套件。

<a href="" id="-default"></a>*/DEFAULT*  
指定建立虛擬應用程式套件時將使用的預設 SPRJ 檔案。 當應用程式第一次排序時，此檔案會當作 sprj 範本使用。

<a href="" id="-upgrade"></a>*/UPGRADE*  
指定將升級之 SPRJ 檔案的路徑和檔案名。

<a href="" id="-decodepath"></a>*/DECODEPATH*  
指定排序電腦上已安裝與序列化應用程式套件相關聯之檔案的目錄。 指定目錄時，請使用下列其中一種格式：

-   /decodepath：問：

-   /decodepath:Q:.

-   /decodepath:"Q:."

-   /decodepath： "Q："

## 相關主題


[關於使用排序器命令列](about-using-the-sequencer-command-line.md)

[如何使用命令列來開啟循序應用程式](how-to-open-a-sequenced-application-using-the-command-line.md)

[如何使用 [開啟封裝] 命令來升級封裝](how-to-upgrade-a-package-using-the-open-package-command.md)

 

 





