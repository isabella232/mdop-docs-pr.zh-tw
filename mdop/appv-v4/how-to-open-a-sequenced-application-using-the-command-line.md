---
title: 如何使用命令列來開啟循序應用程式
description: 如何使用命令列來開啟循序應用程式
author: dansimp
ms.assetid: dc23ee65-8aea-470e-bb3f-a2f2b06cb241
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c99ab6b41947fc255afa9cad5b3ed2e22e672c3e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801209"
---
# 如何使用命令列來開啟循序應用程式


您可以使用命令列開啟虛擬應用程式套件。 您必須以系統管理員身分執行**cmd**提示。

使用下列程式，使用命令列開啟順序化的應用程式套件

**使用命令列開啟順序化的應用程式**

1.  若要開啟命令提示字元，請按一下 [**開始**]，然後選取 [**執行**]，輸入**Cmd**，然後按一下 **[確定]**。

2.  在命令提示字元中，輸入**cd\\**並指定安裝排序器的目錄路徑，然後按**enter。**

3.  在命令提示字元中，輸入下列命令，並以您的值取代斜體文字：

    SFTSequencer/OPEN：「*指定要開啟的 sprj*檔案」

    按**enter**。

4.  您也可以指定下列選用參數。 在命令提示字元中，輸入下列命令，並以您的值取代斜體文字：

    /PACKAGENAME： "*指定套件名稱"*

    /MSI-指定產生關聯的 Microsoft Windows 安裝程式。

    /COMPRESS –指定套件是否會進行壓縮。 根據預設，套件不會壓縮。

    按**enter**。

    **記事** 如果安裝程式或 Windows 安裝程式套件有圖形使用者介面，則會在您指定命令列參數之後顯示。

     

## 相關主題


[如何使用命令列管理虛擬應用程式](how-to-manage-virtual-applications-using-the-command-line.md)

 

 





