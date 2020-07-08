---
title: 如何在用戶端上發佈虛擬應用程式
description: 如何在用戶端上發佈虛擬應用程式
author: dansimp
ms.assetid: 90af843e-b5b3-4a71-a3a1-fa5f4c087f28
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b5585f82150db69929ccedbee3aecab969c5e7dc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801190"
---
# 如何在用戶端上發佈虛擬應用程式


當您使用電子軟體發佈系統部署應用程式虛擬化時，您可以使用下列其中一個程式，將應用程式套件發佈給您的使用者。

**使用獨立的 Windows 安裝程式檔案發佈套件**

1.  用戶端應該安裝，並將*REQUIREAUTHORIZATIONIFCACHED*參數設定為0（零）。 如需設定此參數的詳細資訊，請參閱[應用程式虛擬化用戶端安裝程式命令列參數](application-virtualization-client-installer-command-line-parameters.md)

2.  將 Windows 安裝程式檔案和 SFT 檔案複製到目的電腦上的同一個資料夾。

3.  在電腦上執行下列命令：

    `Msiexec.exe /I "packagename.msi" /q`

**使用 Windows 安裝程式和套件資訊清單發佈套件**

1.  將 Windows 安裝程式檔案複製到目的電腦和 SFT 檔案，移至流式處理伺服器上的內容共用。

2.  在每個使用者的電腦上執行下列命令：

    `Msiexec.exe /I "\\pathtomsi\packagename.msi" MODE=STREAMING  OVERRIDEURL="\\\\server\\share\\package.sft" LOAD=TRUE /q`

    **重要** 針對 OVERRIDEURL，所有反斜線字元都必須使用前面的反斜線來轉義，否則不會正確分析 OVERRIDEURL 路徑。 此外，屬性和值必須以大寫輸入，但值是檔案的路徑。

     

**使用 SFTMIME 發佈套件**

-   如需如何為電腦上的所有使用者發佈應用程式的範例，請在使用者的電腦上執行下列命令：

    `SFTMIME ADD PACKAGE:package-name /MANIFEST manifest-path                                 [/GLOBAL] [/LOG log-pathname | /CONSOLE | /GUI]`

    如需這些及其他 SFTMIME 命令的其他詳細資訊，請參閱[SFTMIME 命令參考](sftmime--command-reference.md)。

## 相關主題


[決定您的發佈方法](determine-your-publishing-method.md)

[以電子軟體發佈為基礎的案例](electronic-software-distribution-based-scenario.md)

[SFTMIME 命令參考](sftmime--command-reference.md)

[Application Virtualization Client 的獨立傳遞案例](stand-alone-delivery-scenario-for-application-virtualization-clients.md)

 

 





