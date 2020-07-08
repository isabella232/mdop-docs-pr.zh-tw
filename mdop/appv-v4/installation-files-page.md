---
title: 安裝檔案頁面
description: 安裝檔案頁面
author: dansimp
ms.assetid: b0aad26f-b143-4f09-87a1-9f016a23cb62
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 08a2e7318271503f072298ca137a1e65e16c0178
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801000"
---
# 安裝檔案頁面


使用 [**安裝**檔案] 頁面來指定所用的安裝檔案，這些檔案是用來建立此嚮導 [**選取套件**] 頁面上指定的虛擬應用程式套件。 如果您建立的虛擬應用程式套件包含多個應用程式，您應該將所有必要的安裝檔案複製到執行 Microsoft Application Virtualization 排序器的電腦上的單一資料夾中。

此頁面包含下列元素：

<a href="" id="original-installation-files"></a>**原始安裝檔**  
按一下 **[流覽]** ，指定原先用來建立虛擬應用程式套件的安裝檔案。 您指定的父目錄應該儲存在本機的電腦上，且必須包含所有必要的安裝檔案或包含安裝檔案的子資料夾。 安裝檔案可以包含在上層資料夾或指定的父資料夾的任何子資料夾中。

<a href="" id="files-installed-on-local-system"></a>**安裝在本機系統上的檔案**  
按一下 **[流覽]** ，指定在執行排序器的電腦上本機安裝的安裝檔案。 如果應用程式安裝檔案已安裝到應用程式的預設位置，您就只能選取此選項。

**記事** 您所提供的預設安裝位置視下列情況而定：

 

-   最初建立套件時指定的套件根目錄。

-   最初建立套件時，在 Windows 安裝程式中指定的安裝位置。

-   預設的應用程式安裝路徑。

例如，如果指定的套件根目錄是**Q:\\Office12** ，且在安裝期間，預設的安裝位置會從**c:\\program files Files\\Office12**變更為**Q:\\Office12**，所以凍結期間指定的路徑必須是**c:\\program files Files\\Office 12**。

如果指定的套件根目錄是**Q:\\Microsoft** ，且安裝期間預設的安裝位置是從**c:\\program files Files\\Office12**改為**Q:\\Microsoft\\Office12**，則在凍結期間指定的路徑必須是**c:\\program files**檔案。

當您使用套件加速器建立套件時，封裝中的每個檔案（例如**Q:\\Office12\\file.txt** ）都是在本機電腦上使用建立套件加速器時所指定的預設位置（例如， **c:\\program files Files\\Office12**）來取代套件根**Q:\\Office12** 。 在上一個範例中，檔案應該位於**c:\\program files Files\\Office12\\file.txt**中。

## 相關主題


[建立封裝加速器精靈 (AppV 4.6 SP1)](create-package-accelerator-wizard--appv-46-sp1-.md)

 

 





