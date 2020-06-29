---
title: 如何使用 [開啟封裝] 命令來升級封裝
description: 如何使用 [開啟封裝] 命令來升級封裝
author: dansimp
ms.assetid: 67c10440-de8a-4547-a34b-f83206d0cc3b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cca438fe90373e8f934d1d790246544cdf46fa18
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801049"
---
# 如何使用 [開啟封裝] 命令來升級封裝


使用 [開啟套件] 命令來升級或將更新套用至已排序的應用程式套件。 當您使用命令列升級現有的虛擬應用程式套件時，會刪除該版本的 sft 檔案的原始版本。 您應該先備份關聯的 sft 檔案，然後再使用命令列升級套件。

**使用 [開啟套件] 命令升級套件**

1.  若要開啟將升級的套件，請在應用程式虛擬化（App-v）中 **，選取 [** 檔案]、[**開啟套件以供升級**]。 在 [**開啟**舊檔] 對話方塊中，選取要升級的套件。

2.  若要啟動 [**先後順序**] 嚮導，請選取 [**工具**]、[**順序] 嚮導**。 完成嚮導套用設定變更，若要儲存新的已排序應用**程式，請選取 [** 檔案]、[**儲存**]。

3.  若要將版本號碼附加到套件名稱，請在 Sequencer 主控台中，選取 [**工具**]、[**選項**]。 選取 [**將套件版本附加至檔案名**]。 按一下 \[確定\] ****。

    **重要** 更新套件版本的檔案名對於成功完成升級而言是必要的。

     

## 相關主題


[如何使用命令列管理虛擬應用程式](how-to-manage-virtual-applications-using-the-command-line.md)

 

 





